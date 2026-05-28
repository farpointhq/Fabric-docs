# Agent Skills in Fabric

🚧 Video tutorial is in progress.

## What is Agent Skills in Fabric?

**Agent Skills** are reusable instruction packs that Fabric's AI agent loads on demand when a task matches their scope. Each skill is defined by a `SKILL.md` file containing system prompt guidelines, capability declarations, and optional tool restrictions — and appears in Settings as a toggleable card.

Skills let you teach the AI your team's coding style, a specific framework's conventions, or any specialized workflow, without having to re-explain context every conversation. You can install skills from the community marketplace, point Fabric at a URL or local folder, or drop a `SKILL.md` directly into your project.


## When to use Agent Skills in Fabric

Use Skills in Fabric when you want to:

* **Specialize agent behavior** — Equip the AI with dedicated expertise for complex roles (vitest writer, database auditor, code refactorer) without repeating context every session.
* **Standardize team workflows** — Install project-scoped skills so every team member's agent generates code that adheres to the same stylistic guidelines and PR structure.
* **Leverage community prompts** — Deploy optimized, community-vetted instruction sets for specific frameworks, tools, or APIs instead of writing them yourself.
* **Write custom skills** — Drop a `SKILL.md` into your project's `.fabric/skills/` folder and Fabric picks it up automatically.


## How to use Agent Skills in Fabric

### Step 1: Open Application Settings

Click the settings gear icon at the bottom of the left sidebar to open the Settings modal.

![Open Application Settings](../../assets/screenshots/skills/1.png)

### Step 2: Navigate to the Skills Tab

Click **Skills** in the Settings sidebar to open the Agent Skills panel, where you can view and manage all installed skills.

![Navigate to the Skills Tab](../../assets/screenshots/skills/2.png)

### Step 3: Skills Panel Overview

The Skills panel lists all installed skills with their name, description, version, and scope. Use **Browse Marketplace** to discover community skills, or **Install from source** to add a skill from a URL or local folder.

![Skills Panel Overview](../../assets/screenshots/skills/3.png)

### Step 4: Filter Skills by Scope

Use the scope filter bar to narrow the list. **All** shows everything, **Project** shows skills stored in your repository (`.fabric/skills/`), and **User** shows skills in your home directory available across all projects. The **Sources** button lets you control whether Fabric also reads skills from `.claude/`, `.cursor/`, or `.agents/` folders.

![Filter Skills by Scope](../../assets/screenshots/skills/4.png)

### Step 5: Expand a Skill Card

Click anywhere on a skill card to expand it and see the full details: file path, scope, allowed tools, bundled files, and the rendered SKILL.md body. Click again to collapse.

![Expand a Skill Card](../../assets/screenshots/skills/5.png)

### Step 6: Skill Card Details

The expanded view shows where the skill file lives on disk, its compatibility metadata, and a rendered preview of the SKILL.md instructions. Use the **Edit** button to open the file directly in Fabric, or the **trash** icon to uninstall it. A confirmation toast with an **Undo** option appears for 6 seconds after uninstalling.

![Skill Card Details](../../assets/screenshots/skills/6.png)

### Step 7: Install a Skill from a URL or Folder

Click **Install from source** to open the installation dialog, where you can paste a GitHub URL, a direct SKILL.md URL, or point to a local folder on disk.

![Install a Skill from a URL or Folder](../../assets/screenshots/skills/7.png)

### Step 8: The Install Dialog

The Install dialog has two tabs: **Marketplace** for browsing the skills.sh registry, and **URL / Folder** for direct installation. Paste any public `SKILL.md` URL or a GitHub repo URL pointing to a skill, choose the scope (**Project** or **User**), and click **Install**.

![The Install Dialog](../../assets/screenshots/skills/8.png)

### Step 9: Close the Install Dialog

Click the **×** or press **Escape** to close the dialog and return to the Skills panel.

![Close the Install Dialog](../../assets/screenshots/skills/9.png)
