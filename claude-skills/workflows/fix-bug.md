# Fix Bug Workflow

## Purpose

A repeatable sequence for handling bug reports carefully and efficiently. This workflow prioritizes root cause over symptom masking and ensures similar bugs are caught across the codebase.

## When To Use

- Mobile view glitches and layout breaks
- Persistence failures (data not saving, loading wrong values)
- Calculation or counting errors
- Broken interactions (scroll, click, gesture, navigation)
- Any user-reported bug or unexpected behavior

## Inputs Expected

- Bug description (expected vs actual behavior)
- Reproduction steps if available
- Environment details (browser, device, screen size) if relevant
- Screenshots or error messages (optional)

## Required Process

### Phase 1: Define expected vs actual behavior

Write down precisely what should happen and what actually happens. Do not skip this step.

### Phase 2: Reproduce or infer the reproduction path

Confirm the bug by tracing the code path. If you can't reproduce directly, infer the most likely path from the code.

### Phase 3: Trace root cause

- Follow the data flow from source to symptom
- Inspect state, props, API responses, persistence
- Compare with similar working features as reference
- Distinguish the root cause from surface symptoms

### Phase 4: Check related systems for similar bugs

Search for the same pattern elsewhere in the app. If the bug exists in one place, it may exist in similar code paths.

### Phase 5: Implement minimal durable fix

- Fix the root cause, not just the symptom
- Make the smallest reliable change
- If a control is broken and misleading, remove it rather than leaving it visible

### Phase 6: Validate on likely edge cases

- Test the fix with normal data and edge cases
- Verify nothing else broke
- Add a regression test if feasible

### Phase 7: Summarize and commit

## Output Format

```markdown
# Bug Fix Summary

## Bug
[Precise description: expected vs actual]

## Root Cause
[What was actually wrong and why it happened]

## Files Changed
[List of modified files with brief explanation]

## Fix Applied
[What the fix does]

## Validation
[How it was verified]

## Remaining Risks
[Any related areas that might have the same problem]
```

## Rules / Constraints

- Root cause over symptom masking -- always
- Visible bugs before invisible ones
- Interaction reliability before visual polish
- Remove broken controls rather than leaving them misleading
- Check for similar patterns elsewhere in the app
- Commit with a message describing both root cause and fix

## Common Mistakes To Avoid

- Patching the symptom without finding the root cause
- Fixing one instance of a bug without checking for the same pattern elsewhere
- Making a broad refactor alongside a targeted bug fix
- Not testing edge cases after applying the fix
- Leaving broken or non-functional UI elements visible
