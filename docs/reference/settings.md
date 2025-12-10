# Settings Reference

All Fabric settings explained.

## API Keys

Configure your AI provider API keys.

| Setting | Description | Default |
|---------|-------------|---------|
| `anthropic_api_key` | Anthropic API key | - |
| `openai_api_key` | OpenAI API key | - |
| `google_api_key` | Google AI API key | - |
| `openrouter_api_key` | OpenRouter API key | - |

## Appearance

| Setting | Description | Default |
|---------|-------------|---------|
| `theme` | Color theme (light/dark/system) | `system` |
| `fontSize` | Chat text size | `14` |
| `codeFontSize` | Code block text size | `13` |
| `fontFamily` | Chat font family | System default |
| `codeFontFamily` | Code font family | `monospace` |

## Chat

| Setting | Description | Default |
|---------|-------------|---------|
| `defaultModel` | Default AI model | `claude-3.5-sonnet` |
| `temperature` | Response randomness (0-2) | `0.7` |
| `maxTokens` | Maximum response length | `4096` |
| `streamResponses` | Enable streaming | `true` |
| `showTimestamps` | Show message times | `false` |

## Context

| Setting | Description | Default |
|---------|-------------|---------|
| `maxContextTokens` | Max tokens to send | `128000` |
| `summarizeThreshold` | When to summarize | `50000` |
| `includeSystemPrompt` | Include custom prompt | `true` |
| `systemPrompt` | Custom system prompt | - |

## Tools

| Setting | Description | Default |
|---------|-------------|---------|
| `enableTools` | Allow tool use | `true` |
| `autoApproveRead` | Auto-approve reads | `true` |
| `autoApproveSearch` | Auto-approve search | `true` |
| `requireApprovalWrite` | Require write approval | `true` |
| `requireApprovalCommand` | Require command approval | `true` |

## Agentic

| Setting | Description | Default |
|---------|-------------|---------|
| `enableAgenticMode` | Allow agentic mode | `true` |
| `showPlanBefore` | Show plan before execution | `true` |
| `maxIterations` | Max autonomous steps | `20` |
| `sandboxMode` | Run in sandbox | `false` |

## Advanced

| Setting | Description | Default |
|---------|-------------|---------|
| `logLevel` | Logging verbosity | `info` |
| `telemetry` | Send usage data | `false` |
| `checkUpdates` | Auto-check for updates | `true` |
| `proxyUrl` | HTTP proxy URL | - |

## Configuration File

Settings are stored in JSON:

```json
{
  "theme": "dark",
  "defaultModel": "claude-3.5-sonnet",
  "temperature": 0.7,
  "enableAgenticMode": true,
  "tools": {
    "autoApproveRead": true,
    "requireApprovalWrite": true
  }
}
```

Location:
- macOS: `~/Library/Application Support/Fabric/config.json`
- Windows: `%APPDATA%\Fabric\config.json`
- Linux: `~/.config/Fabric/config.json`
