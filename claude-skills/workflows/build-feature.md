# Build Feature Workflow

A structured workflow for implementing new features end-to-end.

## Steps

1. **Understand Requirements**: Clarify the feature scope, acceptance criteria, and edge cases
2. **Plan Implementation**: Identify affected files, design the approach, and break into subtasks
3. **Create Branch**: Branch from the latest main/develop branch
4. **Implement**: Write the feature code following project standards
5. **Add Tests**: Write unit and integration tests covering the new functionality
6. **Manual Verification**: Test the feature locally for correct behavior
7. **Code Review Prep**: Self-review the diff, clean up any debug code, ensure linting passes
8. **Commit & Push**: Create clear, atomic commits with descriptive messages

## Checklist

- [ ] Requirements are clear and scoped
- [ ] Implementation follows existing patterns
- [ ] Tests cover happy path and edge cases
- [ ] No unrelated changes included
- [ ] Linting and type checks pass
- [ ] Feature works as expected locally
