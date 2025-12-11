# Settings Reference

Complete reference for all Fabric settings, organized by category.

**Open Settings:** Press `⌘ ,` (macOS) or `Ctrl ,` (Windows/Linux)

---

## General

Configure project settings, chat management, and feature toggles.

### Project Description

| Setting | Description |
|---------|-------------|
| **Project Description** | Optional description of your project that helps the AI understand your codebase context |

Set this in **Settings** → **General** → **Project Description**. This description is included in the system prompt when chatting.

### Chat Management

| Setting | Description | Default |
|---------|-------------|---------|
| **Enable Automatic Chat Cleanup** | Automatically removes inactive chats after a set number of days | `false` |
| **Maximum Chat Age (days)** | Number of days before inactive chats are deleted | 30 |

Configure in **Settings** → **General** → **Chat Management**.

### Web Search

| Setting | Description | Default |
|---------|-------------|---------|
| **Enable Web Search** | Allow supported models to search the web during generation | `true` |

When enabled, models that support web search (like Claude) can access current information from the internet.

### File Tag Preprocessing

| Setting | Description | Default |
|---------|-------------|---------|
| **Enable File Tag Preprocessing** | Replace historical `<file>` tags with `<previously_proposed_edit>` tags before sending to LLM | `false` |

This experimental feature may help reduce confusion but could impact model performance.

### Clear Application Cache

Clear all saved settings, model configurations, and cached application data. This requires an app restart.

**Settings** → **General** → **Clear Cache**

---

## Models

Configure AI providers, API keys, and model settings.

### Provider Management

Fabric supports multiple AI providers. Add and configure providers in **Settings** → **Models**.

**Supported Providers:**

- **Anthropic** (Claude models)
- **OpenAI** (GPT models)
- **Google** (Gemini models)
- **OpenRouter** (Multi-provider access)
- **Custom OpenAI-Compatible Servers** (Local models, custom endpoints)

### API Keys

Each provider requires an API key:

| Provider | Get Your Key |
|----------|--------------|
| **Anthropic** | [console.anthropic.com](https://console.anthropic.com/) → API Keys |
| **OpenAI** | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) |
| **Google** | [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey) |
| **OpenRouter** | [openrouter.ai/keys](https://openrouter.ai/keys) |

!!! tip "API Key Security"
    Your API keys are encrypted and stored locally. They are never sent to Farpoint servers.

### Default Model Selection

| Setting | Description |
|---------|-------------|
| **Default Chat Model** | Model used for new chat conversations |
| **Default Merge Model** | Model used for file summarization and merging |

Select models from **Settings** → **Models** by clicking the radio button next to a model name.

### Model Customization

For each model, you can customize:

| Setting | Description |
|---------|-------------|
| **Temperature** | Response randomness (0.0 - 2.0) |
| **Max Tokens** | Maximum response length |
| **Reasoning Effort** | For models like o1/o3: Low, Medium, or High |
| **API Endpoint** | Custom endpoint for OpenAI-compatible providers |

!!! info "Temperature Guide"
    - **0.0 - 0.3**: More focused, deterministic responses
    - **0.4 - 0.7**: Balanced creativity and consistency (default)
    - **0.8 - 1.0**: More creative, varied responses
    - **1.0+**: Experimental, may be incoherent

### Adding Custom Models

1. Go to **Settings** → **Models**
2. Expand a provider
3. Click **+ Add Model**
4. Enter the model ID and configure settings
5. Click **Save**

This is useful for:
- Local LLM servers (Ollama, LM Studio, vLLM)
- Custom OpenAI-compatible endpoints
- New models not yet in Fabric's defaults

---

## Permissions

Control what actions the AI can take on a per-chat basis.

!!! warning "Per-Chat Permissions"
    Permissions are managed per-chat, not globally. You must have an active chat to configure permissions.

### Bash Command Allowlist

Manage which bash commands the AI can run without asking for approval.

**Settings** → **Permissions** → **Allowed Commands**

- **Add Command**: Enter a command pattern and click Add
- **Remove Command**: Click the delete icon next to a command
- Commands are matched as exact strings (e.g., `git status`)

### Examples

Common commands to allowlist:

```
git status
npm test
ls -la
cat package.json
pwd
```

!!! tip "Security Note"
    Only allowlist read-only or safe commands. Fabric asks for approval before running commands not on the allowlist.

---

## Shortcuts

View all keyboard shortcuts for Fabric.

**Settings** → **Shortcuts**

Shortcuts are organized by category:

- **General**: Window management, settings, help
- **Chat**: New chat, send message, cancel
- **Navigation**: Switch tabs, focus search
- **Text Editing**: Format code, insert snippets

!!! info "Customization Not Available"
    Keyboard shortcuts are currently fixed and cannot be customized. This feature may be added in a future release.

See [Keyboard Shortcuts](shortcuts.md) for the complete list.

---

## Privacy

Control data collection and privacy settings.

### Anonymous Usage Analytics

| Setting | Description | Default |
|---------|-------------|---------|
| **Allow Anonymous Usage Analytics** | Share anonymous interaction data to help improve Fabric | `false` |

**Settings** → **Privacy** → **Anonymous Usage Analytics**

!!! info "What We Collect"
    When enabled, we collect:

    - Which buttons are clicked
    - How users navigate through screens
    - Feature usage patterns

    We **never** collect:

    - Prompt content
    - Code or file contents
    - Usernames or personal information
    - API keys

All sensitive areas are automatically masked from recordings.

### Error Reporting

**Settings** → **Privacy** → **Error Reporting Settings**

When an error occurs, you'll see a screen that allows you to:

- View error details
- Describe what you were doing when the error occurred
- Submit a report to the development team
- Restart the application

Error reports include:

- Error message and stack trace
- App version and platform information
- Your description (if provided)

!!! tip "Privacy Note"
    Error reports do not include personal information or file contents unless you explicitly include them in your description.

---

## Benchmark

Test and compare model performance on your codebase.

**Settings** → **Benchmark**

The benchmark feature allows you to:

1. Select a project to benchmark
2. Choose models to test
3. Run coding tasks against each model
4. Compare performance, speed, and cost

!!! info "Project Required"
    You must have an active project open to run benchmarks.

---

## Data Storage

All Fabric data is stored locally on your machine.

### Storage Locations

| Platform | Location |
|----------|----------|
| **macOS** | `~/Library/Application Support/Fabric/` |
| **Windows** | `%APPDATA%\Fabric\` |
| **Linux** | `~/.config/Fabric/` |

### What's Stored

- **Settings**: User preferences, API keys (encrypted)
- **Chat History**: Conversation logs per project
- **Model Configurations**: Custom model settings
- **Permissions**: Per-chat command allowlists
- **Cache**: Indexed file summaries, embeddings

### Clearing Data

**Clear Cache**: **Settings** → **General** → **Clear Application Cache Data**

This removes:

- Saved settings
- Model configurations
- Cached application data

Requires app restart after clearing.

---

## Theme

Fabric supports light and dark themes.

| Setting | Default |
|---------|---------|
| **Theme** | Dark |

!!! info "Theme Switching"
    Theme switching via UI is not yet implemented. The app currently uses dark theme by default. Light theme support exists in the codebase but cannot be toggled from settings yet.
