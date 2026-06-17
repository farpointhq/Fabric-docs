# Search Your Conversation History

Fabric automatically indexes your past AI conversations — from Fabric itself and from other tools you've used — and makes them searchable from inside any chat session. Ask about a decision you made last month, find a snippet from a session three weeks ago, or recall how you solved a problem you've hit before. The answer comes back as a clean excerpt with a date and source, ready to use.

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../assets/videos/migrate.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</div>

---

## What Gets Indexed

Fabric searches across conversations from:

- **Fabric** — all your past chat sessions in this and other projects
- **Claude** — conversations from Claude desktop and Claude.ai
- **Cursor** — chat history from Cursor's AI panel
- **Gemini** — conversations from Google Gemini

The index builds automatically in the background. There's nothing to import or configure — open Fabric and your history is already there.

---

## How to Search

In any chat session, ask a natural language question about something from your past work:

```
What did we decide about the database schema for the orders table?
```

```
How did I fix the CORS issue last time?
```

```
Find the migration script we wrote for the user authentication refactor.
```

Fabric searches your indexed history and returns the most relevant excerpts with the date and source conversation. Results are ranked by relevance, recency, and whether they came from work on the current project.

---

## Scopes

You can control how wide the search goes:

| Scope | What it searches |
|-------|-----------------|
| **Current project** | Conversations related to the project you have open |
| **Fabric only** | All Fabric chat sessions across all projects |
| **All tools** | Everything — Fabric, Claude, Cursor, Gemini |

By default, Fabric weights results from the current project higher, so relevant context floats to the top without you having to specify.

---

## Why This Matters

Most AI sessions are disposable — you close the chat and the context is gone. Over time you make the same decisions twice, re-explain the same things, and lose track of solutions that worked.

Conversation history search changes that. Every session you've had becomes a resource you can draw on. The longer you use Fabric (and the tools it indexes), the more useful the search becomes.

---

## Notes

- The index updates on a short cycle in the background — new conversations are searchable within a minute or two of finishing.
- Only conversation content is indexed — no file contents from your codebase, no credentials, no environment variables.
- History is stored locally in Fabric's application data folder. It does not leave your machine.
