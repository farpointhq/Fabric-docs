# Quick Start

**From zero to coding with AI in under 5 minutes.**

## Launch and Go

### Step 1: Open Fabric

Launch it like any other app. No terminal commands, no configuration files.

### Step 2: Point It at Your Code

Click **File** → **Open Project** and select your project folder. Fabric starts learning your codebase immediately.

!!! success "This Is Where the Magic Happens"
    Once Fabric knows your project, it stops being a generic AI and becomes *your* AI:

    - It knows where your auth code lives
    - It follows your naming conventions
    - It suggests files you probably need
    - It understands how your components connect

### Step 3: Pick Your Model

Click the model dropdown and choose based on what you're doing:

| Doing This? | Use This |
|-------------|----------|
| Quick question, simple fix | Fast model (Haiku, GPT Mini) |
| Complex problem, code review | Smart model (Sonnet, GPT-4) |
| Not sure? | Start fast, switch if needed |

!!! tip "You Can Switch Anytime"
    Start with a fast model. If the answer isn't deep enough, switch to a smarter one. Fabric keeps all your context.

### Step 4: Ask Anything

Type a question and hit Enter. That's it. No special syntax, no magic commands.

---

## Try These Right Now

### "Why isn't this working?"

Paste broken code and watch Fabric figure it out:

```
This keeps crashing and I don't know why:

TypeError: Cannot read properties of undefined (reading 'map')
  at UserList (UserList.tsx:15:23)
```

**Fabric will:** Find the bug, explain why it happens, and give you multiple ways to fix it.

### "Build this for me"

Describe what you need in plain English:

```
Create a React hook that saves state to localStorage.
It should handle JSON automatically and work with TypeScript.
```

**Fabric will:** Write production-ready code that matches your project's patterns.

### "Is this code any good?"

Get a second opinion before you ship:

```
Review this for security issues and things I might have missed:

app.post('/api/users', async (req, res) => {
  const { email, password } = req.body;
  const user = await db.users.create({ email, password });
  res.json(user);
});
```

**Fabric will:** Catch the missing input validation, unencrypted password, and lack of error handling.

---

## Give Fabric More Context

The more Fabric knows, the better it helps.

### Add Files to Your Question

Click **Files** in the sidebar, find what you need, and click **+**. Fabric will read that file when answering.

!!! tip "Fabric Often Finds Files Automatically"
    Ask "where do we handle authentication?" and Fabric will search your codebase and pull in the relevant files itself. You don't always need to add them manually.

---

## Shortcuts Worth Learning

| Want to... | Press |
|------------|-------|
| Start fresh | `⌘ N` / `Ctrl N` |
| Stop the AI mid-response | `Escape` |
| Find a file | `⌘ P` / `Ctrl P` |
| See all shortcuts | `⌘ /` / `Ctrl /` |

[:octicons-arrow-right-24: Full shortcut reference](../reference/shortcuts.md)

---

## Work on Multiple Things at Once

Real work isn't linear. You're fixing a bug, get asked about something else, then need to check on that feature from yesterday.

### Use Tabs

Hit `⌘ T` for a new conversation. Each tab keeps its own context. Jump between them without losing your place.

### Group Related Chats

Right-click a tab → **Add to Group** → **New Group**

Name it "Auth Rewrite" or "Sprint 42 Bugs" and drag related tabs in. Stay organized without trying.

---

## Let Fabric Do the Heavy Lifting

Some tasks are too big for a single question-and-answer. Turn on **Agentic Mode** and let Fabric plan and execute multi-step tasks.

```
Refactor UserService to use dependency injection,
update all the tests, and make sure everything still passes.
```

Fabric will:

1. **Show you the plan** before doing anything
2. **Execute each step** with your approval
3. **Verify the results** actually work

!!! warning "You Stay in Control"
    Every file change requires your OK. No surprise commits, no mystery modifications.

[:octicons-arrow-right-24: Deep dive into Agentic Mode](../features/agentic-mode.md)

---

## Get Better Results

### Be Specific About the Problem

❌ `Fix my code`

✅ `The login function returns undefined instead of the user object. Here's the function and the failing test.`

### Reference Your Codebase

❌ `Write a button component`

✅ `Write a Button component matching the style in src/components/. Support primary/secondary/danger variants.`

### Iterate, Don't Start Over

The AI remembers the conversation. Build on what it gave you:

```
Good start! Now also add:
- Error handling for the API call
- A loading spinner
```

---

## What's Next?

You're ready to use Fabric. Here's where to go deeper:

<div class="grid cards" markdown>

-   :material-swap-horizontal:{ .lg .middle } **Master Model Selection**

    ---

    Learn when to use fast models vs. powerful ones

    [:octicons-arrow-right-24: Model guide](../features/models.md)

-   :material-brain:{ .lg .middle } **Unlock Agentic Mode**

    ---

    Let Fabric handle complex multi-step tasks

    [:octicons-arrow-right-24: Agentic guide](../features/agentic-mode.md)

-   :material-tools:{ .lg .middle } **Explore Tool Calling**

    ---

    See what Fabric can do beyond just chatting

    [:octicons-arrow-right-24: Tools reference](../features/tool-calling.md)

</div>
