# Portfolio Framing Skill

## Purpose

Transform technical projects into clear, impressive, recruiter-friendly portfolio pieces. This skill reframes work from "what I built" into "why it was hard, what was interesting, and why it matters."

It produces:

- Portfolio descriptions
- Resume bullet points
- Project READMEs
- Case studies
- Demo talking points
- YouTube/video scripts (technical storytelling)

## When To Use

- Finishing a project and preparing to present it
- Writing or updating a project README
- Preparing for job applications or interviews
- Building a portfolio website
- Creating a demo video or walkthrough
- Explaining a project to non-technical audiences
- Creating a project summary or slide deck

## Inputs Expected

Gather the following about the project:

- **Project name**
- **Problem it solves** and why the problem is hard
- **Technical approach**: algorithms, architecture, key optimizations
- **Metrics / results**: performance numbers, before/after comparisons, user impact
- **Visuals or demos** available
- **What makes this project unique** compared to typical solutions
- **What you learned** through the process

## Required Process

### Step 1: Identify the framing angles

Look for and emphasize whichever of these apply:

- Performance optimization (speed, memory, efficiency)
- Algorithm design (novel approaches, interesting tradeoffs)
- System architecture (how components fit together)
- Real-world constraints (what made the problem harder than it looks)
- Tradeoffs and decisions (what was sacrificed and why)
- Interesting technical challenges (what kept you stuck, what was surprising)
- Novel UI/UX ideas (interaction design that's distinctive)
- ML/AI integration (how models are used in practice)
- Mathematical modeling (formulations, simulations, optimization)
- Creative + technical blend (projects that are both artistic and engineered)

### Step 2: Write the one-sentence summary

A clear, impressive one-liner that captures what was built and why it matters.

Example:
> Built a Monte Carlo Tree Search engine for a 4-player strategy game and designed new heuristics to handle multi-agent board control and territory prediction.

### Step 3: Write the project story

Follow the structure: **Problem -> Challenge -> Solution -> Result**

Keep it concise. The story should make someone want to ask follow-up questions.

### Step 4: Extract technical highlights

Bullet list of the most impressive technical components. Focus on:
- What was hard
- What was novel
- What demonstrates skill

### Step 5: Write resume bullet points

Format: **Action verb + technical work + impact/result**

Each bullet should be independently impressive. Avoid vague verbs ("worked on," "helped with").

### Step 6: Write the recruiter explanation

A simple explanation that a non-technical recruiter can understand. No jargon. Focus on the problem and the result.

### Step 7: Write the demo script (if applicable)

What to show, in what order, and what to say at each point.

## Output Format

```markdown
# Portfolio Framing: [Project Name]

## One-Sentence Summary
[Clear, impressive one-liner]

## Project Story
**Problem**: [What needed solving]
**Challenge**: [Why it was hard]
**Solution**: [What you built and how]
**Result**: [What it achieved]

## Technical Highlights
- [Impressive technical component 1]
- [Impressive technical component 2]
- [...]

## Resume Bullet Points
- [Action verb + technical work + impact]
- [Action verb + technical work + impact]
- [...]

## Recruiter Explanation
[Simple, non-technical explanation]

## Demo Script (Optional)
1. [What to show first + what to say]
2. [What to show next + what to say]
3. [...]
```

## Rules / Constraints

- **Never just describe features.** Always explain why it was hard, why it was interesting, and why it matters.
- Lead with the most impressive aspect, not the most obvious one
- Quantify results when possible (percentages, times, comparisons)
- Each resume bullet should stand alone -- don't rely on context from other bullets
- The recruiter explanation should make sense to someone who doesn't code
- Demo scripts should highlight the "wow moment" early

## Common Mistakes To Avoid

- Listing technologies used instead of explaining what was built
- Describing features without explaining the underlying challenge
- Writing resume bullets that sound like task descriptions ("Implemented user login")
- Burying the most impressive work in the middle of a long description
- Using jargon in the recruiter explanation
- Making the demo script a walkthrough of every feature instead of a focused story

## Relationship To Other Skills

- **Creative Orchestrator** (`agents/creative/creative-orchestrator.md`): The orchestrator can identify portfolio value during concept development. This skill takes finished work and frames it for presentation.
- **Visual Art Direction** (`agents/creative/visual-art-direction-agent.md`): Can help ensure the project looks polished and memorable for portfolio presentation.
- **Release Workflow** (`workflows/release.md`): The release workflow evaluates readiness for "recruiter demo" releases. This skill handles the storytelling and framing around that release.
