# Agentic Mode

Let AI autonomously plan and execute complex tasks.

## What is Agentic Mode?

Agentic mode allows Fabric to:

- Break down complex tasks into steps
- Execute code and commands
- Read and modify files
- Make autonomous decisions

All with your approval at key checkpoints.

## Enabling Agentic Mode

1. Click the **Agent** toggle in the toolbar
2. Or use the keyboard shortcut `⌘ ⇧ A`

![Enable Agentic Mode](../assets/screenshots/agentic-toggle.png)

## How It Works

### 1. Planning

The AI analyzes your request and creates a plan:

```
Task: Create a REST API endpoint for user authentication

Plan:
1. Create route handler in /api/auth
2. Implement login logic
3. Add JWT token generation
4. Create middleware for protected routes
5. Write tests

Proceed? [Yes] [Modify] [Cancel]
```

### 2. Execution

With your approval, the AI executes each step:

- Creates files
- Writes code
- Runs tests
- Reports progress

### 3. Review

After completion, review all changes:

```
Completed! Created:
- src/api/auth/login.ts
- src/api/auth/middleware.ts
- tests/auth.test.ts

[Accept] [Revert] [Modify]
```

## Safety Features

### Approval Checkpoints

The AI asks before:

- Creating or deleting files
- Running commands
- Making destructive changes

### Sandbox Mode

Optionally run in sandbox:

- Changes are isolated
- Easy to revert
- Safe experimentation

### Audit Trail

Every action is logged:

- What was changed
- When it happened
- Why it was done

## Best Practices

### Good Prompts for Agentic Mode

```
Refactor this module to use dependency injection.
Update all tests to match.
```

```
Create a new React component library with:
- Button, Input, and Select components
- Storybook documentation
- Unit tests
```

### Not Ideal for Agentic Mode

```
What is React?
```
(Simple question - doesn't need agentic mode)

```
Fix everything wrong with my code
```
(Too vague - be specific about what to fix)

## Limitations

- Cannot access external services without API keys
- Some operations require manual approval
- Best for well-defined tasks
