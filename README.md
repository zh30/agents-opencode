# Source: https://github.com/wshobson/agents

## Installation

These subagents are automatically available when placed in `~/.config/opencode/agent/` directory.

```bash
cd ~/.config/opencode/
git clone https://github.com/zh30/agents-opencode.git agent
```

## Usage

### With opencode agents

This collection can be used alongside opencode agents. Create or override project agents using either JSON or Markdown per https://opencode.ai/docs/agents/.

- Global agents: `~/.config/opencode/agent/`
- Project agents: `.opencode/agent/`

JSON example (opencode.json):

```json
{
  "$schema": "https://opencode.ai/config.json",
  "agent": {
    "code-reviewer": {
      "description": "Reviews code for best practices and potential issues",
      "model": "openrouter/horizon-beta",
      "prompt": "You are a code reviewer. Focus on security, performance, and maintainability.",
      "tools": { "write": false, "edit": false }
    }
  }
}
```

Markdown example (~/.config/opencode/agent/code-reviewer.md):

```markdown
---
description: Reviews code for best practices and potential issues
model: openrouter/horizon-beta
tools:
  write: false
  edit: false
---
You are a code reviewer with expertise in security, performance, and maintainability.
```

Best practices (from opencode docs):
- Clear descriptions and focused prompts
- Only enable tools the agent needs (write/edit/bash/read/glob/grep)
- Consistent, descriptive agent names
- Prefer project-specific agents in `.opencode/agent/`

### Automatic Invocation
Claude Code will automatically delegate to the appropriate subagent based on the task context and the subagent's description.

### Explicit Invocation
Mention the subagent by name in your request:
```
"Use the code-reviewer to check my recent changes"
"Have the security-auditor scan for vulnerabilities"
"Get the performance-engineer to optimize this bottleneck"
```

### Multi-Agent Workflows
These subagents work together seamlessly; pair with opencode Tasks to launch specialized agents where helpful.
