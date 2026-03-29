# Canonical Vocabulary Enforcer Skill

## Purpose

Ensure consistent naming and definitions across code, documentation, UI, database, algorithms, prompts, and architecture diagrams. Inconsistent naming causes confusion, bugs, and bad architecture. This skill prevents that by establishing and enforcing a single canonical name for every important concept in a project.

## When To Use

- Starting a new project (establish vocabulary early)
- During a codebase audit when naming inconsistencies surface
- Before a major refactor to align terminology first
- When onboarding to an existing project and finding conflicting names
- When the same concept is called different things in different files
- When UI labels don't match code names or database fields
- During code review when naming drift is noticed

## Inputs Expected

- Access to the project repository
- The domain area to audit (entire project, specific feature, database layer, UI layer, etc.)
- Any existing glossary or naming conventions (optional)
- Known naming conflicts or confusion points (optional)

## Required Process

### Step 1: Identify core entities

Scan the project for the fundamental concepts. Look across:

- Code (class names, variable names, function names, type definitions)
- Database (table names, column names, schema comments)
- UI (labels, headings, button text, tooltips, error messages)
- Documentation (README, comments, architecture docs)
- API (endpoint names, request/response field names)
- Tests (describe blocks, test names, fixture names)

### Step 2: Find conflicts and duplicates

Identify where the same concept has multiple names. Common patterns:

- Same concept, different names: "Task" / "Todo" / "Item"
- Same name, different meanings: "Event" meaning a calendar entry in one file and a DOM event in another
- Abbreviation inconsistency: "Layout" / "Grid" / "PadMap"
- Temporal confusion: "Session" / "Routine Run" / "Practice Block"
- Metric confusion: "Score" / "Cost" / "Fitness" / "Weight"
- Structural confusion: "Pattern" / "Sequence" / "Chain"

### Step 3: Define canonical names

For each concept, choose one name. The canonical name should be:

- Clear and self-explanatory
- Consistent with the domain language
- Used identically across code, UI, database, and docs
- Not easily confused with other canonical names

### Step 4: Document naming rules

Create explicit rules: "Use X instead of Y" with reasoning.

### Step 5: Identify refactor targets

List specific files and locations where incorrect naming appears, ordered by impact.

## Output Format

```markdown
# Canonical Vocabulary: [Project Name]

## Canonical Entities

| Term | Definition | Replaces | Used In |
|------|-----------|----------|---------|
| Habit | A daily or weekly tracked behavior | Task, Todo, Action | Code, UI, DB |
| Routine | A sequence of habits performed together | Workflow, Chain, Set | Code, UI |
| Event | A time slice containing one or more notes | NoteGroup, Beat, Step | Code, API |
| Layout | Mapping of sounds to pads | GridMapping, PadMap, Grid | Code, UI |
| Cost Function | Evaluation metric for optimization | Score, Fitness, Weight | Code, Docs |

## Naming Rules

- Use **Habit** everywhere. Remove all references to "Task" and "Todo"
- Use **Layout** for the pad-to-sound mapping. "Grid" refers only to CSS grid layout
- Use **Cost Function** in code and docs. Use "Score" only in user-facing UI where it's more intuitive
- Use **Routine Run** for a single execution of a routine. Never "Session" (too ambiguous)

## Conflicts Found

| Location | Current Name | Should Be | File(s) |
|----------|-------------|-----------|---------|
| Database table | `tasks` | `habits` | schema.sql:12 |
| Component name | `TodoList` | `HabitList` | src/components/TodoList.tsx |
| API endpoint | `/api/items` | `/api/habits` | routes/api.ts:45 |
| UI heading | "My Tasks" | "My Habits" | src/pages/Dashboard.tsx:28 |

## Refactor Priority

1. [Highest impact changes first]
2. [...]
3. [...]
```

## Rules / Constraints

- **Every important concept should have one name only** across the entire project
- Canonical names must be used identically in code, UI, database, and documentation
- When a concept needs a different user-facing name (e.g., "Cost Function" in code, "Score" in UI), document this explicitly as a deliberate exception
- Don't rename things that are genuinely different concepts just because they sound similar
- Prioritize renames by impact: API and database names are harder to change than local variables

## Common Mistakes To Avoid

- Choosing canonical names that are technically precise but confusing to users
- Renaming only in code but not in UI or database
- Creating a vocabulary document that nobody references (integrate it into the project)
- Treating every minor variable name as a canonical entity (focus on domain concepts)
- Renaming across a codebase without first establishing tests to catch breakage
- Choosing abbreviations as canonical names (prefer full, clear terms)

## Relationship To Other Skills

- **Codebase Audit** (`prompts/codebase-audit.md`): The codebase audit checks for naming consistency as one of many inspection areas. This skill goes deeper on vocabulary specifically.
- **Code Standards** (`standards/code-standards.md`): Code standards include general naming conventions. This skill defines project-specific vocabulary that those conventions should follow.
- **Refactor Agent** (`agents/refactor-agent.md`): After this skill identifies naming inconsistencies, the refactor agent can execute the renames safely with test verification.
