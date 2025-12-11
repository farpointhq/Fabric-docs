# Welcome to Fabric

<div class="hero" markdown>

# ![Fabric Logo](assets/logo.png){ .no-lightbox width="42" style="vertical-align: middle; margin-right: 8px;" } Fabric

**Ship faster. Stay in control. Never fly blind.**

Stop choosing between speed and quality. Fabric gives you AI coding superpowers while keeping you in the driver's seat.

[Join the Beta](https://farpointalpha.com/fabric){ .md-button .md-button--primary }
[See What's Possible](#what-can-you-build){ .md-button }

</div>

---

## Why Developers Love Fabric

**You've tried AI coding tools.** They're fast—until they hallucinate. They're helpful—until they miss context. They're powerful—until you lose control of your codebase.

Fabric is different. We built it for developers who want the **velocity of AI** without the **anxiety of not knowing what's happening** under the hood.

<div class="grid cards" markdown>

-   :material-eye:{ .lg .middle } **See AI Think, Not Just Output**

    ---

    Watch the AI reason through your problem in real-time. No more black boxes—understand *why* it suggests what it suggests, so you can trust (or correct) its decisions.

    [:octicons-arrow-right-24: How it works](features/agentic-mode.md)

-   :material-swap-horizontal:{ .lg .middle } **Choose the Right Model for the Job**

    ---

    Use fast models for quick tasks, powerful ones for complex reasoning. Switch mid-conversation. You're in control of the cost-quality tradeoff.

    [:octicons-arrow-right-24: Model selection](features/models.md)

-   :material-tab:{ .lg .middle } **Work on Everything at Once**

    ---

    Juggle bug fixes, feature development, and code exploration in parallel. Each conversation keeps its context—no more losing your train of thought.

    [:octicons-arrow-right-24: Chat workspace](guide/chat.md)

-   :material-shield-check:{ .lg .middle } **Your Code, Your Control**

    ---

    Every file change requires your approval. Full audit trail of AI actions. Your API keys, your data, your rules.

    [:octicons-arrow-right-24: Security & privacy](getting-started/configuration.md)

</div>

## What Can You Build?

### Ship Features in Hours, Not Days

Fabric doesn't just write code—it understands your codebase. Ask it to add a feature and it knows where things go, what patterns you use, and how to integrate properly.

!!! example "Real Developer Workflows"
    - "Add JWT authentication to my Express API, following my existing middleware patterns"
    - "Find all the places where we handle user permissions and add admin role support"
    - "Refactor this class to use dependency injection—and update the tests"

### Pick the Perfect Model for Every Task

Why pay premium prices for a simple rename? Why use a fast model for complex architecture decisions? Fabric lets you choose:

| When You Need... | Use | Why |
|------------------|-----|-----|
| Quick answers, simple fixes | Fast models | Instant response, minimal cost |
| Complex reasoning | Powerful models | Better architecture, fewer mistakes |
| Code review | Your choice | Match depth to importance |

!!! tip "Optimize Cost Without Sacrificing Quality"
    Switch models mid-conversation. Start with a fast model to explore, then switch to a powerful one when you need deep reasoning.

### Let AI Handle the Boring Parts

Some tasks are tedious but important: updating tests after a refactor, applying a fix across 50 files, migrating to a new API. Fabric's agentic mode handles multi-step tasks while keeping you in control:

```
"Update all API endpoints to use the new error handling pattern,
and make sure the tests still pass."
```

You'll see exactly what it plans to do, approve each step, and watch it work. No surprises, no mystery commits, no "what did it just do?"

[:octicons-arrow-right-24: See agentic mode in action](features/agentic-mode.md)

### Your Codebase, Fully Understood

Fabric builds a mental model of your project. It knows:

- **Where things live** - Ask about auth code and it knows to look in `src/auth/`
- **How you do things** - It learns your patterns, conventions, and style
- **What connects to what** - Understands relationships between files and modules

!!! success "No More Explaining Your Codebase"
    You don't need to paste context into every prompt. Fabric remembers.

## Get Started in 5 Minutes

<div class="grid cards" markdown>

-   :material-download:{ .lg .middle } **1. Download**

    ---

    Available for macOS, Windows, and Linux. One-click install, no dependencies.

    [:octicons-arrow-right-24: Download Fabric](getting-started/installation.md)

-   :material-key:{ .lg .middle } **2. Connect Your AI**

    ---

    Bring your own API key from Anthropic, OpenAI, or Google—or use our free tier to get started immediately.

    [:octicons-arrow-right-24: Setup guide](getting-started/configuration.md)

-   :material-rocket-launch:{ .lg .middle } **3. Open a Project**

    ---

    Point Fabric at your codebase and start asking questions. It learns your code as you go.

    [:octicons-arrow-right-24: Quick start](getting-started/quickstart.md)

</div>

!!! tip "No API Key? No Problem"
    Fabric includes free tokens to get you started. Try it out before committing to an API subscription.

## What Will You Build Today?

=== "Fix That Bug"

    ```
    I'm getting "Cannot read property 'id' of undefined"
    in UserProfile.tsx. Find the bug and fix it.
    ```

=== "Add a Feature"

    ```
    Add a dark mode toggle to the settings page.
    Store the preference in localStorage and apply
    it app-wide.
    ```

=== "Understand Legacy Code"

    ```
    Explain how the payment processing flow works.
    I need to add a new payment method and don't
    know where to start.
    ```

=== "Review Before Shipping"

    ```
    Review this PR for security issues, edge cases
    I might have missed, and potential performance
    problems.
    ```

## Join the Community

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **Learn More**

    ---

    Dive deeper into Fabric's features with our guides.

    [:octicons-arrow-right-24: Browse documentation](guide/overview.md)

-   :material-github:{ .lg .middle } **Get Involved**

    ---

    Share feedback, request features, and help shape Fabric's future.

    [:octicons-arrow-right-24: GitHub Discussions](https://github.com/farpointhq/Fabric/discussions)

-   :material-keyboard:{ .lg .middle } **Power User Tips**

    ---

    Master keyboard shortcuts to fly through your workflow.

    [:octicons-arrow-right-24: Shortcuts reference](reference/shortcuts.md)

</div>

---

<div class="footer-cta" markdown>

**Ready to code faster without the chaos?**

[Get Fabric Free](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>
