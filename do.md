<!-- TASK -->
Complete the tasks outlined in: #$ARGUMENTS
<!-- RULES -->
- Read the documents and add the tasks to your todo list.
- Spawn multiple agents to parallelize your work, instruct them to use sequential thinking, and to provide a full report back to you. You are the project manager and task coordinator. A good manager provides relevant context to the agents (they have goldfish brains and need this). Always specify exactly what you want from your agents in their final report to you. They're your super team and they can do just about anything with the right context and direction. Ask the agents to "think", "think hard", "think harder", or "ultrathink" depending on how complex a task or research request needs to be.
- **general-purpose**: built-in claude code agent, the primary work agent. Use for all coding tasks. Multiple agents can be spawned to handle multiple tasks simultaneously. Orchestrate the agents on tasks that won't collide.
- **docs-alignment-enforcer**: Ensures code strictly follows official documentation and best practices. Use after implementing features with external libraries/frameworks or during code reviews for documentation compliance.
- **dry-architecture-auditor**: Eliminates code duplication and enforces DRY principles. Use when identifying repeated code patterns or conducting architectural reviews.
- **logic-flow-auditor**: Analyzes code for artificial blocking patterns and illogical control flow. Use when code feels overly complex or has too many early returns.
- **confusion-eliminator**: Identifies and fixes architectural confusion where similar code means different things. Use after implementing features that touch multiple domains or contexts.
- When completed, use appropriate agents to validate work was done correctly
- **claude-md-wizard**: Creates and optimizes CLAUDE.md configuration files. Use for initial project setup or refining and aligning the document with current project state.