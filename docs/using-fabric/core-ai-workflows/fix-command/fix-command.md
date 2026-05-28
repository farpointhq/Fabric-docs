# Fix Command in Fabric

🚧 Video tutorial is in progress.

## What is the Fix Command in Fabric?

The `/fix` command launches a structured, test-driven workflow for fixing GitHub issues in an isolated git worktree. It orchestrates a complete development lifecycle—from issue analysis and planning through adversarial testing and PR creation—while keeping your main workspace clean. The command enforces best practices including isolated development, mandatory planning with deployed artifacts, test-driven development (TDD), and required approval checkpoints.

---

## When to Use the Fix Command

Use `/fix` in Fabric when you want to:

* **Fix Reported Bugs**: Work on GitHub issues with full traceability from plan to PR.
* **Implement Features**: Follow a structured approach for new feature development with planning and testing.
* **Maintain Clean Workspace**: Develop in isolated worktrees without affecting your main project or other sessions.
* **Enforce TDD Workflow**: Ensure tests are written before implementation, every time.
* **Generate Deployed Plans**: Create visual plans with diagrams hosted on GitHub Pages for easy review.
* **Perform Adversarial Testing**: Actively try to break your own code before submitting a PR.
* **Create Linked PRs**: Automatically generate pull requests linked to issues with full context.

**Avoid `/fix` for**: Quick one-line fixes, exploratory work, or changes that don't benefit from formal planning and testing.

---

## How to Use the Fix Command

### Step 1: Invoke the Fix Command

Type the slash command with the GitHub issue number in your chat:

```
/fix 42
```

Fabric fetches the issue details from GitHub and displays the title, description, and labels for reference.

### Step 2: Worktree Creation

Fabric creates an isolated git worktree on a new branch (`fix/issue-42`) based on your `dev` branch. The worktree is stored in `tmp_worktree/issue-42` and automatically added to `.gitignore` to keep it out of version control.

All subsequent file operations happen in this isolated environment.

### Step 3: Environment Setup

Fabric navigates to the worktree, copies `.env` from the main project (if present), and installs dependencies:

```bash
cd tmp_worktree/issue-42
npm install
```

### Step 4: Plans Repo Detection

Fabric detects your repository's sibling plans repo (`<repo>-plans`) and GitHub Pages URL from the `origin` remote. If the plans repo doesn't exist, it will be created during deployment.

### Step 5: Create Plan Document

Fabric analyzes the issue and creates a plan document at `$PLANS_DIR/docs/plans/issue-42-plan.md` containing:

* Issue Summary
* Root Cause Analysis (for bugs)
* Proposed Solution
* Files to Modify
* Test Strategy
* Risks and Considerations

### Step 6: Generate Diagrams

Fabric generates visual diagrams using HTML+CSS (default) or Mermaid for sequence/class diagrams:

* System Architecture diagrams showing component relationships
* Data Flow diagrams tracing how data moves through the system
* Process Flow diagrams with numbered steps and branches
* State Machine diagrams for stateful components
* Before/After comparisons for UI changes

### Step 7: Deploy Plan to GitHub Pages

Fabric commits the plan to the plans repo and triggers GitHub Pages deployment:

```bash
cd $PLANS_DIR
git add -A
git commit -m "docs: Add plan for issue #42"
git push origin main
```

Wait ~30-60 seconds for deployment, then the plan is live at:
`https://<org>.github.io/<repo>-plans/plans/issue-42-plan/`

### Step 8: Approval Checkpoint — Plan Review

**STOP and wait for your approval.** Fabric displays the deployed plan URL and asks:

> "I've created a plan for fixing issue #42. Please review the plan. Let me know:
> 1. **Approved** — proceed with implementation
> 2. **Feedback** — what changes you'd like
> 3. **Cancel** — abort this fix"

If you request changes, Fabric updates the plan and redeploys. Repeat until approved.

### Step 9: Write Tests First (TDD)

Once approved, Fabric writes unit tests that verify the expected behavior after the fix. Tests are placed in the appropriate `tests/` directory following existing patterns.

### Step 10: Run Tests (Expect Failures)

Fabric runs the test suite. The new tests **should fail** at this point, confirming they're actually testing something meaningful.

### Step 11: Commit Tests

Tests are committed with a descriptive message:

```bash
git add -A
git commit -m "test(issue-42): add failing tests for issue #42"
```

### Step 12: Implement the Fix

Fabric implements the fix with atomic commits. After each logical change:

```bash
git add -A
git commit -m "fix(issue-42): <specific change description>"
```

### Step 13: Run Tests After Each Change

Tests are run after each commit. If they fail, Fabric analyzes the failure, fixes the code, commits, and retests until all tests pass.

### Step 14: Full Verification

Once implementation is complete, Fabric runs the full test suite and type checking:

```bash
npm test
npm run typecheck
```

### Step 15: Adversarial Self-Testing

**This phase is required.** Fabric switches to a "hostile QA" mindset and actively tries to break the code by testing:

* **Edge Cases**: Empty inputs, null values, maximum lengths, special characters
* **State Manipulation**: Rapid clicks, interruptions, invalid transitions
* **Integration Attacks**: Unexpected data shapes, network failures, permission denials
* **User Behavior**: Out-of-order actions, repeated rapid inputs

A testing report is created at `$PLANS_DIR/docs/plans/issue-42-adversarial-testing.md`.

### Step 16: Approval Checkpoint — Testing Review

**STOP and wait for your approval.** Fabric displays the adversarial testing report and asks:

> "I've completed adversarial self-testing for issue #42. Please review the testing report. Let me know:
> 1. **Approved** — proceed with PR creation
> 2. **More testing needed** — specific areas to test
> 3. **Manual testing** — you want to test it yourself first"

### Step 17: Create Pull Request

After approval, Fabric pushes the branch and creates a PR:

```bash
git push -u origin fix/issue-42
gh pr create --base dev --title "Fix #42: <issue title>" --body "..."
```

The PR body includes links to the deployed plan and adversarial testing report.

### Step 18: Cleanup

Fabric returns to the main project, removes the worktree, and updates the plan status to "completed":

```bash
cd <project-root>
git worktree remove tmp_worktree/issue-42
git worktree prune
```

---

## Example Session

```
User: /fix 42

Fabric: Fetching issue #42...
        "Login fails when password contains special characters"
        
        Creating worktree: fix/issue-42
        Installing dependencies...
        
        Analyzing issue and creating plan...
        Plan deployed: https://farpointhq.github.io/Fabric-plans/plans/issue-42-plan/
        
        Please review the plan and approve to proceed.
```

After approval, Fabric continues with TDD implementation, adversarial testing, and PR creation.
