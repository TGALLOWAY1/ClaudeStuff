# UI/UX Standards

These are non-negotiable design principles that apply across all projects. They define the quality bar for user-facing interfaces.

## UX Principles

- Every page should have a clear, identifiable purpose
- The most important actions should be visually obvious
- Remove useless text that adds clutter but no meaning
- Avoid duplicate concepts across views -- consolidate related information
- Reduce cognitive load at every opportunity
- Prefer one strong flow over multiple half-overlapping flows
- Workflows should feel continuous, not fragmented across disconnected views

## Visual Consistency Rules

- Maintain consistent spacing rhythm throughout the app
- Use consistent card structure, sizing, and padding
- Use consistent modal behavior (entry, exit, sizing, backdrop)
- Use the same labels for the same concept everywhere
- Avoid overloading dashboards with decorative or low-value metrics
- Default states should be meaningful, not empty decoration
- Use design tokens for colors, spacing, typography, and shadows

## Information Hierarchy

- Primary information first, supporting information second
- Decorative or redundant information should be removed
- Avoid giant stacks of subtext that push important content down
- Preserve scanability -- users should be able to quickly find what matters
- Typography hierarchy should be clear and consistent (size, weight, color)

## Interaction Rules

- Interactive elements must look interactive (buttons, links, clickable items)
- Broken or non-functional interactions should be removed, not left visible
- Don't hide critical actions in inconsistent locations
- Avoid modal-over-modal confusion
- Every user action should have visible feedback
- Allow users to undo destructive actions; use confirmation dialogs

## State Handling

- **Loading states**: Show skeleton screens or spinners for async operations
- **Empty states**: Provide helpful messaging and suggested actions when no data exists
- **Error states**: Display clear, actionable error messages near the relevant context
- **Form validation**: Validate inline on blur; show all errors on submit

## Responsive Design

- Design mobile-first, then enhance for larger screens
- Use fluid layouts that adapt to available space
- Test at standard breakpoints: 320px, 768px, 1024px, 1440px
- Avoid horizontal scrolling on any viewport size
- Respect `prefers-reduced-motion` for animations
