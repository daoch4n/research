

# **Prompt Engineering in Agentic-Driven Software Development: Enhancing Autonomy and Reliability**


## **I. Introduction: The Convergence of Prompt Engineering and Agentic Software Development**


### **A. Defining Agentic-Driven Development**

The discipline of software engineering is currently experiencing a profound transformation, largely driven by the emergence and maturation of agentic Artificial Intelligence (AI). Unlike preceding AI models, which were primarily designed for tasks such as response generation or providing assistance, contemporary agentic AI systems are engineered for a higher degree of operational independence. These systems can autonomously formulate plans, execute actions, make decisions based on evolving circumstances, and interact dynamically with their operational environments to achieve predefined objectives.[1] This evolution signifies a critical paradigm shift, often characterized as a transition from AI functioning as a "co-pilot" to AI assuming the role of the "pilot".[4] Such intelligent agents exhibit an increasing capacity to comprehend nuanced human communication, generate outputs that are contextually relevant, learn from ongoing interactions, and navigate complex information landscapes to perform sophisticated tasks.[1]

This advancement holds particular significance for the field of software development. Agentic systems are beginning to reshape established development processes by automating intricate coding tasks, offering intelligent code suggestions, aiding in debugging and the identification of potential software issues, and facilitating more natural and intuitive forms of human-computer interaction.[1] The central premise is to empower these agents with the capability not only to understand instructions but also to independently devise and implement plans to fulfill complex software engineering goals, such as automated program repair or comprehensive project management.[2]

However, a significant and fundamental challenge persists in the effective translation of high-level human intentions into the precise, actionable steps that an autonomous agent requires for successful execution. Humans typically articulate their objectives in abstract terms, for example, "fix this bug" or "implement this new feature." AI agents, conversely, necessitate concrete, operationalizable sequences of actions to achieve these goals.[2] Large Language Models (LLMs), which frequently constitute the cognitive core of these agents, possess remarkable capabilities but are susceptible to misinterpreting requirements or may lack the comprehensive contextual understanding essential for complex tasks if not meticulously guided.[8] This "intentionality gap" highlights the critical need for a sophisticated mechanism to effectively bridge the divide between human objectives and agent execution.

Furthermore, the ascent of agentic development represents more than a mere incremental enhancement of software engineering tools; it signifies a qualitative shift in the software development lifecycle itself. The pronounced emphasis on autonomy, decision-making capabilities, and proactive behavior exhibited by these agents [1] indicates that these systems are not merely assisting human developers but are increasingly undertaking complex responsibilities. For instance, agents can autonomously perform program repair [2] or collaborate as a virtual team to resolve issues within code repositories.[9] This transition necessitates a thorough re-evaluation of the human developer's role, which is evolving from direct implementation towards orchestration, supervision, and collaboration with AI agents. Consequently, new skills in AI interaction, diligent oversight, and rigorous validation are becoming paramount for software professionals.


### **B. The Indispensable Role of Sophisticated Prompt Engineering**

At the core of effectively harnessing agentic AI for software development lies the discipline of prompt engineering. Far from being a simplistic exercise in phrasing input queries, sophisticated prompt engineering has matured into a strategic lever for designing the very "blueprint" that shapes how AI agents behave, reason, and adapt within their operational environments.[10] It serves as the critical mechanism for translating human intent into precise, machine-executable tasks that guide the agent's actions.[10]

The quality and design of prompts are directly correlated with the performance and efficacy of AI agents. Well-designed prompts are indispensable for optimizing the intelligence, responsiveness, reliability, and contextual adaptability of autonomous systems across a wide spectrum of software development applications.[10] By carefully refining the language, context, and structure of prompts, developers can guide AI models to deliver more accurate, relevant, and actionable results tailored to specific technical needs and project goals.[11] This meticulous crafting of instructions is what unlocks the full potential of agentic AI, making these advanced systems more intuitive and effective for complex software engineering endeavors.


### **C. Report Objectives and Structure**

This report aims to provide an expert-level analysis of the practical applications of prompt engineering within the context of agentic-driven software development. It will delve into the challenges commonly encountered during autonomous code modification by AI agents, particularly in prolonged operational runs, and propose robust strategies for improvement, grounded in advanced prompt engineering principles and agent design. The integration of a practical case study and the documentation of a specific agentic workflow are intended to further illuminate these areas by providing concrete examples of challenges and strategic approaches in real-world or simulated scenarios.

The subsequent sections will explore:



* The foundational principles and techniques of prompt engineering relevant to intelligent software agents.
* The expanding capabilities of AI agents in software engineering, alongside the inherent challenges on their path to true autonomy.
* Common pitfalls in autonomous code generation and modification during extended tasks, factors influencing success rates, and a case study illustrating these operational realities.
* Strategic prompt engineering methodologies for enhancing the success of code modifications, including the documentation of a specific agentic workflow.
* Mechanisms for ensuring the robustness and reliability of agent-generated code through validation, oversight, and effective debugging techniques. \
Finally, the report will offer actionable recommendations and consider the future outlook for agentic AI in software development.


## **II. Foundations of Prompt Engineering for Intelligent Software Agents**


### **A. Core Principles of Effective Prompt Engineering**

The efficacy of AI agents in software development is profoundly influenced by the quality of the prompts that guide them. Several core principles underpin effective prompt engineering:



* **Clarity and Specificity:** Prompts must be unambiguous and precise. Vague or poorly defined instructions can lead to suboptimal, incorrect, or even nonsensical agent behavior.[7] The initial and most crucial step is to define the task or problem the AI agent needs to address with utmost clarity, specifying what constitutes a successful outcome.[11]
* **Context Provision:** Providing comprehensive context is critical because agents cannot infer information that resides solely "in your head".[7] This context should encompass domain-specific knowledge, characteristics of the existing codebase (such as architectural patterns, coding styles, and dependencies), implementation constraints, performance requirements, and any other relevant environmental factors.[10] The more relevant information an agent has, the better it can tailor its actions and outputs.
* **Iterative Refinement:** Prompt engineering is rarely a one-shot process. It is inherently iterative, involving cycles of designing an initial prompt, testing it, observing the agent's response, and progressively refining the prompt based on those observations to achieve the desired results.[7] This iterative loop is essential for fine-tuning agent behavior.
* **Simplicity versus Complexity:** While comprehensive context is vital, prompts should also strive for an optimal balance between detail and conciseness. Overly complex, verbose, or poorly structured prompts can introduce ambiguity, exceed the agent's context processing capabilities, or lead to the generation of irrelevant output.[7] The goal is to be as specific as necessary without overwhelming the agent or introducing noise.

Adherence to these principles forms the bedrock upon which more advanced prompting techniques can be successfully applied to guide intelligent software agents.


### **B. Key Prompt Engineering Techniques and Their Application in Agentic Systems**

A variety of prompt engineering techniques can be employed to guide and control the behavior of AI agents in software development tasks. These techniques are not merely about crafting a single, perfect query but often involve designing a structured interaction that guides the agent through complex processes. This represents an evolution from simple "query crafting" to a more sophisticated "agent choreography," where the engineer designs the flow of information, the invocation of tools, the structure of reasoning, and the handling of feedback over extended interactions. This orchestration is essential because agentic systems require sequences of actions, state management, and interaction with an environment, moving far beyond single-turn responses.[2]

Key techniques include:



* **Role-Based Prompting:** Assigning a specific persona to the AI agent (e.g., "You are a senior backend engineer specializing in microservices," "You are a QA tester focused on identifying security vulnerabilities") helps to guide its tone, style, focus, and decision-making priorities.[11] This ensures the agent's output aligns with the intended technical perspective.
* **Chain-of-Thought (CoT) Prompting:** This technique instructs the agent to break down complex problems into a series of intermediate reasoning steps before arriving at a final answer or generating code.[11] CoT improves the accuracy and transparency of the agent's process, allowing human developers to follow and verify its logical path. For agents, this means guiding an entire problem-solving process, not just a single response.
* **Few-Shot Prompting:** Providing the agent with a small number of examples (shots) of desired input-output pairs can effectively steer its behavior, especially for domain-specific tasks, stylistic consistency, or when adapting to new types of problems.[12]
* **Instruction-Based Prompting:** Clearly and explicitly outlining the steps, rules, or procedures the agent should follow to complete a task.[12] This is fundamental for guiding sequential actions.
* **Context-Based Prompting:** Embedding relevant information, data snippets, or environmental details directly within the prompt to ensure the agent's responses are grounded in the current situation.[12]
* **Zero-Shot Prompting:** Relying on the agent's pre-trained knowledge to perform a task without any specific examples in the prompt.[12] This is often a starting point, with refinements and more specific techniques applied iteratively.
* **Least-to-Most Prompting:** This involves decomposing a complex problem into a sequence of simpler subproblems that the agent solves incrementally.[11] Each step builds upon the previous one, making complex tasks more manageable.
* **Self-Review/Self-Correction Prompts:** Instructing the agent to evaluate its own generated output (e.g., code, plans) against predefined criteria such as correctness, efficiency, adherence to requirements, or potential security flaws.[14] This internal feedback loop can significantly improve output quality.
* **Tool-Use Prompting:** This is crucial for agentic systems that interact with external tools (e.g., compilers, linters, APIs, file systems). Prompts must be structured to enable agents to understand the available tools, their capabilities, the required input/output formats, and the appropriate contexts for their invocation.[2] Frameworks like RepairAgent and the Bolt system exemplify advanced tool-use prompting by defining how agents interact with their operational environment.[2, 7]

