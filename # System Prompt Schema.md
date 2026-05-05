# System Prompt Schema

| Section (schema) | Function | What's in my System_Prompt.txt |
|---|---|---|
| **Identity Line** | Defines the assistant's identity| "You are a personal assistant running inside OpenClaw." |
| **Tooling** | Lists available tools and call rules | **Present but stripped.** Header `## Tooling` + note `"Tool availability (filtered by policy)"`, but lists **only one tool**: `session_status`. The line `"Pi lists the standard tools above. This runtime enables: - session_status..."` reveals that the `params.toolNames` filter has wiped out everything else.  |
| **Interaction Style** | Tone and verbosity (injected by the LLM provider) | **Absent.** No "Interaction Style" block — consistent with the fact that the local Ollama provider doesn't inject style rules. |
| **Tool Call Style** | When to narrate tool use | **Present, standard block.** `## Tool Call Style\nDefault: do not narrate routine, low-risk tool calls...` The Ollama provider didn't override with its own style, so the standard one stays. |
| **Execution Bias** | Pushes toward action instead of planning | **Present.** `## Execution Bias\n- Actionable request: act in this turn...` The `isMinimal` flag is not active (this is a main session, not a sub-agent). |
| **Safety** | Fixed ethical rules (Constitution) | **Present.** `## Safety\nYou have no independent goals...` Unmodified module. |
| **CLI Quick Reference** | Gateway management commands |  **Present.** `## OpenClaw CLI Quick Reference` with `gateway status / restart / start / stop`. |
| **Skills** | Instructions for external SKILL.md files | **Present.** `## Skills (mandatory)` + `<available_skills>` block listing 8 skills (browser-automation, healthcheck, node-connect, skill-creator, taskflow, taskflow-inbox-triage, tmux, weather). Triggered because `params.skillsPrompt` is populated. |
| **Memory** | Rules for memories and citations | **Absent as a structural section.** The memory rules do exist, but they're **injected via AGENTS.md** inside Project Context (sections "Memory", "Write It Down", "MEMORY.md"). This means either `isMinimal=true` or the policy is not emitting the canonical "Memory" block. |
| **Self-Update** | Automatic system updates | **Absent.** Consistent with `capabilities=none` — the agent has no access to the `gateway` tool, so the self-update block isn't added. |
| **Model Aliases** | Short names for other models | **Absent.** No additional models configured beyond the default. |
| **Workspace & Sandbox** | File paths + filesystem restrictions | **Workspace only.** `## Workspace\nYour working directory is: /home/unicef01/.openclaw/workspace` |
| **Messaging & Canvas** | UI / channel rules | **Present, two blocks.** `## Control UI Embed` (for webchat) + `## Messaging` (rules for sessions_send, no exec/curl). Adapted to `runtimeChannel=webchat`. |
| **Reactions & Reasoning** | Emoji + `<think>` tags | **Indirect.** No structural "Reactions & Reasoning" section in the main prompt. The Reactions guidance comes via AGENTS.md (Project Context). The Reasoning part appears only in the last Runtime line: `Reasoning: off (hidden unless on/stream)`. For gpt-oss `thinking=medium` is active: the Runtime line reflects it, but there's no explicit `reasoningTagHint` in the prompt. |
| **# Project Context** | Injection of stable user files | **Present** Loads AGENTS.md , SOUL.md , IDENTITY.md , USER.md , TOOLS.md. **MEMORY.md is missing** (mentioned inside AGENTS.md but not included — consistent: this is a webchat session, MEMORY.md should only load in a direct main session). |
| **CACHE BOUNDARY** | Prompt Caching separator |  No textual `SYSTEM_PROMPT_CACHE_BOUNDARY` sentinel is visible. The structure does show the intent though: everything up to `# Dynamic Project Context` is "stable / cacheable", and the next header explicitly says *"kept below the cache boundary when possible"*. The technical boundary is internal (at `system-prompt.ts:934`) and not emitted as a string. |
| **# Dynamic Context** | Volatile files | **Present.** `# Dynamic Project Context` with HEARTBEAT.md (empty file in this run). Placed below the boundary so it doesn't invalidate the cache. |
| **## Runtime** | OS, Node.js, OpenClaw version, model | **Present, rich.** `Runtime: agent=main \| host=server-cv \| repo=/home/unicef01/.openclaw/workspace \| os=Linux 6.8.0-87-generic (x64) \| node=v22.22.2 \| model=ollama/gpt-oss20b \| default_model=ollama/gpt-oss20b \| shell=bash \| channel=webchat \| **capabilities=none** \| thinking=off`. The `capabilities=none` line is **the diagnostic key** to the failure. |

---

## Extra sections present in my prompt but outside the schema

| Extra section | What it does |
|---|---|
| `## Documentation` | Local docs path + mirror URL + GitHub + Discord + ClawHub. Helps the agent find answers about its own commands. |
| `## Current Date & Time` | Just `Time zone: UTC` — no fixed date, because it's read on-demand via `session_status`. |
| `## Workspace Files (injected)` | Announcer header for what follows in Project Context. Header only, body empty here. |
| `## Assistant Output Directives` | `MEDIA:`, `[[audio_as_voice]]`, `[[reply_to_current]]` — directives for delivery metadata. |
| `## Silent Replies` | The `NO_REPLY` rule  |
| `## Group Chat Context` + `## Inbound Context` | `openclaw.inbound_meta.v2` JSON with channel/provider/surface/chat_type. Trusted metadata. |
| `Sender (untrusted metadata)` | `{"label":"openclaw-tui",...}` JSON — sender of the user message. |

---