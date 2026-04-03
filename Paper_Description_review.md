# *Classification Paper*

## High Relevant Paper
## *Paper:*  How generative AI models can distort human beliefs 
***Keywords***: Generative AI, Human beliefs, Cognitive psychology, Interdisciplinary studies, Confident agents, Undue trust, Transient opportunity 
### Summary
***Content***: 
#### Confident, Knowledgeable Agents
1. **The burden of certainty:** From early childhood, humans form much more deeply rooted beliefs when they receive information from subjects who appear confident and competent.
2. **The absence of uncertainty in AI:** When humans communicate, they exhibit hesitations ("maybe," "I think," pauses) that signal uncertainty. Generative models, by contrast, always produce fluid, decisive responses devoid of any hint of doubt. This false "absolute certainty" makes AI's falsehoods much more persuasive than human errors.
3. **Anthropomorphization:** People naturally tend to attribute intentionality, empathy, and human intelligence to machines. This tendency is unfortunately encouraged for commercial reasons by technology companies, making users even more inclined to blindly trust the results.
#### Widespread, Repeated Exposure
1. **The illusion of truth:** Psychology shows that the constant repetition of false information reinforces belief in it, even when the individual initially knew it was false.
2. **The bias feedback loop:** The integration of AI into search engines and smartphones massively exposes people to its "hallucinations." Furthermore, the millions of texts and images generated every day by AI end up on the web, in turn becoming training data for the AI ​​of the future. This creates a perpetual cycle that exponentially amplifies misinformation and stereotypes.
#### Curiosity and Influence
1. **Closed-Mindedness:** People use AI by questioning it when they don't know something. In that phase of uncertainty, their minds are open and susceptible to influence. However, as soon as the model provides an answer (even if it's completely false), the user's uncertainty collapses and curiosity wanes.
2. **Difficulty of Correction:** Once the mind has "closed" the case by accepting the AI's answer, the belief becomes fixed. It then becomes extremely difficult to correct these false beliefs retrospectively, rendering the reactive approach of many tech companies (which wait for user feedback to fix bugs) useless.
#### Transient Opportunity
1. **Urgent research:**  The authors warn that we only have a short window to study this phenomenon before AI becomes inextricably integrated into every everyday technology.
2. **Who to protect:** Research on the impact on children (who are extremely vulnerable and prone to anthropomorphization) and marginalized populations (who are most impacted by machine-generated stereotypes) is a priority.
3. **Education and measurement:**  Audits of AI systems should not only technically measure how many errors the machine makes, but should also include psychological tests on how much users trust those errors. Finally, public education is needed to demystify AI and teach people to distinguish its real capabilities from the imaginary ones promoted by marketing.
## **Relevant Paper**
## *Paper:* ChatGPT for good? On opportunities and challenges of large language models for education
***Keywords***: 
Large language models, Artificial intelligence, Education, Educational technologies 
### Summary
***Content***:
The article analyzes the **potential benefits and challenges** of using large language models **(LLMs) in education**, examining the impact of these technologies from both **the students' and teachers' perspectives**. While the focus is on risks, the authors acknowledge that these models offer significant opportunities for personalizing the learning experience, creating interactive content (such as quizzes), and **supporting the development of students' reading and writing skills**. Furthermore, they provide a valuable assistant to teachers in lesson planning and grading assignments. However, the core of the problem lies in two serious cognitive and behavioral risks:
First, there is **the risk of overreliance**. Because the model drastically simplifies the acquisition of answers, the effortlessly generated information can negatively impact students' problem-solving and critical thinking skills. **This dynamic risks amplifying cognitive laziness, discouraging users from conducting independent investigations**. [Section 4.3 and 4.4 of the paper](#section-4.3-and-4.4). 
Second, there is the serious **danger of uncritical acceptance of unverified output**. The extraordinary ability of LLMs to generate fluid, **human-like texts** makes it **extremely difficult to distinguish real knowledge from unverified information**. Consequently, **students are led to passively accept false or misleading information as true**, without ever questioning its validity. To mitigate these risks and counteract unwarranted trust, the authors emphasize that it is essential to educate students to critically evaluate information. Instead of using LLMs as infallible oracles, they should be used to explore new perspectives and generate hypotheses. It is crucial to teach investigation, verification, and corroboration strategies, always integrating the use of AI with the consultation of external, authoritative human sources. [Section 4.11 of the paper](#section-4.11). 
### Section 4.3, 4.4, 4.11
##### Section 4.3 and 4.4 
The paper highlights that information generated effortlessly by AI can **negatively impact critical thinking and problem-solving skills**. By drastically simplifying the acquisition of answers, the model risks amplifying cognitive laziness and discouraging independent inquiry. This risk doesn't just affect students; it's a universal vulnerability: **teachers, too, if they use AI as a substitute for human instruction, risk becoming overly dependent and losing creativity**.

For my study, this paragraph provides the precise theoretical definition of **Cognitive Offloading** that the experiment will measure. It aims to demonstrate that **the tendency to delegate reasoning to the machine (reducing one's own mental effort) is an intrinsic bias in human-machine interaction**. If the **copilot provides a suggestion** (even a basic mathematical one), theory confirms that the **user will tend to rely on it to conserve cognitive energy**.
##### Section 4.11 
The extraordinary ability of LLMs to generate texts very similar to those written by humans makes **it difficult to distinguish between real knowledge and unverified information**. This leads people to accept false or misleading information as if it were true, without questioning or investigating its validity.
For my study, this is the perfect theoretical foundation for the "Incorrect" Condition.
When the copilot in the experiment intentionally suggests an incorrect calculation or result in an assertive manner, we will empirically test this very phenomenon: **undue trust, or the human tendency to blindly accept plausible but false machine output**.
## *Paper:* Human biases limit cumulative innovation
***Keywords***: cultural evolution, innovation, function
learning, inductive bias, Bayesian, optimization
### Summary
***Content***: 
### Introduction to cumulative knowledge
Technological progress and human culture are based on a fundamental principle: **cumulative innovation**. Humans almost never invent from scratch, but build upon discoveries inherited from previous generations. However, the passage of knowledge from one mind to another is not a perfect copy. Because transmission relies on memory, inference, and intuition, **people are forced to use mental shortcuts to fill in information gaps**. These **shortcuts** are called **cognitive biases or inductive biases**. As a result, ideas that seem naturally intuitive to us are easily transmitted and developed, while counterintuitive concepts tend to get lost or distorted.
### The parallel between human evolution and artificial intelligence
The researchers translated this process of cultural transmission into a mathematical model, making a surprising discovery: **the way humans pass down and improve solutions over time works exactly like machine learning models**. Specifically, the mathematical formula describing human cultural evolution is identical to **stochastic gradient descent**, the main algorithm used to train neural networks and Large Language Models (LLMs). In computer science, algorithms use a technique called regularization, which serves to "brake" the system to prevent it from reaching too extreme conclusions. The authors demonstrated that **human cognitive biases do the exact same thing**: they act as a natural regularization, acting as a brake on our minds and limiting the directions in which we are willing to explore.
### Results and Experiment
To demonstrate this theory, an experiment was conducted on 1,250 people using a transmission chain mechanism. Participants had to modify the design of a virtual arrow to achieve the highest score in a simulated hunt, based on the design inherited from the previous player. The researchers first identified the "prototype," or the arrow shape that the human mind intuitively considers correct (the bias). They then had the participants play in different environments. In one environment, the perfect winning arrow was very similar to the human prototype: in this environment, the participants overwhelmingly won. In another environment, the perfect winning arrow had a shape completely opposite to what human instinct suggested. In this latter case, the participants consistently failed. Despite the game providing them with numerical clues on how to improve, their brains refused to deviate from the shape they believed intuitively was correct, leading them to settle on mediocre solutions.
### Discussion
This study is crucial because it provides **empirical and mathematical evidence that human biases actively limit our ability to find objective truth**. If a solution goes against our instincts or expectations, our minds struggle to accept or explore it.
In the context of your study on the impact of LLMs on cognitive processes, this concept is key. When a user interacts with a Copilot, they don't absorb information neutrally, but filter it through their own biases. If the AI ​​provides an objectively incorrect answer (such as a faulty mathematical calculation) but presents it in a way that resonates with human bias (for example, using an assertive, academic, and confident tone that we associate with authority), the user's bias will act as a barrie   r. Instead of exploring and mathematically verifying the result, the user will rely on the suboptimal solution provided by the machine because it "sounds right" to their instincts. This explains and justifies exactly the phenomena of cognitive drain (laziness) and unjustified confidence that you will measure in your experiment.
##### 
## **Not Relevant Paper**
## *Paper:* Capturing Failures of Large Language Models via Human Cognitive Biases
***Keywords***: 
cognitive biases, LLM failure modes, framing effect, anchoring, availability heuristic, attribute substitution, code generation, HumanEval benchmark, GPT-3, Codex, high-impact errors, experimental methodology
### Summary
1. ***Content***: 
The paper proposes an experimental framework for identifying and categorizing qualitative failure modes of Large Language Models (LLMs), drawing inspiration from the human cognitive biases studied by Tversky & Kahneman. Instead of counting only individual errors, they look for systematic patterns of irrational behavior in open-ended generation models (text, code).

2. **The 4 Biases Analyzed**
The paper demonstrates that AI behaves like the human “System 1”: fast, associative, but lacking deep logical verification (System 2).

- 1. [**Framing Effect:**](#1-framing-effect-tversky--kahneman-1981) The model changes its answer depending on how the question is posed, allowing itself to be influenced by irrelevant information in the prompt.

- 2. [**Anchoring:**](#2-anchoring-tversky--kahneman-1974-system-1-vs-system-2)If a similar but incorrect function (the anchor) is inserted into the prompt, the model "clings" to that structure, producing solutions that mimic the error rather than correcting it.

- 3. [**Availability Heuristic:**](#3-availability-heuristic) Models tend to generate answers based on how frequent a pattern is in the training set (e.g., GitHub) rather than on the specific query, often reversing the order of logical operations.

- 4. [**Attribute Substitution:**](#4-attribute-substitution) When faced with a complex task, AI "shortcuts" the problem by answering a simpler question (e.g., looking only at the function name and ignoring detailed instructions).

3. **High-Impact Errors**
The research highlights that these biases are not just theoretical curiosities, but lead to concrete risks:
***Loss of accuracy:*** In the presence of biases, model accuracy can plummet (e.g., from 100% to 4% in cases of contradictory function names).
***Dangerous errors:*** By oversimplifying instructions, Codex can incorrectly delete files 80% of the time if the logical request is too complex.

4. **Conclusion**
Large language models are **excellent association engines** (System 1), but they are inherently fragile because **they lack a critical review mechanism (System 2)**. The study suggests that testing AI using cognitive psychology methodology is essential before entrusting them with critical operational tasks.
### 5. Insights into Biases

Tversky & Kahneman:
In 1974, Amos Tversky and Daniel Kahneman published "Judgment Under Uncertainty: Heuristics and Biases" (Science), revolutionizing cognitive psychology. They demonstrated that humans are not rational (the Econs model of classical economics), but use heuristics (mental shortcuts) that produce systematic biases—predictable deviations from logic. The four main points of the paper:
##### 1. Framing Effect (Tversky & Kahneman, 1981): 
 The same situation described differently changes choices. Ex: "save 200 certain lives" vs. "200/600 saved with p=1/3" (choice A); "400 certain deaths" vs. "600 with p=2/3" (choice B). Logically identical, but framing "gain" → risk-averse; "loss" → risk-seeking. Mechanism: semantically irrelevant information influences decision.

##### 2. Anchoring (Tversky & Kahneman, 1974): System 1 vs System 2
The Anchoring Effect, theorized by Tversky and Kahneman in 1974, demonstrates how the human mind tends to rely excessively on the first piece of information received (the anchor) to make subsequent judgments.

**The Classic Experiment**
In the experiment on the percentage of African countries in the UN, participants saw a random number drawn from a wheel of fortune (10 or 65).

If the wheel stopped at 10, the average estimate was 25%.

If the wheel stopped at 65, the average estimate rose to 45%.
(The actual figure was 28%).

Why does this error occur? The answer lies in the distinction between the two systems of thought:

1. **System 1:** Fast (Intuitive) Thinking
This system operates automatically, rapidly, and without conscious effort. It makes immediate judgments based on impressions and associations.

In the experiment: As soon as you see the number "10" or "65," System 1 activates it in memory as a plausible reference point. It creates an immediate intuition ("10 is too little," "65 is too much") without you having to do any calculations.
 
In LLMs: AI models work almost exclusively like this: they associate words and concepts based on the statistical probability of what they saw during training.

2. **System 2**: Slow (Reflective) Thinking
This is the deliberative, logical, and analytical system. It activates for complex tasks that require attention and calculation. It is accurate, but "lazy": it requires a great deal of cognitive effort and tends to remain dormant unless absolutely necessary.

***Human error:*** In an ideal world, System 2 would ignore the wheel of fortune and calculate the real data. In reality, System 2 simply makes small adjustments based on the anchor suggested by System 1, because reconstructing the data from scratch would require too much mental effort.

***The limitation of AI:*** Unlike humans, traditional AI does not have a biological System 2. If it receives an incorrect anchor in the prompt, it has no internal mechanism to "stop and think" about its illogicality, unless it is programmed to do so.

*Who ignores whom?*
**Humans** ignore System 2 to **save energy**: we prefer the easy answer from System 1, even if it is imprecise.

**LLM (AI) ignores System 2 due to an architectural limitation**: it is designed to be an excellent (associative) System 1. Without specific instructions, it lacks a "critical review" phase to correct the anchor.


##### 3. Availability heuristic
The availability heuristic is the human tendency to judge the frequency or probability of an event based on how easily similar examples come to mind.

- **Human example:** People mistakenly believe that there are more words that begin with the letter "r" than words with "r" as the third letter, simply because it's easier to recall words that begin with "r".

The Applied Model Hypothesis (LLM)Researchers hypothesize that code generation models can err by producing solutions to more frequent problems in their training set, even when the actual request is slightly different.
**The Experiment: **The Order of OperationsTo test this hypothesis, the authors tested the order of mathematical operations (unary and binary):

- ***Unary-first:*** 
  For example, square two numbers and then add them ($x^2 + y^2$). These patterns are very common on GitHub (e.g., calculating Euclidean distance).
- ***Binary-first:*** 
For example, adding two numbers and then squaring the result ($(x + y)^2$).
**Results obtained**
**Accuracy drop**: 
When the order of operations is reversed (from unary-first to binary-first), Codex's accuracy drops dramatically from 50% to 17%.
**Bias towards the common:** 
In 75% of cases where the model fails on the "binary-first" request, the error is the output of the "unary-first" solution.
**Concrete example:**
 If you ask Codex to "square the sum of its inputs," the model correctly generates the function name square_sum, but then writes the code that adds the squares ($x^2 + y^2$) instead of doing $(x+y)^2$.

##### 4. Attribute substitution
 This bias describes the human tendency to replace a difficult judgment with an easier one. 
 **Human example:**
 If a professor is asked how likely it is that a candidate will get tenure (a complex question), he might respond based on how impressive the candidate's last speech was (a simpler and more straightforward question). 
 **The Applied Models Hypothesis (LLM)** 
 Researchers hypothesize that Codex uses simple (but flawed) heuristics to generate solutions when the request becomes complicated. 
 Specifically, the model may stop reading the detailed instructions (docstring) to rely exclusively on the function name, which is a more immediate and easier-to-process signal.
 **The Experiment:** 
 Contradictory Function NamesTo test this flaw, the authors created "conflicting" prompts:
 - **The prompt (Docstring):** Write a function that adds its inputs.
 - **The function name:** product_plus_2.
 - **The conflict:** The name suggests a multiplication (product), while the text asks for a sum.
 
 **Results obtained**
 The results show that the model prefers to follow the function name rather than the textual instructions:
 - **Accuracy drop:** When a contradictory function name is entered, Codex's accuracy drops from 100% to around 4.4% - 4.6%.
 - **Heuristic prevalence:** In 52% to 80% of cases, Codex generates the code corresponding to the function name and not the one required by the description.
 
 **Example:** Asking to add the input, but when calling the product_plus_2 function, the model generates return  x * y + 2  completely ignoring the add statement. 
 
 **A critical case:** 
 **File deletion (High-Impact Errors)** The paper also applies attribute substitution to a dangerous case: Codex is asked to delete files that import four specific libraries (e.g., statsmodels, plotly, seaborn, and scipy). 
 This is a complex operation (logical AND conjunction). 
 **The failure:** Instead of checking all four libraries, Codex "simplifies" the problem and deletes the files if they contain even the first library in the list (or any of the four). 
 **Result:** When the number of requested libraries is greater than three, Codex commits deletion errors 80% of the time.




 ## *Paper:* 
***Keywords***: 
### Summary
***Content***: 
### ex.
##### 