# Configuration

Customize Fabric to match your workflow.

## API Keys

Fabric supports multiple AI providers. Configure your API keys in Settings.

### Adding API Keys

1. Open **Settings** (`⌘ ,`)
2. Navigate to **API Keys**
3. Enter your keys for each provider

### Supported Providers

| Provider | Models | Get API Key |
|----------|--------|-------------|
| Anthropic | Claude Opus 4.5, Sonnet 4.5, Haiku 4.5 | [console.anthropic.com](https://console.anthropic.com/) |
| OpenAI | GPT-5 Pro, GPT-5.1, GPT-5.1 Codex, GPT-5 Nano | [platform.openai.com](https://platform.openai.com/api-keys) |
| Google | Gemini 3.0 Pro, Gemini 2.5 Flash | [aistudio.google.com](https://aistudio.google.com/app/apikey) |
| OpenRouter | All models | [openrouter.ai](https://openrouter.ai/keys) |

!!! info "OpenRouter"
    OpenRouter provides access to many models through a single API key. Great for trying different models!

## Appearance

### Theme

Fabric follows your system theme by default, or you can choose:

- **Light** - Clean, bright interface
- **Dark** - Easy on the eyes
- **System** - Follows OS preference

### Font Size

Adjust the chat and code font sizes in Settings > Appearance.

## Advanced Settings

### Context Window

Configure how much context to send to the AI:

```yaml
# settings.json
{
  "maxContextTokens": 128000,
  "summarizeAfter": 50000
}
```

### Custom System Prompts

Add custom instructions that apply to all chats:

1. Go to Settings > Advanced
2. Enter your system prompt
3. Save

Example:
```
You are a senior software engineer. Always:
- Consider edge cases
- Suggest tests
- Follow best practices
```

## Configuration File

Fabric stores configuration in:

| Platform | Location |
|----------|----------|
| macOS | `~/Library/Application Support/Fabric/config.json` |
| Windows | `%APPDATA%\Fabric\config.json` |
| Linux | `~/.config/Fabric/config.json` |
