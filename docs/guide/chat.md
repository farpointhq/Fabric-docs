# Chat Interface

Master Fabric's chat interface for productive AI conversations.

## Interface Overview

![Chat Interface](../assets/screenshots/chat-interface.png)

### Components

1. **Sidebar** - Chat history and navigation
2. **Chat Area** - Conversation with AI
3. **Input Box** - Type your messages
4. **Model Selector** - Choose AI model
5. **Settings** - Configure behavior

## Conversations

### Starting a New Chat

- Click the **+** button in the sidebar
- Use `⌘ N` keyboard shortcut
- Select "New Chat" from the menu

### Managing Chats

- **Rename**: Right-click on a chat
- **Delete**: Swipe left or right-click > Delete
- **Search**: Use the search bar to find past conversations

## Input Features

### Markdown Support

Your messages support Markdown:

```markdown
# Heading
**Bold** and *italic*
- Lists
- Work too

`inline code` and code blocks
```

### Code Blocks

Use triple backticks for code:

````markdown
```python
def hello():
    print("Hello, World!")
```
````

### File Attachments

Drag and drop files into the chat:

- Code files (`.js`, `.py`, `.ts`, etc.)
- Images (for vision-capable models)
- Documents (`.md`, `.txt`)

## Response Controls

### Stopping Generation

- Press `Escape` to stop
- Click the stop button

### Copying Responses

- Click the copy button on any message
- Select text and use `⌘ C`

### Code Actions

For code blocks in responses:

- **Copy** - Copy the code
- **Insert** - Insert into your editor (with extension)
- **Run** - Execute in terminal (agentic mode)
