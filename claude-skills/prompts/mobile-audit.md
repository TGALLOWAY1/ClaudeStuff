# Mobile Audit

## Purpose

Inspect a project specifically for mobile usability, responsiveness, and touch interaction quality. Mobile means more than "responsive layout" -- this audit covers viewport issues, interaction problems, and the specific failure modes that frequently appear on small screens, especially iPhone.

## When To Use

- Before beta testing on real devices
- After introducing a new modal-heavy feature
- Whenever the iPhone layout feels "off"
- Before turning a web app into a more native-feeling mobile product
- After significant layout or component changes

## Inputs Expected

- Access to the full repository (especially CSS/styles and layout components)
- Target device assumptions (default: iPhone-width first, small mobile viewport, touch-first, portrait priority)
- Any known mobile pain points (optional)

## Required Process

### Step 1: Inspect mobile-specific areas

Go beyond responsive breakpoints. Examine:

- Viewport sizing and meta tags
- Horizontal overflow on all pages
- Keyboard overlap with inputs and forms
- Modal clipping at screen edges
- Bottom-sheet safety and safe area insets
- Tap target sizes (minimum 44x44 points)
- Sticky header and bottom bar behavior
- Scrolling behavior and nested scroll containers
- Z-index and stacking context problems
- Animation smoothness and interaction latency

### Step 2: Check for known failure modes

These are the specific problems that recur most often:

- Content hidden behind other panels
- Controls cut off at screen edges
- Inputs obscured by the on-screen keyboard
- Nested scroll containers fighting each other
- Cards too tall for smaller screens
- Duplicated subtext that wastes vertical space
- Non-functional controls still visible on mobile
- Tap areas too small for fingers
- Layout shift when modals open or close
- Sticky UI overlapping scrollable content
- Side-by-side layouts that should stack on mobile

### Step 3: Suggest implementation fixes

For each issue, provide:

- CSS/layout fixes where applicable
- Component structure changes if needed
- Interaction simplifications for touch
- Areas needing responsive breakpoints

## Output Format

```markdown
# Mobile Audit Report

## 1. Executive Summary
## 2. Critical Visibility Issues
## 3. Interaction Problems
## 4. Layout / Responsiveness Issues
## 5. Modal / Overlay Issues
## 6. Scrolling / Gesture Issues
## 7. Information Density Problems
## 8. Recommended Fixes By Priority
```

## Rules / Constraints

- Default target: iPhone width, small mobile viewport, touch-first, portrait mode
- Cite file paths and specific components for every finding
- Prioritize issues that block usability over cosmetic concerns
- Provide actionable fix suggestions, not just descriptions of problems

## Common Mistakes To Avoid

- Only checking if media queries exist without testing what they actually do
- Ignoring keyboard interactions with form inputs
- Missing z-index stacking issues that only manifest on mobile
- Treating "it fits on screen" as sufficient when interaction is broken
- Overlooking safe area insets on notched devices
