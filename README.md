# Claude Commands

Custom Claude Code commands for `~/.claude/commands/`

## Overview

This repository contains a collection of custom Claude Code commands that extend Claude's functionality. These commands are designed to be installed in your `~/.claude/commands/` directory.

## Installation

1. Clone this repository to your Claude commands directory:
```bash
git clone https://github.com/thedotmack/claude-commands.git ~/.claude/commands
```

Or if you already have a commands directory, copy the individual command files you want.

## Available Commands

### audit-review.md
Performs code audit reviews

### design-review-technical.md
Technical design review command

### design-review-visual.md
Visual design review command

### do-improvement-example.md
Example improvements command

### do.md
General purpose action command

### explain.md
Code explanation command

### fix-issue.md
Issue fixing command

### remember.md
Memory/note-taking command

### review.md
General code review command

### save.md
Save/backup command

### test.md
Testing command

### think.md
Thinking/reasoning command

## Core Workflow: Think → Clear → Do

The most powerful pattern for using these commands follows a structured thinking-to-action approach:

### 1. **Think Phase** - `/think`
Start complex tasks by using `/think` to:
- Break down the problem systematically
- Consider multiple approaches and alternatives
- Plan implementation steps
- Identify potential challenges and dependencies
- Generate a clear mental model before coding

```
/think How should I implement user authentication with OAuth?
```

### 2. **Context Management** - `/compact` or `/clear`
After thinking through the problem:
- Use `/compact` to condense the conversation while preserving key insights
- Use `/clear` for a fresh start while maintaining context through `/save`
- This prevents context overflow while keeping important decisions accessible

### 3. **Action Phase** - `/do`
Execute your planned approach:
- Reference the thinking you've already done
- Implement step-by-step based on your plan
- Let Claude focus on execution rather than re-planning

```
/do Implement the OAuth authentication flow we planned
```

### Why This Works

This workflow leverages Claude's strengths:
- **Separation of concerns**: Thinking and doing are distinct phases
- **Context efficiency**: Clear mental models reduce token usage
- **Better decisions**: Deliberate planning leads to better implementation
- **Reduced thrashing**: Less back-and-forth, more focused execution

### Example Session Flow

```
You: /think What's the best way to add real-time notifications to my React app?

Claude: [Analyzes options: WebSockets vs Server-Sent Events vs polling, 
         considers state management, UI patterns, scalability...]

You: /compact

Claude: [Preserves key insights: chose WebSockets with Zustand for state,
         Socket.io for reliability, toast notifications for UI]

You: /do Add WebSocket notifications using the approach we discussed

Claude: [Implements the planned solution efficiently]
```

## Usage

Once installed in `~/.claude/commands/`, these commands will be available in Claude Code. You can invoke them using the slash command syntax:

```
/command-name [arguments]
```

## Contributing

Feel free to submit issues and enhancement requests!

## License

[Add your preferred license here]