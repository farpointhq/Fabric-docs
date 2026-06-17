# Message Queuing

You don't have to wait for the AI to finish before lining up your next instruction. While a response is generating, anything you type can be queued and sent automatically when the current turn completes — so you can keep your train of thought moving instead of sitting idle.

---

## Queuing a Message

![A message queued while the AI is still generating](../../../assets/screenshots/message-queuing/1.png)

While the AI is generating, type your next message and press `Enter`. Instead of interrupting the current response, the message is added to a **queue** and appears as a chip in a small popover just above the input. The input clears, ready for the next one.

You can queue several messages this way (up to 20 per session). They're held in order and sent one after another once the AI is free.

---

## Managing the Queue

The queue popover shows each pending message as a chip. From there you can:

- **Edit** a queued message in place — click the edit icon, change the text, and save.
- **Remove** a message — click the × on its chip to drop it from the queue.
- **Force-send** a single message now — click its send icon to interrupt the current generation and send just that one immediately.
- **Send all** — flush the entire queue at once.
- **Select multiple** — when more than one message is queued, checkboxes let you act on several at a time (send or remove the selected set).

A quick shortcut: while generating, pressing the **Up arrow** with the cursor at the start of an empty input pulls your most recently queued message back into the input box for editing.

---

## How Queued Messages Are Sent

When the current response finishes, the queue flushes automatically. Multiple queued text messages are combined into a single follow-up turn (separated so the AI can tell them apart), and any attached images or files come along with them.

You can also flush manually: with the input empty while the AI is still generating, pressing `Enter` sends the whole queue immediately.

If you force-send a message mid-generation, Fabric stops the current turn first, then sends your message — useful when you realize you need to correct course right away.

---

## When to Use It

- **Batch up a sequence of steps.** Queue "now write the tests", "then update the README", "then run the linter" while the first task runs.
- **Capture a thought before you lose it.** If something occurs to you mid-response, queue it instead of waiting and forgetting.
- **Correct course immediately.** Spot the AI heading the wrong way? Force-send a correction rather than letting it finish.

---

## Notes

- The queue holds up to 20 messages per chat session. Attempting to queue beyond that shows a brief "queue full" warning.
- Each tab has its own independent queue — queuing in one chat doesn't affect another.
- Queued messages persist their attachments (images and files), not just text.
