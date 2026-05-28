# Research and Summarize with Fabric

**Time:** 5 minutes to set up  
**Difficulty:** Beginner  
**What you'll build:** A workflow for reading, researching, and summarizing any kind of document or web content — without leaving Fabric.

---

## Overview

Fabric's in-app browser, file attachments, and persistent conversation context make it a capable research environment. This cookbook covers three common research workflows: summarizing uploaded documents, researching with the built-in browser, and building a running summary across multiple sources.

---

## Workflow 1: Summarize a Document

The fastest way to get value out of a long document is to attach it and ask a direct question.

**Supported formats:** PDFs, plain text files, Markdown, code files, and most document formats.

### Step 1: Attach the Document

Click the **paperclip icon** in the chat input bar and select your file. It appears as a chip above the text field.

### Step 2: Ask a Focused Question

Instead of "summarize this," ask for what you actually need:

```
What are the key arguments in this paper, and what evidence does it use to support them?
```

```
This is a contract — what are the termination clauses and what notice period is required?
```

```
Extract all the action items and owners from this meeting transcript.
```

Specific questions get specific answers. "Summarize this" gets you a generic summary.

### Step 3: Follow Up

Summaries are starting points. Follow up to go deeper:

```
You mentioned the methodology had limitations — what were they?
```

```
Is there anything in the contract that would be unusual or worth flagging to a lawyer?
```

Fabric maintains the full document in context throughout the conversation, so you can ask as many follow-up questions as you need.

---

## Workflow 2: Research with the Built-in Browser

Use the in-app browser to read web content without switching apps, and bring it directly into the conversation.

### Step 1: Open the Browser

Click the **browser icon** in the left sidebar, or switch to a browser tab from the tab bar.

### Step 2: Navigate to Your Source

Type a URL or search query in the address bar. Fabric's browser works like a regular browser — navigate to documentation pages, articles, papers, or any public web page.

### Step 3: Ask Fabric to Read the Page

Switch to the chat tab and ask:

```
Read the page I have open and summarize the key points.
```

In agentic mode, Fabric can browse pages on your behalf:

```
Find the pricing page for this product and tell me what's included in the free tier.
```

```
Look up the changelog for this library and tell me what changed in the last three versions.
```

### Step 4: Compare Multiple Sources

Navigate between pages and build up a comparative picture:

```
I've now shown you three different approaches to this problem.
What are the tradeoffs between them?
```

---

## Workflow 3: Build a Running Summary Across Multiple Sources

When you're doing deeper research across several documents or pages, use a single tab as your research session and build up context incrementally.

### Step 1: Start a Dedicated Research Tab

Open a new tab (click **+** in the tab bar) and label it mentally as your research tab. Keep it separate from your work tabs.

### Step 2: Attach or Browse Sources One at a Time

Add each source to the conversation in sequence. After each one, ask Fabric to integrate it:

```
Here's the second paper. How does its methodology compare to the first one?
```

```
Here's the third article. Does it support or contradict anything we've covered so far?
```

### Step 3: Ask for a Synthesis

Once you've gone through your sources, ask for a synthesis across everything:

```
Based on everything we've read, what's the current consensus on this topic,
and where is there still disagreement?
```

```
I need to write a one-page briefing on this topic.
Draft it based on the sources we've reviewed.
```

### Step 4: Compact When the Conversation Gets Long

Research conversations can grow long. When the context indicator shows the conversation getting full, click **Compact** to summarize the older exchanges while keeping the key findings in context.

---

## Tips

**Paste text directly for quick questions.** For short passages — a paragraph, a few bullet points — you don't need to attach a file. Just paste the text into the message and ask your question inline.

**Ask for a specific output format.** "Give me a bulleted list of the main claims" or "Write this as a one-paragraph executive summary" gets you something immediately usable.

**Use it for non-English content.** Attach a document in any language and ask Fabric to summarize it in English (or vice versa).

**Save the output.** Ask Fabric to write its summary to a file: *"Save this summary as `research-notes/paper-1-summary.md`."* In agentic mode, it will create the file in your project folder.
