# Deployment Audit

## Purpose

Determine whether a project is actually ready to be deployed and used reliably. This is not just "does it build?" It covers: can this run in production, is it safe enough, will users hit obvious failures, and are environment and backend assumptions valid.

## When To Use

- Before deploying to Vercel, Render, Railway, or similar hosting
- Before sharing a private beta with testers
- Before sharing a recruiter demo publicly
- After significant architecture changes that affect hosting

## Inputs Expected

- Access to the full repository
- Target hosting platform (e.g., Vercel, Render, Railway)
- Whether this is a frontend-only, fullstack, or API project
- Any known deployment concerns (optional)

## Required Process

### Step 1: Inspect deployment-readiness categories

Examine each of these areas:

- **Frontend build**: Does it compile cleanly? Are there build warnings?
- **Backend startup**: Does the server start without errors?
- **Environment variables**: Are all required env vars documented? Any missing?
- **Routing assumptions**: Do client-side routes work with the hosting platform's routing?
- **API base URLs**: Are they configurable or hardcoded to localhost?
- **Auth assumptions**: Does auth flow work outside of local development?
- **Rate limiting**: Does it break in serverless environments?
- **CORS**: Are cross-origin policies configured for production domains?
- **Persistence requirements**: Does the app rely on long-lived server memory?
- **Dev-only shortcuts**: Are there bypasses that should be removed for production?
- **Secret handling**: Are secrets properly externalized, not committed?
- **Logging / monitoring readiness**: Is there basic error tracking?
- **Error handling**: Do unhandled errors crash the app or show useful feedback?
- **Cold start / hosting implications**: Will serverless cold starts cause issues?

### Step 2: Ask hosting-aware questions

Especially relevant for Vercel/Render/Railway-style deployments:

- Does this app rely on long-lived server memory that serverless won't support?
- Does rate limiting break when each request hits a new instance?
- Are API routes mismatched between dev proxy and production?
- Are static assets and routes safe for SPA deep links?
- Are there hardcoded `localhost` assumptions?
- Are there hidden dependencies on a local dev proxy?

### Step 3: Categorize the deployment verdict

Classify the result as one of:

- **Not deployable**: Critical issues prevent deployment
- **Deployable for private testing**: Works but has rough edges
- **Deployable for limited beta**: Functional with known limitations
- **Production-ready with caveats**: Solid but has noted risks

Provide clear reasons for the classification.

## Output Format

```markdown
# Deployment Audit Report

## 1. Deployment Verdict
## 2. Build / Runtime Risks
## 3. Environment / Secrets Issues
## 4. API / Backend Risks
## 5. Security / Access Risks
## 6. Hosting Compatibility Notes
## 7. Required Fixes Before Deployment
## 8. Nice-To-Have Improvements
```

## Rules / Constraints

- Always specify the deployment verdict with justification
- Cite file paths for every issue found
- Distinguish between "will break" and "might cause problems"
- Separate required fixes from nice-to-have improvements

## Common Mistakes To Avoid

- Only checking if the build succeeds without examining runtime behavior
- Missing hardcoded localhost URLs buried in config files
- Ignoring environment variable requirements
- Not considering the specific hosting platform's constraints
- Treating dev-mode workarounds as production-ready solutions
