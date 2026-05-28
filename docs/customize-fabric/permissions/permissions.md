# Permissions

Fabric operates on a **trust-ladder** — a five-level permission system that controls exactly what the AI agent is allowed to do without asking you first. Every tool call (file edits, shell commands, browser actions, MCP tools) passes through this system before anything happens to your machine.

---

## The Five Permission Modes

You set the permission mode per chat session using the selector in the chat toolbar. The mode is persisted with the session so it survives restarts.

| Mode | Label | What it means |
| :---: | :--- | :--- |
| **0** | **Chat** | Read-only. No writes, no shell commands. Pure conversation. |
| **1** | **Confirm all** | Fabric asks before *every* action — reads, writes, bash commands, everything. Maximum oversight. |
| **2** | **Confirm writes** | Reads and file listing happen silently. Fabric asks before writing files and running shell commands. |
| **3** | **Automatic writes** | File edits happen without asking. Fabric still asks before running shell commands and browser mutations. |
| **4** | **Fabric take the wheel** | Fully autonomous. All tool calls auto-approve. No prompts (except `AskUserQuestion`, which always prompts). |

> [!TIP]
> **"Fabric take the wheel"** is the default for new sessions. If you are working on sensitive infrastructure or want to review each step, switch to **Confirm writes** or **Confirm all** before sending your first message.

---

## What Triggers a Permission Prompt

Even when the mode allows a category, specific circumstances may still raise a prompt. The table below maps tool categories to when they ask:

| Tool Category | Chat | Confirm all | Confirm writes | Auto writes | Take the wheel |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Read file / list dir | auto | **ask** | auto | auto | auto |
| Edit file (project) | deny | **ask** | **ask** | auto | auto |
| Edit file (external) | deny | **ask** | **ask** | **ask** | auto |
| Bash / shell command | deny | **ask** | **ask** | **ask** | auto |
| Screenshot | deny | **ask** | **ask** | **ask** | auto |
| Directory access | **ask** | **ask** | **ask** | **ask** | auto |
| MCP tool | deny | **ask** | **ask** | **ask** | auto |
| Browser mutation | deny | **ask** | **ask** | **ask** | auto |
| Ask user question | **ask** | **ask** | **ask** | **ask** | **ask** |

> [!NOTE]
> `AskUserQuestion` **always** prompts the user regardless of mode — it is a deliberate interaction, not a side effect.

---

## What the Permission Dialog Shows

When Fabric needs approval, a dialog appears in the chat with full context before any action is taken. The exact content depends on the tool type:

### File Edit
- The file path being modified
- A before/after diff of the proposed change
- Whether the file is outside the project root (flagged as "external")
- Options: **Approve**, **Deny**, or **Edit** (modify the content before accepting)

### Shell Command (Bash)
- The exact command string Fabric wants to run
- Options: **Allow once**, **Allow for session** (persists this command prefix for the rest of the session), or **Deny**

### Directory Access
- The directory path and whether the operation is read or write
- Whether the path is outside the project root
- Options: **Allow** or **Deny**

### MCP Tool
- The server name and tool name
- The arguments being passed
- Options: **Allow once**, **Always allow this tool** (persists to chat metadata), or **Deny**

### Browser Script
- The domain the script targets
- A preview of the script content
- Options: **Allow** or **Deny**

---

## Persistent Permissions ("Always Allow")

Some dialogs offer an **Always allow** option. When selected, that permission is saved to the chat's metadata and will not be asked again for the rest of that session:

- **Bash**: Saved as a command-scope prefix (e.g., allowing `npm run` auto-approves all `npm run *` commands)
- **MCP tools**: Saved per tool name on that server
- **File editing**: Tracked as a boolean flag (`fileEditingAllowed`) on the chat record

Persistent permissions are **per-session** — they reset when you start a new chat tab.

---

## Hard Safety Floor

Regardless of permission mode, certain operations are **always blocked** and cannot be approved:

- `rm -rf /`, `rm -rf ~`, `rm -rf .` and variants
- Writing to raw devices (`/dev/sda`, `/dev/nvme*`)
- Filesystem destruction commands (`mkfs`, `dd of=/dev/...`, `fdisk`, `parted`, `wipefs`)
- Fork bombs (`:(){ :|:& };:`)
- Writing or deleting files in protected system paths (`/etc`, `/usr`, `/bin`, `/lib`, `/System`, etc.)

These are enforced by a safety guard that runs at the tool preparation stage — before any permission prompt is even shown. They cannot be overridden by any permission mode.

> [!CAUTION]
> Even in **"Fabric take the wheel"** mode, the safety floor is always active. The mode controls what Fabric *asks* about — the safety floor controls what Fabric *can never do*.

---

## Subagent Permissions

When Fabric spawns a subagent (via DAG tasks or `DelegateTask`), the subagent's permission requests are **forwarded to the parent chat** for approval. The permission dialog will indicate:

- Which subagent is making the request (by name)
- The same tool context as a normal request

The parent session's permission mode governs whether the subagent's request is auto-approved, prompted, or denied. Subagents cannot escalate their own permissions beyond what the parent session allows.

---

## Changing the Mode Mid-Session

You can change the permission mode at any time during a session using the mode selector in the toolbar. The change takes effect immediately for all subsequent tool calls — including any that are currently waiting in a queue. The new mode is saved to the session's metadata and will be restored if the app restarts.