The dynamic nature of software development, however, presents a challenge known as "prompt brittleness." A prompt meticulously designed for one scenario may prove less effective or even fail when the context, task nuances, or environment changes.[13] Since software projects are inherently evolving with new bugs, changing requirements, and unexpected tool outputs, an agent relying on a fixed, albeit sophisticated, prompt might struggle to adapt. This underscores the necessity for more adaptive prompting strategies, such as the dynamically updated prompt format used by RepairAgent [2], or even meta-learning approaches where agents can reflect on and adjust their own prompting strategies based on performance, as suggested by systems like Prochemy.[15]


### **C. Practical Applications Driven by Prompt Engineering**

Effective prompt engineering unlocks a wide array of practical applications for AI agents in software development and beyond, enhancing efficiency, accuracy, and customization:



* **Enhanced Accuracy and Decision Making:** By refining the language, context, and structure of prompts, AI agents can deliver more accurate and actionable results, leading to improved decision-making in tasks ranging from code generation to bug diagnosis.[10]
* **Workflow Automation:** Well-crafted prompts enable agents to automate repetitive or data-heavy tasks, such as report generation, document processing, or routine administrative functions, thereby streamlining workflows and freeing up human resources for more strategic activities.[11]
* **Personalized Agent Behavior and Recommendations:** Prompts can be designed to tailor an agent's behavior, communication style, and recommendations to specific user needs, preferences, or operational contexts, leading to a more personalized and effective user experience.[10]
* **Domain-Specific Task Execution:** By embedding domain-specific terminology, knowledge, and task logic into prompts, agents can be specialized to perform effectively in niche areas like healthcare (e.g., drafting clinical notes), finance (e.g., data extraction for compliance), or legal services.[10]
* **Code Generation and Assistance:** A prominent application in software development is AI-assisted coding. Tools like GitHub Copilot leverage prompt engineering to understand developer intent from natural language descriptions or partial code snippets and suggest relevant code completions, functions, or even entire blocks of code.[6] Similarly, Microsoft employs prompt engineering to refine its AI models, optimizing their ability to generate accurate and contextually relevant responses for developers using Azure AI services.[12]

These applications demonstrate that prompt engineering is not just a technical exercise but a critical enabler for deploying AI agents that provide tangible value across various domains.

**Table 1: Core Prompt Engineering Techniques for Agentic Software Development**


<table>
  <tr>
   <td><strong>Technique Name</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Example Application in Agentic Development</strong>
   </td>
   <td><strong>Key Benefits</strong>
   </td>
  </tr>
  <tr>
   <td>Role-Based Prompting
   </td>
   <td>Assigning a specific persona or role to the AI agent to guide its behavior, tone, and focus.[11]
   </td>
   <td>"You are a security expert. Review this code for vulnerabilities." Agent prioritizes security aspects in its analysis and suggestions.
   </td>
   <td>Contextual alignment, focused output, consistent perspective.
   </td>
  </tr>
  <tr>
   <td>Chain-of-Thought (CoT)
   </td>
   <td>Instructing the agent to break down complex problems into a sequence of intermediate reasoning steps before providing a final output.[11]
   </td>
   <td>"To refactor this function, first identify its current responsibilities, then outline a new structure, then write the refactored code."
   </td>
   <td>Improved reasoning, transparency, error detection, better complex task handling.
   </td>
  </tr>
  <tr>
   <td>Few-Shot Prompting
   </td>
   <td>Providing a few examples of desired input-output pairs to guide the agent's response pattern or style.[12]
   </td>
   <td>Showing examples of correctly formatted API documentation to an agent tasked with generating similar documentation.
   </td>
   <td>Faster adaptation to new tasks, stylistic consistency, domain specialization.
   </td>
  </tr>
  <tr>
   <td>Instruction-Based Prompting
   </td>
   <td>Clearly outlining the specific steps, rules, or procedures the agent must follow to complete a task.[12]
   </td>
   <td>"1. Read file X. 2. Extract all function names. 3. Write names to file Y." Agent follows the sequence precisely.
   </td>
   <td>Procedural clarity, predictable execution, reduced ambiguity.
   </td>
  </tr>
  <tr>
   <td>Self-Review/Self-Correction
   </td>
   <td>Prompting the agent to evaluate its own output against specified criteria and make necessary corrections.[14]
   </td>
   <td>"After generating the code, review it for any logical errors, inefficiencies, or deviations from the requirements."
   </td>
   <td>Improved output quality, proactive error handling, adherence to standards.
   </td>
  </tr>
  <tr>
   <td>Tool-Use Prompting
   </td>
   <td>Structuring prompts to enable agents to understand and utilize external tools, defining their capabilities and interaction protocols.[2]
   </td>
   <td>"Use the 'compile_code' tool. If errors occur, use the 'analyze_error' tool to understand the cause before attempting a fix."
   </td>
   <td>Extensibility, interaction with environment, automation of complex workflows.
   </td>
  </tr>
  <tr>
   <td>Least-to-Most Prompting
   </td>
   <td>Decomposing complex tasks into simpler, incremental subproblems that the agent solves sequentially.[11]
   </td>
   <td>For implementing a feature: 1. Define data model. 2. Create API endpoint. 3. Implement business logic. 4. Write unit tests.
   </td>
   <td>Manages complexity, step-wise validation, clearer progress tracking.
   </td>
  </tr>
</table>



## **III. Agentic-Driven Development: Capabilities, Challenges, and the Path to Autonomy**


### **A. Expanding Capabilities of AI Agents in Software Engineering**

AI agents are rapidly expanding their capabilities across the software development lifecycle, moving from simple assistants to more autonomous partners. Key areas where their impact is growing include:



* **Code Generation and Completion:** Agents like GitHub Copilot can suggest relevant code snippets and functions in real-time, significantly boosting developer productivity.[6] Beyond mere completion, agents are increasingly capable of generating entire functions, modules, or even boilerplate applications based on natural language descriptions or high-level specifications.[5]
* **Automated Debugging and Program Repair:** A particularly promising area is the automation of debugging and program repair. Agents can analyze code for potential issues, suggest fixes, and in some cases, autonomously repair bugs.[1] Systems like RepairAgent demonstrate the ability to identify bug locations, gather information, and apply patches, sometimes fixing bugs that previous techniques could not.[2] This includes capabilities for real-time code analysis and predictive error identification, aiming to catch issues before they manifest.[1]
* **Software Testing and Quality Assurance:** Agents can automate the generation of test cases, execute tests, and analyze results to identify defects or areas of weakness in an application.[3] Frameworks like MAGIS (LLM-based Multi-Agent framework for GitHub Issue reSolution) explicitly include a "Quality Assurance Engineer" agent responsible for testing aspects of software changes.[9]
* **Requirements Engineering and Software Design:** AI agents are beginning to assist in the earlier stages of software development, such as analyzing requirements documents, identifying ambiguities, and even contributing to software design decisions by proposing architectural patterns or component structures.[5] Platforms like ChatDev simulate an entire software company, with agents collaborating on planning and design phases.[6]
* **Software Maintenance and Evolution:** For existing codebases, agents can proactively refactor code to improve readability or efficiency, manage dependencies, and assist in resolving issues reported in platforms like GitHub.[5] Tools like SWE-Agent are designed specifically for addressing and resolving such issues autonomously.[6]
* **Project Management and Task Automation:** Beyond direct coding tasks, agents can also contribute to project management by assisting in task assignment, tracking progress, and automating various workflow components within the development process.[3]

These expanding capabilities highlight the transformative potential of agentic AI to reshape how software is conceptualized, built, and maintained.


### **B. Inherent Challenges on the Path to True Autonomy**

Despite these advancements, the journey towards truly autonomous AI agents in software engineering is fraught with significant challenges that must be addressed:



* **Ambiguity and Underspecification:** A primary hurdle is the inherent ambiguity in human language and task descriptions. Agents often struggle with vague or incomplete user instructions, which can lead to suboptimal outcomes, incorrect code modifications, or misuse of tools if the agent fails to ask clarifying questions or make reasonable assumptions.[17]
* **Context Window Limitations:** The LLMs that power these agents have finite context lengths. This restricts their ability to comprehend and manage extensive codebases or maintain coherence and recall over prolonged interactions involving many files or complex dependencies.[5] This limitation directly impacts an agent's capacity to understand the full scope and implications of changes in large software systems.
* **Error Propagation and Recovery:** Errors made by an agent in an early stage of a multi-step task can cascade and compound, leading to significantly flawed or broken code by the end of the process. Implementing robust mechanisms for error detection, containment, and recovery is crucial but technically challenging.[2]
* **Ensuring Consistent and Predictable Behavior:** Achieving a balance between granting agents autonomy and ensuring their actions are reliable, consistent, and predictable is a delicate act, especially for critical software modification tasks where errors can have severe consequences.[1]
* **Computational Complexity and Cost:** The sophisticated reasoning and multiple LLM calls required for complex agentic behavior can be computationally intensive and expensive, posing practical limitations on their deployment at scale.[1]
* **Maintaining Human Oversight and Control:** As agents become more autonomous, striking the right balance with necessary human intervention, review, and approval becomes critical. This is particularly true for high-stakes decisions or irreversible actions, where human judgment remains indispensable.[1]
* **Security and Ethical Considerations:** Autonomous agents with the ability to modify code and interact with systems introduce new security vulnerabilities if not properly safeguarded. Ensuring their actions align with ethical standards, avoid bias, and comply with security protocols is a paramount concern.[1]

