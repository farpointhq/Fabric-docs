# Code Reference

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../assets/videos/code-reference.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</div>

When you want to ask the AI about a specific piece of code, you don't have to paste the whole thing into the chat. Fabric lets you **reference** exact lines from a file — select them, bring them into the chat as a compact tag, and the AI knows precisely which code you mean.

---

## How It Works

Open a file in the editor and **select the lines** you want to talk about. Then bring them into the chat one of two ways:

**Copy and paste** — Copy the selected lines (`Ctrl/Cmd C`) and paste them into the chat input (`Ctrl/Cmd V`). Instead of dumping the raw code into your message, Fabric turns it into a small **reference pill** showing the file name and line range — for example `utils.ts:42-50`.

**Right-click → Add to chat** — Right-click the selected code in the editor and choose **Add to previous chat**. The reference pill is added to your chat input instantly, without leaving the editor.

Either way, you end up with a tidy pill in your message instead of a wall of pasted code. You can keep typing your question around it, and add as many references as you like.

---

## Jump Back to the Code

A reference pill is a two-way link. **Click it** — in the input or later in your chat history — and Fabric opens that file and scrolls right to the referenced lines. This makes it easy to revisit exactly what you were discussing, even weeks later when you reopen the conversation.

---

## Why It Matters

Referencing code instead of pasting it solves a few real problems:

- **Keeps your context clean.** A reference is just a file name and line range, so it doesn't fill your conversation (or the AI's context window) with large code blocks. That keeps responses faster and cheaper — see [Cost Tracking](../../core-ai-workflows/cost-tracking/cost-tracking.md).
- **Always accurate.** The AI reads the actual lines from the file when it responds, so it sees the real, current code — not a stale copy you pasted earlier.
- **Easy to navigate.** Every pill is clickable, so your chat history doubles as a set of bookmarks back into the codebase.
- **Precise.** Instead of "the function near the top of that file," the AI gets the exact lines you pointed at.

---

## Copy-Paste, the Smart Way

The nice part is that copy-paste just works the way you'd expect — but smarter. When you copy code from Fabric's editor and paste it into the chat, it becomes a reference pill automatically. And if you paste that same code somewhere outside Fabric, it still arrives as plain code, so nothing is lost. You get the lightweight reference inside Fabric and normal copy-paste everywhere else.
