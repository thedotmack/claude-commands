# 🎭 The Claude Code Command Theater

*Where every command is a performance, and every performance delivers results.*

## 🤔 What Is This?

Welcome to a curated collection of **Claude Code command templates** — your personal repertoire of battle-tested prompts that turn Claude into a specialized coding assistant for any task. Think of these as your greatest hits collection, but for getting stuff done with AI.

Each command in this theater follows the **"Make It Work First"** philosophy outlined in our [MANIFESTO.md](./MANIFESTO.md) — because the best code is code that actually works, not code that's drowning in defensive paranoia.

## 🎯 The Command Lineup

### 💭 **Planning & Strategy**
- **[`think.md`](./think.md)** - *The Strategist*  
  Creates focused step-by-step plans and todo lists. Perfect for when you need to break down complex requests into manageable chunks.

- **[`do.md`](./do.md)** - *The Project Manager*  
  Executes tasks with multiple specialized agents working in parallel. Your go-to for getting things done with proper orchestration.

### 🧠 **Memory & Context**
- **[`save.md`](./save.md)** - *The Archivist*  
  Saves conversation context to persistent memory using claude-mem tools. Never lose important insights again.

- **[`remember.md`](./remember.md)** - *The Detective*  
  Searches claude-mem to find relevant context and previous work. Your AI has amnesia, but this gives it perfect recall.

### 🔍 **Code Review Specialists**
- **[`logic-blocks.md`](./logic-blocks.md)** - *The Logic Block Detective*  
  Self-contained logic block review system focusing on control flow, decision trees, and cognitive complexity. Works independently to analyze code logic structures and integrates seamlessly with the logic-flow-auditor agent.

- **[`design-review-technical.md`](./design-review-technical.md)** - *The System Architect*  
  Comprehensive technical design reviews focusing on root causes of visual inconsistencies and architectural issues.

- **[`design-review-visual.md`](./design-review-visual.md)** - *The Visual Detective*  
  Identifies visual inconsistencies and design system gaps with systematic analysis.

## 🎯 The Philosophy

This collection is built on three core principles:

### 🧠 **Make It Work First**
Stop building defensive fortresses. Write code that does the thing, then fix real problems when they actually happen.

### 🎯 **KISS, DRY, YAGNI**
- **Keep It Simple, Stupid** - Complexity is the enemy
- **Don't Repeat Yourself** - But don't abstract prematurely either
- **You Ain't Gonna Need It** - Build what you need when you need it

### 🎯 **Agent Orchestration**
These commands work with specialized agents:
- 🧠 **general-purpose** - Your primary workhorse
- 📄 **docs-alignment-enforcer** - Keeps code following best practices
- 🌵 **dry-architecture-auditor** - Eliminates code duplication
- 💭 **logic-flow-auditor** - Spots over-complex patterns
- 😵‍💫 **confusion-eliminator** - Fixes architectural chaos
- 🪄 **claude-md-wizard** - Masters CLAUDE.md files

## 🚀 How to Use

### Quick Start
1. **Pick your command** based on what you want to accomplish
2. **Replace `#$ARGUMENTS`** with your specific requirements
3. **Fire it off** to Claude Code
4. **Watch the magic happen**

### Example Usage
```bash
# Want to plan a new feature?
cat think.md | sed 's/#$ARGUMENTS/implement user authentication system/'

# Need to execute a complex task?
cat do.md | sed 's/#$ARGUMENTS/refactor the entire API layer to use TypeScript/'

# Time for a logic block review?
cat logic-blocks.md  # This one guides you interactively
```

### Pro Tips
- **Chain commands**: Use `save.md` after complex work, then `remember.md` in future sessions
- **Parallel execution**: `do.md` excels at orchestrating multiple agents simultaneously
- **Context matters**: Always provide clear, specific arguments — these commands are only as good as your input

## 📋 Command Template Structure

Each command follows a consistent pattern:

```markdown
<!-- TASK -->
[Clear description of what this command does]

<!-- RULES -->
[Specific guidelines and constraints]

<!-- CONFIGURATION -->
[Agent specifications and special instructions]
```

The `#$ARGUMENTS` placeholder gets replaced with your specific requirements, making each command infinitely customizable while maintaining consistent behavior.

## ⚙️ The Technical Details

- **Built for Claude Code CLI** - These templates are optimized for the official Claude Code interface
- **Agent-Aware** - Designed to work with Claude's specialized agent system
- **Memory Integration** - Several commands integrate with claude-mem for persistent context
- **Philosophy-Driven** - Every command embodies the "Make It Work First" mindset

## 💡 Why This Approach Works

Instead of reinventing the wheel every time you need Claude to do something complex, these templates give you:

- **Consistency** - Same high-quality results every time
- **Efficiency** - No more crafting the perfect prompt from scratch
- **Specialization** - Each command is tuned for specific use cases
- **Orchestration** - Built-in agent management and parallel execution
- **Memory** - Persistent context across sessions

## 🔮 Future Commands

Have an idea for a new command template? The pattern is simple:
1. Define the task clearly
2. Specify the rules and constraints
3. Choose the right agents
4. Test with real work
5. Add it to the collection

## 📜 The Manifesto

Don't forget to read the [MANIFESTO.md](./MANIFESTO.md) — it's not just philosophy, it's the secret sauce that makes these commands cut through complexity like a hot knife through butter.

---

*Remember: Every line of defensive code you write before proving your feature works is a lie you tell yourself about problems that don't exist.*

**Make it work first. Make it work always. Make guards earn their keep.**
