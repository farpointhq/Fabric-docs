# Build an MCP Server with Fabric

**Time:** 30–60 minutes  
**Difficulty:** Intermediate  
**What you'll build:** A working MCP (Model Context Protocol) server, scaffolded and implemented by Fabric in agentic mode, then connected back into Fabric so the AI can use its tools.

---

## Overview

The [MCP page](../../../customize-fabric/mcp/mcp.md) covers connecting Fabric to an MCP server that already exists. This cookbook covers the other half: **using Fabric to write a brand-new MCP server from scratch**.

There's no dedicated "scaffold server" button — and there doesn't need to be. Writing an MCP server is a coding task, and coding is exactly what Fabric's agentic mode does. This cookbook walks through a reliable workflow for getting Fabric to build one, end to end.

---

## What Is an MCP Server?

An MCP server is a small program that exposes **tools** (and optionally resources and prompts) to an AI client over the Model Context Protocol. Once connected, the AI can call those tools — query your internal API, hit a database, control a piece of hardware, whatever you implement.

A minimal server has three parts:

- A **transport** (stdio for local servers, or HTTP/SSE for remote ones)
- One or more **tool definitions** (name, description, input schema)
- A **handler** for each tool that does the actual work and returns a result

---

## Step 1: Decide What Your Server Should Do

Before writing any code, get specific about the tools you want. Vague requirements produce vague servers. Open a chat and describe the goal:

```
I want to build an MCP server that exposes my company's internal
inventory API. It should have three tools:
- get_stock(sku): returns current stock level for a SKU
- list_low_stock(threshold): lists SKUs below a stock threshold
- reserve_item(sku, quantity): reserves stock and returns a reservation ID

The API is at https://internal.acme.com/api, authenticated with a
bearer token from the ACME_API_TOKEN environment variable.
```

The clearer the tool list and the API contract, the better the result.

---

## Step 2: Point Fabric at a Reference Implementation

MCP servers follow a consistent shape. Giving Fabric a known-good example to copy dramatically improves the output. Two good options:

- **The official SDK examples** — ask Fabric to use the patterns from `@modelcontextprotocol/sdk` (TypeScript) or the `mcp` Python package.
- **An existing server in your stack** — if you already have one, attach it as context and say "follow this same structure."

```
Use the @modelcontextprotocol/sdk TypeScript SDK with the stdio transport.
Follow the standard server structure: register each tool with a Zod input
schema, and return content as text. Set up a package.json with a build script.
```

---

## Step 3: Let Fabric Scaffold the Project

In **agentic mode**, ask Fabric to create the project structure. It will create files, install dependencies, and write the boilerplate:

```
Scaffold the project: package.json, tsconfig.json, and src/index.ts with
the server skeleton and the three tools stubbed out. Install the SDK and
any other dependencies you need.
```

Review the diffs as they come in. You'll see the project layout, the dependency list, and the server skeleton. Accept the changes you're happy with.

---

## Step 4: Implement the Tools

Now have Fabric fill in the actual logic, one tool at a time. Going tool-by-tool keeps each change reviewable:

```
Implement get_stock. It should read ACME_API_TOKEN from the environment,
call GET /api/stock/{sku}, and return the stock level. Handle a 404 by
returning a clear "SKU not found" message.
```

Repeat for each tool. Because you're in agentic mode, Fabric can also run the build (`npm run build`) and fix any type errors it introduces.

---

## Step 5: Test the Server Locally

Ask Fabric to verify the server starts and responds:

```
Run the build, then start the server and confirm it initializes without
errors. If the SDK has an inspector or a way to list tools, use it to
verify all three tools are registered.
```

The official MCP Inspector (`npx @modelcontextprotocol/inspector`) is a good way to exercise the tools manually before wiring them into Fabric.

---

## Step 6: Connect It to Fabric

Once the server builds and runs, connect it like any other MCP server. Open **Settings → MCP**, click **Add Server**, and configure it:

- **Transport**: stdio
- **Command**: `node`
- **Args**: the path to your built `dist/index.js`
- **Environment**: set `ACME_API_TOKEN`

See the [MCP page](../../../customize-fabric/mcp/mcp.md) for the full walkthrough of the Add Server dialog. Once connected, your new tools appear in Fabric's tool list and the AI can call them.

---

## Step 7: Iterate

Using your server in real conversations will surface rough edges — a tool that needs better error messages, a missing parameter, an output format that's hard to read. Just describe the problem back to Fabric:

```
The list_low_stock tool returns raw JSON that's hard to read. Have it
return a formatted markdown table instead, sorted by stock level ascending.
```

Rebuild, reconnect (or reload the server in MCP settings), and you're done.

---

## Tips

**Keep tools focused.** One tool, one job. A handful of small, well-described tools beats one giant tool with a dozen modes.

**Write great descriptions.** The AI decides when to call a tool based on its description and schema. Spend time here — it's the difference between a tool that gets used correctly and one that gets ignored or misused.

**Validate inputs.** Use a schema library (Zod for TS, Pydantic for Python) so bad input is rejected with a clear message rather than crashing the server.

**Add an AGENTS.md.** If you'll keep developing the server, drop an [AGENTS.md](../set-up-agents-md/set-up-agents-md.md) in its repo so Fabric remembers the conventions and build commands across sessions.
