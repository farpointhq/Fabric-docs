# Tool Calling

AI can use tools to interact with your environment.

## Available Tools

### File Operations

| Tool | Description |
|------|-------------|
| `read_file` | Read contents of a file |
| `write_file` | Create or update a file |
| `list_directory` | List files in a directory |
| `search_files` | Search for files by pattern |

### Code Execution

| Tool | Description |
|------|-------------|
| `run_command` | Execute shell commands |
| `run_script` | Run code in a sandbox |

### Search

| Tool | Description |
|------|-------------|
| `grep` | Search file contents |
| `find` | Find files by name |

## How Tools Work

When the AI needs to use a tool:

1. **Request**: AI requests to use a tool
2. **Approval**: You approve or deny
3. **Execution**: Tool runs and returns results
4. **Continue**: AI uses results to continue

### Example Flow

```
You: What files are in the src directory?

AI: I'll list the directory contents.
[Tool: list_directory("./src")]

Approving...

Results:
- components/
- hooks/
- utils/
- App.tsx
- index.tsx

AI: The src directory contains components, hooks,
    utils folders, and the main App.tsx and index.tsx files.
```

## Permissions

Configure which tools the AI can use:

### Always Allow

Tools that run without asking:

- `read_file`
- `list_directory`
- `search_files`

### Ask First

Tools that require approval:

- `write_file`
- `run_command`
- `delete_file`

### Never Allow

Disabled tools:

- Configure in Settings > Tools

## Safety

### Command Filtering

Dangerous commands are blocked:

- `rm -rf /`
- `sudo` operations
- Network operations

### Sandbox Execution

Code runs in isolation:

- No access to system files
- Limited network access
- Resource limits applied
