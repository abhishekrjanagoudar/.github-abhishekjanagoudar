---
name: deploy
description: Deploy to Vercel production with all checks
disable-model-invocation: true
---

# Deploy Command Workflow (Copilot)

Deploy Lead Gen Man's app to production:

## Pre-flight checks
1. `git status` -- no uncommitted changes
2. `npm run lint` -- zero warnings
3. `npm run build` -- clean production build
4. `npm test` -- all tests green
5. `npx playwright test` -- e2e passing

## Deploy
6. `git push origin main`
7. Wait for Vercel build to complete
8. `npx vercel inspect` -- verify deployment

## Post-deploy verification
9. Hit production URL, check homepage loads
10. Test one template in editor
11. Check Stripe webhook is receiving events
12. Verify /api/health returns 200

## If anything fails
- DO NOT force push or skip checks
- Fix the issue, re-run all checks
- Only Manthan can approve rollbacks
