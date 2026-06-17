# Cost Tracking

Fabric shows you exactly what each AI response costs, right in the conversation. There's no separate billing dashboard to check and no guessing — every completed response carries a small footnote with its cost, token usage, and timing.

---

## Where to Find It

![The response cost footnote beneath a completed message](../../../assets/screenshots/cost-tracking/1.png)

After any AI response finishes generating, look at the footnote directly beneath the message. It shows:

- **Response cost** — the dollar cost of that single response, e.g. `RESPONSE COST: $0.012`
- **Token usage** — input and output tokens, e.g. `[in: 1.2k, out: 523]`
- **Cache rate** — when prompt caching kicks in, the percentage served from cache, e.g. `[95% cached]`
- **Timing** — how long the response took, e.g. `COMPLETED IN: 2.34s`

While a response is still streaming, the footnote shows live elapsed time (`IN PROGRESS: 1.2s`) and switches to the final cost once it completes.

---

## How the Cost Is Calculated

The cost is computed from the response's token usage and the pricing of the model that produced it:

```
cost = (input_price × input_tokens + output_price × output_tokens) / 1,000,000
```

Where `input_price` and `output_price` are the per-million-token rates defined for the selected model. Because the calculation uses the actual token counts returned by the provider, the number reflects what you were really charged for that call — not an estimate.

When **prompt caching** is active, cached input tokens are billed at a reduced rate, which is why a high cache percentage noticeably lowers the cost of follow-up messages in a long conversation.

---

## Why It's Per-Response

Fabric reports cost **per response** rather than as a single running total for the chat. This is deliberate — it makes it obvious which actions are expensive. A quick clarifying question costs a fraction of a cent; a deep agentic task that reads dozens of files and reasons through a complex change costs more. Seeing the cost attached to each response helps you connect the number to the work that produced it.

To gauge the cost of a whole conversation, scan the footnotes — the expensive responses stand out immediately.

---

## Using Cost Awareness in Practice

- **Match the model to the task.** If you notice routine responses costing more than they should, switch to a smaller, cheaper model for that kind of work. See [Models](../../../getting-started/models/models.md).
- **Lean on caching for long sessions.** Keeping a conversation going (rather than restarting) lets prompt caching reduce the cost of each follow-up. Watch the cache percentage climb in the footnotes.
- **Compact instead of restarting.** [Chat Compaction](../chat-compaction/chat-compaction.md) trims context to control both cost and context-window pressure without losing the thread.
- **Notice expensive patterns.** If a single response is surprisingly costly, it's usually because a lot of context was sent. That's a signal to attach fewer files or narrow the task.

---

## Notes

- Costs are calculated locally from token counts and model pricing — they reflect provider usage but are not a substitute for your provider's official billing.
- Fabric's own hosted models and external providers are both costed the same way, using each model's configured rates.
- Continuation steps inside an automated loop don't each show a separate footnote; the cost is reported on the completed response.
