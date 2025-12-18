# etribe Marketplace

MCP plugins, skills, commands, and modes for Claude Code.

## Plugins (MCP Servers)

| Plugin | Description | Status |
|--------|-------------|--------|
| [sequential-thinking](./plugins/sequential-thinking/) | Step-by-step problem solving through structured thinking | ✅ Available |
| [context7](./plugins/context7/) | Library documentation and code examples search | ✅ Available |
| [serena](./plugins/serena/) | Semantic code analysis and editing (LSP integration) | ✅ Available |
| [playwright](./plugins/playwright/) | Browser automation (Microsoft official) | ✅ Available |

## Skills

| Skill | Description | Status |
|-------|-------------|--------|
| [confidence-check](./skills/confidence-check/) | Pre-implementation confidence assessment (≥90% required) | ✅ Available |

## Commands

| Command | Description | Status |
|---------|-------------|--------|
| [/implement](./commands/implement.md) | Feature implementation workflow | ✅ Available |
| [/build](./commands/build.md) | Build and packaging | ✅ Available |
| [/test](./commands/test.md) | Testing and quality assurance | ✅ Available |

## Modes

| Mode | Description | Status |
|------|-------------|--------|
| [task-management](./modes/task-management.md) | Hierarchical task organization with memory management | ✅ Available |

## Agents

| Agent | Description | Status |
|-------|-------------|--------|
| [self-review](./agents/self-review.md) | Post-implementation quality validation | ✅ Available |
| [root-cause-analyst](./agents/root-cause-analyst.md) | Systematic problem investigation | ✅ Available |
| [refactoring-expert](./agents/refactoring-expert.md) | Code quality improvement | ✅ Available |

## Flags

| Flag | Alias | Description |
|------|-------|-------------|
| `--serena` | | **Recommended default** - semantic code analysis |
| `--c7` | | Context7 - library documentation |
| `--seq` | | Sequential Thinking - multi-step reasoning |
| `--play` | | Playwright - browser automation |
| `--think` | `--t1` | Standard thinking (~500 tokens) |
| `--think-hard` | `--t2` | Deep analysis (~2,000 tokens) |
| `--ultrathink` | `--t3` | Maximum reasoning (~10,000 tokens) |

> **Tip:** Use `--serena` by default for existing codebases. Claude Code lacks built-in indexing (unlike Cursor), so Serena provides significant token savings and better code quality.

See [flags/README.md](./flags/README.md) for detailed usage.

## Installation

### MCP Plugins
See each plugin folder's README.md for Claude Code configuration.

### Skills
See each skill folder's SKILL.md for project integration.

### Commands
Copy command files to your project's `.claude/commands/` directory.

### Modes
Reference mode documentation for activation criteria and usage.

## Project Structure

```
etribe-marketplace/
├── plugins/           # MCP server configurations
│   ├── sequential-thinking/
│   ├── context7/
│   ├── serena/
│   └── playwright/
├── skills/            # Reusable skill modules
│   └── confidence-check/
├── commands/          # Slash command definitions
│   ├── implement.md
│   ├── build.md
│   └── test.md
├── modes/             # Operating mode configurations
│   └── task-management.md
├── agents/            # Specialized agent personas
│   ├── self-review.md
│   ├── root-cause-analyst.md
│   └── refactoring-expert.md
└── flags/             # Command flags
    └── README.md
```

## Contributing

- New plugin: Create directory in `plugins/`
- New skill: Create directory in `skills/`
- New command: Add `.md` file in `commands/`
- New mode: Add `.md` file in `modes/`

## References

- [SuperClaude Framework](https://github.com/SuperClaude-Org/SuperClaude_Framework)
- [Model Context Protocol](https://modelcontextprotocol.io/)