The pursuit of increased agent autonomy inherently creates a tension with the need for reliability. As agents are empowered to make more decisions independently over longer and more complex sequences of actions [1], each decision point becomes a potential source of error. This is exacerbated by challenges like ambiguity in instructions [17] and the inherent limitations in processing extensive context.[5] Errors can propagate silently within an autonomous system, only becoming apparent when a significant failure occurs.[8] Consequently, as autonomy increases, the demand for robust internal validation mechanisms, self-correction capabilities [15], and reliable external oversight or human-in-the-loop interventions [18] grows exponentially. This "autonomy-reliability paradox" drives the critical need for advanced prompt engineering that proactively builds in safeguards, validation checks, and clear escalation paths for human review.

Another significant bottleneck for achieving high levels of autonomy in software agents is the transition from proficient code-level manipulation to genuine system-level comprehension. Current LLMs often excel at tasks with relatively local context, such as completing a function or fixing a bug based on a specific error message and stack trace.[2] However, many errors in LLM-generated code arise from a misunderstanding of the broader context or system-wide implications.[8] Truly complex software changes, like introducing a major new feature or performing significant refactoring, require reasoning about interactions between multiple components, adherence to established design patterns, and consideration of non-functional requirements such as performance, security, and long-term maintainability. The previously mentioned context window limitations [5] directly hinder this holistic, system-level understanding. The emergence of multi-agent frameworks like MAGIS, which employ specialized agents for different aspects of a task [9], suggests that a single monolithic agent may struggle with the breadth and depth of knowledge required for comprehensive system-level work. Therefore, a major hurdle for highly autonomous software agents is evolving beyond localized code generation to a deeper understanding of the entire software system's architecture and behavior. Prompt engineering strategies must adapt to help agents build and maintain more abstract models of the software they are working on, potentially through hierarchical planning, sophisticated memory architectures, or structured interactions with dedicated knowledge bases about the codebase.


## **IV. Challenges in Prolonged Autonomous Code Modification**

The objective of achieving successful, autonomous code modification by AI agents, especially over extended tasks, is often hampered by several common pitfalls. These challenges directly impact the success rate of agents in producing working versus broken code.


### **A. Common Pitfalls in Autonomous Code Generation and Modification during Extended Tasks**

Autonomous agents tasked with generating or modifying code can encounter several types of errors that undermine their effectiveness:



* **Logical Errors:** Agents may misinterpret the fundamental logical requirements of a task. This can lead to code that is syntactically correct and executes without crashing but behaves incorrectly or produces nonsensical results.[8] These are often the most insidious errors as they may not be caught by simple compilation or linting.
* **Incomplete Code or Missing Steps:** Particularly in multi-step modification tasks, agents might omit crucial sections of code, fail to implement necessary helper functions, or miss essential steps in a sequence, resulting in partially functional or entirely broken features.[8]
* **Misunderstanding of Broader Context:** A frequent issue is the agent's failure to grasp the full context of the existing codebase or the wider implications of a proposed change. This can lead to generated code that doesn't integrate well with other modules, violates architectural patterns, or introduces unintended side effects.[8] This problem is often exacerbated in prolonged runs where the initial contextual understanding might degrade over time.
* **Syntactic Errors:** While often easier to detect and fix, agents can still generate code with syntax errors, use incorrect function arguments, or produce malformed code structures that prevent compilation or execution.[8]
* **Semantic Errors:** These are high-level logical mistakes that reflect a deeper misunderstanding of task requirements. Examples include using incorrect conditions in control flow statements, setting incorrect constant values, or making errors in mathematical or logical operations.[8]
* **"Garbage Code" or Irrelevant Output:** In some instances, especially with poorly constrained prompts or after numerous iterations without successful convergence, agents may generate code that is syntactically valid but does not contribute to the intended functionality, is entirely off-topic, or consists only of comments or meaningless snippets.[8]
* **Error Accumulation:** In prolonged autonomous runs, minor errors or misinterpretations made in the early stages of a task can compound over successive modifications. Each subsequent step may build upon a slightly flawed foundation, leading to a cascade of issues that result in significantly broken code by the end of the process.

These pitfalls highlight the complexity of achieving reliable autonomous code modification and underscore the need for robust prompting, validation, and error-handling strategies.


### **B. The Impact of Prompt Length, Iteration Count, and Context Degradation**

The way prompts are structured and how agents iterate on tasks significantly influences their performance, especially in prolonged runs:



* **Prompt Length vs. Code Quality:** Research indicates a non-linear relationship between prompt length and code quality. While sufficient detail is necessary, overly long prompts can be detrimental. Prompts with fewer than approximately 50 words have been observed to generally lead to better performance, whereas prompts exceeding 150 words significantly increase the likelihood of errors, including the generation of "garbage code".[8] This presents a challenge for complex tasks that seem to require substantial initial instruction or context. The key is often conciseness and focus, rather than sheer volume of text.
* **Iterative Degradation:** In extended tasks involving many iterations of code generation or modification, the agent's understanding of the task or the integrity of the generated code can degrade. This can occur if feedback loops are not sufficiently robust to correct misunderstandings, or if crucial context is lost or becomes corrupted over time due to the agent's limited context window.[5] Each iteration carries a risk of introducing new errors or compounding existing ones if not carefully managed.
* **Maintaining Focus Over Time:** A critical challenge in prolonged runs is ensuring the agent maintains focus on the original high-level goal throughout a long sequence of modifications. It's possible for an agent to get sidetracked by intermediate complexities, errors, or sub-optimal local solutions, thereby deviating from the overall objective.

One of the underlying reasons for failure in prolonged runs is the "compounding effect of ambiguity." Errors such as logical misinterpretations often originate from ambiguities present in the initial task description or prompt.[8] In an extended, multi-step process, these initial ambiguities don't just cause a single, isolated error. Instead, they can misdirect the agent at multiple subsequent decision points. For example, an agent might start a code modification task, and an initial ambiguity leads to a slight misinterpretation of a specific requirement. The first piece of code generated reflects this misinterpretation. For the next step, the agent reasons based on the current state of the code (which is already slightly flawed) and its (mis)understanding of the overall goal. This can lead to further divergence from the desired outcome, as each step builds upon a potentially erroneous foundation. The agent might even attempt to "correct" issues that are merely symptoms of the initial misunderstanding, inadvertently leading it further astray. This highlights the critical importance of interactive clarification mechanisms upfront to resolve ambiguities [17] and the need for robust validation at each step of the process, not just at the very end.

A major contributor to failure in long agent tasks, beyond initial ambiguity, is "contextual drift." Agents operate with limited context windows [5], and even well-crafted initial prompts can be lengthy.[8] In tasks requiring numerous modifications or interactions with a large and complex codebase, the initially critical context (e.g., high-level requirements, architectural constraints) might be gradually pushed out of the agent's active context window or become less salient as new information from tool outputs, generated code, and intermediate reasoning steps accumulates. This new information also consumes valuable context space. Over many iterations, the original, crucial high-level objectives or constraints might be effectively "forgotten" or overshadowed by more recent, lower-level details. This "contextual drift" can lead the agent to optimize for local sub-problems while losing sight of the global objectives, resulting in code that might be locally correct but is globally flawed, incomplete, or misaligned with the overall requirements.[8] The findings on optimal prompt length [8] suggest that continuously feeding massive amounts of context is not a scalable solution; rather, smarter context management strategies are needed. These might include techniques for context summarization, prioritized context retrieval, or architectural designs where a "manager" agent is responsible for maintaining and refreshing high-level context for "worker" agents focused on specific sub-tasks.


### **C. Success Rate of Code Modifications (Working vs. Broken Code): Factors and Measurement**

Achieving a high success rate for non-trivial autonomous code modifications remains a significant challenge due to the pitfalls mentioned above. The definition of "success" can vary, but generally, it implies that the agent-generated or modified code is functionally correct, integrates properly with the existing codebase, and meets the specified requirements.

**Metrics for Success:**



* **Unit Test Pass Rates:** A common and objective measure is the percentage of predefined unit tests that the agent-modified code successfully passes. For instance, Atlassian's HULA framework reported passing unit tests for 31% of issues on the SWE-bench dataset.[18]
* **Task Completion Rates:** This measures the proportion of tasks or issues an agent successfully resolves. The HULA framework saw 25% of its generated code changes reach the pull request stage, with 59% of those PRs eventually being merged into Atlassian repositories.[18] The MAGIS framework reported resolving 13.94% of GitHub issues on the SWE-bench benchmark.[9]
* **Code Similarity to Human Code:** Metrics can also assess how closely the agent's code resembles human-written solutions, which can be an indicator of quality and maintainability. HULA's output was rated highly similar to human code in 45% of cases using a GPT-based similarity metric.[18]
* **Error Metrics:** More granular metrics like Jaccard similarity (measuring overlap with correct output) and Levenshtein distance (measuring edits needed to correct code) can quantify the extent of errors when code is incorrect.[8]

**Factors Influencing Success:**



* Quality of Initial Prompt: Clear, concise, and contextually rich prompts are fundamental.
* Agent's Reasoning Capability: The underlying LLM's ability to understand, reason, and plan.
* Access to Relevant Codebase Information: The agent's ability to access and comprehend necessary parts of the existing code.
* Effectiveness of Validation Tools: The availability and integration of compilers, linters, and test suites.
* Human Feedback Mechanisms: The ability for humans to intervene, guide, and correct the agent.


### **D. Case Study: Ashank's 27-Hour Autonomous Agent for Code Conversion [21]**

