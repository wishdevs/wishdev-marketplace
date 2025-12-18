# /implement - Feature Implementation Command

Provides a systematic workflow for feature implementation.

## Usage

```
/implement [feature-description] [--type component|api|service|feature] [--framework react|vue|express]
```

## Process Flow

### Stage 1: Analyze Requirements
- Parse feature requirements
- Review existing codebase
- Identify dependencies

### Stage 2: Plan Approach
- Design architecture
- Verify tech stack
- Break down tasks

### Stage 3: Generate Implementation
- Write code
- Apply framework patterns
- Security validation

### Stage 4: Validate Quality
- Code review
- Write tests
- Linting/formatting

### Stage 5: Integrate Documentation
- Update API docs
- Modify README
- Record changes

## MCP Tool Integration

| Tool | Purpose |
|------|---------|
| Context7 | Framework documentation and patterns |
| Sequential Thinking | Complex multi-step planning |
| Playwright | Testing and validation |
| Serena | Semantic code analysis |

## Confidence Check Integration

Always perform confidence check before implementation:

```python
from skills.confidence_check import ConfidenceChecker

checker = ConfidenceChecker()
score = checker.assess({
    "task": "implement new feature",
    "duplicate_check_complete": True,
    "architecture_check_complete": True,
    "official_docs_verified": True,
    "oss_reference_complete": True,
    "root_cause_identified": True
})

if score >= 0.9:
    # Proceed with implementation
    pass
```

## Examples

```bash
# React component implementation
/implement user profile card --type component --framework react

# API endpoint implementation
/implement authentication API --type api --framework express

# Full feature implementation
/implement shopping cart system --type feature
```

## Scope Boundaries

**Supported:**
- Multi-persona feature development
- Security validation
- Testing integration

**Not Supported:**
- Override safety constraints
- Architecture decisions without specialist consultation
