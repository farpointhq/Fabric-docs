# Best Practices

A collection of habits and patterns that make working with Fabric more effective. None of these are required — Fabric works out of the box — but they make a noticeable difference once you're past the basics.

---

## Give the AI the Right Context

The quality of Fabric's output is directly tied to the quality of context it has. Too little and it makes assumptions. Too much and important details get buried.

**Add the files that matter, not all of them.** Use the file browser or the paperclip to attach the specific files relevant to your task. Attaching your entire project for a one-line change slows things down and can confuse the model.

**Be specific about what you want changed.** "Fix the bug in the auth module" is harder to act on than "the `validateToken` function in `src/auth/token.ts` returns `null` when the token is expired instead of throwing — fix that."

**Include error messages verbatim.** Paste the full stack trace or error output. Don't summarize it — the exact wording often contains the signal the AI needs.

**Share the relevant schema when working with data.** If you're asking for a query or a migration, select the tables in the DB browser first. Without the schema, the AI guesses at column names and types.

---

## Set Up AGENTS.md for Every Project

The single highest-leverage thing you can do is create an `AGENTS.md` file at the root of your project. Fabric reads this at the start of every chat session, so anything you put there applies automatically — no need to re-explain your conventions each time.

Good things to include:

- **Project overview** — what the project is and what it does in 2-3 sentences
- **Tech stack** — languages, frameworks, databases, key dependencies
- **Code conventions** — naming patterns, file structure, anything the AI should follow
- **Testing rules** — how to run tests, what test framework you use, any commands to avoid
- **Safety rules** — files or folders that shouldn't be touched, operations that require confirmation
- **Common workflows** — how to add a new feature, how to run the dev server, how to deploy

The more specific you are, the less correction you'll need. Start lean and add to it whenever you find yourself re-explaining something.

---

## Use Agentic Mode for Multi-Step Work

Agentic mode unlocks the ability to read files, run commands, edit code, and loop back on failures. Use it for anything that involves more than one step.

**Let it plan before it acts.** Ask Fabric to describe its approach before making changes: *"Before you start, tell me what files you'll touch and what the overall approach is."* This surfaces misunderstandings early, before they become edits you need to undo.

**Review diffs before accepting.** Fabric shows you every file change in a diff viewer. Don't bulk-accept everything — scan for unintended changes, especially in files you didn't mention.

**Use "Fabric take the wheel" for well-defined tasks.** Full autonomous mode is best when the task is clear and the blast radius is small — generating tests, updating a config, reformatting a file. Reserve it for tasks where surprises are easy to catch and reverse.

**Keep tasks focused.** "Refactor the whole codebase" is hard to do well. "Rename `getUserData` to `fetchUserProfile` everywhere it's used and update the tests" is tractable.

---

## Pick the Right Model for the Task

Not every task needs the most powerful model. Matching the model to the task saves cost and usually gets you results faster.

| Task type | Recommended tier |
|-----------|-----------------|
| Architecture decisions, hard debugging, complex refactors | Large / XLarge |
| Feature development, code review, writing | Medium |
| Quick edits, renaming, formatting, simple questions | Small |
| Background helper tasks (tab naming, file suggestions) | Fabric auto-selects |

Switch models mid-conversation when the task changes. If you started exploring with a fast model and are now ready to implement something complex, bump up — the context carries over.

---

## Use Tabs to Stay Organized

Each tab is an independent conversation with its own context. Use this to your advantage.

- Keep **one tab per task**, not one tab for everything. A tab for the feature you're building, a separate one for the bug you're investigating.
- Run **long agentic tasks in a background tab** while you continue working in another.
- Open a **research tab** for browsing docs or reading papers so it doesn't pollute your coding context.
- Use **Compact** when a conversation gets long but you want to continue it — it summarizes older messages and frees up context window space without starting over.

---

## Prompt Effectively

Fabric is a capable AI, but a well-framed prompt still gets better results than a vague one.

**Say what you want, not just what's wrong.** "This function is slow" is less useful than "This function is slow — rewrite it to reduce the number of database calls."

**Give constraints upfront.** If you need something done without external dependencies, say so. If it needs to match an existing pattern, point to the pattern. Constraints at the start prevent back-and-forth at the end.

**Ask for explanations when learning.** If you're in unfamiliar territory, ask Fabric to explain what it's doing as it goes. You'll catch misunderstandings earlier and learn faster.

**Iterate.** A good first response is often 80% of the way there. Follow up: "The logic looks right but the error handling is missing — add it." You don't need to start a new conversation to refine.

---

## Keep Your Context Clean

Context window space is a finite resource. Managing it well keeps the AI accurate over long sessions.

- **Use Compact** before a long agentic task to clear out earlier back-and-forth that's no longer relevant.
- **Start a new tab** when the current conversation has drifted far from the original topic.
- **Remove attached files** (click the × on a chip) when they're no longer needed for the current question.
- **Watch the context indicator** in the chat bar — when it's getting full, compact or continue in a new tab.
