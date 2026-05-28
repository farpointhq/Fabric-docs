# Quick Start

## Installation

**Download → Install → Start coding. That's it.**

## Get Fabric

<div class="grid cards" markdown>

-   :material-apple:{ .lg .middle } **macOS**

    ---

    Works on Apple Silicon (M1/M2/M3/M4) and Intel Macs. macOS 12 or later.

    [Download for Mac](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-microsoft-windows:{ .lg .middle } **Windows**

    ---

    Windows 10 or later (64-bit).

    [Download for Windows](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-linux:{ .lg .middle } **Linux**

    ---

    AppImage or .deb package. Ubuntu 20.04+ or equivalent.

    [Download for Linux](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>

!!! success "Free to Start"
    Use free-tier providers like Google, Mistral, or OpenRouter to get started without paying for API access.

## What You Need

- **Internet connection** (AI models run in the cloud)
- **4GB RAM** minimum, 8GB+ for large projects
- **API key** from any provider (free tiers available from Google, Mistral, OpenRouter)

---

## Installation Steps

=== "macOS"

    1. Open the downloaded `.dmg` file
    2. Drag **Fabric** to your **Applications** folder
    3. Open Fabric from Applications

    !!! tip "First Launch"
        macOS may show a security warning. Right-click the app → **Open** → **Open** again.

=== "Windows"

    1. Run `Fabric-Setup.exe`
    2. Follow the installer
    3. Launch from Start Menu

    !!! tip "Windows Security"
        If SmartScreen appears, click **More info** → **Run anyway**.

=== "Linux"

    **AppImage (easiest):**
    ```bash
    chmod +x Fabric.AppImage
    ./Fabric.AppImage
    ```

    **Debian/Ubuntu:**
    ```bash
    sudo dpkg -i Fabric.deb
    ```

---

## First Launch

Open Fabric and you'll see the chat interface immediately. No setup wizard, no configuration forms.

### Try It Now (No API Key Needed)

Fabric includes free tokens to get started. Open a project folder and ask a question:

```
What does this codebase do?
```

### Add Your Own API Keys (Optional)

Want more control over which models you use? Add your own keys in Settings:

| Provider | Where to Get Key |
|----------|------------------|
| **Anthropic** | [console.anthropic.com](https://console.anthropic.com/) |
| **OpenAI** | [platform.openai.com](https://platform.openai.com/api-keys) |
| **Google** | [aistudio.google.com](https://aistudio.google.com/app/apikey) |

!!! tip "Free Tier Options"
    - **Google** — Generous free tier for Gemini models
    - **Mistral** — Free API access to get started
    - **OpenRouter** — Free models like DeepSeek R1

---

## Updates

Fabric updates itself automatically. You'll see a notification when a new version is available.


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

