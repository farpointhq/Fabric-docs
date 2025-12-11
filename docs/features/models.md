# AI Models

**Use the right tool for each job—fast models for quick tasks, smart ones for hard problems.**

Most AI tools lock you into one model. Fabric lets you choose. Running a quick lint check? Use a fast, cheap model. Debugging a gnarly race condition? Switch to something powerful. You control the cost-quality tradeoff.

!!! success "No More Overpaying"
    Stop using expensive models for simple tasks. Fabric's model selector puts you in control of your AI costs.

---

## Model Tier System

Fabric automatically selects models based on task complexity using a three-tier system:

!!! info "Tier Selection"
    Models are ranked by a formula that balances **intelligence** (SWE-bench score), **speed** (tokens/sec), and **efficiency** (latency and cost):

    ```
    Score = SWE-bench × (tokens/sec) / (latency × totalCost)
    ```

### :material-brain: Large Tier - Most Capable

Used for complex reasoning, detailed planning, and architecture decisions.

**Trade-off:** Intelligence > Speed/Cost

| Model | Provider | SWE-bench | Cost/M Tokens |
|-------|----------|-----------|---------------|
| **claude-opus-4-5** | Anthropic | 72 | $30 |
| **gpt-5-pro** | OpenAI | 70 | $135 |
| **claude-sonnet-4-5** | Anthropic | 68 | $18 |
| **gemini-3-pro-preview** | Google | 65 | $14 |
| **gpt-5.1** | OpenAI | 62 | $11.25 |
| **gpt-5.1-codex** | OpenAI | 60 | $11.25 |
| **deepseek-reasoner** | Deepseek | 55 | $2.74 |
| **qwen3-235b-thinking** | OpenRouter | 52 | $0.71 |

### :material-scale-balance: Medium Tier - Balanced

Used for targeted code changes, merging, and code review.

**Trade-off:** Balance of speed, cost, and capability

| Model | Provider | SWE-bench | Tokens/sec | Cost/M Tokens |
|-------|----------|-----------|------------|---------------|
| **claude-haiku-4-5** | Anthropic | 48 | 200 | $6 |
| **gpt-5.1-codex-mini** | OpenAI | 45 | 150 | $2.25 |
| **zai-glm-4.6** | Cerebras | 42 | 2000 | $5 |
| **qwen-3-235b-instruct** | Cerebras | 40 | 1500 | $1.80 |
| **deepseek-chat** | Deepseek | 38 | 100 | $1.37 |
| **qwen3-coder-30b** | OpenRouter | 35 | 120 | $0.31 |
| **grok-code-fast-1** | OpenRouter | 33 | 300 | $1.70 |

### :material-flash: Small Tier - Fast & Cheap

Used for summaries, tab naming, and high-volume background operations.

**Trade-off:** Speed/Cost > Intelligence

| Model | Provider | SWE-bench | Tokens/sec | Cost/M Tokens |
|-------|----------|-----------|------------|---------------|
| **qwen-3-32b** | Cerebras | 30 | 2500 | $1.20 |
| **gpt-oss-120b** | Cerebras | 28 | 2200 | $1.10 |
| **gemini-2.5-flash** | Google | 32 | 500 | $0.75 |
| **gpt-5-nano** | OpenAI | 25 | 300 | $0.45 |
| **deepseek-r1:free** | OpenRouter | 35 | 80 | Free |
| **deepseek-v3.2-speciale** | OpenRouter | 55 | 100 | $0.68 |
| **local models** | Local | 20 | 50 | Free |

---

## Supported Providers

### :simple-anthropic: Anthropic

Claude models are known for thoughtful, nuanced responses and excellent code generation.

