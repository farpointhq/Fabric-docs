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

## Recently Shipped

- **Deep Codebase Understanding** — Semantic mapping of your entire codebase ([learn more](features/knowledge-base.md))
- **Graph Tab** — Visual codebase exploration
- **TDD Mode** — Plan → Test plan → Red/Green loop until tests pass
- **Agentic Mode** — Autonomous tool calling with supervision
- **Plan Mode** — Lighter workflow without test-first requirement
- **Multi-Model Selection** — Choose the right model for each task
- **Tab Groups** — Organize related conversations
- **Transparent Reasoning** — See the AI think step-by-step

---

## Have an Idea?

We build what developers need. If something's missing or broken, tell us:

[:octicons-arrow-right-24: GitHub Discussions](https://github.com/farpointhq/Fabric/discussions){ .md-button }

---

!!! quote "Our Philosophy"
    **Velocity without blindness.** Ship faster, but always know what's happening. That's the future we're building.
