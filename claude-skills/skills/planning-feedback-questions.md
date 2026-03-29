# Planning Feedback Questions Skill

## Purpose

When entering planning mode or brainstorming mode, formulate insightful multiple-choice questions to understand the user's preferences, constraints, and priorities before proposing solutions. This prevents wasted effort from assumptions, surfaces hidden requirements early, and produces plans that genuinely reflect what the user wants.

## When To Use

- The user enters plan mode or explicitly asks to plan/brainstorm
- The user describes a new feature, project, or significant change without clear requirements
- The user asks "how should we..." or "what's the best way to..."
- Any open-ended task where multiple valid approaches exist

## Required Process

### Step 1: Analyze the request

Read the user's request carefully. Identify areas of ambiguity, unstated preferences, and decision points where reasonable people would disagree.

### Step 2: Formulate 5-15 multiple-choice questions

Generate between 5 and 15 questions depending on the complexity of the task. Each question must:

- Target a **specific decision point** that affects the plan (not trivia or obvious choices)
- Offer **3-5 concrete answer options** labeled A, B, C, D, E
- Include a brief parenthetical clarification for each option so the user understands the tradeoff
- Cover a **mix of categories**: scope, priorities, constraints, style, risk tolerance, timeline, and technical preferences
- Be **ordered from most impactful to least impactful** — the first few questions should address choices that change the overall direction

### Step 3: Present the questions clearly

Format the questions as a numbered list. Group related questions under short headings if there are more than 8. Allow the user to answer with just the letters (e.g., "1A, 2C, 3B...") for speed.

### Step 4: Incorporate answers into the plan

After receiving answers, explicitly map each answer to a planning decision. Then produce the plan reflecting those preferences. Do not silently ignore any answer.

## Question Design Guidelines

**Good questions probe:**
- Scope (minimal vs. comprehensive)
- Priority ordering (speed vs. quality vs. flexibility)
- Risk tolerance (proven vs. experimental approaches)
- Style preferences (verbose vs. concise, simple vs. abstracted)
- Maintenance expectations (one-off vs. long-lived)
- User experience preferences (when applicable)
- Technical constraints the user may not have mentioned

**Avoid questions that:**
- Have an obviously correct answer
- Are too abstract to act on ("How important is quality to you?")
- Duplicate information the user already provided
- Require deep domain expertise the user may not have

## Example

> **User:** I want to add authentication to my app.

**Preference Questions:**

1. **Scope** — How much of the auth surface do you want to cover right now?
   - A) Just login/logout with email and password
   - B) Email/password plus OAuth (Google, GitHub, etc.)
   - C) Full suite: email, OAuth, MFA, password reset, email verification
   - D) SSO/enterprise auth (SAML, OIDC)

2. **Implementation approach** — How do you want to handle the auth logic?
   - A) Managed service (Auth0, Clerk, Supabase Auth — minimal custom code)
   - B) Framework library (NextAuth, Passport.js — more control, some setup)
   - C) Roll my own (custom JWT/session logic — full control, more work)

3. **Session strategy** — How should sessions work?
   - A) Stateless JWTs (simple, no server-side storage)
   - B) Server-side sessions with a session store (more secure, more infra)
   - C) No preference — pick what fits best

*(and so on, up to 15 questions depending on complexity)*
