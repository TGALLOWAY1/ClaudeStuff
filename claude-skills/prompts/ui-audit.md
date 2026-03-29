# UI Audit

## Purpose

Evaluate the application for usability, visual hierarchy, consistency, clarity, and product flow. This is broader than a mobile audit -- it examines whether the app feels coherent as a product, not just whether it renders correctly.

## When To Use

- Dashboard redesign or evaluation
- Analytics or data-heavy page review
- Before creating mockups or design specs
- When a product "works" but feels messy or unfocused
- After building multiple related views that need to feel unified

## Inputs Expected

- Access to the full repository (especially components, pages, and styles)
- Understanding of the product's intended purpose (optional but helpful)
- Any specific pages or flows to focus on (optional)

## Required Process

### Step 1: Evaluate UX categories

Inspect the following across all major views:

- **Visual hierarchy**: Is the most important content visually prominent?
- **Spacing rhythm**: Is spacing consistent and intentional?
- **Typography consistency**: Are font sizes, weights, and styles coherent?
- **Naming consistency**: Are the same concepts labeled the same way everywhere?
- **Button semantics**: Do primary/secondary/danger actions look distinct?
- **Information density**: Is content appropriately dense or sparse?
- **Component repetition**: Are similar patterns built consistently?
- **Navigation clarity**: Can users always tell where they are and where they can go?
- **Empty states**: What happens when there is no data?
- **Error states**: What happens when something goes wrong?
- **Page purpose clarity**: Does each page have one clear job?

### Step 2: Ask product questions

Go beyond CSS and component structure:

- Does each page have a clear purpose the user can identify?
- Is anything duplicated across views that should be consolidated?
- Are there concepts the user has to mentally reconcile between different parts of the app?
- Does the page explain itself or require external context?
- Is there useless text that adds clutter without adding meaning?
- Are the most important actions visually obvious?
- Do dashboards show useful metrics or decorative ones?
- Do panels feel coordinated or like independent widgets?
- Is shared data shown consistently across different views?
- Do modals handle things that should be full pages, or vice versa?
- Do workflows feel continuous or fragmented across multiple views?

### Step 3: Produce both critique and direction

Don't just list problems. For significant issues, suggest a redesign direction.

## Output Format

```markdown
# UI Audit Report

## 1. Overall Product Clarity
## 2. Strongest Parts Of The UI
## 3. Main UX Problems
## 4. Visual Hierarchy Issues
## 5. Copy / Labeling Issues
## 6. Workflow Friction
## 7. Component-Level Recommendations
## 8. Page-Level Recommendations
## 9. High-Leverage Redesign Opportunities
```

## Rules / Constraints

- Evaluate as a product, not just as code
- Cite specific components, pages, and file paths
- Distinguish between "broken" and "could be better"
- Prioritize changes that would have the highest user-facing impact

## Common Mistakes To Avoid

- Treating the audit as a CSS review instead of a product review
- Listing only negatives without identifying what already works well
- Suggesting redesigns without understanding the existing product intent
- Ignoring empty states, error states, and loading states
- Focusing on individual components without evaluating page-level coherence
