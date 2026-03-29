# Code Standards

## General Principles

- Write clear, self-documenting code; use comments only for "why", not "what"
- Follow the single responsibility principle for functions and modules
- Keep functions short and focused (aim for under 30 lines)
- Prefer immutability and pure functions where practical
- Handle errors explicitly; never silently swallow exceptions

## Naming Conventions

- Use descriptive, intention-revealing names
- Variables: nouns that describe the value (`userCount`, `isActive`)
- Functions: verbs that describe the action (`fetchUser`, `calculateTotal`)
- Booleans: prefix with `is`, `has`, `should`, `can`
- Constants: UPPER_SNAKE_CASE for true constants

## Code Organization

- Group related code together; separate concerns into distinct modules
- Keep imports organized and sorted
- Avoid circular dependencies
- Limit file length; split when a file exceeds ~300 lines

## Error Handling

- Validate inputs at system boundaries
- Use typed errors/exceptions with meaningful messages
- Fail fast on programmer errors; recover gracefully from operational errors
- Log errors with sufficient context for debugging

## Testing

- Write tests alongside code, not as an afterthought
- Test behavior and outcomes, not implementation details
- Maintain fast, reliable test suites; fix flaky tests immediately
