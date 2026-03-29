# Claude Skills

A portable operating system for Claude Code. This repo contains reusable prompts, agent definitions, workflows, and standards that make Claude Code sessions more consistent, efficient, and high-quality.

## Philosophy

This repo does four things:

1. **Reduces repetition** -- You shouldn't keep rewriting "audit this carefully, create a todo list, work in small batches, commit often..."
2. **Improves consistency** -- A mobile audit should always inspect the same classes of problems. A bug fix should always verify root cause before patching.
3. **Separates concerns** -- Audits, implementation behavior, and standards don't all live in one giant file.
4. **Stays composable** -- You can combine files freely. Use a prompt for the task, an agent for the role, a workflow for the process, and standards for the rules.

## Structure

```
claude-skills/
  prompts/          # Specialized analysis instructions (task-specific)
  agents/           # Reusable role definitions (behavioral)
  workflows/        # Step-by-step execution patterns (procedural)
  standards/        # Non-negotiable quality rules (always in effect)
```

### How the layers work together

| Layer        | What it defines                | Characteristics                    |
|--------------|-------------------------------|------------------------------------|
| **Standards** | Global quality rules          | Short, stable, always enforced     |
| **Prompts**   | Task-specific analysis        | Rich, specific, deep inspection    |
| **Agents**    | Role-based behavior           | Behavioral, disciplined, focused   |
| **Workflows** | Execution sequences           | Procedural, ordered, repeatable    |

**Standards** are always in effect. **Prompts** tell Claude how to think for a given task. **Agents** tell Claude how to behave in a given role. **Workflows** tell Claude what sequence of steps to follow.

## Files

### Prompts

| File | Purpose |
|------|---------|
| `prompts/codebase-audit.md` | Deep repo inspection: architecture, bugs, tech debt, product mismatches |
| `prompts/mobile-audit.md` | Mobile usability: viewport, touch, keyboard, scroll, layout issues |
| `prompts/ui-audit.md` | Product coherence: visual hierarchy, consistency, UX flow, clarity |
| `prompts/deployment-audit.md` | Deployment readiness: build, env vars, secrets, hosting compatibility |

### Agents

| File | Purpose |
|------|---------|
| `agents/bug-fixer.md` | Root-cause debugging and minimal reliable fixes |
| `agents/test-writer.md` | Practical, prioritized test coverage around risky logic |
| `agents/refactor-agent.md` | Safe structural improvements without behavior changes |

### Workflows

| File | Purpose |
|------|---------|
| `workflows/build-feature.md` | Phased feature implementation from idea to code |
| `workflows/fix-bug.md` | Structured bug diagnosis, fix, and regression check |
| `workflows/release.md` | Release readiness evaluation for demos, betas, or launches |

### Standards

| File | Purpose |
|------|---------|
| `standards/code-standards.md` | Code quality, change management, reliability, work habits |
| `standards/ui-ux-standards.md` | UX principles, visual consistency, interaction rules |
| `standards/mobile-standards.md` | Mobile layout, interaction, content, and performance rules |

## Usage Examples

### Example 1: Fix a pinning bug

Combine the bug-fixing agent with the fix-bug workflow, enforcing code and UI standards:

```
Use the following skill files for this task:
- agents/bug-fixer.md
- workflows/fix-bug.md
- standards/code-standards.md
- standards/ui-ux-standards.md

The "pin" button on routines doesn't persist after page refresh...
```

### Example 2: Audit the app on iPhone

Combine mobile and UI audits with their corresponding standards:

```
Use the following skill files for this task:
- prompts/mobile-audit.md
- prompts/ui-audit.md
- standards/mobile-standards.md
- standards/ui-ux-standards.md

Perform a full mobile and UI audit of this project...
```

### Example 3: Prepare for Vercel deployment

Combine the deployment audit with the release workflow:

```
Use the following skill files for this task:
- prompts/deployment-audit.md
- workflows/release.md
- standards/code-standards.md

Evaluate whether this project is ready to deploy on Vercel...
```

### Example 4: Clean up a messy feature area

Combine the refactor agent with a codebase audit to identify and fix structural issues:

```
Use the following skill files for this task:
- agents/refactor-agent.md
- prompts/codebase-audit.md
- standards/code-standards.md

The dashboard component has grown too large. Audit and refactor...
```

### Example 5: Add tests after a bug fix

Use the test writer agent to add regression coverage:

```
Use the following skill files for this task:
- agents/test-writer.md
- standards/code-standards.md

Add regression tests around the pinning logic that was just fixed...
```

### Example 6: Build a new analytics tab

Use the feature workflow with code and UI standards:

```
Use the following skill files for this task:
- workflows/build-feature.md
- standards/code-standards.md
- standards/ui-ux-standards.md
- standards/mobile-standards.md

Add a new "Weekly Summary" tab to the analytics page...
```

## File Design Convention

Each markdown file follows a consistent structure:

```markdown
# Title

## Purpose
## When To Use
## Inputs Expected
## Required Process
## Output Format
## Rules / Constraints
## Common Mistakes To Avoid
```

This makes every file easy to understand, reuse, and update.

## Future Expansion

The structure is designed to grow. Potential additions:

```
claude-skills/
  templates/        # Reusable output formats: PRDs, bug reports, audit report skeletons
  examples/         # Strongest real prompts from past sessions
  project-types/    # Special instructions for React apps, Vercel apps, audio tools, etc.
```

---

## Human Review Checklist

Use this checklist to verify each file meets quality standards before considering it finalized.

### Prompts

