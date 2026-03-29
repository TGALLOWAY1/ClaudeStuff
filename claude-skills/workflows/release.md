# Release Workflow

## Purpose

Prepare a project for sharing, demoing, beta testing, or launch. This workflow covers feature completeness, visual polish, mobile compatibility, deployment config, and all the small things that make the difference between "it works locally" and "it's ready for others to use."

## When To Use

- Preparing a demoable V1 for stakeholders
- Deciding if a project is ready for Vercel / hosting deployment
- Packaging something for recruiters or portfolio review
- Preparing for friends/family or private beta testing
- Any time you need a clear go/no-go assessment

## Inputs Expected

- The project to evaluate
- Release type: recruiter demo, private beta, internal development, or public release
- Target hosting platform (e.g., Vercel, Render, Railway)
- Any specific concerns or known issues (optional)

## Required Process

### Phase 1: Determine release type

Different releases have different standards:

- **Recruiter demo**: Must look polished, core flows must work, edge cases can be rough
- **Private beta**: Core features must be reliable, known limitations should be documented
- **Internal development**: Functional but rough edges are acceptable
- **Public release**: Full polish, error handling, monitoring, onboarding clarity

### Phase 2: Run the release checklist

Evaluate each area:

- [ ] **Feature completeness**: Are the planned features working end-to-end?
- [ ] **Visual polish**: Do pages look intentional and consistent?
- [ ] **Mobile compatibility**: Does the app work on phone-sized screens?
- [ ] **Test status**: Do existing tests pass?
- [ ] **Environment variables**: Are all required env vars documented and set?
- [ ] **Deployment config**: Does the build succeed for the target platform?
- [ ] **Analytics / logging**: Is basic error tracking in place?
- [ ] **Empty states**: Do pages handle "no data" gracefully?
- [ ] **Error states**: Do failures show useful messages, not blank screens?
- [ ] **Onboarding clarity**: Can a new user understand what to do?
- [ ] **Data integrity**: Is data saved and loaded correctly?
- [ ] **Performance**: Are there any obvious performance problems?

### Phase 3: Classify readiness

Provide a clear verdict:

- **Not ready**: Critical issues prevent sharing
- **Ready with caveats**: Works but has documented limitations
- **Ready**: Meets the standard for the target release type

### Phase 4: Document what remains

## Output Format

```markdown
# Release Readiness Review

## 1. Release Type
[Which type of release this was evaluated for]

## 2. What Is Ready
[Features and areas that meet the bar]

## 3. What Is Blocking Release
[Critical issues that must be fixed first]

## 4. Risks After Release
[Things that might cause problems for users]

## 5. Required Fixes
[Specific changes needed before release, ordered by priority]

## 6. Recommended Follow-Ups
[Nice-to-haves that can come after release]
```

## Rules / Constraints

- Always specify the release type being evaluated
- Adjust the quality bar to match the release type
- Separate "must fix" from "nice to have" clearly
- Test on mobile if the app is user-facing
- Verify the build works on the target hosting platform

## Common Mistakes To Avoid

- Applying production-level standards to a recruiter demo
- Declaring "ready" without actually testing the core flows
- Ignoring mobile when the app will be accessed on phones
- Not checking environment variables and deployment config
- Skipping empty states and error states in the review
