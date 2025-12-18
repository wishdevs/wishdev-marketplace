# Flags

Command flags for quick activation of tools and thinking modes.

## Default Recommendation: Use Serena

**`--serena` should be your default flag for most coding tasks.**

### Why Serena by Default?

| Benefit | Description |
|---------|-------------|
| **Claude Code has no indexing** | Unlike Cursor, Claude Code lacks built-in code indexing. Serena fills this gap. |
| **Token efficiency** | Works at symbol level instead of reading entire files |
| **Faster responses** | Semantic search is faster than grep/glob |
| **Better code quality** | Understands code structure, not just text patterns |
| **Free & open-source** | No subscription required |

### When to Use Serena

```
✅ Navigating large codebases
✅ Refactoring existing code
✅ Finding symbol references
✅ Understanding code architecture
✅ Editing specific functions/classes
```

### When Serena is Less Useful

```
❌ Writing code from scratch (no existing structure)
❌ Very small projects (few files)
❌ Non-code files (config, markdown)
```

### Recommended Default Command Pattern

```bash
# Always include --serena for existing codebases
/implement feature --serena --c7 --t2

# Skip serena only for new projects
/implement new-project --c7 --t1
```

---

## MCP Tool Flags

| Flag | Full Name | Description |
|------|-----------|-------------|
| `--c7` | Context7 | Activate Context7 for library documentation |
| `--seq` | Sequential | Activate Sequential Thinking for multi-step reasoning |
| `--serena` | Serena | Activate Serena for semantic code analysis |
| `--play` | Playwright | Activate Playwright for browser automation |

## Thinking Mode Flags

| Flag | Alias | Description | Token Budget |
|------|-------|-------------|--------------|
| `--think` | `--t1` | Standard thinking | ~500 tokens |
| `--think-hard` | `--t2` | Deep analysis | ~2,000 tokens |
| `--ultrathink` | `--t3` | Maximum reasoning | ~10,000 tokens |

## Usage Examples

```bash
# Implement with Context7 documentation
/implement user auth --c7

# Build with deep analysis
/build --type prod --t2

# Test with Playwright and sequential thinking
/test --type e2e --play --seq

# Complex feature with maximum reasoning
/implement payment system --t3 --c7 --serena
```

## Flag Combinations

### Development Workflow
```bash
# Research phase - check docs first
/implement feature --c7 --t1

# Implementation phase - analyze code
/implement feature --serena --t2

# Testing phase - browser automation
/test --play --seq
```

### Complex Implementation
```bash
# Simple component
/implement button --t1

# Feature with external API
/implement oauth login --c7 --t2

# Critical system component
/implement payment gateway --t3 --c7 --serena
```

## Thinking Modes Explained

### --think (--t1): Standard Thinking
- Quick analysis
- Straightforward tasks
- Single-step operations

### --think-hard (--t2): Deep Analysis
- Multiple approaches considered
- Trade-off evaluation
- Architecture decisions

### --ultrathink (--t3): Maximum Reasoning
- Complex system design
- Critical debugging
- Multi-component integration
- When confidence < 70%
