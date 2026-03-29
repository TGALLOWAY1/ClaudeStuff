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
  prompts/              # Specialized analysis instructions (task-specific)
  agents/               # Reusable role definitions (behavioral)
    creative/           # Creative lab: multidisciplinary creative agents
  workflows/            # Step-by-step execution patterns (procedural)
  standards/            # Non-negotiable quality rules (always in effect)
  skills/               # Standalone utilities for recurring non-code tasks
```

### How the layers work together

| Layer         | What it defines                | Characteristics                    |
|---------------|-------------------------------|------------------------------------|
| **Standards** | Global quality rules          | Short, stable, always enforced     |
| **Prompts**   | Task-specific analysis        | Rich, specific, deep inspection    |
| **Agents**    | Role-based behavior           | Behavioral, disciplined, focused   |
| **Workflows** | Execution sequences           | Procedural, ordered, repeatable    |
| **Skills**    | Standalone utility processes  | Focused, repeatable, output-driven |

**Standards** are always in effect. **Prompts** tell Claude how to think for a given task. **Agents** tell Claude how to behave in a given role. **Workflows** tell Claude what sequence of steps to follow. **Skills** are standalone processes for recurring non-code tasks like framing portfolio pieces, resetting project context, or enforcing naming consistency.

## Files

### Prompts

| File | Purpose |
|------|---------|
| `prompts/codebase-audit.md` | Deep repo inspection: architecture, bugs, tech debt, product mismatches |
| `prompts/mobile-audit.md` | Mobile usability: viewport, touch, keyboard, scroll, layout issues |
| `prompts/ui-audit.md` | Product coherence: visual hierarchy, consistency, UX flow, clarity |
| `prompts/deployment-audit.md` | Deployment readiness: build, env vars, secrets, hosting compatibility |

### Agents (Engineering)

| File | Purpose |
|------|---------|
| `agents/bug-fixer.md` | Root-cause debugging and minimal reliable fixes |
| `agents/test-writer.md` | Practical, prioritized test coverage around risky logic |
| `agents/refactor-agent.md` | Safe structural improvements without behavior changes |

### Agents (Creative Lab)

The creative lab is a team of specialized agents that work together as a multidisciplinary creative studio. They're designed for projects at the intersection of music, math, visuals, animation, and interactive tools.

| File | Role | Purpose |
|------|------|---------|
| `agents/creative/creative-orchestrator.md` | Director | Takes vague ideas and turns them into structured multidisciplinary concepts |
| `agents/creative/cross-domain-translator.md` | Translator | Maps one creative medium into another (music to visuals, math to motion) |
| `agents/creative/music-systems-agent.md` | Specialist | Music as a system: composition, sound design, performance, musical UX |
| `agents/creative/visual-art-direction-agent.md` | Specialist | Visual identity, composition, mood, aesthetic coherence |
| `agents/creative/math-structures-agent.md` | Specialist | Mathematical beauty into intuitions, visuals, dynamics, and interactions |
| `agents/creative/animation-motion-agent.md` | Specialist | Motion as meaning: rhythm, transformation, pacing, synchronization |
| `agents/creative/creative-tool-builder-agent.md` | Productizer | Turns creative concepts into usable software with clear scope |

**How the creative lab works:**

```
Stage 1 -- Orchestrator frames the idea
    |
Stage 2 -- Specialists deepen their domains
    |       (music, math, visuals, motion, tools)
    |       Cross-domain translator bridges between them
    |
Stage 3 -- Orchestrator reunifies into concept + scope + plan
```

The orchestrator coordinates. The specialists provide depth. The translator finds the connections between disciplines. The tool builder turns concepts into buildable products.

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

### Skills

Skills are standalone utility processes for recurring non-code tasks. Unlike agents (which define behavior) or workflows (which define execution sequences), skills are focused tools that produce a specific type of output.

| File | Purpose |
|------|---------|
| `skills/portfolio-framing.md` | Transform projects into recruiter-friendly portfolio pieces, resume bullets, and demo scripts |
| `skills/weekly-project-reset.md` | Re-enter a project quickly with a clear snapshot of state, priorities, and next steps |
| `skills/canonical-vocabulary-enforcer.md` | Establish and enforce consistent naming across code, UI, database, and docs |
| `skills/prompt-pack-generator.md` | Generate optimized prompts for the same task across multiple AI agents |
| `skills/decision-log.md` | Record architectural and technical decisions with context, reasoning, and tradeoffs |

## Usage Examples

### Engineering Examples

#### Example 1: Fix a pinning bug

```
Use the following skill files for this task:
- agents/bug-fixer.md
- workflows/fix-bug.md
- standards/code-standards.md
- standards/ui-ux-standards.md

