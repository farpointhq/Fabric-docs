# Run a Code Review Workflow with Fabric

**Time:** 10 minutes to set up, ongoing use  
**Difficulty:** Beginner  
**What you'll build:** A repeatable code review workflow using Fabric's `/review` command and diff viewer.

---

## Overview

Fabric's `/review` command runs a structured analysis of any file in your project across six dimensions: correctness, security, performance, maintainability, testing, and best practices. It returns a prioritized report with severity ratings and concrete suggestions.

Once you have a review, you can ask Fabric to apply the fixes and inspect each change in the interactive diff viewer before committing anything.

This cookbook walks through the full cycle: review → inspect findings → apply fixes → verify.

---

## Step 1: Open the File You Want to Review

In the file browser, navigate to the file you want to review. Click it to open it in the editor, then right-click and choose **Add to Chat** to attach it as context.

Alternatively, you can skip this step — the `/review` command accepts a file path directly as an argument.

---

## Step 2: Run the Review

In the chat input, type:

```
/review src/auth/token.ts
```

Replace the path with your file. Fabric will read the file, analyze it, and stream back a structured report.

The report organizes findings by severity:

- **Critical** — bugs, security vulnerabilities, data loss risks
- **Major** — logic errors, performance problems, missing error handling
- **Minor** — style issues, naming, DRY violations

Each finding includes the exact line or function, a description of the issue, and a suggested fix.

---

## Step 3: Read the Report Carefully

Don't immediately ask Fabric to fix everything. Read through the findings and decide:

- Which findings are definitely real issues you want to fix
- Which are stylistic preferences you disagree with
- Which would require refactoring beyond the scope of this change

For a PR review, focus on Critical and Major findings. Minor issues are worth fixing but shouldn't block a merge.

---

## Step 4: Ask Fabric to Apply Specific Fixes

Instead of "fix everything," be selective:

```
Apply the fix for the missing token expiry validation in validateToken().
Keep everything else as-is.
```

Fabric will use its edit tool to make the targeted change and show you the result in the diff viewer.

---

## Step 5: Inspect the Diff

The diff viewer shows the original code on the left and the proposed change on the right. For each change:

- Press `A` to **accept** the highlighted change
- Press `D` to **discard** it
- Use `W` / `S` to scroll between changes
- Use the file-level controls to accept or reject all changes at once

Take your time here. You're the last line of defence before the code changes.

---

## Step 6: Iterate

After applying fixes, run the review again on the same file:

```
/review src/auth/token.ts
```

A clean second pass means the issues are resolved. If new findings appear, they were likely introduced by the fix — worth a quick look before moving on.

---

## Step 7: Run Your Tests

In the built-in terminal:

```bash
npx vitest run src/auth/token.test.ts
```

Always run the tests for the file you changed before committing. If you don't have tests for this file, ask Fabric to write them:

```
Write unit tests for validateToken() covering the happy path, expired tokens, and malformed input.
```

---

## Variations

**Review before a PR, not after** — Run `/review` on every file you changed before opening a PR, not just when you suspect a problem. It catches things that are easy to miss when you've been staring at the code.

**Review someone else's code** — Open the file from the file browser and run `/review`. Useful for understanding an unfamiliar module or auditing a colleague's PR.

**Focus the review** — You can ask for a focused review instead of the full analysis:

```
Review src/payments/stripe.ts for security issues only.
```

**Use it for learning** — If you're new to a codebase or a language, `/review` on a file you wrote is a fast way to get specific, actionable feedback on your code.
