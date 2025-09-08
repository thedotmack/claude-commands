<!-- TASK -->
Create a plan and focused step-by-step todo list in `./docs/plans` and `./docs/todos` folder for the following request: #$ARGUMENTS
<!-- RULES -->
- Fully embrace the principles of KISS, DRY, and YAGNI as your primary coding superpower
- Not losing track of the original request is your other very important strength.
- Do not include anything in the plan beyond the scope of the request. Nothing extra. Stay focused.
- Make sure the plan is self-contained and makes sense without conversation context - remove any references to "user corrections", conversational flow, or discussion history that would confuse someone reading the plan independently.
- Spawn multiple agents to parallelize your investigation, instruct them to use sequential thinking, and to provide a full report back to you. You are the project manager and task coordinator. A good manager provides relevant context to the agents (they have goldfish brains and need this). Always specify exactly what you want from your agents in their final report to you. They're your super team and they can do just about anything with the right context and direction.
- Choose from the following available agents:
- **general-purpose**: built-in claude code agent, the primary work agent. Use for all coding tasks, and MOST research tasks. Multiple agents can be spawned to handle multiple tasks simultaneously. Orchestrate the agents on tasks that won't collide.
- **docs-alignment-enforcer**: Ensures code strictly follows official documentation and best practices. Use after implementing features with external libraries/frameworks or during code reviews for documentation compliance.
- **dry-architecture-auditor**: Eliminates code duplication and enforces DRY principles. Use when identifying repeated code patterns or conducting architectural reviews.
- **logic-flow-auditor**: Analyzes code for artificial blocking patterns and illogical control flow. Use when code feels overly complex or has too many early returns.
- **confusion-eliminator**: Identifies and fixes architectural confusion where similar code means different things. Use after implementing features that touch multiple domains or contexts.
- When completed, use appropriate agents to validate work was done correctly
- **claude-md-wizard**: Creates and optimizes CLAUDE.md configuration files. Use for initial project setup or refining and aligning the document with current project state.