# Codebase Audit

Perform a comprehensive audit of the codebase, evaluating:

- **Code Quality**: Readability, consistency, naming conventions, and adherence to best practices
- **Architecture**: Module structure, separation of concerns, dependency management
- **Security**: Input validation, authentication/authorization patterns, secret management, OWASP top 10
- **Performance**: Inefficient algorithms, N+1 queries, unnecessary re-renders, memory leaks
- **Technical Debt**: Deprecated dependencies, TODO/FIXME comments, duplicated code, dead code
- **Testing**: Coverage gaps, missing edge cases, flaky tests
- **Documentation**: Missing or outdated docs, unclear function signatures

## Output Format

Provide findings grouped by severity (Critical, High, Medium, Low) with:
1. File path and line number
2. Description of the issue
3. Recommended fix
4. Priority for remediation
