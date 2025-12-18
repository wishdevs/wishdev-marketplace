# Task Management Mode

Systematic approach for handling complex, multi-step operations through hierarchical task organization and persistent memory management.

## Activation Criteria

This mode activates when:
- Operations involve more than 3 steps
- Multiple file scopes involved
- Complex dependencies exist
- Explicit flag `--task-manage` used

## Task Hierarchy

```
Plan          → Overall objective
  └── Phase   → Major milestones
       └── Task   → Specific deliverables
            └── Todo  → Atomic actions
```

### Example Structure

```
Plan: Implement User Authentication
├── Phase 1: Backend Setup
│   ├── Task: Create auth module
│   │   ├── Todo: Define user schema
│   │   ├── Todo: Implement JWT utils
│   │   └── Todo: Create auth middleware
│   └── Task: Setup database
│       ├── Todo: Create migrations
│       └── Todo: Seed test data
├── Phase 2: Frontend Integration
│   ├── Task: Login component
│   └── Task: Protected routes
└── Phase 3: Testing
    ├── Task: Unit tests
    └── Task: E2E tests
```

## Memory Management

### Session Start
```python
# Load existing state
memories = list_memories()
state = read_memory("current_task_state")
```

### During Execution
```python
# Update progress in parallel
update_memory("task_progress", current_status)
TodoWrite(todos=[...])  # Track atomic actions
```

### Session End
```python
# Save checkpoint
write_memory("checkpoint_[timestamp]", final_state)
cleanup_temp_memories()
```

## Tool Mapping

| Task Type | Primary Tools |
|-----------|---------------|
| Code Changes | Edit, Write, Serena |
| UI Components | Playwright (validation) |
| Testing | Playwright, Bash |
| Documentation | Context7, Read |
| Research | WebSearch, WebFetch |

## Execution Flow

```
1. Load State      → Retrieve existing progress
2. Create Hierarchy → Break down into phases/tasks/todos
3. Execute         → Work through todos sequentially
4. Track Progress  → Update memory and todo list
5. Checkpoint      → Save state periodically
6. Complete        → Document outcome, cleanup
```

## Memory Schema

| Key Pattern | Purpose |
|-------------|---------|
| `plan_[timestamp]` | Overall plan storage |
| `phase_[number]` | Phase-specific data |
| `task_[id]` | Individual task state |
| `checkpoint_[timestamp]` | Recovery points |
| `temp_*` | Temporary working data |

## Best Practices

1. **Always checkpoint** before risky operations
2. **Update todos** as you complete each action
3. **Clean up** temporary memories on completion
4. **Document blockers** in memory for context
5. **Use phases** to organize related tasks

## Integration with Confidence Check

Before starting any phase:

```python
checker = ConfidenceChecker()
score = checker.assess(phase_context)

if score < 0.9:
    # Document uncertainty
    # Request clarification
    # Do NOT proceed
    pass
```

## Example Session

```bash
# Start task management mode
/implement user auth system --task-manage

# System creates:
# - Plan with 3 phases
# - 8 tasks across phases
# - 24 atomic todos

# Execution:
# ✅ Phase 1: Backend (8/8 todos)
# 🔄 Phase 2: Frontend (3/6 todos in progress)
# ⏳ Phase 3: Testing (pending)

# Checkpoint saved: checkpoint_20251218_143022
```