The "pin" button on routines doesn't persist after page refresh...
```

#### Example 2: Audit the app on iPhone

```
Use the following skill files for this task:
- prompts/mobile-audit.md
- prompts/ui-audit.md
- standards/mobile-standards.md
- standards/ui-ux-standards.md

Perform a full mobile and UI audit of this project...
```

#### Example 3: Prepare for Vercel deployment

```
Use the following skill files for this task:
- prompts/deployment-audit.md
- workflows/release.md
- standards/code-standards.md

Evaluate whether this project is ready to deploy on Vercel...
```

#### Example 4: Clean up a messy feature area

```
Use the following skill files for this task:
- agents/refactor-agent.md
- prompts/codebase-audit.md
- standards/code-standards.md

The dashboard component has grown too large. Audit and refactor...
```

#### Example 5: Add tests after a bug fix

```
Use the following skill files for this task:
- agents/test-writer.md
- standards/code-standards.md

Add regression tests around the pinning logic that was just fixed...
```

#### Example 6: Build a new analytics tab

```
Use the following skill files for this task:
- workflows/build-feature.md
- standards/code-standards.md
- standards/ui-ux-standards.md
- standards/mobile-standards.md

Add a new "Weekly Summary" tab to the analytics page...
```

### Creative Lab Examples

#### Example 7: Turn an abstract idea into a project concept

```
Use the following skill files for this task:
- agents/creative/creative-orchestrator.md

I want to build something that blends harmonic motion with differential
geometry into a visual interactive piece...
```

#### Example 8: Design a music + math interactive project

Full creative pipeline with orchestrator coordinating specialists:

```
Use the following skill files for this task:
- agents/creative/creative-orchestrator.md
- agents/creative/math-structures-agent.md
- agents/creative/music-systems-agent.md
- agents/creative/animation-motion-agent.md
- agents/creative/visual-art-direction-agent.md
- agents/creative/creative-tool-builder-agent.md

I want to build a visual interactive project based on harmonic motion
and differential geometry. The math should drive the visuals, music
should influence the geometry, and the whole thing should be explorable...
```

#### Example 9: Translate music into animation

```
Use the following skill files for this task:
- agents/creative/cross-domain-translator.md
- agents/creative/music-systems-agent.md
- agents/creative/animation-motion-agent.md

Map a chord progression with rising tension into a particle animation
system. The visual should feel like the music sounds...
```

#### Example 10: Design a music-learning tool

```
Use the following skill files for this task:
- agents/creative/creative-tool-builder-agent.md
- agents/creative/music-systems-agent.md
- standards/ui-ux-standards.md
- standards/mobile-standards.md

Design a practice mode for learning chord progressions by ear.
It should work on mobile and feel musical, not academic...
```

#### Example 11: Art direct a portfolio piece

```
Use the following skill files for this task:
- agents/creative/visual-art-direction-agent.md
- agents/creative/creative-orchestrator.md

I have a working generative math visualization but it looks generic.
Help me develop a distinctive visual identity that would be
memorable in a portfolio...
```

#### Example 12: Build a creative tool from a math concept

```
Use the following skill files for this task:
- agents/creative/math-structures-agent.md
- agents/creative/creative-tool-builder-agent.md
- agents/creative/visual-art-direction-agent.md

Turn Fourier transforms into an interactive toy where people can
draw shapes and see them decompose into frequencies...
```

### Skill Examples

#### Example 13: Frame a project for your portfolio

```
Use the following skill files for this task:
- skills/portfolio-framing.md

I just finished my MCTS game engine project. Help me frame it
for my portfolio, resume, and recruiter conversations...
```

#### Example 14: Re-enter a project after time away

```
Use the following skill files for this task:
- skills/weekly-project-reset.md

I haven't worked on this project in two weeks. Give me a reset:
where things stand, what's broken, and what I should work on next...
```

#### Example 15: Fix naming chaos across a project

```
Use the following skill files for this task:
- skills/canonical-vocabulary-enforcer.md
- agents/refactor-agent.md

The same concept is called "Task", "Todo", and "Item" in different
parts of the codebase. Audit the naming and create a canonical
vocabulary, then refactor to enforce it...
```

#### Example 16: Generate prompts for multiple AI tools

```
Use the following skill files for this task:
- skills/prompt-pack-generator.md

