# Generate Documents (Word, PowerPoint, and PDF)

**Time:** 15–30 minutes  
**Difficulty:** Beginner  
**What you'll build:** A workflow that turns a single source of content into polished `.docx`, `.pptx`, and `.pdf` files in one pass — a report, a slide deck, and a print-ready PDF, all from the same material.

---

## Overview

Fabric doesn't generate Office documents out of the box — there's no built-in "export to Word" button. What it *does* have is a skill system. By installing document-generation skills from the [Skills Marketplace](../../../customize-fabric/skills-marketplace/skills-marketplace.md), you give Fabric the ability to author real `.docx`, `.pptx`, and `.pdf` files, and then you can ask it to produce all three formats from one conversation.

This cookbook shows how to set that up and run a multi-format generation in a single workflow.

---

## Step 1: Install the Document Skills

Open **Settings → Skills**, click **Browse Marketplace**, and search for document-generation skills. Look for skills that cover:

- **docx** — Microsoft Word documents
- **pptx** — PowerPoint presentations
- **pdf** — PDF creation (and form-filling / merging)

Install the ones you need. Once installed, Fabric can invoke them automatically when a task calls for that format — you don't have to call them by name.

!!! tip "Install all three"
    If you want true multi-format output in one pass, install all three skills up front. The AI can only produce a format it has a skill for, so having docx, pptx, and pdf available is what makes the single-prompt workflow below possible.

---

## Step 2: Prepare Your Source Content

Decide what the documents are *about* and give Fabric the raw material. This can be:

- A document or notes you attach (paperclip or drag-and-drop)
- Content already in your project (a markdown file, a dataset)
- Or just a description in the prompt

For example, attach a `quarterly-summary.md` with your Q2 results, or paste the key points directly.

The better your source content, the better all three outputs — they're only as good as what they're generated from.

---

## Step 3: Ask for All Three Formats in One Pass

With the skills installed and your content ready, make a single request describing the three deliverables:

```
Using the attached quarterly-summary.md, produce three documents in ./output:

1. A Word report (quarterly-report.docx) — full prose, headings for each
   section, and a summary table of the key metrics.
2. A PowerPoint deck (quarterly-deck.pptx) — one title slide plus one slide
   per section, concise bullet points, and the metrics table on its own slide.
3. A PDF (quarterly-onepager.pdf) — a single-page executive summary with the
   three most important takeaways.

Keep the messaging consistent across all three.
```

Fabric will work through each deliverable, invoking the matching skill for each format. Because it's all one conversation, the three documents stay consistent with each other — the same numbers, the same framing, adapted to each format's strengths (prose for Word, bullets for slides, brevity for the one-pager).

---

## Step 4: Review the Output

In agentic mode, Fabric writes the files into your project. Open them to check:

- The `.docx` opens cleanly in Word with proper headings and a real table
- The `.pptx` opens in PowerPoint with the expected slides
- The `.pdf` renders as a clean single page

If something's off, just say so:

```
The deck has too much text per slide. Cut each slide to 3 bullets max and
move the detail into the speaker notes.
```

Fabric regenerates the affected file without you having to restart.

---

## Step 5: Iterate on One Format Without Touching the Others

Because each document is a separate file, you can refine them independently:

```
Leave the Word report and PDF as they are. For the PowerPoint, add a closing
slide with next steps and three action items.
```

---

## Variations

**Single format** — You don't have to generate all three. Install only the skill you need and ask for just that format.

**From a template** — Attach an existing `.docx` or `.pptx` and ask Fabric to follow its structure and styling for the new document.

**Data-driven** — Connect a [database](../../../using-fabric/app/databases/databases.md) or attach a spreadsheet and ask Fabric to pull the numbers directly into the report, deck, and PDF.

**Fill an existing PDF** — The PDF skill can also fill forms and merge files, not just create new PDFs — useful for populating a template with generated content.

---

## Tips

**Install before you prompt.** The AI can't produce a format it has no skill for. If a request for a `.pptx` comes back as plain text, the pptx skill probably isn't installed yet.

**Be explicit about file names and location.** Tell Fabric exactly what to name each file and where to put it, so the output lands where you expect.

**Describe the shape of each format.** Word wants prose and headings; slides want short bullets; a one-pager wants ruthless brevity. Spelling out the structure for each gives you far better results than "make a deck and a doc."

**Keep one source of truth.** Generating all formats from the same source content in one conversation is what keeps them consistent. If you generate them in separate sessions, they can drift apart.
