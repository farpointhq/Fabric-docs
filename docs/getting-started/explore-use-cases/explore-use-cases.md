# Explore Use Cases

Fabric started as an AI IDE, and it's still the best place to write, review, and ship code. But the combination of parallelization, deep customization, and persistent knowledge management opens up a much broader set of workflows — from individual developers clearing a backlog to students writing research papers to finance professionals automating reporting. If your work involves reading, writing, reasoning, or organizing information, Fabric can help.

---

## For Developers

As fellow developers, we built the platform we wanted to use ourselves. That means no artificial limits on how you work.

**Unconstrained model selection** — Swap between Anthropic, OpenAI, Google, DeepSeek, local models, and Fabric's own hosted models mid-conversation. Pick the model that's right for the task, not the one your tool happens to support.

**Agentic harnesses** — Fabric's orchestration layer manages multi-step tasks end-to-end: reading files, running commands, applying edits, and looping back when something doesn't look right. You stay in the loop without manually driving every step.

**Reduce context switching** — Run a long agentic task in one tab while asking questions in another. Background agents tackle backlog items while you stay focused on the work in front of you.

**Multi-modal programming** — Attach screenshots, mockups, diagrams, and design files directly to the conversation. Describe a UI visually, reference an error screenshot, or paste an architectural diagram — Fabric handles it all as first-class input.

**Codebase research** — Instead of grepping through files yourself, ask Fabric to map how a system works, trace a data flow, or find every place a pattern is used. It reads the actual code and gives you answers grounded in your project.

!!! example "Developer Workflows"
    - "I have 12 open issues — triage them and draft a fix for anything under 30 minutes of work"
    - "Trace every place we call the payments API and flag anywhere that doesn't handle errors"
    - "Here's a Figma screenshot — build this component to match"
    - "Run the test suite, find the failures, and fix them one by one"

---

## For Enterprises

Enterprise teams face a different problem: scale. Hundreds of engineers, millions of lines of code, and AI tools that require constant hand-holding to stay accurate.

**99% frontier accuracy at 70% lower cost** — Fabric's proprietary routing algorithm directs each task to the most appropriate model for the job. Simple tasks go to fast, cheap models. Complex reasoning goes to frontier models. The result is near-frontier accuracy across the board without paying frontier prices for everything.

**Parallelization at scale** — Multiple agents can work concurrently across different parts of the codebase — one addressing security findings, another writing tests for new features, another updating documentation. Work that would take a developer days can run in parallel in the background.

**Knowledge management across teams** — Fabric's persistent memory system means your engineering standards, architectural decisions, and codebase conventions are encoded once and respected consistently. New engineers get up to speed faster. AI agents follow the same rules the team does.

**Customization without engineering overhead** — Skills, MCP integrations, and custom slash commands let teams extend Fabric to fit their specific stack and workflows — without forking the tool or building internal tooling from scratch.

!!! example "Enterprise Workflows"
    - Run automated code review on every PR against your team's documented standards
    - Generate migration scripts across a large codebase when upgrading a dependency
    - Maintain living documentation that reflects the real state of the code
    - Onboard new engineers by letting them query the codebase in natural language

---

## For Students

Whether you're working on assignments, preparing for exams, or getting through a dense reading list, Fabric acts as a tireless study partner that knows your material and keeps up with your thinking.

**Understand difficult material** — Paste a dense academic paper, a textbook chapter, or a lecture transcript and ask Fabric to explain it clearly, break it into key ideas, or connect it to something you already know.

**Write better, faster** — Fabric doesn't write your essays for you, but it will help you sharpen an argument, restructure a draft, check your reasoning, and suggest where your evidence is weak. Think of it as a writing tutor available at 2am before a deadline.

**Research without drowning** — Use the built-in browser to read sources without leaving the app. Ask Fabric to summarize a paper, extract the relevant findings, or compare two conflicting arguments from different sources.

**Prepare for exams** — Share your notes and ask Fabric to generate practice questions, quiz you on the material, or identify the concepts most likely to come up based on what you've covered.

**Cite and format correctly** — Ask Fabric to format a bibliography in APA, MLA, or Chicago, or to check that your in-text citations are consistent throughout a document.

!!! example "Student Workflows"
    - "Here's a 40-page paper — summarize the key argument and methodology in plain English"
    - "I'm writing about climate policy. Here's my draft thesis — is the argument logically sound?"
    - "Generate 20 practice questions from these lecture notes for my exam on Friday"
    - "Explain Bayes' theorem to me like I haven't taken statistics before"

---

## For Researchers

Research moves slowly when you're switching between papers, notes, data, and writing tools. Fabric keeps everything in one place and lets you move faster through the parts that don't require your expertise.

**Literature review at speed** — Feed Fabric a collection of papers or abstracts and ask it to identify common themes, contradictions, gaps in the literature, or how a specific concept evolves across sources.

**Data analysis and interpretation** — Connect a database or attach a CSV, describe what you're looking for, and ask Fabric to query, summarize, or visualize the data. No need to write Python or SQL yourself unless you want to.

**Draft and iterate on writing** — Fabric can write a first draft of a methodology section, an abstract, or a discussion section based on your notes. It keeps track of what you've written so later drafts stay consistent.