This case study, drawn from a publicly shared experience by a developer named Ashank, provides a practical illustration of deploying an autonomous AI agent for a prolonged and complex software development task: converting a Laravel (PHP) application to Golang. The experiment highlights both the potential and the persistent challenges of agentic systems in real-world scenarios.



* **Agent Setup and Task Definition:**
    * **Objective:** To refactor a substantial portion of a legacy Laravel application to Golang, driven by the developer's need to save time while studying for exams.
    * **Core Tooling:** The agent was orchestrated using "RooCode," a VSCode extension enabling LLM API interaction for code writing, terminal command execution, and autonomous codebase interaction.
    * **LLM Configuration:**
        * **Orchestrator Agent:** GPT-4.1 via OpenRouter, chosen for its large context window (1M tokens) and cost-effectiveness.
        * **Architect & Code Agents:** GPT-4.1 via a VSLLM API, selected for instruction-following capabilities and cost savings, as tasks typically did not require the full 128k context window.
    * **Operational Duration:** The agent ran for 27 hours in real-time, although nearly half of this duration was attributed to rate-limiting.
    * **Source of Truth (Directional Engineering):** A critical element was the establishment of a "solid, single source of truth." This comprised:
        1. The legacy PHP codebase itself.
        2. Pre-defined tests from the legacy application.
        3. A meticulously structured to-do list. An example to-do item for /admin/users included:
            * A modifiable checkbox [x] for the agent to track completion.
            * Intended page path and behavior.
            * Specific API endpoints to be implemented (e.g., GET /admin/users).
            * Detailed page structure (header, search bar, buttons, table columns).
            * A list of UI components to create (e.g., UserTable, UserSearchBar), with links to their intended locations.
            * A section for the LLM to leave notes.
            * References to specific legacy files (e.g., legacy-panel/resources/views/admin/users/index.blade.php) for business logic.
            * Links to tests to be copied from the legacy code.
    * **Workflow – The "Essential Loop":** The system employed a multi-agent approach:
        1. **Orchestrator:** Passed high-level tasks (e.g., research and outline requirements for a feature) to the Architect.
        2. **Architect:** Researched, outlined design choices, and provided Go code snippets. Subtasks were constrained to be short (1-3 minutes for a junior developer).
        3. **Orchestrator:** Relayed the Architect's output to the Code agent.
        4. **Code Agent:** Implemented the feature based on the Architect's specifications, including generating secure session IDs, storing data in Redis, setting cookies, and integrating with controllers.
        5. **Context Management:** A key feature of RooCode, termed "Boomerang," was utilized. While the blog post doesn't detail its mechanics, its use was cited as crucial for preventing context poisoning and enabling the extended run.
