# Decision Log Skill

## Purpose

Record important decisions so the reasoning is not lost over time. This prevents re-discussing the same decisions, forgetting why something was designed a certain way, repeating failed ideas, and architecture drift.

A decision that is not written down will be forgotten and re-argued later.

## When To Use

- Choosing between architectures or frameworks
- Choosing algorithms or data structures
- Making performance tradeoffs (speed vs. memory, accuracy vs. simplicity)
- Changing data models or database schemas
- Simplifying scope or cutting features
- Choosing technologies, libraries, or services
- Changing UI structure or navigation patterns
- Any decision that someone (including future you) might question later

## Inputs Expected

- The decision being made
- The problem or context that prompted the decision
- The options that were considered
- The reasoning behind the choice
- Any constraints that influenced the decision

## Required Process

### Step 1: Capture the decision

Write a clear, short title for the decision. This should be scannable in a list.

### Step 2: Document the context

What problem were you trying to solve? What constraints existed? What triggered this decision? This is the most important section -- without context, the decision makes no sense later.

### Step 3: List options considered

Document every option that was seriously considered, even briefly. Include options that were rejected -- knowing what you didn't choose and why is as valuable as knowing what you did choose.

### Step 4: Record the decision and reasoning

What was chosen and why. Be specific about the reasoning. "It felt right" is not sufficient. "It handles our use case of X better because Y" is.

### Step 5: Acknowledge tradeoffs

What are the downsides of this decision? What did you give up? Every decision has costs -- documenting them prevents surprise later.

### Step 6: Define revisit conditions

Under what circumstances should this decision be reconsidered? This prevents both premature re-evaluation and indefinite commitment to outdated choices.

## Output Format

```markdown
# Decision Log: [Project Name]

---

### [Decision Title]

**Date**: [When decided]

**Context**: [What problem prompted this decision]

**Options Considered**:
- **Option A**: [Brief description + pros/cons]
- **Option B**: [Brief description + pros/cons]
- **Option C**: [Brief description + pros/cons]

**Decision**: [What was chosen]

**Reasoning**: [Why this option was selected over others]

**Tradeoffs**: [What downsides were accepted]

**Revisit When**: [Conditions that should trigger reconsideration]

---
```

## Example

```markdown
### Use Simulated Annealing for Layout Optimization

**Date**: 2026-03-15

**Context**: Need to search a large layout space efficiently to find
optimal pad-to-sound mappings. The search space is too large for brute
force and has many local minima.

**Options Considered**:
- **Beam Search**: Fast, deterministic, but easily trapped in local minima
- **Simulated Annealing**: Handles large spaces and escapes local minima,
  tunable temperature schedule
- **Genetic Algorithm**: Good for exploration but adds complexity with
  crossover/mutation operators and population management

**Decision**: Simulated Annealing

**Reasoning**: Best balance of exploration vs. exploitation for our
search space size. The temperature schedule gives direct control over
the exploration/exploitation tradeoff. Simpler to implement and tune
than GA. Our cost function is smooth enough that SA's neighborhood
search works well.

**Tradeoffs**: Not guaranteed optimal. Results vary between runs.
Requires tuning the temperature schedule and neighborhood function.

**Revisit When**: If the layout space becomes highly constrained (small
enough for exact search) or if we need deterministic results.
```

## Rules / Constraints

- **Write decisions down when they're made**, not later when memory has faded
- Context is the most important section -- a decision without context is useless
- Always document rejected options and why they were rejected
- Be honest about tradeoffs -- every decision has costs
- Keep entries scannable -- decision titles should be clear enough to find later
- The log is append-only in spirit -- don't delete old decisions, mark them superseded

## Common Mistakes To Avoid

- Recording the decision without the reasoning ("We chose X" but not why)
- Omitting rejected options (knowing what you didn't choose is valuable)
- Writing context that's too vague to be useful later ("We needed a better approach")
- Forgetting to define revisit conditions (decisions become permanent by inertia)
- Making the log so formal that people don't bother using it
- Recording trivial decisions that don't warrant documentation (focus on architectural and strategic choices)

## Relationship To Other Skills

- **Codebase Audit** (`prompts/codebase-audit.md`): Audits may uncover undocumented architectural decisions. The decision log captures those decisions going forward.
- **Weekly Project Reset** (`skills/weekly-project-reset.md`): The reset process can reference the decision log to remember why things were built a certain way.
- **Build Feature Workflow** (`workflows/build-feature.md`): Feature implementation often involves decisions about architecture, patterns, and scope. Log significant decisions during the process.
