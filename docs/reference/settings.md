# Settings Reference

Complete reference for all Fabric settings, organized by category.

**Open Settings:** Press `⌘ ,` (macOS) or `Ctrl ,` (Windows/Linux)

---

## API Keys

Configure your AI provider API keys. You need at least one key to use Fabric.

### Anthropic (Claude)

| Setting | Description |
|---------|-------------|
| **API Key** | Your Anthropic API key from [console.anthropic.com](https://console.anthropic.com) |

Get your key: [Anthropic Console](https://console.anthropic.com/) → API Keys → Create Key

### OpenAI (GPT)

| Setting | Description |
|---------|-------------|
| **API Key** | Your OpenAI API key from [platform.openai.com](https://platform.openai.com/api-keys) |
| **Organization ID** | Optional. Your OpenAI organization ID |

Get your key: [OpenAI Platform](https://platform.openai.com/api-keys) → API Keys → Create new secret key

### Google (Gemini)

| Setting | Description |
|---------|-------------|
| **API Key** | Your Google AI API key from [aistudio.google.com](https://aistudio.google.com/app/apikey) |

Get your key: [Google AI Studio](https://aistudio.google.com/app/apikey) → Get API key

### OpenRouter

| Setting | Description |
|---------|-------------|
| **API Key** | Your OpenRouter API key from [openrouter.ai](https://openrouter.ai/keys) |

OpenRouter provides access to multiple providers through a single API.

!!! tip "API Key Security"
    Your API keys are stored locally and encrypted. They are never sent to Farpoint servers.

---

## General

Basic application settings.

### Default Model

| Setting | Description | Default |
|---------|-------------|---------|
| **Default Model** | Model used for new conversations | Claude 3.5 Sonnet |

Choose from any model you have access to. This can be changed per-conversation.

### Project Settings

| Setting | Description | Default |
|---------|-------------|---------|
| **Default Project** | Project to open on startup | Last opened |
| **Auto-index Files** | Automatically index project files | `true` |
| **Ignore Patterns** | Files to exclude from indexing | `.git, node_modules, dist` |

### Updates

| Setting | Description | Default |
|---------|-------------|---------|
| **Check for Updates** | Automatically check for new versions | `true` |
| **Auto-download Updates** | Download updates automatically | `false` |

---

## Appearance

Customize the visual appearance of Fabric.

### Theme

| Setting | Options | Default |
|---------|---------|---------|
| **Theme** | Light, Dark, System | System |

System theme follows your operating system's light/dark mode setting.

### Typography

| Setting | Description | Default |
|---------|-------------|---------|
| **Font Size** | Base text size in chat | 14px |
| **Code Font Size** | Text size in code blocks | 13px |
| **Font Family** | Chat text font | System UI |
| **Code Font Family** | Code block font | JetBrains Mono, Menlo, monospace |
| **Line Height** | Space between lines | 1.5 |

### Layout

| Setting | Description | Default |
|---------|-------------|---------|
| **Sidebar Width** | Default sidebar width | 260px |
| **Show Line Numbers** | Show line numbers in code blocks | `true` |
| **Compact Mode** | Reduce spacing in UI | `false` |

---

## Chat

Configure chat behavior and AI responses.

### Response Settings

| Setting | Description | Default |
|---------|-------------|---------|
| **Stream Responses** | Show responses as they generate | `true` |
| **Show Timestamps** | Display message timestamps | `false` |
| **Copy Button** | Show copy button on messages | `true` |

### AI Behavior

| Setting | Description | Default | Range |
|---------|-------------|---------|-------|
| **Temperature** | Response randomness | 0.7 | 0.0 - 2.0 |
| **Max Tokens** | Maximum response length | 4096 | 100 - 128000 |
| **Top P** | Nucleus sampling parameter | 1.0 | 0.0 - 1.0 |

!!! info "Temperature Guide"
    - **0.0 - 0.3**: More focused, deterministic responses
    - **0.4 - 0.7**: Balanced creativity and consistency
    - **0.8 - 1.0**: More creative, varied responses
    - **1.0+**: Experimental, may be incoherent

### System Prompt

| Setting | Description | Default |
|---------|-------------|---------|
| **Custom System Prompt** | Additional instructions for the AI | Empty |
| **Include in Context** | Whether to include system prompt | `true` |

Example system prompts:

```
You are a senior TypeScript developer. Prefer functional programming
patterns and always include proper error handling.
```

```
When reviewing code, check for:
- Security vulnerabilities (OWASP Top 10)
- Performance issues
- Accessibility (WCAG)
- Test coverage
```

---

## Context

Configure how Fabric manages conversation context.

### Context Window

| Setting | Description | Default |
|---------|-------------|---------|
| **Max Context Tokens** | Maximum tokens to send to AI | Model-dependent |
| **Include File Context** | Auto-include opened files | `true` |
| **Context Preview** | Show context size indicator | `true` |

### Auto-Summarization

| Setting | Description | Default |
|---------|-------------|---------|
| **Enable Summarization** | Summarize long conversations | `true` |
| **Summarize Threshold** | Token count to trigger summary | 50,000 |
| **Summary Model** | Model for summarization | Same as chat |

When enabled, Fabric automatically summarizes earlier parts of long conversations to stay within context limits.

### File Handling

| Setting | Description | Default |
|---------|-------------|---------|
| **Max File Size** | Largest file to include | 1MB |
| **Binary File Handling** | How to handle binary files | Skip |
| **Include Hidden Files** | Include dotfiles | `false` |

---

## Permissions

Control what actions the AI can take.

### Tool Permissions

| Tool | Options | Default |
|------|---------|---------|
| **File Read** | Always Allow / Ask Once / Always Ask | Always Allow |
| **File Write** | Always Allow / Ask Once / Always Ask | Ask Once |
| **File Delete** | Always Allow / Ask Once / Always Ask | Always Ask |
| **Shell Commands** | Always Allow / Ask Once / Always Ask | Ask Once |
| **Web Requests** | Always Allow / Ask Once / Always Ask | Always Ask |
| **Screenshots** | Always Allow / Ask Once / Always Ask | Always Ask |

### Command Safety

| Setting | Description | Default |
|---------|-------------|---------|
| **Block Dangerous Commands** | Prevent obviously harmful commands | `true` |
| **Command Allowlist** | Commands that don't need approval | `git status, npm test, ls` |
| **Command Blocklist** | Commands always blocked | `rm -rf /, sudo rm` |

### Path Restrictions

| Setting | Description | Default |
|---------|-------------|---------|
| **Allowed Paths** | Directories tools can access | Project directory |
| **Restricted Paths** | Directories tools cannot access | `/etc, /System, ~/Library` |

---

## Agentic Mode

Configure autonomous task execution.

### Execution Settings

| Setting | Description | Default |
|---------|-------------|---------|
| **Enable Agentic Mode** | Allow agentic features | `true` |
| **Show Plan** | Display plan before execution | `true` |
| **Require Plan Approval** | Must approve plan to continue | `true` |
| **Max Steps** | Maximum autonomous steps | 20 |
| **Step Timeout** | Max time per step | 120s |

### Safety Settings

| Setting | Description | Default |
|---------|-------------|---------|
| **Sandbox Mode** | Run in isolated environment | `false` |
| **Auto-Revert on Error** | Undo changes if task fails | `false` |
| **Require Final Review** | Review changes before accepting | `true` |

### Approval Workflow

| Setting | Description | Default |
|---------|-------------|---------|
| **Approval Level** | Strict / Balanced / Permissive | Balanced |
| **Batch Approvals** | Allow "Approve All Similar" | `true` |
| **Pause on Error** | Stop and ask on errors | `true` |

---

## Shortcuts

Customize keyboard shortcuts. See [Keyboard Shortcuts](shortcuts.md) for the full list.

### Customizing Shortcuts

1. Go to **Settings** → **Shortcuts**
2. Click on any shortcut
3. Press your new key combination
4. Click **Save**

### Resetting Shortcuts

Click **Reset to Defaults** to restore original shortcuts.

---

## Privacy

Control data collection and privacy settings.

### Telemetry

| Setting | Description | Default |
|---------|-------------|---------|
| **Send Usage Analytics** | Anonymous usage statistics | `false` |
| **Send Error Reports** | Crash and error reports | `true` |

!!! info "What We Collect"
    - **Usage Analytics** (opt-in): Feature usage, model selection, session duration
    - **Error Reports** (opt-in): Crash logs, stack traces (no code or personal data)

    We **never** collect: Your code, conversations, API keys, or personal information.

### Data Storage

| Setting | Description | Default |
|---------|-------------|---------|
| **Clear Chat History** | Delete all conversation history | - |
| **Clear Cache** | Delete cached data | - |
| **Export Data** | Download all your data | - |

### Local Data Location

Your data is stored locally:

| Platform | Location |
|----------|----------|
| **macOS** | `~/Library/Application Support/Fabric/` |
| **Windows** | `%APPDATA%\Fabric\` |
| **Linux** | `~/.config/Fabric/` |

---

## Models

Configure available AI models.

### Enabled Models

Toggle which models appear in the model selector:

| Provider | Models |
|----------|--------|
| **Anthropic** | Claude 3.5 Sonnet, Claude 3.5 Haiku, Claude 3 Opus |
| **OpenAI** | GPT-4o, GPT-4o Mini, GPT-4 Turbo |
| **Google** | Gemini 1.5 Pro, Gemini 1.5 Flash |
| **OpenRouter** | All available models |

### Model-Specific Settings

Configure per-model settings:

| Setting | Description |
|---------|-------------|
| **Display Name** | Custom name in model selector |
| **Default Temperature** | Override default temperature |
| **Max Context** | Override context window |

---

## Advanced

Expert settings for advanced users.

### Debugging

| Setting | Description | Default |
|---------|-------------|---------|
| **Log Level** | Logging verbosity (debug/info/warn/error) | info |
| **Show Developer Tools** | Enable DevTools access | `false` |
| **Verbose Tool Output** | Show full tool responses | `false` |

### Network

| Setting | Description | Default |
|---------|-------------|---------|
| **Proxy URL** | HTTP proxy for API calls | None |
| **Request Timeout** | API request timeout | 120s |
| **Retry Count** | Number of retries on failure | 3 |

### Performance

| Setting | Description | Default |
|---------|-------------|---------|
| **Hardware Acceleration** | Use GPU for rendering | `true` |
| **Max Memory** | Memory limit for indexing | 512MB |
| **Background Indexing** | Index files when idle | `true` |

---

## Configuration File

Settings are stored in JSON format at these locations:

| Platform | Path |
|----------|------|
| **macOS** | `~/Library/Application Support/Fabric/config.json` |
| **Windows** | `%APPDATA%\Fabric\config.json` |
| **Linux** | `~/.config/Fabric/config.json` |

### Example Configuration

```json
{
  "appearance": {
    "theme": "dark",
    "fontSize": 14,
    "codeFontSize": 13
  },
  "chat": {
    "defaultModel": "claude-3.5-sonnet",
    "temperature": 0.7,
    "maxTokens": 4096,
    "streamResponses": true
  },
  "permissions": {
    "fileRead": "always_allow",
    "fileWrite": "ask_once",
    "fileDelete": "always_ask",
    "shellCommands": "ask_once"
  },
  "agentic": {
    "enabled": true,
    "showPlan": true,
    "maxSteps": 20
  },
  "privacy": {
    "telemetry": false,
    "errorReports": true
  }
}
```

!!! warning "Manual Editing"
    If you edit the config file manually, restart Fabric for changes to take effect. Invalid JSON will be ignored.

---

## Resetting Settings

### Reset Individual Settings

In the Settings panel, each section has a **Reset** button to restore defaults for that section.

### Reset All Settings

1. Go to **Settings** → **Advanced**
2. Click **Reset All Settings**
3. Confirm the reset

This will not delete your chat history or API keys.

### Factory Reset

To completely reset Fabric:

1. Quit Fabric
2. Delete the configuration directory (see paths above)
3. Restart Fabric

!!! danger "Factory Reset"
    This deletes all settings, chat history, and cached data. Export your data first if needed.