* **Chronicle of Challenges Encountered & Mitigations:**
    * **Initial Failures:** Prior to the successful 27-hour run, the longest attempt lasted about 5 hours before catastrophic failure, described by Ashank as the agent "collapsed in on itself and basically nuked the entire codebase with random unicode characters, then rm -rf(ing) the /src/ folder."
    * **Common Failure Points (Observed during testing):**
        * API errors.
        * Response too long (exceeding context or output limits).
        * Hallucination (generating incorrect or irrelevant information/code).
        * Generation of random characters.
        * Diff errors (problems applying generated code changes).
        * Code deletion or corruption of existing logic.
        * Context poisoning (where the agent's understanding degrades due to flawed or irrelevant information in its context).
    * **Mitigation Strategies Implemented:**
        * **Single Source of Truth:** Emphasized as paramount. Ashank noted, "There must ALWAYS be a single source of truth. There cannot be conflicts in directions, or the [agent] will get confused eventually."
        * **Hyperspecific Instructions:** Instructions needed to be extremely detailed, referencing documentation, specific code files, and any relevant context. This allowed the agent to operate autonomously for extended periods.
        * **RooCode "Boomerang" Feature:** Explicitly credited with mitigating context poisoning, forming a core part of the successful loop.
        * **Structured Subtask Prompts:** Prompts from Orchestrator to Architect and Code agents were highly specific, including constraints like "Only perform the work outlined above and do not deviate" and signaling completion with a specific tool call (_attempt_completion).
    * **Unexpected Emergent Behavior:** Around the 3-hour mark, the Orchestrator agent spontaneously began creating documentation subtasks for the Architect. For example, it requested updates to analysis/database_structure.md to include a "detailed, navigable breakdown of the database schema," specifying Mermaid diagrams, Obsidian-style links, summaries, and navigation instructions. This behavior was short-lived, occurring for only one or two documents before ceasing for the remainder of the run.
* **Outcomes and Lessons Learned:**
    * **Success Rate:** The outcome was described as "somewhat" successful but "stellar" given the complexity.
        * **Routes:** 39 out of 47 specified routes were fully functional.
        * **React Pages:** 32 out of 33 specified React pages were fully functional.
    * **Primary Cause of Failures:** Failures in the remaining routes were mostly attributed to "badly written tests" in the legacy system, which likely provided misleading validation for the agent.
    * **Key Lessons from the Experiment:**
        1. **Single Source of Truth is Paramount:** Ashank concluded that without a clear, unambiguous source of truth (like the detailed to-do list and legacy code), "the models get lost, or have their contexts poisoned super easily."
        2. **The "Barrier of Specificity":** While hyperspecific instructions are necessary for current agents to succeed in long autonomous runs, this creates a significant upfront burden. Ashank questioned, "it's impossible to get specific enough for hallucination prevention without basically pseudocoding the entire project. At that point why didn't you just code it yourself?" This highlights a major hurdle for true autonomy, especially when not merely converting existing code.
        3. **Persistent Hallucination Problem:** Hallucination remains a significant challenge. Until this is better managed, extensive effort will be required to create detailed specifications for agents to follow.
    * **Proposed Future Improvements by Ashank:**
        * **Model Selection Refinements:**
            * **Orchestrator/Architect:** Gemini 2 Pro (for strong research/architecture).
            * **Code:** GPT-4.1 (for instruction following).
            * **Debug:** Claude 3.7 Sonnet (for code quality and logic correction on failed tests).
        * **Enhanced Tooling:** Incorporate more specialized models or tools like SPARC, Vertex AI, or Perplexity MCPs for web search during architecture and debugging phases to improve accuracy.
        * **Improved Testing:** Implicitly, better initial tests for the legacy system would lead to more reliable agent performance.
        * **Cost Optimization:** The initial model choices reflected a balance between capability and cost, using OpenRouter and VSLLM APIs strategically.

This case study vividly demonstrates the current state-of-the-art in applying autonomous agents to substantial software engineering tasks. It underscores the power of meticulous prompt engineering, structured workflows, and robust sources of truth, while also realistically portraying the significant challenges that remain, particularly concerning context management, hallucination, and the sheer effort required to achieve high levels of specificity in instructions. Ashank's experience suggests that while AI can be a powerful "time-saver," the "setup cost" in terms of detailed planning and prompting is currently very high for complex, prolonged autonomous operations.

**Table 2: Common Failure Modes in Agent-Driven Code Modification & Prompt-Based Mitigation Strategies**


<table>
  <tr>
   <td><strong>Failure Mode</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Example Prompt Engineering Strategy to Mitigate</strong>
   </td>
  </tr>
  <tr>
   <td>Logical Error
   </td>
   <td>Code is syntactically correct but functions incorrectly due to flawed logic. [8]
   </td>
   <td>Use Chain-of-Thought prompting to outline logic before coding. Provide explicit examples of correct logic (Few-Shot). Instruct agent to self-review logic against requirements. "Explain your reasoning for this conditional statement."
   </td>
  </tr>
  <tr>
   <td>Incomplete Code/Missing Steps
   </td>
   <td>Crucial sections of code or necessary steps in a process are omitted by the agent. [8]
   </td>
   <td>Use instruction-based prompting with a clear checklist of steps. Employ Least-to-Most prompting to break down the task. Prompt for a plan first, then code each part. "Ensure all helper functions are defined and called."
   </td>
  </tr>
  <tr>
   <td>Context Misunderstanding
   </td>
   <td>Agent fails to grasp the full context of the existing codebase or implications of changes. [8]
   </td>
   <td>Provide concise codebase summaries and architectural guidelines in the prompt. Use role-based prompting (e.g., "You are a maintainer of this specific module"). Refer to specific existing files/patterns using @references if available. [14]
   </td>
  </tr>
  <tr>
   <td>Syntactic Error
   </td>
   <td>Code contains syntax errors, incorrect function arguments, or malformed structures. [8]
   </td>
   <td>Prompt the agent to use a linter or compiler as a tool and correct errors based on feedback. Specify coding language and version. "Ensure the generated Python code is compatible with version 3.9 and passes Flake8 linting."
   </td>
  </tr>
  <tr>
   <td>Semantic Error
   </td>
   <td>High-level logical mistakes such as incorrect conditions, constant values, or operational errors. [8]
   </td>
   <td>Provide clear specifications for conditions and constants. Use Few-Shot examples demonstrating correct semantic usage. Prompt for self-review of calculations and comparisons. "Verify that all loop termination conditions are correctly implemented."
   </td>
  </tr>
  <tr>
   <td>"Garbage Code"/Irrelevant Output
   </td>
   <td>Agent generates code that is syntactically valid but doesn't contribute to the task or is off-topic. [8]
   </td>
   <td>Keep prompts concise and focused (&lt;50-150 words where possible [8]). Clearly define the scope of the task. Use negative constraints (e.g., "Do not include logging functionality in this module"). "The output should only be the Python function requested."
   </td>
  </tr>
  <tr>
   <td>Error Accumulation
   </td>
   <td>Minor errors in early stages compound over a prolonged task, leading to major failures.
   </td>
   <td>Implement incremental generation with validation at each step. Use Human-in-the-Loop for intermediate checkpoints. Prompt for regeneration rather than patching flawed intermediate code if errors are significant. [14]
   </td>
  </tr>
  <tr>
   <td>Context Poisoning
   </td>
   <td>Agent's understanding degrades due to flawed/irrelevant info in its context window over time. (Ashank's Case Study [21])
   </td>
   <td>Utilize specialized tool features (e.g., RooCode's "Boomerang"). Maintain a strict single source of truth. Design prompts to be hyperspecific and self-contained for sub-tasks. Regularly refresh or reset context if possible.
   </td>
  </tr>
</table>



## **V. Strategic Prompt Engineering for Enhancing Code Modification Success in Agentic Systems**

To overcome the challenges inherent in autonomous code modification and improve the success rate of agentic systems, strategic prompt engineering is paramount. This involves not only crafting precise initial instructions but also designing sophisticated interaction frameworks and leveraging advanced techniques to guide agent behavior throughout complex tasks.


### **A. Crafting High-Fidelity Prompts for Code Generation and Modification**

The foundation of successful agent-driven code modification lies in the quality of the prompts that initiate and guide the process. High-fidelity prompts are characterized by:



* **Detailed Context and Specificity:** As emphasized previously, providing comprehensive context is crucial. This includes clearly defining the specific problem domain, detailing relevant characteristics of the existing codebase (such as architectural patterns, established style guides, and naming conventions), outlining all implementation constraints (e.g., library versions, performance targets), and specifying any non-functional requirements.[14] The use of mechanisms like @references to point the agent to specific files, functions, or classes within the codebase can significantly enhance precision by grounding the request in existing artifacts rather than relying solely on textual descriptions.[14] Ashank's case study [21] reinforces this, where to-do items contained direct links to legacy files and specific component paths.
* **Clear Functionality Requirements and Logical Steps:** Prompts should clearly articulate the desired functionality and, where appropriate, guide the LLM through the logical implementation steps required to achieve it. This includes instructing the agent to respect existing architectural boundaries and design patterns within the codebase.[14] Ashank's detailed to-do structure, outlining page structures and endpoints, exemplifies this.[21]
* **Iterative Refinement and Regeneration:** Given that the first attempt may not be perfect, prompt engineering should embrace an iterative cycle. This involves testing the agent's output, identifying shortcomings, and refining the prompt accordingly.[11] When errors occur, it is often more effective to prompt the agent to regenerate the solution, potentially with revised instructions or new constraints, rather than attempting to patch flawed logic. Regeneration can provide a fresh perspective and avoid the propagation of earlier mistakes.[14] Automated approaches to iterative prompt refinement, such as those explored by Prochemy, which optimizes prompts based on model performance, also show promise.[15]
* **Conciseness and Focus:** While detail is important, there is a careful balance to be struck to avoid overly long and verbose prompts, which can increase error rates or lead to the generation of irrelevant "garbage code".[8] Prompts should be as concise as possible while still conveying all necessary information, prioritizing clarity and removing any superfluous details that might confuse the agent or dilute the core instructions.[11] Ashank's strategy of breaking down tasks into 1-3 minute sub-tasks for a "junior developer" aligns with this, ensuring each prompt to the Code agent was focused.[21]


### **B. Advanced Prompting Frameworks and Methodologies**

Beyond basic prompt construction, advanced frameworks and methodologies are emerging to better control and enhance the capabilities of software engineering agents:



* **Dynamic Prompting:** Systems like RepairAgent utilize prompts that are not static but are dynamically updated based on the outputs of tools the agent uses, the actions it has taken, and the evolving state of the repair task.[2] RepairAgent's prompt, for instance, is a structured composite of static sections (Role, Goals, Guidelines, Output Specification) and dynamic sections (State Description, Available Tools, Gathered Information, Last Executed Command and Result) that adapt as the agent progresses through the bug-fixing process.[2] This allows the agent to maintain relevant context and adjust its strategy based on intermediate findings. Ashank's use of RooCode's "Boomerang" feature, while not fully detailed, likely involves a form of dynamic context management or prompt adjustment to prevent poisoning.[21]
* **Tool Integration and Interaction Protocols:** For agents to perform meaningful software engineering tasks, they must effectively interact with external tools (e.g., compilers, linters, version control systems, debuggers). Prompt engineering plays a critical role in defining these interactions. Prompts must clearly delineate the available tools, their specific purposes, the arguments they accept, their expected output formats, and the conditions under which they should be invoked.[2] The Bolt system, for example, employs a structured tool usage format with clear examples and a step-by-step confirmation process to prevent erroneous or excessive tool use.[7] Ashank's agent interacted with the file system and version control (implied by committing code). The RooCode tool itself facilitated these interactions.[21]
* **Self-Review and Reflection Mechanisms:** Agents can be prompted to critically evaluate their own generated code or plans. This involves instructing the agent to check its output for correctness against requirements, logical consistency, efficiency, potential edge cases, and security vulnerabilities.[14] The agent might be asked to "think step-by-step" about potential flaws or to justify its design choices, leading to more robust and reliable outputs. Ashank's prompts included instructions like "Use rationale comments to explain each step."[21]
* **Generating Multiple Solution Approaches:** Instead of settling for the first solution an agent proposes, it can be prompted to generate two or three distinct implementation strategies for a given problem. Subsequently, the agent can be instructed to analyze the trade-offs between these approaches, considering factors such as time and space complexity, readability, maintainability, and alignment with project constraints, before selecting and refining the most suitable option.[14] This encourages a more thorough exploration of the solution space.


### **C. Multi-Agent Systems and Collaborative Prompting**

For highly complex software development tasks that require diverse expertise or parallel processing, multi-agent systems are emerging as a powerful paradigm. Prompt engineering in this context expands to orchestrating collaboration among multiple specialized agents:



* **Specialized Agent Roles:** Frameworks like MAGIS (LLM-based Multi-Agent framework for GitHub Issue reSolution) employ a team of agents with distinct, predefined roles, such as a Manager, Repository Custodian, Developer, and Quality Assurance Engineer.[9] Prompts are crucial for defining these roles, their responsibilities, their areas of expertise, and their interaction protocols. Ashank's setup explicitly used an "Orchestrator," "Architect," and "Code" agent, with consideration for a "Debug" agent, demonstrating this principle.[21]
* **Task Decomposition and Allocation:** A "Manager" agent, guided by appropriate prompts, can analyze a complex problem (e.g., a GitHub issue) and break it down into smaller, manageable sub-tasks. These sub-tasks can then be allocated to specialized "Developer" agents, each receiving prompts tailored to their specific assignment and the relevant code files.[9] Ashank's Orchestrator agent performed this role, breaking down the conversion task and assigning research/outlining to the Architect and implementation to the Code agent. The .roorules instruction to keep subtasks "no longer than 1-3 minutes in length for a JR developer" exemplifies fine-grained task decomposition.[21]
* **Inter-Agent Communication and Planning:** Effective multi-agent systems require carefully designed prompts and communication protocols that enable agents to share information, coordinate their actions, and collaboratively build a solution. For example, MAGIS incorporates a "kick-off meeting" phase where agents, guided by the Manager, discuss the plan, clarify task dependencies, and ensure alignment before coding begins.[9] In Ashank's workflow, the Orchestrator passed specific instructions and (presumably) outputs between the Architect and Code agents. The "Signal completion with _attempt_completion" instruction served as a basic communication/protocol element.[21]

The development of such multi-agent systems, like MAGIS [9] and ChatDev (which simulates an entire software company with roles for planning, coding, testing, and documentation [6]), implies a significant evolution in prompt engineering. It moves towards what could be termed "organizational prompting." In this paradigm, the focus is not just on guiding individual agent actions but on defining the roles, responsibilities, interaction patterns, and collaborative workflows of an entire team of AI agents. Ashank's experiment, though focused on a single developer's setup, clearly implements a rudimentary form of this "AI organization." The success of the system then hinges on how well this "AI organization" is designed and orchestrated through these high-level prompts and communication protocols, effectively creating a virtual software development team.[21]


### **D. Documented Agentic Workflow: A Structured Approach**

*(This section was originally intended to document a workflow from "Image 2." As that image was not available, this section remains a template for how such a workflow would be analyzed if provided.)*

A documented agentic workflow, such as one visualized in a Mermaid diagram, provides a clear and structured representation of how a multi-component AI system might tackle a specific software development task. Documenting such a workflow would typically involve:



* **Workflow Overview and Purpose:**
    * A high-level description of the overall goal the workflow is designed to achieve.
    * The context in which this workflow operates.
* **Identification and Description of Roles/Components:**
    * Clear identification of the distinct agents, modules, or components.
    * Detailed responsibilities for each identified role/component.
* **Sequence of Actions, Data Flow, and Interactions:**
    * A step-by-step breakdown of task progression.
    * Specification of inputs and outputs for each component.
    * Description of inter-component interaction protocols.
* **Testing, Validation, and Quality Assurance Phases:**
    * Identification of explicit stages for testing and validation.
* **Feedback Loops and Iteration Mechanisms:**
    * How the workflow handles failures and refinements.
    * Mechanisms for iteration until a satisfactory outcome.

Enhancement to the Research Document:

Documenting such a workflow would offer a concrete example of concepts like "Multi-Agent Systems" (Section V.C), "agent choreography" [2], or "organizational prompting" [6, 9] in action. It would make abstract notions tangible and provide a blueprint for designing agentic systems. Analyzing its structural choices would highlight design philosophies and inform best practices.


### **E. Techniques for Self-Correction and Iterative Improvement in Agent-Generated Code**

To enhance the reliability of agent-generated code, techniques that enable self-correction and iterative improvement are vital:



* **Automated Prompt Refinement:** Systems like Prochemy are being developed to automate the process of prompt optimization. Prochemy iteratively refines an initial prompt based on the agent's performance on a set of code generation tasks, aiming to discover a final, optimized prompt that consistently yields better results for that task type.[15]
* **Iterative Error Handling and Case Testing:** Agents can be designed with built-in mechanisms for iterative error handling. PyCapsule, for example, features sophisticated prompt inference combined with iterative error correction and test case validation to ensure the stability, safety, and correctness of the generated code.[16] Ashank's experience [21], where the agent would loop "for an hour or so on certain routes" before succeeding or failing, implies an iterative error handling or retry mechanism, though the specifics of its guidance are not detailed beyond the model potentially re-attempting based on test failures.
* **Feedback Loops with Validation Tools:** A powerful approach involves prompting the agent to utilize standard software development validation tools such as linters, compilers, and automated test suites. The agent is then prompted to interpret the feedback from these tools (e.g., error messages, failed test reports) and use that information to correct its own code. The HULA framework, for instance, incorporates feedback from compilers and linters into its code generation loop.[18] Ashank's reliance on "predefined tests" and the observation that "badly written tests" led to "bricked" routes underscores the critical role of validation tools in the feedback loop, even if the agent's interpretation of that feedback could be improved.[21]

By strategically combining these advanced prompting techniques and frameworks, developers can significantly improve the likelihood of autonomous agents producing correct, reliable, and useful code modifications, even in complex and prolonged tasks.

**Table 3: Overview of Advanced Frameworks for Agentic Code Repair and Generation**


<table>
  <tr>
   <td><strong>Framework</strong>
   </td>
   <td><strong>Core Concept</strong>
   </td>
   <td><strong>Key Prompting/Agent Interaction Strategy</strong>
   </td>
   <td><strong>Primary Application</strong>
   </td>
   <td><strong>Strengths</strong>
   </td>
  </tr>
  <tr>
   <td>RepairAgent [2]
   </td>
   <td>Autonomous LLM-based agent for program repair using a set of tools.
   </td>
   <td>Dynamically updated prompt with sections for goals, guidelines, current state, available tools, gathered info, and tool outputs. Agent autonomously selects tools.
   </td>
   <td>Automated bug fixing.
   </td>
   <td>Autonomous planning and tool use, dynamic adaptation to bug context, state-of-the-art repair performance.
   </td>
  </tr>
  <tr>
   <td>MAGIS [9]
   </td>
   <td>LLM-based Multi-Agent framework for GitHub Issue Resolution.
   </td>
   <td>Four specialized agents (Manager, Repository Custodian, Developer, QA Engineer) collaborate. Manager decomposes tasks; "kick-off meeting" for planning.
   </td>
   <td>Resolving GitHub issues.
   </td>
   <td>Handles complex, repository-level tasks through agent collaboration and specialized roles.
   </td>
  </tr>
  <tr>
   <td>HULA [18]
   </td>
   <td>Human-in-the-Loop LLM-based agents framework for software development tasks.
   </td>
   <td>Iterative process: Engineer sets context, AI generates plan, engineer reviews/approves, AI generates code, engineer reviews/approves, AI raises pull request.
   </td>
   <td>Automating repetitive coding tasks.
   </td>
   <td>Balances automation with human control, integrates with existing developer workflows (Jira, Bitbucket).
   </td>
  </tr>
  <tr>
   <td>Prochemy [15]
   </td>
   <td>Automated iterative refinement of prompts for code generation.
   </td>
   <td>Iteratively refines an initial prompt based on model performance on a training set of coding tasks, producing an optimized final prompt.
   </td>
   <td>Enhancing code generation quality.
   </td>
   <td>Automates prompt optimization, improves consistency and reliability, compatible with existing methods.
   </td>
  </tr>
  <tr>
   <td>PyCapsule [16]
   </td>
   <td>Framework for Python code generation with error handling and testing.
   </td>
   <td>Sophisticated prompt inference, iterative error handling mechanisms, and integrated case testing for validation.
   </td>
   <td>Stable and correct code generation.
   </td>
   <td>Focus on generation stability, safety, and correctness through built-in error handling and testing.
   </td>
  </tr>
  <tr>
   <td>Bolt System (conceptual, from [7])
   </td>
   <td>Agent system with structured tool use and planning/acting modes.
   </td>
   <td>Defines structured tool-use format, step-by-step confirmation, plan mode for strategizing, act mode for execution. Emphasizes holistic planning.
   </td>
   <td>General agent task execution.
   </td>
   <td>Clear tool interaction, safety via confirmation, separation of planning and execution, context awareness.
   </td>
  </tr>
  <tr>
   <td>RooCode (Ashank's Case Study [21])
   </td>
   <td>VSCode extension for LLM API interaction, enabling autonomous codebase interaction.
   </td>
   <td>Multi-agent (Orchestrator, Architect, Code), detailed to-do list as source of truth, "Boomerang" feature for context management, hyperspecific prompts.
   </td>
   <td>Legacy code conversion (PHP to Golang).
   </td>
   <td>Demonstrated prolonged autonomous run (27 hrs), high task completion with specific prompting, practical cost optimization.
   </td>
  </tr>
</table>



## **VI. Ensuring Robustness and Reliability: Validation, Oversight, and Debugging**

As AI agents take on more significant roles in software development, ensuring the robustness and reliability of their outputs becomes paramount. This requires a multi-faceted approach encompassing automated validation strategies, effective human oversight, and robust debugging techniques for the agentic systems themselves.


### **A. Automated Validation Strategies for Agent-Generated Code**

Automated validation is crucial for catching errors early and ensuring that agent-generated or modified code meets quality standards. Key strategies include:



* **Test-Driven Development (TDD) with Agents:** A powerful paradigm involves prompting agents to adopt a TDD workflow. This means the agent is first instructed to write tests based on the given requirements and expected input/output pairs. It then runs these tests (which should initially fail if the functionality doesn't exist or is incorrect) and subsequently writes the implementation code with the goal of making all tests pass.[22] The agent can iterate on the code, re-running tests until success. This provides a clear, objective criterion for correctness. Ashank's case study [21] heavily relied on pre-existing tests as a validation mechanism, demonstrating the importance of tests, although the quality of those tests impacted the final outcome.
* **Static Analysis Feedback Loops:** Integrating AI agents with static analysis tools (e.g., SonarQube, DeepCode, linters) creates a valuable feedback loop.[23] Agents can be prompted to execute these tools on their generated code, interpret the reported warnings or errors (related to bugs, code smells, security vulnerabilities, or style violations), and then automatically refactor the code to address these issues. This improves code quality, security, and adherence to coding standards before the code is even executed or committed.
* **Incremental Code Generation and Validation:** For complex tasks, it's often beneficial for agents to generate code in smaller, manageable increments. Validation—such as compilation checks, linting, or running unit tests specific to the generated chunk—can then occur at each increment.[20] This approach helps to catch and rectify errors early in the development process, preventing them from propagating and becoming more difficult to resolve later. Ashank's approach of breaking tasks into 1-3 minute sub-tasks aligns with this incremental validation philosophy.[21]
* **Pre-commit Validation and Safety:** Prompt strategies can be designed to guide agents to perform thorough checks and adhere to safety guidelines before any code is committed to a repository. This includes prompting the agent to consider all relevant files, review previous changes, analyze project context and dependencies, and anticipate potential impacts on other parts of the system, as emphasized by the holistic planning approach in systems like Bolt.[7] Adherence to code formatting standards and diff specifications also falls under this pre-emptive validation. Ashank's agent was instructed to "stage and commit with the message: 'Implement sessio[n]'", implying a pre-commit step, though the depth of validation at this stage isn't fully detailed.[21]

The effectiveness of these automated validation strategies is significantly enhanced by prompt engineering. While tools like static analyzers and test suites can identify issues, the agent's ability to understand and act upon this feedback is determined by how it is prompted. For example, simply presenting an error message to an agent might not be sufficient. The prompt must guide the agent on how to interpret the specific type of error and what kind of corrective action is expected (e.g., "Analyze this null pointer exception stack trace, identify the problematic line in your generated code, and implement a null check to prevent it."). Thus, automated validation and prompt engineering work symbiotically, forming a crucial feedback loop that enables agents to engage in constructive self-correction and improve the quality of their output.


### **B. The Critical Role of Human-in-the-Loop (HITL) Oversight**

Despite advancements in AI, current software engineering agents are not infallible. Human expertise remains crucial for handling complex decision-making, resolving ambiguities that AI cannot, ensuring high-quality outputs, and addressing ethical considerations.[1] Human-in-the-Loop (HITL) frameworks formalize this collaboration:



* **Rationale for HITL:** The primary reason for HITL is to mitigate risks associated with fully autonomous agent actions. Humans can catch errors, provide nuanced judgments, and ensure that agent outputs align with broader project goals and quality standards. Ashank's experiment, while aiming for prolonged autonomy, still required initial setup, prompt engineering, and post-run assessment, representing a form of HITL at the macro level.[21]
* **HITL Frameworks:** Systems like Atlassian's HULA (Human-in-the-loop LLM-based Agents) explicitly integrate human engineers at key stages of the automated development process.[18] In HULA, an engineer initiates a task, provides context, and then reviews and approves (or requests modifications to) an AI-generated coding plan. Once the plan is approved, the AI generates the code. The engineer again reviews this code, provides feedback for regeneration if necessary, and finally approves the changes for a pull request. This iterative review and approval process keeps the human engineer in control.
* **Interactive Ambiguity Resolution:** When agents encounter underspecified instructions or ambiguous requirements, HITL allows them to pause and prompt the human user for clarification. Studies have shown that this interactivity significantly improves agent performance and task success rates by ensuring the agent has the necessary information to proceed correctly.[17] While Ashank's agent ran autonomously for 27 hours, the initial detailed to-do list served as a preemptive ambiguity resolution mechanism.[21]
* **Balancing Automation and Human Judgment:** HITL systems aim to strike an optimal balance. They allow AI agents to autonomously handle routine, well-defined parts of a task, thereby increasing efficiency, while escalating uncertain, critical, or novel decisions to human experts for their judgment and guidance.[19] Ashank's goal was to maximize automation due to time constraints, pushing the boundaries of what could be achieved with minimal intervention during the run itself.[21]

While HITL currently serves as an essential safeguard and quality control mechanism, its role can extend beyond mere correction. The interactions within HITL systems—where humans review, modify, and guide agent outputs—generate valuable data. Each human intervention (e.g., correcting a flawed plan, refining poorly generated code, clarifying an ambiguous requirement) represents a data point indicating where the agent's initial approach was suboptimal. This rich dataset, comprising the agent's attempt, the human's correction, and the surrounding context, can be used to fine-tune the agent's underlying model or its prompting strategies. The long-term goal is for the agent to learn from these interventions, effectively internalizing the patterns of human guidance and requiring progressively fewer corrections for similar tasks over time. In this sense, HITL acts as a "scaffolding" for developing more autonomous and capable agents, and prompt engineering can play a role in structuring these HITL interactions to maximize this learning potential.


### **C. Debugging Agentic AI Systems in Software Development**

Debugging agentic AI systems presents unique challenges compared to traditional software debugging. The autonomous decision-making, real-time learning capabilities, and probabilistic nature of the underlying LLMs can make it difficult to trace why an agent made a specific decision or produced a particular output.[25] Effective debugging requires specialized techniques and a focus on observability:

**Observability Pillars:**



* **Logs:** Comprehensive logging of agent actions, decisions made, inputs received, outputs generated, tool invocations, and any errors or warnings encountered is fundamental. These logs provide a detailed record for reconstructing the agent's behavior.[25] Ashank's ability to identify failure modes like "random unicode characters" or "rm -rf(ing) the /src/ folder" implies some level of logging or observation of the agent's destructive actions.[21]
* **Metrics:** Collecting quantitative metrics on agent performance, such as task success rates, latency of actions, frequency of tool use, and error rates, offers insights into overall system health and potential bottlenecks.[25] Ashank's reporting of "39 routes and 32 pages were fully functional" is a high-level success metric.[21]

**Key Debugging Techniques for Agentic Systems:**



* **Behavior Tracing and Action Logging:** This involves capturing every significant action an agent takes, along with the inputs, context, and reasoning (if inferable) behind those actions. This detailed trace helps developers reconstruct the agent's decision-making process and understand the sequence of events leading to a particular outcome or error.[25] The detailed to-do list with checkboxes in Ashank's setup served as a form of high-level action log.[21]
* **Time-Travel Debugging:** This technique involves recording snapshots of the agent's state and its environment at various points in time. This allows developers to "rewind" and examine the system's state before and after certain events or changes, aiding in pinpointing when and why a deviation occurred.[25]
* **Intent Inference and Goal Tracking:** This focuses on monitoring whether the agent's low-level actions are aligning with its stated high-level goals or inferred intent. Discrepancies can indicate flawed reasoning or incorrect task interpretation.[25] The unexpected documentation subtasks in Ashank's experiment could be an example where intent inference might be useful for understanding agent deviations.[21]
* **Agent Communication Analysis:** In multi-agent systems, analyzing the logs of messages exchanged between agents is crucial for debugging coordination issues, misunderstandings, or failures in collaborative tasks.[25] Understanding the flow between Orchestrator, Architect, and Code agents in Ashank's setup would require this.[21]
* **Error Categorization and Pattern Recognition:** Grouping similar errors observed across multiple runs or different tasks can help identify recurring patterns or systemic flaws in the agent's design or prompting.[25] Ashank listed several common failure points encountered during testing, indicating a process of error categorization.[21]
* **Simulation and Scenario-Based Testing:** Testing agents in controlled, simulated environments with predefined scenarios allows developers to reproduce bugs, test specific functionalities, and isolate issues more effectively than in complex, live environments.[25]
* **Practical Tools and Approaches:** Utilizing debug flags provided by agent frameworks (e.g., Claude's --mcp-debug flag [22]) can help identify configuration or operational issues. Another practical approach is to use separate agent instances for different parts of a task, for example, having one agent generate code and a second, independent agent review that code, which can help catch errors or biases.[22] Ashank's consideration of a dedicated "Debug model" (Claude 3.7 Sonnet) points towards this specialized approach.[21]

By implementing robust observability and employing these specialized debugging techniques, developers can gain better insights into the complex behaviors of agentic AI systems and more effectively address issues that arise.


## **VII. Recommendations and Future Outlook**

The integration of agentic AI into software development is a rapidly advancing frontier. To navigate this landscape effectively and harness the potential of these systems while mitigating risks, several recommendations can be made for developers and teams. Concurrently, emerging research directions promise to further enhance the capabilities and reliability of these intelligent agents.


### **A. Actionable Recommendations for Developers and Teams**



* **Embrace Iterative Prompt Development:** Recognize that crafting effective prompts is an iterative process. Start with simple prompts, rigorously test the agent's responses and behavior, and systematically refine the prompts based on observed outcomes and output quality. Foster a team culture that encourages experimentation and continuous learning in prompt engineering. Ashank's journey from 5-hour failures to a 27-hour run exemplifies this iterative refinement.[21]
* **Prioritize Context and Specificity in Prompts:** Invest significant time and effort in creating prompts that provide comprehensive, unambiguous, and highly specific context relevant to the software task at hand. This includes details about the existing codebase, architectural constraints, desired functionalities, and any domain-specific knowledge required. Ashank's "hyperspecific" instructions and detailed to-do lists were key to his success.[21]
* **Integrate Validation Early and Often:** Implement automated validation mechanisms—such as unit testing, static code analysis, and linting—directly into the agent's workflow. Crucially, prompt the agents to actively use the feedback from these tools to self-correct and improve their generated code. The reliance on, and pitfalls from, legacy tests in Ashank's case study highlight the importance of *quality* validation.[21]
* **Strategically Implement Human-in-the-Loop (HITL) Oversight:** Identify critical decision points, high-risk operations, or areas requiring nuanced judgment where human review and approval are essential. Design clear, efficient, and minimally intrusive HITL interaction points to balance automation with necessary human control. While Ashank aimed for maximum autonomy, the initial setup and final assessment were crucial HITL phases.[21]
* **Develop Standardized Tooling and Prompt Libraries:** For recurring software development tasks or common agent interactions, create and maintain libraries of well-tested, standardized prompts and tool interaction protocols. This promotes consistency, efficiency, and reusability across projects and teams. Ashank's structured prompts for Orchestrator-to-Architect and Orchestrator-to-Code are steps in this direction.[21]
* **Focus on Observability and Debugging from the Outset:** When developing or deploying agentic systems, implement robust logging, metrics collection, and tracing capabilities from the beginning. This focus on observability is crucial for understanding agent behavior, diagnosing issues, and ensuring system reliability.
* **Stay Informed on Emerging Research and Best Practices:** The field of agentic AI and prompt engineering is evolving at a rapid pace. Encourage continuous learning and stay abreast of new agent architectures, advanced prompting techniques, novel validation methods, and emerging best practices from the research community and industry. Ashank's desire to try different models (Gemini, Claude) and specialized tools shows this forward-looking perspective.[21]

The recommendation to "Develop Standardized Tooling and Prompt Libraries," coupled with the research direction of "Automated Prompt Discovery" [15] (discussed below), points towards an eventual "industrialization" of prompt engineering. What is currently often an artisanal, craft-based skill will likely evolve into a more systematic and engineering-oriented discipline. This will involve the creation of reusable prompt assets, automated tools to assist in prompt generation and optimization, and the establishment of widely accepted best practices and design patterns for prompting, akin to those found in traditional software engineering.


### **B. Emerging Research Directions**

The continued advancement of agentic AI in software engineering will be fueled by ongoing research in several key areas:



* **Automated Prompt Discovery and Optimization:** Current prompt engineering relies heavily on manual effort. Research into techniques like Prochemy [15], which aim to automatically discover, generate, or refine prompts for specific tasks based on performance metrics, could significantly reduce this burden and lead to more consistently effective prompts.
* **Advanced Memory and Context Management for Agents:** Overcoming the current limitations of LLM context windows is critical. Future research will likely focus on developing more sophisticated memory architectures and context management strategies for agents, enabling them to handle much larger codebases, maintain coherence over very long interactions, and effectively recall relevant information for complex, extended tasks.[5] Ashank's reliance on RooCode's "Boomerang" feature and choice of a 1M token model for the Orchestrator highlight the current focus on managing large contexts.[21]
* **More Sophisticated Reasoning and Planning Capabilities:** Enhancing the ability of agents to perform complex, multi-step reasoning and strategic planning is essential for tackling system-level software design, modification, and problem-solving.[1] This includes improving their capacity for abstract thought and long-term goal orientation. The multi-agent (Orchestrator, Architect, Code) setup in Ashank's experiment is a step towards distributing reasoning and planning.[21]
* **Self-Improving and Adaptive Agents:** The development of agents that can learn from their own mistakes and successes to autonomously improve their performance, decision-making algorithms, and even their internal prompting strategies over time represents a significant long-term goal.
* **Ethical AI and Robust Safety Guardrails:** As agent autonomy increases, research into developing more reliable and verifiable methods for ensuring their behavior aligns with ethical principles, avoids harmful biases, and adheres to stringent safety requirements will become even more critical.[1] The "nuked the entire codebase" incident in Ashank's early tests underscores the need for safety.[21]
* **Interpretability and Explainability:** Improving our ability to understand why an agent made a particular decision or generated a specific piece of code is crucial for building trust, facilitating debugging, and ensuring accountability.[1] Research in this area aims to make agent reasoning processes more transparent. The unexpected documentation behavior in Ashank's run is an example where better interpretability would be valuable.[21]

One notable tension in the evolution of prompt engineering for agents is between "democratization" and "specialization." While some tools and platforms aim to make agent use highly accessible, allowing users with minimal programming experience to achieve results through natural language instructions [20], the development of highly effective, reliable, and sophisticated software engineering agents currently requires deep expertise. This expertise spans prompt engineering nuances, agent architecture design, and specific domain knowledge of software engineering principles.[2] The detailed considerations for dynamic prompts [2], multi-agent system orchestration [9], and the provision of rich, accurate context [14] all point to a high skill ceiling. Ashank's detailed setup and prompt crafting clearly demonstrate this required expertise.[21] This suggests that while basic agent utilization might become widely democratized for simpler tasks, the design, construction, and fine-tuning of advanced, mission-critical agentic software development systems will likely remain a specialized skill set. Consequently, the role of the "Prompt Engineer" or "AI Interaction Strategist" may become increasingly vital and distinct within development teams.[10] The future may therefore see a two-tiered landscape: broadly accessible agentic tools for common, less complex tasks, alongside a cohort of specialists dedicated to engineering complex agentic systems for high-stakes software development.


### **C. The Evolving Landscape: Towards Truly Collaborative Intelligent Systems**

The trajectory of agentic AI in software engineering points towards a future where these systems evolve from mere assistants into truly collaborative partners. The potential for AI agents to become integral members of development teams, taking on significant responsibilities for coding, testing, maintenance, and even design, is substantial. However, realizing this vision depends on continued research and development to address the fundamental challenges of reliability, safety, predictability, and control.

Ultimately, the widespread adoption and successful integration of highly autonomous agents in software development will hinge on establishing a robust framework of trust. This trust cannot be assumed; it must be earned through demonstrable reliability and verifiable performance. Developers and organizations will need confidence that agents can produce high-quality work, operate safely within defined boundaries, and be understandable when issues arise. The legal and ethical implications of agentic actions, particularly when errors occur, further underscore this need for trustworthy systems.[4] The emphasis on "trust" as the linchpin for widespread adoption implies that future agentic AI systems in software development will need to incorporate "auditable reasoning" pathways. It will not be sufficient for them merely to produce correct code; they will also need to articulate *how* they arrived at a particular solution in a manner that human developers can understand, verify, and consequently trust, especially when troubleshooting or validating critical operations. This requirement extends beyond simple logging to encompass more profound forms of explainability and transparency in agent decision-making processes. Ashank's reflection on the "barrier of specificity" and the hallucination problem touches on this: if the process isn't transparent or reliable enough, the human effort to guide it can outweigh the benefits.[21]

Therefore, the future of agentic software development will be shaped not just by the raw capabilities of AI models, but by the ecosystem of tools, methodologies, and practices that ensure their outputs are verifiable (through transparent reasoning, rigorous testing, and clear audit trails [1]) and that human developers retain meaningful control and oversight (through well-designed HITL systems and robust safety guardrails [1]). Sophisticated prompt engineering, as detailed throughout this report and exemplified in Ashank's case study [21], will be a cornerstone in building this framework of trust, ensuring agents operate reliably, predictably, and in alignment with human intent. Ultimately, bridging the intentionality gap and enabling AI to truly act as the 'pilot' in software development hinges not only on technological advancement but on our collective ability to cultivate this trust through rigorous engineering, transparent processes, and a deeply collaborative human-agent paradigm. As these intelligent systems continue to evolve, the synergy between human expertise and agent capabilities promises to redefine the art and science of software creation.


## **VIII. Works Cited**

[1] Agents arxiv: Exploring AI Language Agents - BytePlus. Accessed May 23, 2025. https://www.byteplus.com/en/topic/513019

[2] RepairAgent: An Autonomous, LLM-Based Agent for Program Repair - Software Lab. Accessed May 23, 2025. https://software-lab.org/publications/icse2025_RepairAgent.pdf

[3] What are AI agents? - GitHub. Accessed May 23, 2025. https://github.com/resources/articles/ai/what-are-ai-agents

[4] The Rise of Agentic AI: From Conversation to Action | Insights & Resources | Goodwin. Accessed May 23, 2025. https://www.goodwinlaw.com/en/insights/publications/2025/05/insights-technology-aiml-the-rise-of-agentic-ai-from-conversation

[5] From LLMs to LLM-based Agents for Software Engineering: A Survey of Current, Challenges and Future - arXiv. Accessed May 23, 2025. https://arxiv.org/html/2408.02479v2

[6] Top AI Agents for Software Development 2025 - Prismetric. Accessed May 23, 2025. https://www.prismetric.com/top-ai-agents-for-software-development/

[7] Prompt Engineering for AI Agents - PromptHub. Accessed May 23, 2025. https://www.prompthub.us/blog/prompt-engineering-for-ai-agents

[8] Using LLMs for Code Generation: A Guide to Improving Accuracy ... Accessed May 23, 2025. https://www.prompthub.us/blog/using-llms-for-code-generation-a-guide-to-improving-accuracy-and-addressing-common-issues

[9] NeurIPS Poster MAGIS: LLM-Based Multi-Agent Framework for ... Accessed May 23, 2025. https://neurips.cc/virtual/2024/poster/93481

[10] How Prompt Engineering Is Shaping the Future of Autonomous Enterprise Agents - AiThority. Accessed May 23, 2025. https://aithority.com/machine-learning/how-prompt-engineering-is-shaping-the-future-of-autonomous-enterprise-agents/

[11] Prompt Engineering for AI: Definition and Use Cases - Cohere. Accessed May 23, 2025. https://cohere.com/blog/prompt-engineering

[12] AI Prompt Engineering - Applications, Benefits, Techniques, Process ... Accessed May 23, 2025. https://appinventiv.com/blog/ai-prompt-engineering/

[13] How to build your Agent: 11 prompting techniques for better AI agents - Augment Code. Accessed May 23, 2025. https://www.augmentcode.com/blog/how-to-build-your-agent-11-prompting-techniques-for-better-ai-agents

[14] How to write good prompts for generating code from LLMs · potpie-ai ... Accessed May 23, 2025. https://github.com/potpie-ai/potpie/wiki/How-to-write-good-prompts-for-generating-code-from-LLMs

[15] Prompt Alchemy: Automatic Prompt Refinement for Enhancing Code Generation - arXiv. Accessed May 23, 2025. https://arxiv.org/html/2503.11085v1

[16] Large Language Model Guided Self-Debugging Code Generation - arXiv. Accessed May 23, 2025. https://arxiv.org/html/2502.02928

[17] arxiv.org. Accessed May 23, 2025. https://arxiv.org/abs/2502.13069

[18] Human in the Loop Software Development Agents - Work Life by Atlassian. Accessed May 23, 2025. https://www.atlassian.com/blog/atlassian-engineering/hula-blog-autodev-paper-human-in-the-loop-software-development-agents

[19] Bridging Minds and Machines: Agents with Human-in-the-Loop – Frontier Research, Real-World Impact, and Tomorrow's Possibilities - Camel AI. Accessed May 23, 2025. https://www.camel-ai.org/blogs/human-in-the-loop-ai-camel-integration

[20] CrowdStrike Research: Securing AI-Generated Code with Multiple Self-Learning AI Agents. Accessed May 23, 2025. https://www.crowdstrike.com/en-us/blog/secure-ai-generated-code-with-multiple-self-learning-ai-agents/

[21] Ashank. "A guide to Autonomous AI Agents." ashank.tech blog, May 20, 2025. Accessed May 23, 2025. https://ashank.tech/blog/running-autonomous-agents (Content derived from blog post provided by the user).

[22] Claude Code: Best practices for agentic coding - Anthropic. Accessed May 23, 2025. https://www.anthropic.com/engineering/claude-code-best-practices

[23] What is AI Code Review, How It Works, and How to Get Started | LinearB Blog. Accessed May 23, 2025. https://linearb.io/blog/ai-code-review

[24] AI Code Review: Revolutionizing Software Quality and Efficiency - CodeStringers. Accessed May 23, 2025. https://www.codestringers.com/insights/ai-code-review/

[25] Top Tools & Techniques for Debugging Agentic AI Systems - Amplework Software. Accessed May 23, 2025. https://www.amplework.com/blog/debugging-agentic-ai-tools-techniques/