**Cross-reference and fact-check** — Ask Fabric to verify claims against sources you've attached, flag statements that need citations, or identify where two sources say conflicting things.

**Organize your thinking** — Describe a research question out loud and let Fabric help you structure it: what sub-questions does it raise, what would falsify the hypothesis, what prior work is most relevant.

!!! example "Research Workflows"
    - "Here are 8 abstracts on working memory. What are the main areas of disagreement?"
    - "I have this dataset connected — what's the distribution of outcomes by demographic group?"
    - "Write a discussion section based on these results and these three cited papers"
    - "Which claims in this draft don't have a supporting citation?"

---

## For Finance Professionals

Finance work is full of structured data, repetitive reporting, and documents that need to be read carefully and summarized precisely. Fabric handles the mechanical parts so you can focus on the judgment calls.

**Analyze financial documents** — Attach an earnings report, 10-K, or investor deck and ask Fabric to extract the key figures, flag unusual line items, or compare performance against a prior period.

**Build and check models** — Describe the logic of a financial model in plain language and let Fabric generate the formulas, spot errors in your spreadsheet structure, or explain what a formula is doing in a model you've inherited.

**Automate reporting** — Connect to a database with your financial data, select the relevant tables, and ask Fabric to draft a weekly or monthly performance summary in whatever format your team uses.

**Research companies and markets** — Use the built-in browser to read filings, news, and analyst reports. Ask Fabric to extract the relevant numbers, summarize the narrative, or compare two companies on specific metrics.

**Draft client communications** — Describe the situation and key points, and ask Fabric to draft an investment update, a portfolio summary, or a client memo in your firm's tone and format.

!!! example "Finance Workflows"
    - "Here's a 10-K filing — what are the three biggest risk factors and how do they compare to last year?"
    - "I have a P&L connected in the database — summarize the variance against budget by department"
    - "This DCF model has a circular reference somewhere — help me find it"
    - "Draft a one-page investor update for Q2 based on these bullet points"

---

## Day-to-Day Automations

Beyond any specific profession, Fabric is useful for the recurring tasks that eat up time across every kind of work.

**Summarize long documents** — Drop in any long document — a contract, a meeting transcript, a report, a thread — and get a clean summary with the key points pulled out. No more reading a 40-page document to find the two paragraphs that matter to you.

**Process and transform information** — Ask Fabric to reformat data, convert between structures, extract specific fields from unstructured text, or turn a list of items into a structured table. Tedious data wrangling becomes a one-sentence instruction.

**Draft repetitive communications** — Writing similar emails or messages over and over? Describe the context and what needs to be said, and ask Fabric to draft it. Review, edit, and send — in a fraction of the time.

**Build personal knowledge bases** — Keep a folder of notes, articles, and documents in Fabric and use it as a searchable, queryable second brain. Ask questions across everything you've saved, not just within a single document.

**Plan and organize** — Describe a project, event, or goal and ask Fabric to break it into steps, identify what you're missing, draft a timeline, or spot conflicts in your plan.

**Automate file and folder work** — In agentic mode, Fabric can rename files, reorganize folders, batch-process documents, and apply consistent formatting across multiple files — the kind of housekeeping that never gets done because it takes too long manually.

!!! example "Day-to-Day Workflows"
    - "Here's a 2-hour meeting transcript — give me a summary and a list of action items with owners"
    - "I have 200 customer feedback responses — cluster them by theme and count each"
    - "Draft a follow-up email to a client who hasn't responded in two weeks, professional but direct"
    - "Rename all the files in this folder to follow the format YYYY-MM-DD_description"

---

## New Paradigms

Fabric's team works closely with design partners to shape what AI-assisted development looks like as the technology matures. A few directions that are coming into focus:

**Background agents as a new primitive** — The most powerful shift isn't faster autocomplete — it's agents that work on tasks autonomously while you do other things. Fabric is built from the ground up to support this: task queuing, parallel execution, and transparent logs of what each agent did.

**Codebase as context** — Rather than treating each conversation as stateless, Fabric treats your entire codebase as persistent context. The more you work in a project, the better Fabric understands it — your patterns, your conventions, your architecture.

**Humans in the loop, not out of it** — Full autonomy isn't always the right answer. Fabric is designed around the idea that the best outcomes come from AI doing the heavy lifting while the developer makes the calls that matter — approving changes, setting direction, catching things that require judgment.

---

## What to Try First

Not sure where to start? Here are a few high-value workflows to explore in your first week:

| If you want to... | Try this |
|-------------------|----------|
| Clear old issues | Ask Fabric to triage your backlog and generate fixes for the simple ones |
| Understand unfamiliar code | Open a file and ask "how does this work and what calls it?" |
| Speed up code review | Use `/review` on a file before submitting or merging a PR |
| Understand a dense paper | Paste the PDF and ask for a plain-English summary of the key argument |
| Prepare for an exam | Share your notes and ask Fabric to generate practice questions |
| Analyze a financial document | Attach a report and ask Fabric to pull out the key figures and flag anything unusual |
| Process a long meeting | Drop in a transcript and get a summary plus action items |
| Automate repetitive file work | Describe what needs doing and let agentic mode handle it |
| Draft something faster | Describe the context, get a first draft, refine from there |

The best way to find your workflow is to start with something you already do manually and ask: *could Fabric handle this?* More often than not, the answer is yes.