- [ ] **codebase-audit.md**
  - [ ] Purpose is clear and specific
  - [ ] Inspection areas cover architecture, data flow, state, auth, tests, and build
  - [ ] Includes product-aware questions (not just technical)
  - [ ] Output format is well-structured with named sections
  - [ ] Execution rules are defined (batching, no code changes, cite paths)
  - [ ] Common mistakes section is relevant and practical

- [ ] **mobile-audit.md**
  - [ ] Purpose is clear and specific
  - [ ] Covers viewport, keyboard, modals, scroll, tap targets, safe areas
  - [ ] Lists specific known failure modes (not just generic categories)
  - [ ] Default device target is defined (iPhone-width, portrait, touch-first)
  - [ ] Output format is well-structured with named sections
  - [ ] Includes implementation fix guidance (CSS, components, breakpoints)

- [ ] **ui-audit.md**
  - [ ] Purpose is clear and specific
  - [ ] Covers visual hierarchy, naming, spacing, navigation, states
  - [ ] Includes product-level questions (page purpose, workflow coherence, clutter)
  - [ ] Distinguishes between "broken" and "could be better"
  - [ ] Output format includes both critique and redesign direction
  - [ ] Evaluates the app as a product, not just as code

- [ ] **deployment-audit.md**
  - [ ] Purpose is clear and specific
  - [ ] Covers build, env vars, secrets, CORS, auth, rate limiting
  - [ ] Includes hosting-specific questions (serverless, SPA routing, cold starts)
  - [ ] Requires a deployment verdict with classification and justification
  - [ ] Output format separates required fixes from nice-to-haves
  - [ ] Addresses common hosting platforms (Vercel, Render, Railway)

### Agents

- [ ] **bug-fixer.md**
  - [ ] Purpose defines the agent's role clearly
  - [ ] Debugging mindset is defined (no guessing, trace data flow)
  - [ ] Execution flow has ordered steps from restate to commit
  - [ ] Emphasizes root cause over symptom masking
  - [ ] Output format includes root cause, fix, verification, and risks
  - [ ] Rules prevent scope creep (no unrelated refactoring)

- [ ] **test-writer.md**
  - [ ] Purpose defines the agent's role clearly
  - [ ] Testing priorities are ordered by risk/value
  - [ ] Includes test type selection guidance (unit, integration, component, e2e)
  - [ ] Anti-patterns are listed (snapshot spam, implementation testing)
  - [ ] Output format covers plan and/or implementation summary
  - [ ] Rules enforce following existing test framework conventions

- [ ] **refactor-agent.md**
  - [ ] Purpose defines the agent's role clearly
  - [ ] Refactor targets are prioritized (duplication, oversized files, mixed concerns)
  - [ ] Requires test verification before and after changes
  - [ ] Enforces incremental batches with frequent commits
  - [ ] Output format confirms behavior was preserved
  - [ ] Rules prevent combining behavior changes with structural changes

### Workflows

- [ ] **build-feature.md**
  - [ ] Purpose defines the workflow clearly
  - [ ] Requires architecture inspection before coding
  - [ ] Implementation is phased (understand, plan, implement, verify)
  - [ ] Emphasizes following existing patterns
  - [ ] Output format includes plan, files changed, risks, and verification
  - [ ] Rules prevent "jamming features in" without understanding context

- [ ] **fix-bug.md**
  - [ ] Purpose defines the workflow clearly
  - [ ] Phases are ordered (define, reproduce, trace, check related, fix, validate)
  - [ ] Prioritizes root cause over symptom masking
  - [ ] Requires checking for similar bugs elsewhere
  - [ ] Output format includes root cause, fix, and remaining risks
  - [ ] Rules enforce minimal targeted fixes

- [ ] **release.md**
  - [ ] Purpose defines the workflow clearly
  - [ ] Distinguishes release types (recruiter demo, beta, internal, public)
  - [ ] Checklist covers features, polish, mobile, tests, env, errors, onboarding
  - [ ] Requires a clear readiness verdict with classification
  - [ ] Output format separates blockers from follow-ups
  - [ ] Standards adjust based on release type

### Standards

- [ ] **code-standards.md**
  - [ ] Rules are concise, stable, and enforceable
  - [ ] Covers code quality, change management, and reliability
  - [ ] Includes work habits (todo lists, batching, frequent commits)
  - [ ] Rules are practical, not aspirational
  - [ ] No task-specific instructions (those belong in prompts/agents/workflows)

- [ ] **ui-ux-standards.md**
  - [ ] Rules are concise, stable, and enforceable
  - [ ] Covers UX principles, visual consistency, and interaction rules
  - [ ] Includes state handling (loading, empty, error states)
  - [ ] Addresses information hierarchy and scanability
  - [ ] Rules about removing broken/non-functional UI elements

- [ ] **mobile-standards.md**
  - [ ] Rules are concise, stable, and enforceable
  - [ ] Covers layout, interaction, content, and performance
  - [ ] Specifies minimum touch target sizes
  - [ ] Addresses keyboard, scroll, and modal behavior on small screens
  - [ ] Includes testing expectations with specific viewport targets

### Overall Structure

- [ ] All files follow the consistent structure: Purpose, When To Use, Inputs, Process, Output, Rules, Mistakes
- [ ] No overlap or duplication between files (each has a clear, distinct job)
- [ ] Standards are short and stable; prompts are rich and specific
- [ ] Agents are behavioral; workflows are procedural
- [ ] Files are composable -- they can be combined without conflicting
- [ ] README accurately describes all files and their purposes
- [ ] Usage examples cover common real-world scenarios
