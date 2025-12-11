# Deep Codebase Understanding

**Fabric doesn't just read your code—it understands how it all connects.**

Most AI tools treat your codebase like a pile of text files. Search for something and you get grep results. Ask a question and the AI has no idea how your auth module relates to your API routes.

Fabric is different. It builds a semantic map of your entire codebase, understanding relationships between files, modules, and components. When you search for code, you don't just get matches—you get context about how that code fits into the bigger picture.

---

## How It Works

When you open a project, Fabric analyzes your codebase and builds an understanding of:

- **File relationships** — Which files import from which, how modules connect
- **Code patterns** — Recurring structures, conventions you follow
- **Semantic clusters** — Groups of related functionality (auth, API, UI, etc.)

This happens automatically in the background. You don't configure anything.

---

## What You Experience

### Smarter Search Results

Search for a function and you don't just get the file—you get context about what part of the codebase it belongs to and how it connects to related code.

### Context-Aware Responses

Ask "where do we handle authentication?" and Fabric knows to look in the right places, pulling in related files you might not have thought to mention.

### Better Suggestions

When the AI suggests changes, it understands your patterns and conventions. New code fits naturally with your existing codebase.

---

## Graph Tab

Explore your codebase visually with the Graph Tab:

- **See connections** — Visualize how modules, files, and components relate
- **Find complexity clusters** — Spot tightly-coupled areas that might need refactoring
- **Navigate unfamiliar code** — Understand large codebases without getting lost

Click on any node to see details. Zoom, pan, and explore how your code is organized.

---

## Tips for Best Results

### Keep Projects Focused

Fabric works best when a project represents a coherent codebase. If you have multiple unrelated projects in one folder, consider opening them separately.

### Let Indexing Complete

The first time you open a large project, give Fabric a moment to build its understanding. You'll see better results once indexing completes.

### Use Natural Questions

Instead of searching for exact function names, try asking questions like:

- "Where do we validate user input?"
- "How does the payment flow work?"
- "What touches the user database?"

Fabric's semantic understanding helps it find relevant code even when you don't know the exact names.
