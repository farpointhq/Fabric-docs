# Tool Calling

Understand how Fabric's AI uses tools to interact with your development environment.

## What is Tool Calling?

Tool calling allows the AI to go beyond text responses and take actions in your environment:

- **Read files** to understand your code
- **Write and edit files** to implement changes
- **Execute commands** to run tests, builds, and scripts
- **Search** through your codebase
- **Take screenshots** for visual context

These tools enable powerful workflows while keeping you in control through permission settings.

---

## How Tools Work

```mermaid
sequenceDiagram
    participant You
    participant Fabric
    participant AI
    participant Tool

    You->>Fabric: "Run the tests"
    Fabric->>AI: Process request
    AI->>Fabric: Tool call: bash("npm test")
    Fabric->>You: Permission request
    You->>Fabric: Approve
    Fabric->>Tool: Execute command
    Tool->>Fabric: Output/result
    Fabric->>AI: Continue with result
    AI->>Fabric: "Tests passed! Here's the summary..."
    Fabric->>You: Display response
```

### Tool Call Flow

1. **You send a message** - Your request may require tool use
2. **AI decides** - The AI determines which tools are needed
3. **Permission check** - Fabric checks if approval is needed
4. **Execution** - The tool runs if approved
5. **Result processing** - AI uses the result to continue
6. **Response** - You see the final response with tool outputs

---

## Available Tools

### File Operations

#### Read

Read file contents to understand code.

| Property | Value |
|----------|-------|
| **Permission** | Auto-approved |
| **Use case** | Understanding code, getting context |

```
Can you explain what src/utils/auth.ts does?
```

The AI will read the file and provide an explanation.

#### Write

Create new files.

| Property | Value |
|----------|-------|
| **Permission** | Ask once (configurable) |
| **Use case** | Creating new components, utilities |

```
Create a new React component for displaying user profiles
```

#### Edit

Modify existing files with surgical precision.

| Property | Value |
|----------|-------|
| **Permission** | Ask once (configurable) |
| **Use case** | Bug fixes, refactoring, adding features |

```
Add error handling to the fetchUser function in api.ts
```

The AI shows you the exact changes before applying.

#### Delete

Remove files (use with caution).

| Property | Value |
|----------|-------|
| **Permission** | Always ask |
| **Use case** | Cleanup, removing deprecated files |

```
Delete all .bak files in the project
```

!!! danger "Deletion is Permanent"
    File deletion cannot be undone through Fabric. Make sure you have version control or backups.

### Search Tools

#### Glob

Find files by pattern.

| Property | Value |
|----------|-------|
| **Permission** | Auto-approved |
| **Use case** | Finding files, understanding structure |

```
Find all TypeScript files in the components directory
```

#### Grep (Ripgrep)

Search file contents using patterns.

| Property | Value |
|----------|-------|
| **Permission** | Auto-approved |
| **Use case** | Finding usages, locating code |

```
Where is the UserContext defined and used?
```

The AI searches your codebase and shows relevant locations.

### Code Execution

#### Bash

Execute shell commands.

| Property | Value |
|----------|-------|
| **Permission** | Ask once (configurable) |
| **Use case** | Running tests, builds, installations |

**Safe commands** (often auto-approved):
```
npm test
npm run build
git status
ls -la
```

**Risky commands** (always require approval):
```
rm -rf
sudo
npm publish
git push --force
```

!!! warning "Command Safety"
    Fabric blocks obviously dangerous commands by default. Always review commands before approving.

### Visual Tools

#### Screenshot

Capture screen regions for visual context.

| Property | Value |
|----------|-------|
| **Permission** | Always ask |
| **Use case** | UI debugging, visual verification |

```
Take a screenshot of the current page and identify any layout issues
```

---

## Permission System

### Permission Levels

Configure how tools request approval:

| Level | Behavior |
|-------|----------|
| **Always Allow** | Execute without asking |
| **Ask Once** | Ask first time, remember choice |
| **Always Ask** | Require approval every time |

### Configuring Permissions

1. Open **Settings** (`⌘ ,`)
2. Navigate to **Permissions**
3. Set permissions for each tool category

**Recommended Settings:**

| Tool | Development | Production Work |
|------|-------------|-----------------|
| File Read | Always Allow | Always Allow |
| File Write | Ask Once | Always Ask |
| File Delete | Always Ask | Always Ask |
| Bash | Ask Once | Always Ask |
| Search | Always Allow | Always Allow |
| Screenshot | Always Ask | Always Ask |

