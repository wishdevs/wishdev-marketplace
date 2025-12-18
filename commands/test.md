# /test - 테스트 및 품질 보증 명령어

Test execution and analysis utility for comprehensive quality assurance.

## Usage

```
/test [target] [--type unit|integration|e2e] [--coverage] [--watch] [--verbose]
```

## Options

| Option | Description |
|--------|-------------|
| `--type unit` | Run unit tests |
| `--type integration` | Run integration tests |
| `--type e2e` | Run E2E tests (Playwright) |
| `--coverage` | Generate coverage report |
| `--watch` | Watch mode for file changes |
| `--verbose` | Verbose logging |

## Test Types

### Unit Tests
- Individual function/component testing
- Fast feedback loop
- Isolated environment

### Integration Tests
- Module interaction testing
- API endpoint validation
- Database integration

### E2E Tests (End-to-End)
- Full user scenario validation
- Browser automation (Playwright)
- Cross-browser testing

## Process Flow

### Stage 1: Detect Test Framework
- Auto-detect pytest, jest, vitest, etc.
- Read configuration files

### Stage 2: Execute Tests
- Real-time progress display
- Immediate failure notification

### Stage 3: Analyze Results
- Pass/fail summary
- Failure analysis
- Coverage metrics

## Examples

```bash
# Run all tests
/test

# Unit tests only
/test --type unit

# E2E tests (Playwright)
/test --type e2e

# Tests with coverage
/test --coverage

# Test specific path
/test src/utils --type unit

# Watch mode
/test --watch
```

## MCP Tool Integration

```
E2E tests auto-activate Playwright MCP:
- Browser automation
- Snapshot comparison
- Network mocking
```

## Failure Analysis

On test failure, provides:
1. List of failed tests
2. Error messages and stack traces
3. Expected vs actual values
4. Related code locations

## Scope Boundaries

**Supported:**
- Execute existing test suites
- Generate quality reports
- Provide failure diagnostics

**Not Supported:**
- Create new test files
- Modify test framework settings
- Run tests requiring unconfigured external services
