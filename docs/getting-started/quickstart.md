# Quick Start

Get productive with Fabric in 5 minutes.

## Your First Chat

1. **Launch Fabric** - Open the application
2. **Select a model** - Choose from the dropdown (Claude 3.5 Sonnet recommended)
3. **Type your prompt** - Ask anything about code!

![First Chat](../assets/screenshots/first-chat.png)

## Example Prompts

Try these to get started:

### Code Explanation

```
Explain what this code does:

function debounce(fn, delay) {
  let timeoutId;
  return (...args) => {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn(...args), delay);
  };
}
```

### Code Generation

```
Write a React hook that:
- Fetches data from an API
- Handles loading and error states
- Supports automatic refetching
```

### Code Review

```
Review this code for potential issues:

async function getUser(id) {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
}
```

## Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| New chat | `⌘ N` |
| Send message | `⌘ Enter` |
| Stop generation | `Escape` |
| Toggle sidebar | `⌘ B` |

See [Keyboard Shortcuts](../reference/shortcuts.md) for the full list.

## Next Steps

- [Chat Interface Guide](../guide/chat.md) - Master the chat interface
- [Model Selection](../guide/models.md) - Choose the right model
- [Agentic Mode](../features/agentic-mode.md) - Let AI handle complex tasks
