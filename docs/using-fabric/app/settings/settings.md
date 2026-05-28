# Settings

Open the Settings panel by clicking the gear icon in the left sidebar. The panel is organized into tabs that let you configure models, permissions, integrations, terminal profiles, keyboard shortcuts, privacy, and benchmarks.

---

## General

![General Settings](../../../../assets/screenshots/settings/1_general.png)

**Project Description** — Enter a brief summary of your application to personalize AI assistance and improve prompt relevance.

**Chat Management**

* **Enable automatic chat cleanup** — Automatically remove inactive chats after a set number of days.
* **Maximum chat age (days)** — How many days to keep inactive chats before removing them (default: 30).
* **Auto-collapse on final output** — Collapse thinking blocks and tool calls when the model finishes generating a response.

**Notifications**

* **Enable tab notification sound** — Play a sound when a background tab requires user attention.

---

## Models

![Models Settings](../../../../assets/screenshots/settings/2_models.png)

**Helper Model** — The lightweight LLM that analyzes your request, proposes relevant files to edit, and suggests concise tab names before the main model runs. Choose between Medium, Small, or other tiers.

**Subagent Model** — The model used when the assistant spawns a subagent. Options include:

* Same as helper model
* Let the main model decide
* Medium / Small (pin a specific tier)

**LLM Providers** — Add and manage API keys for multiple providers. Expand any provider to view available models and configure API endpoints, temperature, and max tokens.

* **Fabric** — Built-in model provider
* **Anthropic** — Claude models (API key required)
* **OpenAI** — GPT models (API key required)
* Additional providers can be added via the "Add Provider" button

---

## Permissions

![Permissions Settings](../../../../assets/screenshots/settings/3_permissions.png)

**Commands** — Whitelist safe terminal commands the AI is allowed to run without explicit approval. Default allowed commands include `ls`, `pwd`, `stat`, `file`, `du`, `df`, `cat`, `head`, `tail`, `grep`, and others. Use the "Add" button to add custom commands.

**Directories** — Configure which directories the AI can access for file operations. This restricts the scope of file reads, writes, and searches to approved locations.

---

## Skills

![Skills Settings](../../../../assets/screenshots/settings/4_skills.png)

**Agent Skills** — Reusable instruction packs the agent loads on demand when a task matches. Skills can be:

* **Project-scoped** — Dropped into your project as a `SKILL.md` file
* **User-scoped** — Installed globally for your user account
* **From the Marketplace** — Browse and install community-made skills

Each skill can be toggled on or off individually. Use **Browse Marketplace** to discover new skills or **Install from source** to add a custom one.

---

## MCP

![MCP Settings](../../../../assets/screenshots/settings/5_mcp.png)

**MCP Servers** — Add and manage Model Context Protocol servers. Connected servers expose tools, resources, and prompts that the LLM can use. Each server shows its version, number of tools, and connection status. Use **Disconnect**, **Edit**, or **Remove** to manage existing servers, or **Add Server** to connect a new one.

**MCP Features**

* **Resource @ Mentions** — Type `@` in the chat input to browse and attach MCP server resources as context.
* **Prompts as Slash Commands** — MCP server prompts appear as slash commands (e.g. `/server/prompt`) in the composer.
* **Enable MCP Tools** — Allow the LLM to call MCP server tools. Individual tool permissions can be managed per-tool.

**Tool Permissions** — Control which MCP tools are allowed or denied. Rules are created automatically when you click "Always Allow" on tool permission prompts in chat.

---

## Terminal

![Terminal Settings](../../../../assets/screenshots/settings/6_terminal.png)

**Default Profile** — The shell profile used when creating a new terminal with the "+" button. Click "Set Default" on any profile below to change it.

**Detected Profiles** — Shells automatically detected on your system:

* Windows PowerShell
* Command Prompt
* Git Bash
* Ubuntu (WSL)

**Custom Profiles** — User-defined shell profiles. Custom profile management is coming soon.

---

## Shortcuts

![Shortcuts Settings](../../../../assets/screenshots/settings/7_shortcuts.png)

**Diff Viewer**

| Action | Shortcut |
|--------|----------|
| Scroll To Previous Change | `W` |
| Accept Highlighted Change | `A` |
| Scroll to Next Change | `S` |
| Discard Highlighted Change | `D` |

**Chat View**

| Action | Shortcut |
|--------|----------|
| Enter Prompt | `↵` |
| Record Voice (Push-to-talk) | `Right Alt` |
| Send Latest Agent to Background | `Ctrl + B` |

**File Search**

| Action | Shortcut |
|--------|----------|
| Search Files | `Ctrl + F` |
| Toggle Case Sensitive | `Ctrl + I` |
| Toggle Regex | `Ctrl + R` |

**Window**

| Action | Shortcut |
|--------|----------|
| Collapse Terminal | `Ctrl + \`` |

---

## Privacy

![Privacy Settings](../../../../assets/screenshots/settings/8_privacy.png)

**Usage Analytics**

* **Allow usage analytics** — Share interaction data to help improve the app. No prompt content or files are ever collected.

**Error Reporting Settings**

Fabric includes automatic error reporting to help improve the application. When an error occurs, you can:

* View details about the error
* Describe what you were doing when the error occurred
* Submit a report to the development team
* Restart the application

Error reports are sent to the Fabric GitHub repository as issues and include the error message, stack trace, app version, platform information, and your description (if provided). Error reports do not include any personal information or file contents.

---

## Benchmark

![Benchmark Settings](../../../../assets/screenshots/settings/9_benchmark.png)

**Run Benchmark** — Evaluate model performance on standardized coding tasks. Select a benchmark from the dropdown and click **Run Benchmark** to start the evaluation.

**Benchmark Results** — View historical benchmark runs and compare scores across different models and configurations.
