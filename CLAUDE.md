# CLAUDE.md

## Skills

- **Planning Feedback Questions** — See `claude-skills/skills/planning-feedback-questions.md`
- **Feature Inventory** — See `claude-skills/skills/feature-inventory.md`
- **Decision Log** — See `claude-skills/skills/decision-log.md`

## Requirements

### Planning & Brainstorming Mode

When entering planning mode, brainstorming mode, or any open-ended design discussion, Claude **must** formulate **5-15 insightful multiple-choice questions** before proposing a plan or solution. This is mandatory — do not skip straight to a plan.

**Rules:**
1. Present the questions **first**, before any plan or implementation details.
2. Each question must offer 3-5 concrete options with brief clarifications of tradeoffs.
3. Scale the number of questions to the complexity of the task (5 for simple, up to 15 for complex).
4. Order questions from most impactful to least impactful.
5. Allow the user to respond with just letters (e.g., "1A, 2C, 3B") for speed.
6. After receiving answers, explicitly incorporate every answer into the resulting plan.
7. Cover a mix of: scope, priorities, constraints, style preferences, risk tolerance, timeline, and technical choices.

**Full skill definition:** `claude-skills/skills/planning-feedback-questions.md`

### Feature Inventory

Claude **must** maintain a living feature inventory in `docs/FEATURE-INVENTORY.md`. This is mandatory and applies to every code change.

**Rules:**
1. After **adding** a feature, append a new entry to the inventory in the same commit.
2. After **modifying** a feature's behavior or scope, update its entry in the same commit.
3. After **removing or deprecating** a feature, move its entry to the "Removed / Deprecated" section with a date and reason, in the same commit.
4. If the inventory file does not exist, create it before recording the first entry.
5. Each entry must include: feature name, one-line description, status, key file paths, and date.
6. Organize entries into logical categories that match the project's domain.
7. The inventory is the **source of truth** for what the project can do — keep it accurate.

**Full skill definition:** `claude-skills/skills/feature-inventory.md`

### Decision Log

Claude **must** maintain a decision log in `docs/DECISION-LOG.md`. Every significant architectural, technical, or scope decision made during development must be recorded.

**Rules:**
1. Record decisions **when they are made**, not after the fact — in the same commit as the related code change.
2. Each entry must include: title, date, context, options considered, decision, reasoning, tradeoffs, and revisit conditions.
3. Always document **rejected alternatives** and why they were rejected.
4. The log is append-only — never delete old decisions; mark them as superseded if a later decision overrides them.
5. If the decision log file does not exist, create it before recording the first entry.
6. Focus on architectural and strategic choices — do not log trivial decisions.
7. Context is the most important field — a decision without context is useless to future readers.

**Full skill definition:** `claude-skills/skills/decision-log.md`
