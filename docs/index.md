# Welcome to Fabric

<div class="hero" markdown>

# ![Fabric Logo](assets/logo.png){ .no-lightbox width="42" style="vertical-align: middle; margin-right: 8px;" } Fabric

**The fastest way to code with AI, without giving up control**

Secure, context-aware code generation that always aligns with your standards.

[Join the Beta](https://farpointalpha.com/fabric){ .md-button .md-button--primary }
[View Documentation](#what-is-fabric){ .md-button }

</div>

---

## What is Fabric?

Fabric is a powerful AI code assistant that helps you write, understand, and improve code. It combines the latest large language models with a sleek interface designed for developers who want AI assistance without sacrificing control.

<div class="grid cards" markdown>

-   :material-flash:{ .lg .middle } **Fast & Intelligent**

    ---

    Get instant code suggestions, explanations, and refactoring advice powered by state-of-the-art AI models like Claude 4.5, GPT-5, and Gemini 3.0.

    [:octicons-arrow-right-24: Learn about models](features/models.md)

-   :material-tab:{ .lg .middle } **Multi-Chat Workspace**

    ---

    Work on multiple features, bug fixes, and explorations simultaneously with tabbed conversations and chat groups.

    [:octicons-arrow-right-24: Chat interface](guide/chat.md)

-   :material-tools:{ .lg .middle } **Tool Calling**

    ---

    AI can execute code, search files, read documentation, and interact with your development environment—safely and with your approval.

    [:octicons-arrow-right-24: Available tools](features/tool-calling.md)

-   :material-brain:{ .lg .middle } **Agentic Mode**

    ---

    Let AI autonomously plan and execute multi-step tasks like refactoring modules or creating new features—with full transparency and control.

    [:octicons-arrow-right-24: Agentic workflows](features/agentic-mode.md)

</div>

## Key Features

### Multi-Model Support

Switch between AI models based on your task. Each model has different strengths:

| Model | Best For | Speed | Context |
|-------|----------|-------|---------|
| **Claude Opus 4.5** | Complex reasoning, code review, architecture | Medium | 200K |
| **Claude Sonnet 4.5** | Balanced performance, daily driver | Fast | 200K |
| **Claude Haiku 4.5** | Quick tasks, simple questions | Very Fast | 200K |
| **GPT-5 Pro** | Advanced reasoning, general assistance | Medium | 400K |
| **GPT-5.1 Codex** | Code-specialized tasks | Fast | 400K |
| **Gemini 3.0 Pro** | Long documents, multimodal tasks | Medium | 1M |

!!! tip "Switch Models Mid-Conversation"
    You can switch models at any point in a conversation. Fabric maintains full context when you switch.

### Agentic Workflows

Enable agentic mode for complex, multi-step tasks:

```
"Refactor the authentication module to use JWT tokens,
update all related tests, and document the changes."
```

Fabric will:

1. **Plan** the implementation steps
2. **Execute** each step with your approval
3. **Test** changes automatically
4. **Document** what was changed
5. **Present** results for your review

[:octicons-arrow-right-24: Learn more about Agentic Mode](features/agentic-mode.md)

### Context-Aware Assistance

Fabric understands your project:

- **Auto File Select** - Automatically suggests relevant files based on your question
- **Project Summaries** - AI-generated summaries of your codebase
- **Database Awareness** - Connect databases to get schema-aware SQL assistance
- **Terminal Integration** - Execute commands directly from the chat

### Privacy & Security

Your code stays safe:

- **Local Processing** - Files are processed locally, not sent to external servers
- **API Key Control** - You manage your own API keys
- **Approval Workflow** - Review and approve all file changes before they happen
- **Audit Trail** - Full history of all AI actions

## Getting Started

!!! info "Beta Access"
    Fabric is currently in private beta. [Join the waitlist](https://farpointalpha.com/fabric) to get access.

Once you have access:

<div class="grid cards" markdown>

-   :material-download:{ .lg .middle } **1. Install**

    ---

    Download Fabric for macOS, Windows, or Linux from your beta email.

    [:octicons-arrow-right-24: Installation guide](getting-started/installation.md)

-   :material-key:{ .lg .middle } **2. Configure**

    ---

    Add your API key from Anthropic, OpenAI, or Google.

    [:octicons-arrow-right-24: Configuration](getting-started/configuration.md)

-   :material-rocket-launch:{ .lg .middle } **3. Start Coding**

    ---

    Open a project and start chatting with AI about your code.

    [:octicons-arrow-right-24: Quick start](getting-started/quickstart.md)

</div>

## Example Prompts

Here are some things you can ask Fabric:

=== "Code Review"

    ```
    Review this function for potential bugs,
    performance issues, and best practices:

    [paste your code]
    ```

=== "Debugging"

    ```
    I'm getting this error when running my tests:

    [paste error]

    The relevant code is in src/auth/login.ts
    ```

=== "Feature Development"

    ```
    Create a React component for a sortable data table
    with pagination, following the patterns in our
    existing components.
    ```

=== "Refactoring"

    ```
    Refactor the UserService class to use dependency
    injection. Update the tests accordingly.
    ```

## Getting Help

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **Documentation**

    ---

    You're here! Browse the sidebar for detailed guides.

-   :material-github:{ .lg .middle } **GitHub**

    ---

    [Report issues](https://github.com/farpointhq/Fabric/issues) or [join discussions](https://github.com/farpointhq/Fabric/discussions)

-   :material-keyboard:{ .lg .middle } **Keyboard Shortcuts**

    ---

    Press `⌘ /` (or `Ctrl /`) in Fabric to see all shortcuts.

    [:octicons-arrow-right-24: Shortcuts reference](reference/shortcuts.md)

</div>

---

<div class="footer-cta" markdown>

Ready to accelerate your development?

[Join the Fabric Beta](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>
