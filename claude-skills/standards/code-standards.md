# Code Standards

These are non-negotiable quality rules that apply across all projects. They are always in effect regardless of which prompts, agents, or workflows are being used.

## General Quality Rules

- Favor clarity over cleverness
- Keep functions and components focused on a single responsibility
- Prefer explicit, descriptive naming over abbreviations
- Reduce duplication, but don't over-abstract (three similar lines is fine)
- Avoid hidden side effects -- make data flow obvious
- Keep business logic out of presentation layers when reasonable
- Preserve existing patterns unless intentionally improving them
- Use comments for "why," not "what" -- code should be self-documenting

## Change Management Rules

- Make atomic changes -- each commit should do one thing
- Avoid unrelated edits in the same commit
- Do not silently rename important concepts without updating all references
- Keep diffs understandable and reviewable
- Prefer safe incremental refactors over giant rewrites
- Do not leave half-migrated patterns (some old, some new)
- Do not introduce dead code without a clear reason

## Reliability Rules

- Verify assumptions in code before editing
- Validate inputs at system boundaries (user input, external APIs)
- Handle errors explicitly -- never silently swallow exceptions
- Fail fast on programmer errors; recover gracefully from operational errors
- Log errors with sufficient context for debugging
- Add regression tests for critical bugs when feasible
- Fix flaky tests immediately -- do not let them accumulate

## Work Habits

- Create a todo list before starting large work
- Work in manageable batches to avoid context loss and timeouts
- Commit frequently with descriptive messages
- Test after each meaningful batch of changes
- Keep architecture aligned with deployment reality (e.g., don't rely on server memory in serverless)