I need to refactor the dashboard component. Generate optimized
prompts for Claude Code, Cursor, and GPT so I can compare
how each handles it...
```

#### Example 17: Log a technical decision

```
Use the following skill files for this task:
- skills/decision-log.md

We just decided to use Simulated Annealing instead of Genetic
Algorithms for layout optimization. Document this decision with
full context, reasoning, and tradeoffs...
```

## File Design Conventions

### Engineering agents, prompts, workflows, and standards

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

### Creative agents

```markdown
# Agent Name

## Purpose
## Best Use Cases
## Core Perspective
## Priorities
## Inputs It Expects
## Required Process
## Output Format
## Anti-Patterns To Avoid
## Relationship To Other Agents
```

The creative agents include a "Relationship To Other Agents" section because they're designed to work as a coordinated team, not in isolation.

### Skills

```markdown
# Skill Name

## Purpose
## When To Use
## Inputs Expected
## Required Process
## Output Format
## Rules / Constraints
## Common Mistakes To Avoid
## Relationship To Other Skills
```

Skills follow the same structure as engineering files but add a "Relationship To Other Skills" section to show how they connect to existing prompts, agents, and workflows.

## Future Expansion

The structure is designed to grow. Potential additions:

```
claude-skills/
  templates/            # Reusable output formats: PRDs, bug reports, audit report skeletons
  examples/             # Strongest real prompts from past sessions
  project-types/        # Special instructions for React apps, Vercel apps, audio tools, etc.
  agents/creative/
    sound-design-agent.md
    generative-art-agent.md
    curriculum-designer-agent.md
    portfolio-story-agent.md
    scientific-visualization-agent.md
  skills/
    code-review-checklist.md
    prd-generator.md
    retrospective.md
    dependency-audit.md
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

### Engineering Agents

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

### Creative Lab Agents

- [ ] **creative-orchestrator.md**
  - [ ] Purpose clearly defines the orchestrator as the central coordinator
  - [ ] Core perspective covers creative director, systems designer, project scoper, translator
  - [ ] Process moves from framing to discipline mapping to synthesis
  - [ ] Output format includes concept, emotional goal, disciplines, scope options, next steps
  - [ ] Explains when and how to route to specialist agents
  - [ ] Anti-patterns prevent feature-list thinking over concept thinking

- [ ] **cross-domain-translator.md**
  - [ ] Purpose clearly defines structural translation between creative domains
  - [ ] Core perspective emphasizes structural correspondence over arbitrary mapping
  - [ ] Process includes identifying source structure, finding correspondences, defining rules
  - [ ] Output format includes mapping table, translation rules, and aesthetic quality check
  - [ ] Acknowledges where metaphors break down
  - [ ] Anti-patterns prevent arbitrary color-to-note style mappings

- [ ] **music-systems-agent.md**
  - [ ] Purpose defines music-as-system thinking (not just music theory)
  - [ ] Core perspective balances musicality with systems thinking
  - [ ] Priorities list musicality, tension/release, phrase shape, groove, performability
  - [ ] Covers harmony, melody, rhythm, timbre, dynamics, structure, and performance
  - [ ] Anti-patterns prevent over-theoretical but emotionally flat outputs
  - [ ] Addresses hand/finger ergonomics for performance interfaces

- [ ] **visual-art-direction-agent.md**
  - [ ] Purpose defines taste and composition, not just visual design
  - [ ] Distinguishes between functional UI, portfolio UI, brand visuals, and generative systems
  - [ ] Covers mood, composition, color logic, typography, texture, and visual metaphor
  - [ ] Priorities emphasize hierarchy, coherence, restraint, emotion, and distinction
  - [ ] Anti-patterns prevent generic aesthetics and decoration without hierarchy
  - [ ] Assessment adjusts based on context (product vs. portfolio vs. art)

- [ ] **math-structures-agent.md**
  - [ ] Purpose defines math as beauty/structure/dynamics, not academic subject
  - [ ] Core perspective moves from symbolic form toward intuition, visuals, dynamics
  - [ ] Process covers mathematical core, intuition, visual metaphor, dynamic behavior, parameters
  - [ ] Output format includes beauty/surprise and interaction opportunities
  - [ ] Priorities emphasize intuition over formalism and visual thinking
  - [ ] Anti-patterns prevent purely symbolic explanations and visually arbitrary animations