### Session Permissions

Permissions can be set per-session:

- **Approve** - Allow this specific action
- **Approve All** - Allow all similar actions this session
- **Deny** - Block this action
- **Deny All** - Block all similar actions this session

Session permissions reset when you close Fabric.

---

## Tool Output Display

### In Chat

Tool outputs appear in collapsible sections:

```
┌─ 🔧 bash: npm test ────────────────────────────────────────┐
│                                                            │
│ PASS src/utils/auth.test.ts                               │
│   ✓ should hash password correctly (12ms)                 │
│   ✓ should verify token (8ms)                             │
│   ✓ should reject expired tokens (5ms)                    │
│                                                            │
│ Tests: 3 passed                                           │
│ Time: 1.234s                                              │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### Tool Call History

View all tool calls in the current conversation:

1. Click the **Tools** icon in the message header
2. See a list of all tool calls
3. Expand any call to see full input/output

---

## Safety Features

### Blocked Commands

Fabric blocks dangerous patterns by default:

```bash
# Always blocked
rm -rf /
sudo rm -rf
:(){ :|:& };:
> /dev/sda

# Blocked without explicit approval
git push --force
npm publish
docker run --privileged
```

### Path Restrictions

By default, tools can only access:

- Your project directory
- Temporary directories
- Explicitly allowed paths

Configure allowed paths in **Settings** → **Permissions** → **Allowed Paths**.

### Rate Limiting

Tools have rate limits to prevent runaway execution:

| Tool | Default Limit |
|------|---------------|
| File Read | 100/minute |
| File Write | 20/minute |
| Bash | 10/minute |
| Search | 50/minute |

If limits are reached, you'll see a warning and can continue manually.

---

## Best Practices

### Be Specific About Files

Instead of:
```
Update the component
```

Try:
```
Update src/components/UserCard.tsx to add a loading state
```

### Verify Before Approving

Always review:

- **File paths** - Is it modifying the right file?
- **Changes** - Do the edits look correct?
- **Commands** - Is the command safe?

### Use Read-Only First

When exploring unfamiliar code:

1. Ask questions first (read-only)
2. Understand the codebase
3. Then request modifications

### Review Command Output

After running commands:

- Check exit codes (0 = success)
- Review any errors or warnings
- Verify expected behavior

---

## Troubleshooting

### Tool Not Working

**File not found:**
```
Error: ENOENT: no such file or directory
```
- Check the file path is correct
- Ensure you're in the right project directory

**Permission denied:**
```
Error: EACCES: permission denied
```
- Check file system permissions
- Ensure Fabric has access to the directory

### Command Fails

**Command not found:**
```
bash: npm: command not found
```
- The tool may not be in PATH
- Try using full path: `/usr/local/bin/npm`

**Timeout:**
```
Command timed out after 60s
```
- Command took too long
- Try breaking into smaller steps
- Check for infinite loops

### Unexpected Behavior

**Wrong file modified:**
- Be more specific with file paths
- Use full paths from project root

**Changes didn't apply:**
- Check for syntax errors in the changes
- Verify the file wasn't locked
- Try the edit again with more context

---

## Tool Reference

### Quick Reference Card

| Tool | Command | Permission | Use For |
|------|---------|------------|---------|
| **Read** | `read_file` | Auto | Understanding code |
| **Write** | `write_file` | Ask once | Creating files |
| **Edit** | `edit_file` | Ask once | Modifying files |
| **Delete** | `delete_file` | Always ask | Removing files |
| **Bash** | `bash` | Ask once | Running commands |
| **Glob** | `glob` | Auto | Finding files |
| **Grep** | `ripgrep` | Auto | Searching content |
| **Screenshot** | `screenshot` | Always ask | Visual capture |

### Tool Parameters

Each tool accepts specific parameters:

**read_file:**
```json
{
  "path": "src/utils/auth.ts",
  "offset": 0,
  "limit": 1000
}
```

**edit_file:**
```json
{
  "path": "src/utils/auth.ts",
  "old_string": "function login(",
  "new_string": "async function login("
}
```

**bash:**
```json
{
  "command": "npm test",
  "timeout": 60000
}
```

---

## Next Steps

- [Agentic Mode](agentic-mode.md) - Use tools autonomously
- [Settings Reference](../reference/settings.md) - Configure tool permissions
- [Chat Interface](../guide/chat.md) - Basic chat without tools