| Model | Display Name | Context | Output | Vision | Reasoning | Intelligence |
|-------|--------------|---------|--------|--------|-----------|--------------|
| **claude-opus-4-5** | opus 4.5 | 200k | 32k | :material-check: | On/Off | :star::star::star::star::star: |
| **claude-sonnet-4-5** | sonnet 4.5 | 200k | 64k | :material-check: | On/Off | :star::star::star::star: |
| **claude-haiku-4-5** | haiku 4.5 | 200k | 64k | :material-check: | On/Off | :star::star::star: |

!!! success "Capabilities"
    - :material-eye: Vision support (images, PDFs)
    - :material-thought-bubble: Extended thinking mode
    - :material-wrench: Tool use
    - :material-code-json: JSON mode
    - :material-web: Web search
    - :material-stream: Streaming responses

### :simple-openai: OpenAI

GPT-5 series models with advanced reasoning capabilities.

| Model | Display Name | Context | Output | Vision | Reasoning | Intelligence |
|-------|--------------|---------|--------|--------|-----------|--------------|
| **gpt-5-pro** | gpt 5 pro | 400k | 128k | :material-check: | Effort Levels | :star::star::star::star::star: |
| **gpt-5.1** | gpt 5.1 | 400k | 128k | :material-check: | Effort Levels | :star::star::star::star: |
| **gpt-5.1-codex** | gpt 5.1 codex | 400k | 128k | :material-check: | Effort Levels | :star::star::star::star: |
| **gpt-5.1-codex-mini** | gpt 5.1 codex mini | 400k | 128k | :material-check: | Effort Levels | :star::star::star: |
| **gpt-5-nano** | gpt 5 nano | 400k | 128k | :material-check: | :material-close: | :star::star: |

!!! info "Reasoning Effort Levels"
    OpenAI models support configurable reasoning effort: **low**, **medium**, **high**

    Intelligence ratings vary by effort level (e.g., gpt-5-pro: high=5★, medium=5★, low=4★)

!!! success "Capabilities"
    - :material-eye: Vision support (images, PDFs)
    - :material-thought-bubble: Extended thinking with effort control
    - :material-wrench: Tool use
    - :material-code-json: JSON mode
    - :material-web: Web search
    - :material-stream: Streaming responses

### :simple-google: Google

Gemini models with massive context windows and code execution.

| Model | Display Name | Context | Output | Vision | Reasoning | Intelligence |
|-------|--------------|---------|--------|--------|-----------|--------------|
| **gemini-3-pro-preview** | gemini 3.0 pro | 1M | 64k | :material-check: | On/Off | :star::star::star::star::star: |
| **gemini-2.5-flash** | gemini 2.5 flash | 1M | 65k | :material-check: | :material-close: | :star::star::star: |

!!! success "Capabilities"
    - :material-eye: Vision support (images, PDFs)
    - :material-thought-bubble: Extended thinking mode (gemini-3-pro only)
    - :material-wrench: Tool use
    - :material-code-json: JSON mode
    - :material-web: Web search
    - :material-play: **Code execution** (unique to Google)
    - :material-stream: Streaming responses

### :material-brain-circuit: Cerebras

Ultra-fast inference models optimized for code generation.

| Model | Display Name | Context | Output | Reasoning | Intelligence |
|-------|--------------|---------|--------|-----------|--------------|
| **zai-glm-4.6** | ZAI GLM 4.6 (preview) | 131k | 8k | :material-close: | :star::star::star::star: |
| **gpt-oss-120b** | GPT-OSS 120B | 131k | 8k | :material-close: | :star::star::star: |
| **qwen-3-32b** | Qwen 3 32B | 131k | 8k | On/Off | :star::star::star: |
| **qwen-3-235b-instruct** | Qwen 3 235B Instruct (preview) | 131k | 8k | On/Off | :star::star::star::star: |

!!! tip "Performance"
    Cerebras models deliver **2000-2500 tokens/sec** - the fastest in Fabric's lineup.

!!! note "Capabilities"
    - :material-wrench: Tool use
    - :material-stream: Streaming responses
    - :material-thought-bubble: Extended thinking (select models)
    - :material-close: No vision support
    - :material-close: No PDF support

