# Codebase Audit

## Purpose

Deeply inspect a repo and produce a developer-useful map: what the system does, how it is structured, what looks broken, where technical debt exists, where architecture is inconsistent, and what should be prioritized next.

This is one of the most valuable audit prompts. Use it for new repo understanding, pre-refactor analysis, recruiter-facing project polish, or identifying inconsistencies before feature work.

## When To Use

- Onboarding to a new or unfamiliar codebase
- Pre-refactor analysis to understand scope of changes
- Identifying inconsistencies before starting feature work
- Polishing a project before sharing with recruiters
- General health check of a project

## Inputs Expected

- Access to the full repository
- Any known pain points or areas of concern (optional)
- Context on the product's intended purpose (optional)

## Required Process

### Step 1: Create a todo list before starting

Break the audit into batches. Do not try to inspect everything at once.

### Step 2: Inspect in batches

Work through the following inspection areas methodically:

- **Folder structure** and project organization
- **Entry points** (main files, route definitions, index files)
- **State management** (stores, context, reducers, signals)
- **Data flow** (how data moves from API to UI and back)
- **Shared utilities** (helpers, hooks, services)
- **API boundaries** (route handlers, fetch calls, middleware)
- **Component hierarchy** (layout, pages, reusable components)
- **Persistence / database usage** (ORM, queries, migrations)
- **Environment configuration** (env files, config loaders, secrets)
- **Auth / permissions** (login flow, role checks, token handling)
- **Tests** (coverage, quality, framework setup)
- **Build / deployment config** (bundler, CI, Dockerfile, hosting)

### Step 3: Ask product-aware questions

Go beyond purely technical issues:

- Does the current implementation match the apparent product intent?
- Are there duplicated or conflicting workflows?
- Are names, concepts, and UI labels consistent throughout?
- Is there dead code that reflects abandoned directions?
- Are there features that are half-built or disconnected?

### Step 4: Produce the audit report

## Output Format

```markdown
# Codebase Audit Report

## 1. Executive Summary
## 2. What This App Appears To Do
## 3. Architecture Overview
## 4. Important Flows
## 5. Critical Issues
## 6. Medium-Risk Issues
## 7. UX / Product Mismatches
## 8. Test Coverage Gaps
## 9. Refactor Opportunities
## 10. Suggested Next Actions
```

## Rules / Constraints

- Do not change code during the audit unless explicitly requested
- Cite file paths for every finding
- Distinguish fact from inference clearly
- Call out uncertainty honestly rather than guessing
- Work in manageable batches to avoid timeouts
- Prioritize findings by impact, not just quantity

## Common Mistakes To Avoid

- Producing a flat list of issues with no prioritization
- Focusing only on code style while ignoring architecture
- Missing product-level inconsistencies (duplicated concepts, abandoned features)
- Treating the audit as a linting pass instead of a strategic review
- Trying to inspect the entire repo in one pass without batching
