# Set Up AGENTS.md for Your Project

**Time:** 15 minutes  
**Difficulty:** Beginner  
**What you'll build:** A persistent memory file that makes Fabric aware of your project's conventions, stack, and rules — automatically, every session.

---

## What Is AGENTS.md?

`AGENTS.md` is a plain Markdown file you place at the root of your project. Fabric reads it at the start of every chat session and uses its contents as persistent context. Anything you put there is automatically available to the AI — no copy-pasting, no re-explaining.

Without `AGENTS.md`, Fabric starts each session cold and has to re-learn your project from scratch. With it, the AI already knows your stack, your conventions, your testing rules, and anything else you've written down.

---

## Step 1: Create the File

In your project's root directory, create a file called `AGENTS.md`.

```bash
touch AGENTS.md
```

Or create it directly in Fabric's file browser by right-clicking the root folder.

---

## Step 2: Add a Project Overview

Start with a short description of what the project is. Two or three sentences is enough.

```markdown
# AGENTS.md

## Project Overview
This is a Next.js 14 web app for managing freelance invoices.
It uses Supabase for the database and Auth.js for authentication.
The main user flow is: create client → create project → generate invoice → send to client.
```

This helps the AI orient itself before it reads any code.

---

## Step 3: Document Your Stack

List the key technologies, versions where relevant.

```markdown
## Tech Stack
- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript (strict mode)
- **Database**: Supabase (Postgres)
- **Auth**: Auth.js v5
- **Styling**: Tailwind CSS
- **Testing**: Vitest + React Testing Library
- **Deployment**: Vercel
```

---

## Step 4: Capture Your Conventions

This is where `AGENTS.md` earns its keep. Write down the conventions that exist in your head but aren't visible in the code.

```markdown
## Code Conventions
- Components go in `src/components/`, one file per component
- Server actions go in `src/actions/`, named `verbNoun.ts` (e.g. `createInvoice.ts`)
- Use named exports, never default exports
- All database queries go through `src/lib/db.ts` — never query Supabase directly in components
- Error handling: use the `Result<T>` type from `src/lib/result.ts`, never throw in server actions
- CSS: Tailwind utility classes only, no custom CSS files
```

---

## Step 5: Add Testing Rules

Prevent the AI from running commands you don't want it to run, or tell it exactly how to run your tests.

```markdown
## Testing
- Run tests with: `npx vitest run`
- Do NOT use `npm test` — it runs a different script
- Test files live next to the source file: `component.tsx` → `component.test.tsx`
- Mock Supabase with the helpers in `src/test/mocks/supabase.ts`
- Do not write snapshot tests
```

---

## Step 6: Add Safety Rules

If there are files or operations the AI should never touch without asking, say so explicitly.

```markdown
## Safety Rules
- Never modify `supabase/migrations/` directly — always create a new migration file
- Never commit `.env.local` or any file containing secrets
- Ask before changing `src/lib/db.ts` — it's used everywhere
- The `main` branch is protected — always work on a feature branch
```

---

## Step 7: Add Common Workflows

Anything you do repeatedly that requires multiple steps is worth documenting.

```markdown
## Common Workflows

### Adding a new page
1. Create the route in `src/app/`
2. Add a server component for data fetching
3. Add a client component in `src/components/` for interactivity
4. Add the route to `src/config/nav.ts`

### Running the dev server
```bash
npm run dev
```
App runs at http://localhost:3000

### Creating a database migration
```bash
npx supabase migration new <migration-name>
```
Edit the file in `supabase/migrations/`, then run `npx supabase db push`.
```

---

## Step 8: Test It

Open Fabric, start a new chat, and ask: *"What's this project and what testing framework does it use?"*

If Fabric answers correctly without you having said anything, `AGENTS.md` is working.

---

## Tips

**Keep it honest.** The AI will follow what's in `AGENTS.md` — if it says something outdated, you'll get outdated behavior. Review it when the stack or conventions change.

**Add to it over time.** Don't try to write the perfect file upfront. Add a rule whenever you find yourself correcting the AI for the same thing twice.

**Be specific about commands.** "Run the tests" is ambiguous. `npx vitest run` is not.

**Use it for non-code projects too.** A writing project, a research folder, a financial model — any project folder can have an `AGENTS.md` with context that shapes how Fabric helps.