### :material-key-chain: Deepseek

Specialized reasoning models with excellent code understanding.

| Model | Display Name | Context | Output | Reasoning | Intelligence |
|-------|--------------|---------|--------|-----------|--------------|
| **deepseek-reasoner** | deepseek reasoner | 128k | 64k | On/Off | :star::star::star: |
| **deepseek-chat** | deepseek chat | 64k | 4k | On/Off | :star::star::star: |

!!! success "Capabilities"
    - :material-thought-bubble: Extended thinking mode
    - :material-wrench: Tool use
    - :material-code-json: JSON mode
    - :material-stream: Streaming responses
    - :material-close: No vision support

### :material-router: OpenRouter

Access to diverse open-source and commercial models through a single API.

| Model | Display Name | Context | Output | Reasoning | Intelligence |
|-------|--------------|---------|--------|-----------|--------------|
| **x-ai/grok-code-fast-1** | Grok Code Fast 1 | 256k | 128k | :material-close: | :star::star::star::star: |
| **deepseek/deepseek-v3.2-speciale** | DeepSeek V3.2 Speciale | 164k | 65k | On/Off | :star::star::star::star: |
| **qwen/qwen3-235b-thinking** | Qwen3 235B Thinking | 262k | 81k | On/Off | :star::star::star::star: |
| **z-ai/glm-4.6** | GLM 4.6 | 202k | 100k | :material-close: | :star::star::star::star: |
| **minimax/minimax-m2** | Minimax M2 | 204k | 100k | :material-close: | :star::star::star: |
| **qwen/qwen3-coder-30b** | Qwen3 Coder 30B | 262k | 128k | :material-close: | :star::star::star: |
| **deepseek/deepseek-r1:free** | DeepSeek R1 | 164k | 128k | On/Off | :star::star::star: |

!!! success "Capabilities"
    - :material-wrench: Tool use
    - :material-stream: Streaming responses
    - :material-thought-bubble: Extended thinking (select models)
    - :material-currency-usd-off: Free tier available (deepseek-r1)

!!! note "Limitations"
    - :material-close: No vision support (most models)
    - :material-close: No JSON mode
    - :material-close: No web search

### :material-laptop: Local Models

Run models locally using llama.cpp, Ollama, or custom endpoints.

| Feature | Status |
|---------|--------|
| **Endpoint** | `http://localhost:8080/v1/` |
| **Context** | Model-dependent |
| **Output** | Model-dependent |
| **Cost** | Free |
| **Intelligence** | :star::star: (typical) |

!!! info "Local Setup"
    Configure local providers through Settings → Models → Add Provider

    Supported backends:

    - **llama.cpp** - High-performance C++ inference
    - **Ollama** - Easy model management
    - **Custom** - Any OpenAI-compatible endpoint

!!! warning "Limitations"
    - :material-close: No vision support
    - :material-close: No tool use
    - :material-close: No JSON mode
    - :material-close: No reasoning mode
    - :material-stream: Streaming supported

---

## Model Capabilities

### Vision Support

Models that can process images and PDFs:

- All **Anthropic** models (Claude 4.5 series)
- All **OpenAI** models (GPT-5 series)
- All **Google** models (Gemini)

!!! example "Supported Formats"
    - Images: PNG, JPEG, GIF, WebP
    - Documents: PDF (automatic extraction)

### Extended Thinking

Models with chain-of-thought reasoning:

!!! info "Reasoning Types"
    - **On/Off** - Simple toggle (Anthropic, Google, Deepseek, select others)
    - **Effort Levels** - Configurable low/medium/high (OpenAI)

**Supported models:**

- Anthropic: All Claude 4.5 models
- OpenAI: gpt-5-pro, gpt-5.1, gpt-5.1-codex, gpt-5.1-codex-mini
- Google: gemini-3-pro-preview
- Cerebras: qwen-3-32b, qwen-3-235b-instruct
- Deepseek: All models
- OpenRouter: deepseek-v3.2, qwen3-235b-thinking, deepseek-r1

