# Installation

Get Fabric up and running on your machine.

## Join the Beta

!!! info "Beta Access Required"
    Fabric is currently in private beta. Public releases are coming soon!

To get access to Fabric:

1. Visit **[farpointalpha.com/fabric](https://farpointalpha.com/fabric)**
2. Enter your email to join the waitlist
3. You'll receive a download link when your access is approved

<div class="grid cards" markdown>

-   :material-email-fast:{ .lg .middle } **Quick Approval**

    ---

    Most beta requests are approved within 24-48 hours.

-   :material-update:{ .lg .middle } **Auto Updates**

    ---

    Once installed, Fabric automatically updates to the latest version.

</div>

## System Requirements

| Platform | Minimum Requirements |
|----------|---------------------|
| **macOS** | macOS 12 (Monterey) or later, Apple Silicon or Intel |
| **Windows** | Windows 10 (64-bit) or later |
| **Linux** | Ubuntu 20.04+ or equivalent, x64 architecture |

### Additional Requirements

- **Internet connection** for AI model access
- **API key** from at least one provider (Anthropic, OpenAI, or Google)
- **4GB RAM** minimum (8GB+ recommended for large projects)

## Installing Fabric

Once you receive your beta download link, follow the instructions for your platform:

### macOS

=== "Apple Silicon (M1/M2/M3/M4)"

    1. Download `Fabric-arm64.dmg` from your beta email
    2. Double-click the downloaded `.dmg` file to mount it
    3. Drag **Fabric** to your **Applications** folder
    4. Open Fabric from Applications

    !!! tip "First Launch on macOS"
        On first launch, macOS may show a security warning. Right-click the app and select **Open**, then click **Open** in the dialog to allow it.

=== "Intel Mac"

    1. Download `Fabric-x64.dmg` from your beta email
    2. Double-click the downloaded `.dmg` file to mount it
    3. Drag **Fabric** to your **Applications** folder
    4. Open Fabric from Applications

### Windows

1. Download `Fabric-Setup.exe` from your beta email
2. Run the installer
3. Follow the installation wizard
4. Launch Fabric from the Start Menu or Desktop shortcut

!!! note "Windows Defender SmartScreen"
    Windows may show a SmartScreen warning for new applications. Click **More info** → **Run anyway** to proceed.

### Linux

=== "AppImage (Recommended)"

    1. Download `Fabric.AppImage` from your beta email
    2. Make it executable:
       ```bash
       chmod +x Fabric.AppImage
       ```
    3. Run the application:
       ```bash
       ./Fabric.AppImage
       ```

=== "Debian/Ubuntu (.deb)"

    1. Download `Fabric.deb` from your beta email
    2. Install via terminal:
       ```bash
       sudo dpkg -i Fabric.deb
       sudo apt-get install -f  # Install dependencies if needed
       ```
    3. Launch from your applications menu

## First Launch Setup

When you first open Fabric, you'll be guided through initial setup:

### 1. Welcome Screen

You'll see a welcome screen introducing Fabric's key features.

### 2. API Key Configuration

Fabric needs at least one API key to connect to AI models:

<div class="grid cards" markdown>

-   :simple-anthropic:{ .lg .middle } **Anthropic (Claude)**

    ---

    Get your API key from [console.anthropic.com](https://console.anthropic.com/)

    Recommended for: Complex reasoning, code review, long-form tasks

-   :simple-openai:{ .lg .middle } **OpenAI (GPT-4)**

    ---

    Get your API key from [platform.openai.com](https://platform.openai.com/api-keys)

    Recommended for: General assistance, quick tasks

-   :material-google:{ .lg .middle } **Google (Gemini)**

    ---

    Get your API key from [aistudio.google.com](https://aistudio.google.com/app/apikey)

    Recommended for: Long context, multimodal tasks

</div>

!!! tip "Start with One Key"
    You only need one API key to get started. You can add more providers later in Settings.

### 3. Optional: Project Setup

You can optionally open a project folder to give Fabric context about your codebase.

### 4. Start Chatting!

You're ready to go. Try asking Fabric to:

- Explain a piece of code
- Help debug an error
- Generate a new function
- Review your code for improvements

## Updating Fabric

Fabric automatically checks for updates and will notify you when a new version is available.

To manually check for updates:

1. Open **Settings** (`⌘ ,` on macOS, `Ctrl ,` on Windows/Linux)
2. Navigate to **General**
3. Click **Check for Updates**

## Uninstalling

### macOS
Drag Fabric from Applications to the Trash.

### Windows
Use **Add or Remove Programs** in Windows Settings.

### Linux
Remove the AppImage file, or use `sudo dpkg -r fabric` for .deb installations.

## Troubleshooting

### Fabric won't start

1. Ensure your system meets the minimum requirements
2. Try restarting your computer
3. Re-download and reinstall Fabric

### API key not working

1. Verify the key is correct (no extra spaces)
2. Check that you have credits/quota with your provider
3. Ensure your API key has the required permissions

### Performance issues

1. Close other resource-intensive applications
2. Try reducing the context window size in Settings
3. Switch to a faster model (e.g., Claude 4.5 Haiku)

!!! question "Need More Help?"
    Visit our [GitHub Discussions](https://github.com/farpointhq/Fabric/discussions) for community support.

## Next Steps

- [Quick Start Guide](quickstart.md) - Learn the basics in 5 minutes
- [Configuration](configuration.md) - Customize Fabric to your workflow
- [Chat Interface](../guide/chat.md) - Master the chat interface
