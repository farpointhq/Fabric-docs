# Persistent Memory

## What is Persistent Memory?

Persistent Memory is how you give Fabric's AI a permanent set of instructions about your project — things it should always know, without you having to explain them in every conversation.

You do this by placing an **`AGENTS.md`** file in the root of your project. Every time you start a chat in Fabric, the AI reads this file automatically before it does anything else. Think of it as a standing briefing: project background, coding standards, important decisions, and any rules the AI must follow.

## Why AGENTS.md Matters

Without persistent memory, every new chat session starts with a blank slate. You end up repeating the same context — "we use Vitest, not Jest", "never squash-merge", "this service lives in `src/main/services/`" — over and over.

With an `AGENTS.md` in your project, that context is always loaded. The AI knows your conventions before you say a word.

It's also the right place to put **safety rules and workflow requirements** that the AI must respect on every task — things like "never run `npm test` directly" or "always create a PR, never push to main". These instructions carry more weight than a one-off message because the AI sees them at the start of every session.

## How to Use It

**1. Create the file**

Add `AGENTS.md` to your project root (next to `package.json`, `README.md`, etc.):

```
my-project/
├── AGENTS.md        ← create this
├── package.json
└── src/
```

**2. Write your instructions in plain English**

No special syntax required — just markdown. Focus on the things the AI cannot figure out from reading your code:

```markdown
# My Project Agent Instructions

## Project Overview
This is a Next.js app with a Postgres database. The backend API lives in
`src/api/` and the frontend components in `src/components/`.

## Coding Standards
- Use TypeScript everywhere. No `any` types.
- All database queries go through the service layer in `src/services/`.
- Write tests with Vitest. Test files live next to the code they test.

## Critical Rules
- Never push directly to `main`. Always open a PR.
- Never run the full test suite locally — it takes 10+ minutes. Run
  `npm run test:changed` instead.

## How We Work
When fixing a bug, always add a regression test before changing the code.
When adding a feature, update the relevant section in `docs/` when done.
```

**3. Fabric loads it automatically**

You don't need to do anything else. Next time you open a chat session in Fabric pointing at this project, the AI will have already read your `AGENTS.md` and will follow its instructions throughout the conversation.

## What to Put in AGENTS.md

Good things to include:

- **Project overview** — what the project does, its main directories, how it's structured
- **Coding standards** — formatting rules, naming conventions, which libraries to use
- **Workflow rules** — how PRs work, branch naming, review process
- **Safety rules** — commands that must never be run, files that must not be changed, things that require user approval
- **Testing conventions** — which test runner, where tests live, what to test
- **Common pitfalls** — things that have caused bugs before, gotchas the AI should watch out for

Avoid putting things in `AGENTS.md` that are already obvious from reading the code — save it for context the AI genuinely cannot infer on its own.

## Scope: Project vs User

You can have more than one `AGENTS.md`:

- **Project-level** (`<project-root>/AGENTS.md`) — applies only to this project. Commit it to your repo so the whole team benefits.
- **User-level** (`~/.agents/AGENTS.md` or `~/.claude/AGENTS.md`) — applies to every project you open in Fabric. Good for personal preferences like "always explain your reasoning" or "prefer concise responses".

When both exist, Fabric combines them, with project-level instructions taking priority over user-level ones.

## Tips

- **Be direct.** The AI takes instructions literally. "Prefer functional components" is clearer than "we tend to like functional components".
- **Keep it focused.** A 50-line `AGENTS.md` that covers the real risks is more effective than a 500-line one that the AI has to wade through.
- **Update it when things change.** If you add a new service, rename a directory, or change a convention, update `AGENTS.md` at the same time.
- **Start with safety rules.** The highest-value entries are the ones that prevent the AI from doing something irreversible — add those first.
