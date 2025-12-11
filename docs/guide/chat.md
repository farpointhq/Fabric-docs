# Chat Interface

Master Fabric's chat interface for productive AI conversations.

## Interface Overview

The Fabric interface is designed for efficient coding conversations:

```
┌─────────────────────────────────────────────────────────────────┐
│  [Tab Bar]  Chat 1  │  Chat 2  │  Chat 3  │  +                 │
├─────────┬───────────────────────────────────────────────────────┤
│         │                                                       │
│ Sidebar │                  Chat Area                            │
│         │                                                       │
│ • Files │  ┌─────────────────────────────────────────────────┐ │
│ • Chat  │  │ User: How do I optimize this function?         │ │
│   History│  │                                                 │ │
│ • DB    │  │ Assistant: Here are some optimization          │ │
│         │  │ strategies...                                   │ │
│         │  └─────────────────────────────────────────────────┘ │
│         │                                                       │
│         ├───────────────────────────────────────────────────────┤
│         │  [Model: Claude 4.5 Sonnet ▾] [Agentic: Off]         │
│         │  ┌─────────────────────────────────────────────────┐ │
│         │  │ Type your message...                   [Send]   │ │
│         │  └─────────────────────────────────────────────────┘ │
└─────────┴───────────────────────────────────────────────────────┘
```

### Main Components

| Component | Description | Shortcut |
|-----------|-------------|----------|
| **Tab Bar** | Manage multiple chat conversations | `⌘ T` new, `⌘ W` close |
| **Sidebar** | File browser, chat history, database | `⌘ B` toggle |
| **Chat Area** | Conversation display | Scroll to navigate |
| **Model Selector** | Choose AI model | Click to open |
| **Input Box** | Type your messages | `Enter` to send |

---

## Conversations

### Starting a New Chat

=== "Keyboard"

    Press `⌘ N` (macOS) or `Ctrl N` (Windows/Linux)

=== "Mouse"

    Click the **+** button in the tab bar

=== "Menu"

    **File** → **New Chat**

Each new chat starts with a fresh context—perfect for switching topics or starting a new task.

### Chat Tabs

Fabric supports multiple concurrent chats in tabs:

- **Switch tabs:** Click on a tab or press `⌘ 1-9` for tabs 1-9
- **Reorder tabs:** Drag and drop tabs to rearrange
- **Close tab:** Click the **×** or press `⌘ W`
- **Duplicate tab:** Right-click → **Duplicate**

!!! tip "When to Use Multiple Tabs"
    - Working on different features simultaneously
    - Keeping a reference conversation while starting a new one
    - Separating debugging from implementation questions

### Chat Groups

Organize related chats into collapsible groups:

1. **Create a group:** Right-click a tab → **Add to Group** → **New Group**
2. **Name the group:** Enter a descriptive name (e.g., "Auth Feature")
3. **Add more chats:** Drag tabs into the group header
4. **Collapse/expand:** Click the group name

**Example Organization:**

```
📁 Authentication Feature
   └── API Design
   └── Frontend Implementation
   └── Testing

📁 Bug Fixes
   └── Issue #123
   └── Issue #456

📄 General Questions
```

### Managing Chat History

Access past conversations from the sidebar:

1. Click the **History** icon in the sidebar (or press `⌘ H`)
2. Browse or search your conversation history
3. Click a conversation to reopen it

**Actions:**

- **Search:** Type to filter conversations
- **Rename:** Right-click → **Rename**
- **Delete:** Right-click → **Delete** (or swipe left on trackpad)
- **Export:** Right-click → **Export as Markdown**

---

## Message Input

### Writing Messages

The input box supports rich text features:

#### Markdown

Your messages are rendered with full Markdown support:

```markdown
# Headings work
**Bold** and *italic* text
- Bullet lists
- Work great

`inline code` and code blocks:

```python
def hello():
    print("Hello!")
```
```

#### Code Blocks

Use triple backticks with a language identifier for syntax highlighting:

````markdown
```typescript
interface User {
  id: string;
  name: string;
  email: string;
}
```
````

Supported languages include: JavaScript, TypeScript, Python, Go, Rust, Java, C++, SQL, HTML, CSS, and many more.

#### Multi-line Input

- Press `Enter` for a new line
- Press `⌘ Enter` (or `Ctrl Enter`) to send the message

### File Attachments

Add files to your message for context:

#### Drag and Drop

Simply drag files from your file explorer into the chat input area. Supported files:

- **Code files:** `.js`, `.ts`, `.py`, `.go`, `.rs`, `.java`, `.cpp`, `.c`, `.h`, etc.
- **Documents:** `.md`, `.txt`, `.json`, `.yaml`, `.xml`, `.csv`
- **Images:** `.png`, `.jpg`, `.gif`, `.webp` (for vision-capable models)

#### File Browser

1. Open the file browser in the sidebar (`⌘ E`)
2. Navigate to your file
3. Click the **+** button next to the filename
4. The file appears as an attachment in your input

### Image Attachments

For models that support vision (Claude 3, GPT-4o):

1. Drag and drop an image, or
2. Paste from clipboard (`⌘ V`), or
3. Click the image icon in the input toolbar

**Use cases:**

