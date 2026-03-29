# CLAUDE.md

## Skills

- **Planning Feedback Questions** — See `claude-skills/skills/planning-feedback-questions.md`

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
