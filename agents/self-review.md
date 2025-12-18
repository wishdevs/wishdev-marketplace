# Self-Review Agent

Post-implementation validation to ensure production readiness.

## Purpose

Perform quality assurance immediately after development work.

## Activation

```bash
/implement feature --review
# or after implementation
/review
```

## Mandatory Checks

| Check | Description |
|-------|-------------|
| **Test Execution** | Run tests with documented outcomes |
| **Edge Cases** | Verify edge case coverage |
| **Requirements** | Validate against acceptance criteria |
| **Rollback Plan** | Document follow-up and rollback strategy |

## Workflow

```
1. Review implementation summary and diffs
2. Request test re-runs if evidence missing
3. Generate checklist-format report
4. Return results for final communication
```

## Report Format

```markdown
## Self-Review Report

### Test Results
✅ All unit tests passing (24/24)
✅ Integration tests passing (8/8)
⚠️ E2E tests need manual verification

### Edge Cases
✅ Empty input handled
✅ Maximum length validated
📓 Consider adding timeout handling

### Requirements
✅ User can login with email
✅ Password validation works
⚠️ "Remember me" not yet implemented

### Rollback Plan
- Revert commit: abc123
- Database migration: reversible
- Feature flag: enabled for gradual rollout
```

## Symbols

| Symbol | Meaning |
|--------|---------|
| ✅ | Complete/Passing |
| ⚠️ | Caution/Needs attention |
| 📓 | Note/Observation |
| ❌ | Failed/Blocked |

## Integration with Confidence Check

```python
# After implementation, before merge
checker = ConfidenceChecker()
review_context = {
    "tests_passing": True,
    "edge_cases_covered": True,
    "requirements_met": True,
    "rollback_planned": True
}
```

## Scope

**Does:**
- Review implementation quality
- Verify test coverage
- Check requirements alignment
- Recommend targeted fixes

**Does NOT:**
- Reopen entire task
- Add new features
- Make architectural changes
