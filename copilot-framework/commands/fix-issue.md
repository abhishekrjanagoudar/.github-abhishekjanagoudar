---
name: fix-issue
argument-hint: [issue-number]
---

# Fix Issue Command (Copilot)

Fix a GitHub issue by following these steps:

## Step 1: Read the Issue
- `gh issue view [issue-number]` to read the description and comments.
- Identify the problem area (component, API, lib).

## Step 2: Investigation
- Locate the relevant source files.
- Use `git grep` and `git log` to find related logic and past changes.

## Step 3: Implement Fix
- Apply the minimal change needed.
- Write a regression test to prevent recurrence.

## Step 4: Verification
- `npm test` -- ensure all tests pass (no regressions).
- `npm run lint` -- code check.

## Step 5: Finalize
- Commit message: "fix: [description] (closes #[issue-number])"
- Confirm the fix is verified.
