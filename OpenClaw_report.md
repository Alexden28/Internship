# OpenClaw
---
## Index
1. [Gateway Architecture](#1-gateway-architecture)  
2. [Agent Loop](#2-agent-loop)
3. [Agent Workspace](#3-agent-workspace)
4. [Session Management](#4-session-management)
5. [Memory](#5-memory)
6. [System Prompt](#6-system-prompt)
7. [Context](#7-context)
8. [Context Engine](#8-context-engine)
9. [Command Queue](#9-command-queue)
10. [Streaming e Chunking](#10-streaming-e-chunking)
11. [Messages](#11-messages)

---
## 1. Gateway Architecture
The Gateway is the central component of OpenClaw. It's the only component that open sessions to messanger's providers(WhatsApp by Baileys, Telegram by grammY,etc). All the other actors, like operative nodes and control clients, connects to the Gateway by WebSocket on the configurated address (default '127.0.0.1:18789').
It exist exactly one Gateway gor each host.

The Gateway also serves the HTTP canvas host under:
- `/__openclaw__/canvas/` — Agent-editable HTML/CSS/JS
- `/__openclaw__/a2ui/` — A2UI host

## Actors  

**Gateway (daemon)**
It mantains the connection to providers, exposes a API WebSocket tipizzed, valid for input frame versus JSON Schema and emits events like:
 `agent` : streaming of the Agent Loop during the execution: tool's updates, lifecycle(start/end/error)
`chat`: Updates history for the UI client, normalized and cleaned (silent token removed, too-call XML stripped)
`presence`: Updated about the state of connected devides(Operator and node) 
`health`: Update about the snapshot health of the Gateway and connected provider
`heartbeat`: Stream update about heartbeat of the agent, the schedulated job that execute `HEARTBEAT.md`
`cron`: notify of change on run o scheduled job, when they ends or when they start or when they change status.

**Clients (mac app/CLI/web admin / automation)**
Each client use a single WebSocket connection.
They send request:
`health`: require the health snapshot of the Gateway and the connected providers 
`status`: Require the recap of the state of the Gateway; Sensitive fields are visible only to clients with the scope `operator.admin` 
`send`: send directly a message to a channel, account, thread, out of the normal chat runner 
`agent`: start a agent loop, come back soon with `runId` and `acceotedAt`, the loop run in backround. 
`system-presence`: riquire the current snapshot at the presence of the all connected devices.
and subscribe to events: 
`tick`: periodic keepalive each 15 seconds 
`agent`: streaming of the agent loop in execution 
`presence`: update about the state of connected devices
`shutdown`: notify that the Gateway is shutting down, so clients can close the connection and cleanup

**Nodes(macOS/iOS/Android/handless)**
Nodes connect to the same server WebSocket with 'role: node'. They give a device identity in the frame 'connect' and the pairing is device-based. They expose concrete command like 

`canvas.*`: interact with the UI canvas on the device 
`camera.*`: acquire image from camera  
`screen.record`: record the screen 
`location.get`: read the location

**WebChat**
Static UI that use the Gateway WebSocket Api to history and send messages. In remote setup,connect by the same tunnelSSH/Tailscale of the other clients.

## Autentication and Authorization
The authentication system has two different levels:
**Level 1 - Gateway auth**: Each connection must pass an access check — either via shared-secret (token or password in the `connect` frame), via identity header (Tailscale/trusted-proxy), or disabled completely (`mode: "none"`, only on private ingress).
**Level 2 — Device Pairing:** Each client signs a challenge nonce with its device identity; new devices require manual approval (except local loopback), after which the Gateway issues a device token for subsequent reconnections.
**Important:** The `v3` signature also binds `platform` and `deviceFamily` — changing this metadata invalidates the existing pairing and requires new approval.

### Connection lifecycle
1. Client send `req:connect` as first frame.
2. Gateway validate access(JSON Schema + auth + pairing).
3. If ok, reply with presence and health snapshot.
4. Client receive push event ( `event:presence`, `event:tick`,...)
5. Client send operative command (es, `req:agent`)
6. Gateway reply with an immediate ack 
---

## 2. Agent Loop
The Agent Loop is a complete and real execution of an agent:
intake → context assembly → model inference → tool execution → streaming replies → persistence, is the authorative path that transform a message into actions and reply, maintaining the state of the session consistent. 
