# Fix Bug Workflow

A structured workflow for diagnosing and resolving bugs.

## Steps

1. **Understand the Report**: Gather reproduction steps, expected vs actual behavior, and environment details
2. **Reproduce**: Confirm the bug locally with a minimal reproduction
3. **Diagnose**: Trace the code path to identify the root cause
4. **Write Failing Test**: Create a test that demonstrates the bug
5. **Implement Fix**: Apply the minimal change that resolves the root cause
6. **Verify**: Confirm the failing test now passes and no existing tests break
7. **Check for Similar Issues**: Search for the same pattern elsewhere in the codebase
8. **Commit & Push**: Commit with a message that describes the root cause and fix

## Checklist

- [ ] Bug is reproducible locally
- [ ] Root cause is identified (not just symptoms)
- [ ] Regression test is added
- [ ] Fix is minimal and targeted
- [ ] All existing tests still pass
- [ ] Similar patterns checked across codebase
