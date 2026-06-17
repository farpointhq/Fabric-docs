# Clarifying Questions

Sometimes the AI needs a decision from you before it can proceed — which framework to use, whether to include tests, which of two approaches you prefer. Instead of guessing or stopping to ask in plain text, Fabric can present a structured multiple-choice question right in the conversation, and you answer by clicking.

---

## How It Works

![A multiple-choice clarifying question with tabs and selectable options](../../../assets/screenshots/clarifying-questions/1.png)

When the AI determines it genuinely needs input it can't infer, it asks a structured question. A compact dialog appears inline in the chat with:

- The **question** text
- A set of **selectable options**, each with an optional short description
- An **"Other"** choice with a free-text field, in case none of the options fit

You pick an option (or type your own), and your answer is sent straight back to the AI, which continues with your decision in hand.

---

## Single and Multiple Selection

Questions come in two modes:

- **Single-select** — radio-style; pick one option. After you choose, the dialog can advance automatically.
- **Multi-select** — checkbox-style; select as many options as apply, then submit.

A single prompt can bundle several questions together. When it does, the dialog shows tabs across the top — one per question — with a progress indicator like `2 of 3 answered`. Work through each tab; once all are answered the whole set submits at once.

---

## Answering a Question

- **Click an option** to select it. For multi-select questions, click each option you want.
- **Choose "Other"** and type into the field if you need to give an answer that isn't listed.
- **Submit** with the button at the bottom (single-select questions may auto-advance/submit once chosen).
- Your draft answers are preserved if you switch between tabs, so you won't lose a selection by navigating around.

---

## Why It's Better Than a Plain-Text Question

- **No ambiguity.** Structured options make the choice explicit, so the AI gets a clean, unambiguous answer rather than parsing free-form text.
- **Faster.** Clicking a button beats typing out a full reply.
- **Fewer wrong turns.** Because the AI surfaces the decision instead of assuming, you avoid the situation where it confidently builds the wrong thing and you have to backtrack.

---

## When You'll See It

The AI is designed to ask only when it truly needs to — when a decision materially changes what it does next and it can't reasonably pick a default. You'll typically see clarifying questions:

- At the start of an open-ended task with several valid approaches
- When a request is ambiguous and the options lead to meaningfully different outcomes
- Before a step that's hard to undo, where confirming direction is worth a moment

If you'd rather the AI just proceed with its best judgment, tell it so — it will lean on sensible defaults instead of asking.

> In fully autonomous runs, clarifying questions are skipped entirely — the AI proceeds with its best judgment rather than waiting on input that won't come.
