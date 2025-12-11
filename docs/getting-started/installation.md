# Installation

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

---

## Trouble?

| Problem | Solution |
|---------|----------|
| **Won't start** | Restart your computer, re-download if needed |
| **API key not working** | Check for extra spaces, verify you have credits |
| **Slow responses** | Try a faster model, close other heavy apps |

!!! question "Still Stuck?"
    [Ask the community](https://github.com/farpointhq/Fabric/discussions) — we're happy to help.

---

## Ready to Code?

[:octicons-arrow-right-24: Quick Start Guide](quickstart.md) — Be productive in 5 minutes