- [ ] **animation-motion-agent.md**
  - [ ] Purpose defines motion as meaning, not just movement
  - [ ] Core perspective covers rhythm, energy, momentum, emergence, legibility
  - [ ] Process includes choreography with phases, hero moments, and synchronization
  - [ ] Priorities emphasize purpose, rhythm, continuity, and restraint
  - [ ] Addresses music-synced motion and math-driven animation specifically
  - [ ] Anti-patterns prevent purposeless motion and visual fatigue

- [ ] **creative-tool-builder-agent.md**
  - [ ] Purpose defines productizing creative concepts into usable software
  - [ ] Core perspective addresses the depth-vs-usability tension directly
  - [ ] Process includes core experience, interaction model, feature architecture, V1 scoping
  - [ ] Progressive complexity is defined (immediate, discovery, mastery)
  - [ ] Output format includes magic moment and scope decisions (must/should/cut)
  - [ ] Anti-patterns prevent feature bloat and power-user-only interfaces

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

### Skills

- [ ] **portfolio-framing.md**
  - [ ] Purpose clearly defines transforming projects into portfolio pieces
  - [ ] Framing angles cover performance, algorithms, architecture, tradeoffs, creative+technical blend
  - [ ] Output format includes one-liner, story, technical highlights, resume bullets, recruiter explanation
  - [ ] Key rule enforced: explain why it was hard, interesting, and matters -- not just features
  - [ ] Demo script section addresses what to show and what to say
  - [ ] Relationship to other skills documented (orchestrator, visual art direction, release workflow)

- [ ] **weekly-project-reset.md**
  - [ ] Purpose clearly defines quick re-entry after time away
  - [ ] Process covers project summary, current state, architecture, next tasks, backlog, risks
  - [ ] Next tasks limited to exactly 3 (forces prioritization)
  - [ ] Backlog section exists to acknowledge deferred ideas without acting on them
  - [ ] Definition of progress is specific and outcome-based, not effort-based
  - [ ] Output is lightweight snapshot, not comprehensive project plan

- [ ] **canonical-vocabulary-enforcer.md**
  - [ ] Purpose clearly defines single canonical names across code, UI, database, and docs
  - [ ] Process covers entity identification, conflict detection, canonical naming, and refactor targets
  - [ ] Output includes canonical entities table with definitions and replacement terms
  - [ ] Naming rules are explicit ("Use X instead of Y")
  - [ ] Addresses the code-vs-UI naming exception (when user-facing names differ deliberately)
  - [ ] Relationship to refactor agent documented for executing renames

- [ ] **prompt-pack-generator.md**
  - [ ] Purpose clearly defines generating agent-specific prompts for the same task
  - [ ] Covers all 5 target agents (Claude Code, Codex/GPT, Gemini, Cursor, General LLM)
  - [ ] Each prompt includes: objective, context, files, instructions, constraints, testing, deliverables
  - [ ] Agent-specific adaptations are documented (different styles for different tools)
  - [ ] Key rule enforced: prompts must be implementation-ready, not vague
  - [ ] Each generated prompt is self-contained

- [ ] **decision-log.md**
  - [ ] Purpose clearly defines recording decisions with reasoning
  - [ ] Format includes: decision, date, context, options, reasoning, tradeoffs, revisit conditions
  - [ ] Includes a concrete example (Simulated Annealing)
  - [ ] Emphasizes context as the most important section
  - [ ] Requires documenting rejected options and why
  - [ ] Defines revisit conditions to prevent both premature re-evaluation and permanent commitment

### Overall Structure

- [ ] All engineering files follow: Purpose, When To Use, Inputs, Process, Output, Rules, Mistakes
- [ ] All creative files follow: Purpose, Best Use Cases, Core Perspective, Priorities, Inputs, Process, Output, Anti-Patterns, Relationships
- [ ] All skill files follow: Purpose, When To Use, Inputs, Process, Output, Rules, Mistakes, Relationships
- [ ] No overlap or duplication between files (each has a clear, distinct job)
- [ ] Standards are short and stable; prompts are rich and specific
- [ ] Engineering agents are behavioral; workflows are procedural
- [ ] Creative agents define taste and constraints, not just generic helpfulness
- [ ] Creative agents have explicit cross-references to each other
- [ ] The orchestrator clearly coordinates the creative pipeline
- [ ] Skills are standalone utilities with clear output formats and cross-references
- [ ] Files are composable -- they can be combined without conflicting
- [ ] README accurately describes all files and their purposes
- [ ] Usage examples cover engineering, creative, and skill scenarios
