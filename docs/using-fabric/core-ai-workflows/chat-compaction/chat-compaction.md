# Chat Compaction

Over the course of a long conversation, your chat history grows — and so does the token count. Every message, file read, and tool result stays in the model's context window. Eventually you approach the limit, and the model starts losing track of earlier parts of the discussion.

**Compaction** solves this by compressing your chat history into a concise summary. Fabric reads through the entire conversation, extracts the key decisions and outcomes, and replaces the full back-and-forth with a shortened version that preserves what matters.

---

## How It Works

When you click the **Compact** button in the chat toolbar, Fabric:

1. Reads through every message in the current conversation
2. Identifies the important decisions, code changes, and conclusions
3. Generates a compact summary that captures the essential context
4. Replaces the verbose chat history with that summary

The result is a much smaller token footprint, freeing up space for new messages while keeping the model informed about what you've already accomplished.

---

## The Compact Button

![Compact Button](../../../assets/screenshots/compaction/compact-button.png)

The **Compact** button lives in the chat composer toolbar, between the agentic controls and the model selector. Click it any time during a conversation to trigger compaction.

---

## When to Use Compaction

* **Long-running conversations** — When you've been working on the same task for dozens of messages and the context window is filling up
* **Before a major pivot** — When you're about to ask a completely new question and want to preserve the important outcomes from earlier without carrying the full discussion
* **After a review or debug session** — When the back-and-forth produced a clear result (a fixed bug, a refactored file) and the detailed reasoning is no longer needed
* **When the indicator turns yellow or red** — Fabric's context window indicator warns you as you approach the limit; compaction is the fastest way to reclaim space without losing context

Compaction is non-destructive in the sense that the full conversation is still visible in the chat history — but the *model* only sees the compacted version going forward. This gives you the best of both worlds: a readable transcript for yourself, and an efficient context for the AI.
