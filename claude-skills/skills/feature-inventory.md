# Feature Inventory Skill

## Purpose

Maintain a living inventory of all features in the codebase so that the project's capabilities are always documented, discoverable, and up to date. This prevents feature drift, forgotten functionality, and duplicated effort.

A feature that is not tracked will eventually be forgotten, broken without notice, or accidentally reimplemented.

## When To Use

- After adding a new feature or capability
- After modifying an existing feature's behavior or scope
- After removing or deprecating a feature
- During refactors that change what the system can do
- When onboarding to a codebase (to build the initial inventory)

## Inputs Expected

- The feature being added, changed, or removed
- A brief description of what it does
- Its current status (active, deprecated, planned, removed)
- Where it lives in the codebase (key files/modules)

## Required Process

### Step 1: Identify the change

After any code change, determine whether a feature was added, updated, or removed. A "feature" is any user-facing capability, developer-facing API, integration, or significant internal subsystem.

### Step 2: Update the inventory file

Maintain the inventory in `docs/FEATURE-INVENTORY.md` at the project root. If the file does not exist, create it.

- **Added feature**: Append a new entry to the appropriate category.
- **Updated feature**: Edit the existing entry to reflect the new behavior, scope, or location.
- **Removed feature**: Move the entry to the "Removed / Deprecated" section with a date and brief reason.

### Step 3: Keep entries minimal but useful

Each entry should be scannable in under 5 seconds. Avoid long prose — use the format below.

## Output Format

```markdown
# Feature Inventory

> Last updated: [date]

## [Category Name]

| Feature | Description | Status | Key Files | Added |
|---------|-------------|--------|-----------|-------|
| [Name]  | [One-line description] | Active | `path/to/module` | [date] |
| [Name]  | [One-line description] | Active | `path/to/file.ts` | [date] |

## Removed / Deprecated

| Feature | Description | Status | Removed | Reason |
|---------|-------------|--------|---------|--------|
| [Name]  | [One-line description] | Removed | [date] | [Brief reason] |
```

## Example

```markdown
# Feature Inventory

> Last updated: 2026-04-09

## Core

| Feature | Description | Status | Key Files | Added |
|---------|-------------|--------|-----------|-------|
| User Authentication | Email/password login and session management | Active | `src/auth/` | 2026-01-10 |
| Role-Based Access | Admin, editor, viewer permission levels | Active | `src/auth/roles.ts` | 2026-02-03 |

## Integrations

| Feature | Description | Status | Key Files | Added |
|---------|-------------|--------|-----------|-------|
| Stripe Payments | Subscription billing via Stripe Checkout | Active | `src/billing/stripe.ts` | 2026-03-01 |

## Removed / Deprecated

| Feature | Description | Status | Removed | Reason |
|---------|-------------|--------|---------|--------|
| Legacy CSV Export | Export data as CSV via `/api/export` | Removed | 2026-04-01 | Replaced by unified export module |
```

## Rules / Constraints

- **Update the inventory in the same commit as the code change** — do not defer it
- Keep descriptions to one line; link to docs or READMEs for detail
- Use consistent category names across the project
- The inventory is the source of truth for "what does this project do"
- When in doubt about whether something is a "feature", include it — removing a trivial entry is cheaper than rediscovering a forgotten one
- Organize features into logical categories that match the project's domain

## Common Mistakes To Avoid

- Letting the inventory go stale by not updating it alongside code changes
- Writing descriptions that are too vague ("Handles data") or too detailed (multi-paragraph explanations)
- Forgetting to move removed features to the deprecated section (they just disappear)
- Creating entries for internal implementation details that aren't meaningful capabilities
- Having no categories, making the list hard to scan

## Relationship To Other Skills

- **Decision Log** (`skills/decision-log.md`): Decisions often result in new, changed, or removed features. The inventory tracks the outcome; the decision log tracks the reasoning.
- **Build Feature Workflow** (`workflows/build-feature.md`): The final step of building a feature should include updating the inventory.
- **Codebase Audit** (`prompts/codebase-audit.md`): The inventory serves as a checklist during audits to verify all features are accounted for and working.
