# Built-in Terminal

Fabric ships with a full-featured terminal built directly into the app. Run commands, manage multiple sessions with tabs, split panes side by side, and pipe terminal output straight into the AI chat — without ever leaving the window.

---

## Opening the Terminal

Press `Ctrl Shift ` `` (Windows/Linux) or `⌃ Shift ` `` (Mac) to open a new terminal. The terminal panel appears at the bottom of the window — a full shell session running alongside your chat.

![The built-in terminal](../../../assets/screenshots/built-in-terminal/1.png)

You can also collapse and expand the panel at any time with `Ctrl ` `` / `⌃ ` ``.

---

## Terminal Controls

The terminal header gives you quick access to common actions: create a new session, split the current pane, copy output, and paste into the chat input. The tab bar on the right lets you switch between multiple open sessions.

![Terminal controls and tab bar](../../../assets/screenshots/built-in-terminal/2.png)

- **New terminal** — Opens an additional session. Each terminal is independent with its own scrollback.
- **Split pane** — Splits the current terminal so you can watch two sessions side by side (e.g. a dev server in one, a test runner in the other).
- **Copy** — Copies the terminal selection or buffer to your clipboard.
- **Paste to prompt** — Sends the terminal output straight into the chat input, so you can ask the AI about an error or a command result without copy-pasting manually.

---

## Working with the AI

The built-in terminal is tightly integrated with Fabric's chat. This is what makes it more than just a shell:

- When Fabric runs commands in **agentic mode**, you see them execute in the terminal in real time.
- Use **Paste to prompt** to feed a stack trace or failing test output directly into the conversation: *"here's the error — fix it."*
- Run your dev server or watch process in a split pane while the AI makes changes, so you see the effect immediately.

---

## Keyboard Shortcuts

| Action | Mac | Windows / Linux |
|--------|-----|-----------------|
| New terminal | `⌃ Shift \`` | `Ctrl Shift \`` |
| Split terminal | `⌘ \` | `Ctrl Shift 5` |
| Collapse / expand panel | `⌃ \`` | `Ctrl \`` |
| Focus next pane | `⌥ ⌘ →` | `Alt →` |
| Focus previous pane | `⌥ ⌘ ←` | `Alt ←` |
| Focus terminal tabs | `⌘ Shift \` | `Ctrl Shift \` |
| Paste into terminal | `⌘ V` | `Ctrl V` |
| Kill terminal (tabs focused) | `⌘ ⌫` | `Del` |

---

## Tips

- **Use split panes for long-running processes.** Keep a dev server or `tail -f` log running in one pane while you work in another.
- **Each tab keeps its history.** Switching between terminal tabs preserves the scrollback, so you won't lose output when you jump between sessions.
- **Exited terminals stay visible.** When a process exits, the tab dims but remains so you can read the final output before closing it.
