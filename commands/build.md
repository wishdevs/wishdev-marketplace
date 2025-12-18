# /build - Build and Packaging Command

Project compilation and packaging with sophisticated error management.

## Usage

```
/build [target] [--type dev|prod|test] [--clean] [--optimize] [--verbose]
```

## Options

| Option | Description |
|--------|-------------|
| `--type dev` | Development build (with sourcemaps) |
| `--type prod` | Production build (optimized) |
| `--type test` | Test build |
| `--clean` | Clean cache before build |
| `--optimize` | Apply additional optimizations |
| `--verbose` | Verbose logging |

## Process Flow

### Stage 1: Analyze Project Structure
- Check build config files (package.json, pyproject.toml, etc.)
- Validate dependencies
- Verify environment variables

### Stage 2: Validate Build Environment
- Check Node.js/Python version
- Verify required packages installed
- Check disk space

### Stage 3: Execute Build Process
- Compile/transpile
- Process assets
- Real-time error detection

### Stage 4: Optimize Artifacts
- Minimize bundle size
- Tree shaking
- Code splitting

### Stage 5: Generate Report
- Build time
- Bundle size analysis
- Performance metrics

## Examples

```bash
# Development build
/build --type dev

# Production build with optimization
/build --type prod --optimize

# Clean build
/build --clean --type prod

# Target specific build
/build frontend --type prod
```

## Error Handling

On build failure:
1. Analyze error message
2. Check dependency conflicts
3. Review environment settings
4. Clear cache and retry

## Scope Boundaries

**Supported:**
- Execute builds
- Provide optimization advice
- Generate build reports

**Not Supported:**
- Modify build configurations
- Install missing dependencies
- Post-build deployment operations
