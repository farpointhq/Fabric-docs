# Context Window Tracking

Every AI model has a **Context Window** — the maximum amount of text it can hold in its "working memory" during a single conversation. Think of it like a whiteboard: once you fill it up, you have to erase something old before you can write something new. The context window includes everything the model sees at once — your prompts, file contents, chat history, and system instructions.

Fabric tracks your token usage in real time and shows it right in the chat composer.

---

## How It Works

As you chat, every message, code snippet, file read, and image you send consumes tokens. Fabric continuously tallies these tokens and displays your current usage against the selected model's limit. The circular indicator next to the model name shows how full your context window is:

![Context Window Indicator](../../../assets/screenshots/context-window/context-window-tooltip.png)

Hover over the indicator to see a detailed breakdown:

* **Total Usage** — How many tokens you're currently using out of the model's total capacity
* **Project Description** — Tokens from your project description setting
* **Project Directory** — Tokens from the project file tree
* **Database Tables** — Tokens from any database schema context
* **File Contents** — Tokens from files you've opened or attached
* **User Prompt** — Tokens from your current message
* **User Images** — Tokens from images you've sent
* **System Prompt** — Tokens from Fabric's built-in instructions
* **Chat History** — Tokens from all previous messages in the conversation

---

## Model Size Differences

Different models have different context window sizes. For example:

* **Fabric XLarge** — 230k tokens
* **Claude 3.5 Sonnet** — 200k tokens
* **GPT-4o** — 128k tokens
* **Smaller models** — Often 8k–32k tokens

When you switch models, Fabric automatically recalculates your usage against the new model's limit. A conversation that fits comfortably in one model might be near the edge for another.

---

## What Happens When You Get Close to the Limit

As your conversation grows, the circular indicator fills up. When you approach the limit:

* The indicator changes color to warn you
* The model may start to "forget" earlier parts of the conversation
* Response quality can degrade as the model struggles to fit everything into memory

If you hit the limit, you have a few options: start a new chat, remove unnecessary file attachments, or use **Compaction** to compress your chat history while keeping the important parts.
