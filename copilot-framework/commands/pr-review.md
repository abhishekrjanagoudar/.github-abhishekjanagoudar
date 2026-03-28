---
name: pr-review
argument-hint: [pr-number]
---

# PR Review Command (Copilot)

Review a Pull Request by following these steps:

## Step 1: Read the PR
- `gh pr view [pr-number]` to read the description and comments.
- `git fetch origin pull/[pr-number]/head:pr-[pr-number]`
- `git diff main...pr-[pr-number]`

## Step 2: Audit Logic
- Read through every changed file.
- Use the `code-reviewer` agent logic to audit quality and security.

## Step 3: Performance Check
- Verify Next.js Server Components, Canvas logic, and bundle impacts.
- Ensure no blocking calls or unnecessary re-renders.

## Step 4: Feedback
- Report as: CRITICAL / WARNING / SUGGESTION.
- Use severity labels: `[blocking]`, `[important]`, `[nit]`.

## Step 5: Verification
- `npm run build` -- ensures a clean production build from the PR source.
- `npm run lint` -- code check.
