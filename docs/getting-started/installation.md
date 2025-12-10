# Installation

Get Fabric up and running on your machine.

## System Requirements

| Platform | Requirements |
|----------|-------------|
| macOS | macOS 12 (Monterey) or later |
| Windows | Windows 10 or later |
| Linux | Ubuntu 20.04+ or equivalent |

## Download

### macOS

=== "Apple Silicon (M1/M2/M3)"

    ```bash
    # Download the latest release
    curl -LO https://github.com/farpointhq/Fabric/releases/latest/download/Fabric-arm64.dmg

    # Mount and install
    open Fabric-arm64.dmg
    ```

=== "Intel"

    ```bash
    # Download the latest release
    curl -LO https://github.com/farpointhq/Fabric/releases/latest/download/Fabric-x64.dmg

    # Mount and install
    open Fabric-x64.dmg
    ```

### Windows

Download the installer from our [releases page](https://github.com/farpointhq/Fabric/releases).

### Linux

```bash
# Download AppImage
curl -LO https://github.com/farpointhq/Fabric/releases/latest/download/Fabric.AppImage

# Make executable
chmod +x Fabric.AppImage

# Run
./Fabric.AppImage
```

## First Launch

1. Open Fabric
2. You'll be prompted to configure your API keys
3. Enter at least one API key (Claude, OpenAI, etc.)
4. Start chatting!

!!! tip "API Keys"
    You need at least one API key to use Fabric. We recommend starting with [Anthropic's Claude](https://console.anthropic.com/) or [OpenAI](https://platform.openai.com/api-keys).

## Next Steps

- [Quick Start Guide](quickstart.md) - Learn the basics
- [Configuration](configuration.md) - Customize Fabric
