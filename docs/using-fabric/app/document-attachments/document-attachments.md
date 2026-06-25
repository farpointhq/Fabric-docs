# Document Attachments

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../assets/videos/document-attachments.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</div>

You don't have to copy text out of a document to ask the AI about it. Fabric lets you attach **PDFs, Word documents, Excel spreadsheets, and PowerPoint files** directly to the chat — Fabric reads their contents and makes them available to the AI as context.

---

## Supported File Types

You can attach common document formats:

| Type | Extensions |
|------|------------|
| **PDF** | `.pdf` |
| **Word** | `.docx`, `.doc` |
| **Excel** | `.xlsx`, `.xls` |
| **PowerPoint** | `.pptx`, `.ppt` |

On top of these, you can attach plain text and code files, and — with a vision-capable model — images. This page focuses on the document formats above.

---

## How to Attach a Document

Click the **paperclip icon** in the chat input bar to open a file picker, then choose one or more files. They appear as chips above the text field. Type your question around them and send as usual.

---

## What Fabric Does With Them

When you attach a document, Fabric doesn't just hand the raw file to the AI — it **extracts the content** into a form the AI can actually read and reason about:

- **PDFs** — the text is pulled out so the AI can read the whole document. (Models with native PDF support can also see the pages directly.)
- **Excel spreadsheets** — each sheet is converted into a clean table the AI can read, with your headers and rows intact.
- **Word documents** — the text is extracted, along with any embedded images.
- **PowerPoint files** — the text from each slide is extracted, along with images from the deck.

This means you can ask real questions about the document's content — summarize it, pull out specific figures, compare sections, or turn it into something else — without copying and pasting anything.

---

## What You Can Do With It

- **Summarize a long PDF** — attach a report, contract, or paper and ask for the key points.
- **Work with spreadsheet data** — attach an Excel file and ask the AI to analyze the numbers, explain a trend, or draft a formula.
- **Pull details out of a document** — "What's the termination clause in this contract?" or "List every action item in these meeting notes."
- **Reformat or transform** — turn a slide deck's content into a written summary, or a spreadsheet into a report.

---

## Notes and Limits

- **File size** — documents up to **25 MB** each.
- **Long documents** — very large documents are truncated to fit the AI's context, and Fabric warns you when that happens.
- **Scanned PDFs** — Fabric reads the text layer of a PDF. Scanned or image-only PDFs (with no selectable text) can't be read, since there's no built-in OCR.
- **Password-protected PDFs** — these are rejected; remove the protection and attach again.
- **Privacy** — extracted content is sent to the AI model you've selected as part of your conversation, just like the rest of your message.
