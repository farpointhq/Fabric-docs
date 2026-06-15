# Code Review with Fabric

<video controls playsinline width="100%">
  <source src="../../../../assets/videos/code-review.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## What is Code Review with Fabric?

Fabric's built-in **Code Review** feature lets you request a thorough, structured analysis of any file in your workspace using the `/review` slash command. The AI examines code across six dimensions—Correctness, Security, Performance, Maintainability, Testing, and Best Practices—and returns a prioritized report with severity ratings and actionable fixes.

When you're ready to act on the review, you can ask Fabric to apply the suggested changes directly. The assistant uses the `edit` tool to make precise, targeted modifications, which are presented in an interactive **side-by-side diff viewer**. You can accept or reject individual hunks, undo decisions, or accept all changes at once before saving them to disk.


## When to use Code Review with Fabric

Use the Code Review feature in Fabric when you want to:

* **Catch bugs early** — Have a second pair of eyes scan new code for logic errors, edge cases, and security vulnerabilities before merging.
* **Improve code quality** — Get constructive feedback on naming, abstraction, DRY violations, and TypeScript strictness.
* **Validate PRs** — Review pull request diffs or specific files without leaving your editor.
* **Apply fixes safely** — Let the AI generate edits and inspect every change in the interactive diff UI before committing.


## How to use Code Review with Fabric

### Step 1: Open Model Selector

Click the main model selector in the chat toolbar to choose a model that supports tool use for code review and edits.

![Open Model Selector](../../../../assets/screenshots/code-review/1.png)

### Step 2: Select Fabric XLarge

Select the 'Fabric XLarge' model to enable advanced tool-use capabilities required for code review and file editing.

![Select Fabric XLarge](../../../../assets/screenshots/code-review/2.png)

### Step 3: Type the Review Command

Type the `/review` slash command followed by the file path you want to analyze. The argument hint shows you can also pass a PR number or description.

![Type the Review Command](../../../../assets/screenshots/code-review/3.png)

### Step 4: Submit the Review Request

Press Enter or click the Send button to submit the review request. Fabric reads the file, analyzes it, and begins streaming a structured review report.

![Submit the Review Request](../../../../assets/screenshots/code-review/4.png)

### Step 5: Review the Analysis Report

Fabric streams a comprehensive code review report organized by severity: Critical, Major, and Minor. Each finding includes the exact location, a description of the issue, and a concrete suggestion for how to fix it.

![Review the Analysis Report](../../../../assets/screenshots/code-review/5.png)

### Step 6: Request Fix Application

After reading the review, ask Fabric to apply the suggested fixes. The AI will use the edit tool to make precise, targeted changes to the file.

![Request Fix Application](../../../../assets/screenshots/code-review/6.png)

### Step 7: Submit the Fix Request

Press Enter or click Send to trigger the fix application. Fabric generates the proposed changes and presents them in the interactive diff viewer.

![Submit the Fix Request](../../../../assets/screenshots/code-review/7.png)

### Step 8: Inspect the Interactive Diff

Fabric presents the proposed changes in a side-by-side diff viewer. Each hunk shows the original code on the left and the proposed change on the right. Use the checkmark button to accept a change, the X button to reject it, or the undo button to reverse a decision. You can also accept or reject all changes at the file level.

![Inspect the Interactive Diff](../../../../assets/screenshots/code-review/8.png)
