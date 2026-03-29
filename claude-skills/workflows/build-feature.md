# Build Feature Workflow

## Purpose

Defines how to implement a new feature from idea to finished code using a phased, architecture-aware approach. This workflow prevents "jamming features in" by requiring inspection of existing patterns before writing new code.

## When To Use

- Adding a new page, tab, or section to an app
- Building a new dashboard or analytics view
- Implementing a new user-facing flow
- Adding significant new functionality to an existing feature

## Inputs Expected

- Feature description and requirements
- Acceptance criteria or expected behavior
- Any constraints (performance, compatibility, design direction)
- Target files or areas of the codebase (optional)

## Required Process

### Phase 1: Understand the feature and constraints

- Clarify what the feature should do and what it should not do
- Identify acceptance criteria and edge cases
- Note any design or performance constraints

### Phase 2: Inspect current architecture

Do not start coding immediately. First check:

- Existing patterns in the codebase that this feature should follow
- State management approach (stores, context, signals, etc.)
- Naming conventions for similar features
- Whether similar features already exist that can be extended
- Whether the feature belongs in the current page structure or needs a new one

### Phase 3: Write an implementation plan

- Identify all affected files and systems
- Break work into small, ordered batches
- Note risks or areas of uncertainty
- Create a todo list to track progress

### Phase 4: Implement incrementally

1. Work through the plan in small batches
2. Test after each batch to catch issues early
3. Commit frequently with descriptive messages
4. Follow existing patterns and naming conventions

### Phase 5: Verify UX and edge cases

- Test the feature with realistic data
- Check empty states, error states, and loading states
- Verify behavior on mobile if applicable
- Confirm the feature integrates cleanly with surrounding UI

### Phase 6: Summarize and commit

## Output Format

```markdown
# Feature Implementation Summary

## Plan
[High-level approach and files to change]

## Files Changed
[List of files with brief description of changes]

## Risks
[Any known risks or caveats]

## Verification
[How the feature was tested and validated]

## Follow-Up
[Any remaining work or improvements for later]
```

## Rules / Constraints

- Always inspect existing patterns before writing new code
- Break work into small batches to avoid timeouts
- Commit frequently with clear messages
- Do not introduce new patterns when existing ones work
- Test after each batch, not just at the end

## Common Mistakes To Avoid

- Starting to code without understanding the existing architecture
- Introducing a new pattern when the codebase already has an established one
- Building the entire feature in one giant uncommitted batch
- Skipping edge case and empty state handling
- Not testing on mobile when the app is mobile-facing
