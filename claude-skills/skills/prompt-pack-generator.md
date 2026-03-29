# Prompt Pack Generator Skill

## Purpose

Generate high-quality, implementation-ready prompts for multiple coding agents for the same task. Different AI agents respond better to different prompt styles. This skill rewrites the same task optimized for each target agent.

It produces prompts for:

- Claude Code
- Codex / GPT
- Gemini
- Cursor
- General LLM

## When To Use

- Starting a task you want to run across multiple AI tools
- Comparing how different agents handle the same work
- Delegating a task to a specific AI tool and wanting an optimized prompt
- Preparing a prompt library for repeated task types
- When you want the highest quality output from a specific agent

## Inputs Expected

- **Task description**: What needs to be done
- **Codebase context**: Project structure, framework, language, relevant patterns
- **Files involved**: Which files to read, modify, or create
- **Constraints**: What must be preserved, what must be avoided
- **Definition of done**: What success looks like, specifically
- **What to avoid**: Known pitfalls, anti-patterns, or previous failed approaches

## Required Process

### Step 1: Understand the task fully

Before generating any prompts, clarify:

- What is the actual goal (not just the surface request)?
- What context does an agent need to do this well?
- What are the likely failure modes for each agent?
- What testing or verification should the agent perform?

### Step 2: Generate agent-specific prompts

For each target agent, write a complete prompt that includes:

1. **Objective**: Clear statement of what to accomplish
2. **Context**: Project background, architecture, relevant patterns
3. **Relevant files**: Specific paths to read and modify
4. **Instructions**: Step-by-step plan with decision points
5. **Constraints**: What to preserve, what to avoid, boundaries
6. **Edge cases**: Known tricky scenarios to handle
7. **Testing**: How to verify the work is correct
8. **Deliverables**: Exactly what output is expected (code changes, commits, summaries)

### Step 3: Adapt style for each agent

Each agent has different strengths and prompt preferences:

- **Claude Code**: Responds well to structured instructions with explicit constraints, todo lists, and phased work. Include file paths, testing expectations, and commit instructions.
- **Codex / GPT**: Prefers clear, direct instructions with examples. Benefits from explicit code blocks showing expected patterns. Include type signatures and function contracts.
- **Gemini**: Works well with high-level context followed by specific instructions. Benefits from explicit reasoning about tradeoffs and architecture.
- **Cursor**: Optimized for file-scoped changes. Reference specific line ranges. Include clear before/after descriptions. Benefits from inline code context.
- **General LLM**: Most portable format. Provide full context inline (don't assume file access). Include code snippets directly in the prompt.

## Output Format

```markdown
# Prompt Pack: [Task Name]

## Task Summary
[One-paragraph description of what needs to be done]

---

## Claude Code Prompt
[Full prompt optimized for Claude Code]

---

## Codex / GPT Prompt
[Full prompt optimized for Codex/GPT]

---

## Gemini Prompt
[Full prompt optimized for Gemini]

---

## Cursor Prompt
[Full prompt optimized for Cursor]

---

## General LLM Prompt
[Full prompt in portable format]
```

## Rules / Constraints

- **Prompts must be implementation-ready, not vague.** Each prompt should contain enough information for the agent to start working immediately without asking clarifying questions.
- Every prompt must include: objective, context, files, instructions, constraints, testing, and deliverables
- Adapt the tone and structure to each agent's strengths
- Include concrete file paths, not "the relevant files"
- Include concrete success criteria, not "make sure it works"
- Each prompt should be self-contained -- don't require reading other prompts in the pack

## Common Mistakes To Avoid

- Writing the same generic prompt for all agents (defeats the purpose)
- Being vague about which files to modify or how to test
- Omitting constraints and letting the agent make its own assumptions
- Forgetting to include commit/deliverable instructions
- Writing prompts that describe the problem but not the expected solution approach
- Including unnecessary context that dilutes the core instructions
