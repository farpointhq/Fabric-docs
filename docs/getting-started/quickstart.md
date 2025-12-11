# Quick Start

Get productive with Fabric in 5 minutes.

!!! info "Prerequisites"
    Make sure you've [installed Fabric](installation.md) and added at least one API key.

## Your First Chat

### 1. Launch Fabric

Open Fabric from your Applications folder (macOS), Start Menu (Windows), or run the AppImage (Linux).

### 2. Open a Project (Optional but Recommended)

For the best experience, open a project folder:

1. Click **File** → **Open Project** (or press `⌘ O` / `Ctrl O`)
2. Select your project folder
3. Fabric will index your files for context-aware assistance

!!! tip "Why Open a Project?"
    When you open a project, Fabric can:

    - Suggest relevant files automatically
    - Understand your codebase structure
    - Follow your existing coding patterns
    - Search through your files when needed

### 3. Select a Model

Click the model selector in the toolbar to choose your AI model:

| Model | When to Use |
|-------|-------------|
| **Claude 4.5 Sonnet** | Best for complex tasks, code review, debugging |
| **Claude 4.5 Haiku** | Quick questions, simple explanations |
| **GPT-5 Pro** | General coding assistance |
| **GPT-5.1 Mini** | Fast, cost-effective responses |

!!! success "Recommended for Getting Started"
    **Claude 4.5 Sonnet** offers the best balance of intelligence and speed for most coding tasks.

### 4. Start Chatting!

Type your question in the input box at the bottom and press `Enter` to send.

---

## Example Prompts to Try

### Explain Code

Paste code and ask for an explanation:

```
Explain what this code does and suggest any improvements:

function debounce(fn, delay) {
  let timeoutId;
  return (...args) => {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn(...args), delay);
  };
}
```

**What you'll get:** A clear explanation of the debounce pattern, when to use it, and potential improvements like adding TypeScript types or a cancel method.

### Generate Code

Describe what you need:

```
Write a React hook called useLocalStorage that:
- Syncs state with localStorage
- Handles JSON serialization automatically
- Works with TypeScript generics
- Handles SSR (no window on server)
```

**What you'll get:** A complete, production-ready hook with TypeScript types and proper error handling.

### Debug an Error

Paste your error message:

```
I'm getting this error:

TypeError: Cannot read properties of undefined (reading 'map')
  at UserList (UserList.tsx:15:23)

Here's my component:

function UserList({ users }) {
  return (
    <ul>
      {users.map(user => <li key={user.id}>{user.name}</li>)}
    </ul>
  );
}
```

**What you'll get:** Identification of the issue (users is undefined on initial render) and multiple solutions (optional chaining, default value, loading state).

### Code Review

Ask for a thorough review:

```
Review this API handler for security issues, error handling,
and best practices:

app.post('/api/users', async (req, res) => {
  const { email, password } = req.body;
  const user = await db.users.create({ email, password });
  res.json(user);
});
```

**What you'll get:** Identification of issues like missing input validation, password hashing, error handling, and suggestions for improvement.

---

## Adding Files to Context

Fabric works best when it has context about your code.

### Method 1: File Browser

1. Click the **Files** icon in the sidebar (or press `⌘ E` / `Ctrl E`)
2. Navigate to the file you want to include
3. Click the **+** button next to the file name
4. The file will be added to your current message context

You can also paste images directly into the chat input area for image analysis.

!!! tip "Token Awareness"
    Fabric shows you how many tokens your message uses. Keep an eye on this when adding large files—you may want to add only the relevant sections.

---

## Essential Keyboard Shortcuts

Learn these shortcuts to work faster:

| Action | macOS | Windows/Linux |
|--------|-------|---------------|
| **New Chat** | `⌘ N` | `Ctrl N` |
| **Send Message** | `Enter` | `Enter` |
| **Stop Generation** | `Escape` | `Escape` |
| **Toggle Sidebar** | `⌘ B` | `Ctrl B` |
| **Open Settings** | `⌘ ,` | `Ctrl ,` |
| **Search Files** | `⌘ P` | `Ctrl P` |
| **Show All Shortcuts** | `⌘ /` | `Ctrl /` |

[:octicons-arrow-right-24: See all keyboard shortcuts](../reference/shortcuts.md)

---

## Using Multiple Chats

Fabric supports multiple concurrent conversations:

### Tabs

- **New Tab:** Click the **+** button in the tab bar or press `⌘ T`
- **Switch Tabs:** Click on a tab or use `⌘ 1-9` to jump to specific tabs
- **Close Tab:** Click the **×** on a tab or press `⌘ W`

### Chat Groups

Organize related chats into groups:

1. Right-click on a tab
2. Select **Add to Group** → **New Group**
3. Name your group (e.g., "Auth Feature", "Bug Fixes")
4. Drag other tabs into the group

!!! example "Workflow Example"
    Working on a new feature? Create a group with:

    - One chat for implementation questions
    - One chat for writing tests
    - One chat for documentation

---

## Enabling Agentic Mode

For complex, multi-step tasks, enable Agentic Mode:

1. Click the **Agent** toggle in the toolbar
2. Ask for a complex task:

```
Refactor the UserService class to use dependency injection.
Update all the tests and add JSDoc comments.
```

3. Review the AI's plan before it executes
4. Approve or modify each step

!!! warning "Review Before Approving"
    Agentic mode can create, modify, and delete files. Always review the AI's plan and approve each action carefully.

[:octicons-arrow-right-24: Learn more about Agentic Mode](../features/agentic-mode.md)

---

## Tips for Better Results

### Be Specific

Instead of:
```
Fix my code
```

Try:
```
The login function is returning undefined instead of the user object.
Here's the function and the test that's failing.
```

### Provide Context

Instead of:
```
Write a button component
```

Try:
```
Write a Button component that matches the style of our existing
components in src/components/. It should support variants (primary,
secondary, danger) and sizes (sm, md, lg).
```

### Iterate

If the first response isn't quite right, provide feedback:

```
Good start! Can you also:
- Add error handling for the API call
- Include loading state
- Make the retry button optional
```

---

## Next Steps

<div class="grid cards" markdown>

-   :material-chat:{ .lg .middle } **Chat Interface**

    ---

    Learn all the features of the chat interface

    [:octicons-arrow-right-24: Chat guide](../guide/chat.md)

-   :material-swap-horizontal:{ .lg .middle } **Model Selection**

    ---

    Choose the right model for each task

    [:octicons-arrow-right-24: Models guide](../guide/models.md)

-   :material-robot:{ .lg .middle } **Agentic Mode**

    ---

    Let AI handle complex multi-step tasks

    [:octicons-arrow-right-24: Agentic guide](../features/agentic-mode.md)

-   :material-cog:{ .lg .middle } **Configuration**

    ---

    Customize Fabric to your workflow

    [:octicons-arrow-right-24: Configuration](configuration.md)

</div>