- Share UI mockups for implementation
- Show error screenshots for debugging
- Reference design specifications

---

## Response Controls

### During Generation

While the AI is responding:

| Action | How |
|--------|-----|
| **Stop** | Press `Escape` or click the stop button |
| **Scroll** | Scroll up to read while generation continues |

### After Generation

Once a response is complete:

| Action | How |
|--------|-----|
| **Copy response** | Click the copy icon, or select text and `⌘ C` |
| **Regenerate** | Click regenerate icon or press `⌘ ⇧ R` |
| **Edit and resend** | Click edit on your message |
| **Branch conversation** | Edit a previous message to create a branch |

### Code Block Actions

Code blocks in responses have special actions:

- **Copy:** Copy the code to clipboard
- **Insert:** Insert into your editor (if connected)
- **Run:** Execute in terminal (agentic mode)
- **Apply:** Apply as a diff to existing file

!!! tip "Applying Code Changes"
    When Fabric suggests changes to an existing file, you can click **Apply** to see a diff view and selectively accept changes.

---

## Context and Tokens

### Understanding Tokens

Fabric shows token usage to help you manage context:

```
┌────────────────────────────────────────┐
│  Message tokens: 1,234 / 200,000       │
│  ████████░░░░░░░░░░░░░░░  6%           │
└────────────────────────────────────────┘
```

**What counts as tokens:**

- Your message text
- Attached files
- System prompts
- Previous messages in the conversation

!!! warning "Context Limits"
    Each model has a maximum context window. When you approach the limit:

    - Start a new conversation
    - Remove unnecessary file attachments
    - Summarize earlier parts of the conversation

### Token-Efficient Practices

1. **Attach only relevant files** - Don't add entire directories
2. **Use file excerpts** - Copy specific functions instead of whole files
3. **Reference by name** - "Update the `handleSubmit` function in `Form.tsx`" instead of re-pasting the code
4. **Summarize context** - "Based on our earlier discussion about the auth flow..."

---

## Sidebar Features

### File Browser

Navigate your project files:

- **Open folder:** `⌘ O` to open a project
- **Toggle browser:** `⌘ E` or click the Files icon
- **Search files:** `⌘ P` for quick file search
- **Add to context:** Click **+** next to any file

**File Icons:**

Fabric uses file-type icons so you can quickly identify:
- 📄 Documents (`.md`, `.txt`)
- 🟨 JavaScript/TypeScript
- 🐍 Python
- 🦀 Rust
- 📊 Data files (`.json`, `.yaml`)

### Chat History

Access previous conversations:

- **Open history:** Click History icon or `⌘ H`
- **Search:** Type to filter by content or date
- **Sort:** By date, name, or relevance

### Database Browser

Connect to databases for schema-aware assistance:

1. Click the **Database** icon in the sidebar
2. Click **Add Connection**
3. Enter connection details (PostgreSQL, MySQL, SQLite)
4. Browse tables, columns, and relationships

!!! example "Database-Aware Queries"
    With a database connected, Fabric understands your schema:

    ```
    Write a query to get all users who signed up in the last 30 days
    and have completed at least one order, sorted by order count
    ```

    Fabric will use your actual table and column names.

---

## Advanced Features

### Conversation Branching

Create alternative conversation paths by editing earlier messages:

1. Hover over a previous user message
2. Click the **Edit** icon
3. Modify your message
4. Send to create a new branch

The original conversation is preserved—you can switch between branches using the branch navigator.

### Keyboard Navigation

Navigate the interface entirely with keyboard:

| Action | Shortcut |
|--------|----------|
| Focus chat input | `⌘ L` |
| Focus file browser | `⌘ E` |
| Navigate messages | `↑` / `↓` (in chat area) |
| Previous/next chat | `⌘ [` / `⌘ ]` |

---

## Tips for Effective Conversations

### Structure Your Requests

```markdown
## Task
[What you want to accomplish]

## Context
[Relevant background information]

## Requirements
- [Specific requirement 1]
- [Specific requirement 2]

## Files
@relevant-file.ts
```

### Iterative Refinement

Don't expect perfection on the first try. Iterate:

1. **Initial request:** Get the basic structure
2. **Refinement:** "Can you also add error handling?"
3. **Polish:** "Update the variable names to be more descriptive"

### Use the Right Model

| Task | Recommended Model |
|------|-------------------|
| Complex architecture decisions | Claude 4.5 Sonnet |
| Quick syntax questions | Claude 4.5 Haiku |
| Broad general knowledge | GPT-5 Pro |
| Long document analysis | Gemini 3.0 Pro |

---

## Troubleshooting

### Response is cut off

The model hit its output limit. Try:

- "Please continue from where you left off"
- Break the request into smaller parts

### Wrong file referenced

Be explicit about file paths:

- ❌ "Update the button component"
- ✅ "Update `src/components/ui/Button.tsx`"

### Lost conversation context

For long conversations, provide a summary:

```
Quick recap: We're building a user authentication system.
We've completed the login endpoint and are now working
on the password reset flow.
```

---

## Next Steps

- [Model Selection](models.md) - Choose the right model for your task
- [Code Generation](code-generation.md) - Best practices for generating code
- [Agentic Mode](../features/agentic-mode.md) - Automate complex tasks
