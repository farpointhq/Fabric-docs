# Roadmap

**Where Fabric is headed—and why it matters for your workflow.**

We're building the AI coding assistant we always wanted: fast enough for daily use, smart enough for complex problems, and transparent enough that you always know what's happening.

---

## Coming Soon

### :material-lightning-bolt: Parallel Task Execution

**The Problem:** Big features have many parts. Current AI tools do one thing at a time—write a component, wait, write another, wait. It's slow.

**What We're Building:** When you describe a feature, Fabric creates a plan with task dependencies. Independent tasks launch in parallel tabs. Dependent tasks wait for their prerequisites. Each task must pass its tests before completing. Tabs close automatically as work finishes.

*Think of it as AI-powered parallel development with built-in quality gates.*

**Timeline:** Coming in the next few weeks.

---

### :material-database-search: Database-Aware SQL

**The Problem:** Writing SQL without seeing your schema is like coding blindfolded. AI generates queries that look right but reference wrong tables.

**What We're Building:** Connect your database and Fabric knows your schema. It suggests columns that actually exist, joins that actually work, and queries optimized for your data.

---

### :material-source-branch: Git-Native Workflows

**The Problem:** AI helps you write code, but the commit-PR-review cycle is still manual. Context gets lost between "write this feature" and "ship it."

**What We're Building:** Integrated version control that helps you commit with meaningful messages, create PRs with proper descriptions, and track what AI contributed to each change.

---

## Live Now

### :material-graph: Graph Tab — Explore Your Codebase Visually

Fabric builds a semantic map of your entire codebase. Open the Graph Tab to:

- **See how modules connect** — Visualize relationships between files and components
- **Find complexity clusters** — Spot areas that might need refactoring
- **Understand unfamiliar code** — Navigate large codebases without getting lost

When you search for code, Fabric uses this understanding to give you context about how that code fits into the bigger picture—even if you didn't ask for it.

### :material-test-tube: TDD Mode

Fabric's most rigorous workflow:

1. **Plan** — AI researches your codebase, asks clarifying questions, creates an implementation plan
2. **You approve** — Review and refine the plan
3. **Test plan** — AI designs tests that verify the feature works correctly
4. **You approve** — Review the test criteria
5. **Red/Green loop** — AI writes failing tests first, then implements code until all tests pass

No hardcoded retry limits. The AI keeps iterating until the tests pass or asks for help.

### :material-lightning-bolt: Agentic Mode

Let AI call tools autonomously—read files, run commands, edit code—while you supervise. Good for exploration and quick tasks where you don't need the full TDD rigor.

### :material-clipboard-list: Plan Mode

A lighter workflow: AI creates a plan, you approve it, then implementation proceeds. No test-first requirement.

### :material-eye: Transparent Reasoning

See the AI think through problems step-by-step. No more black boxes—understand *why* it suggests what it suggests.

### :material-swap-horizontal: Multi-Model Selection

Choose the right model for each task. Fast models for quick questions, powerful ones for complex reasoning. Switch mid-conversation without losing context.

### :material-tab: Tab Groups

Organize related conversations. Keep your "Auth Rewrite" separate from your "Sprint Bugs."

### :material-shield-check: Approval Workflow

Every file change requires your OK. Full audit trail of AI actions.

---

## Have an Idea?

We build what developers need. If something's missing or broken, tell us:

[:octicons-arrow-right-24: GitHub Discussions](https://github.com/farpointhq/Fabric/discussions){ .md-button }

---

!!! quote "Our Philosophy"
    **Velocity without blindness.** Ship faster, but always know what's happening. That's the future we're building.