### Tool Use

All models except local models support tool/function calling for:

- Code execution
- File operations
- API integrations
- Custom tools

### Web Search

Models with integrated web search capabilities:

- All **Anthropic** models
- All **OpenAI** models
- All **Google** models

### Code Execution

Only **Google Gemini** models natively support code execution in the model environment.

---

## Provider Configuration

### Adding API Keys

!!! tip "Quick Setup"
    1. Go to **Settings → Models**
    2. Select your provider
    3. Enter your API key
    4. Choose default models for each tier

### Custom Endpoints

For self-hosted or custom model endpoints:

```
Provider: custom
Endpoint: https://your-api.example.com/v1/
API Key: your-key-here
```

Fabric supports any OpenAI-compatible API endpoint.

---

## Model Selection Strategy

Fabric automatically selects models based on the task:

| Task | Tier | Example Use Case |
|------|------|------------------|
| **Planning** | Large | Creating implementation plans, architecture decisions |
| **Code Review** | Large | Reviewing medium model output, complex refactoring |
| **Implementation** | Medium | Writing targeted code changes, merging edits |
| **Quick Tasks** | Small | Summaries, tab naming, background operations |

!!! info "Manual Override"
    You can manually select any model regardless of tier from the model dropdown.

---

## Cost Optimization

### Budget-Friendly Options

**Free models:**

- OpenRouter: deepseek-r1:free
- Local: Any self-hosted model

**Low-cost high-performers:**

| Model | Provider | Cost/M | SWE-bench | Speed |
|-------|----------|--------|-----------|-------|
| **qwen3-235b-thinking** | OpenRouter | $0.71 | 52 | Moderate |
| **gemini-2.5-flash** | Google | $0.75 | 32 | Fast |
| **deepseek-chat** | Deepseek | $1.37 | 38 | Moderate |
| **qwen-3-235b-instruct** | Cerebras | $1.80 | 40 | Very Fast |

### Performance Options

For maximum intelligence regardless of cost:

1. **claude-opus-4-5** - Best reasoning (SWE-bench: 72)
2. **gpt-5-pro** - Strong all-around (SWE-bench: 70)
3. **claude-sonnet-4-5** - Excellent balance (SWE-bench: 68)

---

## Frequently Asked Questions

??? question "Which model should I use?"

    **For most coding tasks:** Start with **claude-sonnet-4-5** or **gpt-5.1-codex** (large tier)

    **For quick tasks:** Use **claude-haiku-4-5** or **gemini-2.5-flash** (small tier)

    **For complex architecture:** Use **claude-opus-4-5** or **gpt-5-pro** (large tier)

    **On a budget:** Use **deepseek-r1:free** or local models

??? question "How does tier selection work?"

    Fabric ranks models within each tier by:

    1. **Intelligence** (SWE-bench score)
    2. **Speed** (tokens per second)
    3. **Efficiency** (latency and cost)

    The highest-ranked available model is auto-selected for each task type.

??? question "Can I use multiple providers simultaneously?"

    Yes! Configure API keys for multiple providers and Fabric will use the best available model for each task based on tier rankings.

??? question "Do I need all API keys?"

    No - configure only the providers you want to use. At minimum, one provider with large, medium, and small tier models is recommended.

??? question "What's the difference between reasoning types?"

    - **On/Off**: Simple toggle for extended thinking (Anthropic, Google, Deepseek)
    - **Effort Levels**: Adjustable low/medium/high reasoning intensity (OpenAI)

    Higher effort = better quality but slower responses and higher costs.

??? question "Can I add custom models?"

    Yes! Use the **custom** provider option with any OpenAI-compatible endpoint. Local models (llama.cpp, Ollama) are also supported.
