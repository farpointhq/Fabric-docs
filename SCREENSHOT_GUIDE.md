# Screenshot Capture Guide

This document lists all the screenshots needed for the Fabric documentation. Screenshots should be captured at 2x resolution (Retina) and saved to `docs/assets/screenshots/`.

## Recommended Settings for Screenshots

- **Resolution**: 2880x1800 or similar Retina resolution
- **Window Size**: 1440x900 for full app screenshots
- **Theme**: Capture both light and dark mode versions if possible
- **Format**: PNG with transparency where appropriate

## Required Screenshots

### Homepage & Getting Started

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `hero-screenshot.png` | Full app with sample conversation | index.md |
| `first-launch.png` | Welcome screen on first launch | installation.md |
| `api-key-setup.png` | API key configuration dialog | installation.md, configuration.md |

### Chat Interface

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `main-interface.png` | Full app with sidebar, chat, and input | chat.md |
| `chat-tabs.png` | Multiple tabs open with tab bar visible | chat.md |
| `chat-groups.png` | Tab groups organized by topic | chat.md |
| `model-selector.png` | Model dropdown expanded showing options | chat.md, models.md |
| `file-attachment.png` | Chat input with file attached | chat.md |
| `code-block-response.png` | AI response with code block and actions | chat.md |
| `diff-viewer.png` | Side-by-side diff display | chat.md |

### Sidebar Features

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `sidebar-files.png` | File browser panel | chat.md |
| `sidebar-history.png` | Chat history panel | chat.md |
| `sidebar-database.png` | Database browser panel | chat.md |

### Agentic Mode

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `agentic-toggle.png` | Agentic mode toggle in toolbar | agentic-mode.md |
| `agentic-plan.png` | Task plan display before execution | agentic-mode.md |
| `agentic-progress.png` | Step-by-step execution progress | agentic-mode.md |
| `agentic-approval.png` | Approval dialog for file changes | agentic-mode.md |
| `agentic-results.png` | Final results summary | agentic-mode.md |

### Tool Calling

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `tool-output.png` | Collapsible tool output in chat | tool-calling.md |
| `tool-approval.png` | Tool approval dialog | tool-calling.md |
| `tool-history.png` | Tool call history view | tool-calling.md |

### Settings

| Filename | Description | Page Used On |
|----------|-------------|--------------|
| `settings-general.png` | General settings tab | settings.md |
| `settings-models.png` | Models settings tab | settings.md |
| `settings-permissions.png` | Permissions settings tab | settings.md |
| `settings-shortcuts.png` | Keyboard shortcuts settings | settings.md, shortcuts.md |
| `settings-privacy.png` | Privacy settings tab | settings.md |

## How to Capture Screenshots

### On macOS

1. **Full Window**: `⌘ ⇧ 4`, then press `Space`, click the window
2. **Selection**: `⌘ ⇧ 4`, then drag to select area
3. **Touch Bar**: `⌘ ⇧ 6` (if applicable)

### Tips

- Close unnecessary tabs and clear sample data before capturing
- Use clean, realistic example conversations
- Ensure consistent window sizing across screenshots
- Consider using CleanShot X or similar for annotations

## Adding Screenshots to Documentation

Once captured, place in `docs/assets/screenshots/` and reference in markdown:

```markdown
![Chat Interface](../assets/screenshots/chat-interface.png)
```

For larger screenshots that benefit from lightbox zoom:

```markdown
[![Full Interface](../assets/screenshots/main-interface.png)](../assets/screenshots/main-interface.png)
```

The glightbox plugin will automatically add click-to-zoom functionality.

## Placeholder Images

If you need placeholder images before final screenshots are ready, you can use:

```markdown
!!! note "Screenshot Coming Soon"
    This section will include a screenshot of the [feature name].
```
