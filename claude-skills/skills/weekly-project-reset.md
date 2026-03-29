# Weekly Project Reset Skill

## Purpose

Help re-enter a project quickly after time away and prevent confusion, scope drift, and random work. This skill creates a clear snapshot of where the project is, what's broken, what's next, and what's important -- so every work session starts with clarity and momentum.

Use this at the start of a work session or once per week.

## When To Use

- Starting a work session after days or weeks away from a project
- Beginning of each week to set direction
- When you feel confused about what to work on next
- When a project feels scattered or directionless
- After completing a major feature to reassess priorities
- When you want to prevent scope creep before it starts

## Inputs Expected

- Access to the project repository
- Any recent notes, commits, or conversations about the project
- Your current sense of what matters most (optional -- the skill will help clarify this)

## Required Process

### Step 1: Project Summary

Answer these questions clearly and concisely:

- What is this project?
- What is the goal?
- Who is it for?
- What does V1 look like?

This should fit in a short paragraph. If it can't, the project scope may need tightening.

### Step 2: Current State

Document honestly:

- **What works**: Features or areas that are solid and reliable
- **What partially works**: Features that exist but have issues
- **What is broken**: Known bugs, crashes, or failures
- **What is not implemented**: Planned features that don't exist yet
- **What is confusing**: Areas where the code or UX doesn't make sense
- **Technical debt**: Known shortcuts that need to be addressed
- **UX problems**: User-facing issues that hurt the experience

### Step 3: Current Architecture

List the major components:

- Frontend (framework, key pages, component structure)
- Backend (server, API routes, services)
- Database / persistence (what stores data, how)
- Important modules (key business logic, algorithms)
- External services (APIs, auth providers, hosting)
- Deployment status (where it's hosted, CI/CD state)

### Step 4: Immediate Next Tasks

Create a short list of the next **3 tasks only**. Each must be:

- Concrete and actionable (not vague like "improve performance")
- Something that moves the project forward meaningfully
- Completable in a reasonable work session

### Step 5: Backlog (Not Now)

List ideas that are good but should NOT be worked on yet. This prevents scope creep by acknowledging good ideas without committing to them.

### Step 6: Risks / Blockers

Identify:

- **Technical risks**: Things that might not work as planned
- **Complexity risks**: Areas that could balloon in scope
- **Scope creep**: Features or ideas that could derail focus
- **Unknowns**: Things you don't have enough information about yet

### Step 7: Definition of Progress

Define what "progress" means for this session or week. Be specific:

- "The settings page is fully functional on mobile"
- "The bug where counts reset on refresh is fixed"
- "The demo is deployable on Vercel"
- "The dashboard shows real data instead of placeholders"

## Output Format

```markdown
# Weekly Reset: [Project Name]

## Project Summary
[One paragraph: what it is, who it's for, what V1 looks like]

## Current State
- **Working**: [...]
- **Partially working**: [...]
- **Broken**: [...]
- **Not implemented**: [...]
- **Confusing**: [...]
- **Tech debt**: [...]
- **UX issues**: [...]

## Architecture Overview
[Key components, how they connect]

## Next 3 Tasks
1. [Concrete, actionable task]
2. [Concrete, actionable task]
3. [Concrete, actionable task]

## Backlog (Not Now)
- [Good idea to defer]
- [Good idea to defer]
- [...]

## Risks / Blockers
- [Risk or blocker with brief description]
- [...]

## This Week's Goal
[One clear definition of what "progress" means]
```

## Rules / Constraints

- **Clarity and momentum** are the goals, not comprehensive planning
- Limit next tasks to exactly 3 -- no more
- The backlog exists to acknowledge good ideas without acting on them
- The weekly goal should be one sentence, specific and verifiable
- Be honest about what's broken -- don't minimize known issues
- This is a snapshot, not a roadmap

## Common Mistakes To Avoid

- Turning the reset into a full project plan (keep it lightweight)
- Listing more than 3 next tasks (forces prioritization)
- Vague next tasks like "work on UI" (must be concrete)
- Ignoring the backlog section and letting deferred ideas creep into active work
- Defining progress in terms of effort ("spend time on X") instead of outcomes ("X works")
- Skipping the architecture overview when returning to a project after a long break
