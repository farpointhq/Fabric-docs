# Configurez AGENTS.md pour votre projet

**Durée :** 15 minutes  
**Difficulté :** Débutant  
**Ce que vous allez construire :** Un fichier de mémoire persistante qui rend Fabric conscient des conventions, de la stack et des règles de votre projet — automatiquement, à chaque session.

---

## Qu'est-ce qu'AGENTS.md ?

`AGENTS.md` est un simple fichier Markdown que vous placez à la racine de votre projet. Fabric le lit au début de chaque session de discussion et utilise son contenu comme contexte persistant. Tout ce que vous y mettez est automatiquement mis à la disposition de l'IA — sans copier-coller, sans réexpliquer.

Sans `AGENTS.md`, Fabric démarre chaque session à froid et doit réapprendre votre projet à partir de zéro. Avec lui, l'IA connaît déjà votre stack, vos conventions, vos règles de test et tout ce que vous avez consigné.

---

## Étape 1 : Créez le fichier

Dans le répertoire racine de votre projet, créez un fichier nommé `AGENTS.md`.

```bash
touch AGENTS.md
```

Ou créez-le directement dans l'explorateur de fichiers de Fabric en faisant un clic droit sur le dossier racine.

---

## Étape 2 : Ajoutez un aperçu du projet

Commencez par une courte description de ce qu'est le projet. Deux ou trois phrases suffisent.

```markdown
# AGENTS.md

## Project Overview
This is a Next.js 14 web app for managing freelance invoices.
It uses Supabase for the database and Auth.js for authentication.
The main user flow is: create client → create project → generate invoice → send to client.
```

Cela aide l'IA à s'orienter avant de lire le moindre code.

---

## Étape 3 : Documentez votre stack

Listez les technologies clés, avec les versions le cas échéant.

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

## Étape 4 : Consignez vos conventions

C'est là qu'`AGENTS.md` prouve son utilité. Notez les conventions qui sont dans votre tête mais qui ne sont pas visibles dans le code.

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

## Étape 5 : Ajoutez des règles de test

Empêchez l'IA d'exécuter des commandes que vous ne voulez pas qu'elle lance, ou indiquez-lui exactement comment lancer vos tests.

```markdown
## Testing
- Run tests with: `npx vitest run`
- Do NOT use `npm test` — it runs a different script
- Test files live next to the source file: `component.tsx` → `component.test.tsx`
- Mock Supabase with the helpers in `src/test/mocks/supabase.ts`
- Do not write snapshot tests
```

---

## Étape 6 : Ajoutez des règles de sécurité

S'il existe des fichiers ou des opérations que l'IA ne devrait jamais toucher sans demander, dites-le explicitement.

```markdown
## Safety Rules
- Never modify `supabase/migrations/` directly — always create a new migration file
- Never commit `.env.local` or any file containing secrets
- Ask before changing `src/lib/db.ts` — it's used everywhere
- The `main` branch is protected — always work on a feature branch
```

---

## Étape 7 : Ajoutez les flux de travail courants

Tout ce que vous faites de manière répétée et qui nécessite plusieurs étapes mérite d'être documenté.

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

## Étape 8 : Testez

Ouvrez Fabric, démarrez une nouvelle discussion et demandez : *« Qu'est-ce que ce projet et quel framework de test utilise-t-il ? »*

Si Fabric répond correctement sans que vous ayez rien dit, c'est qu'`AGENTS.md` fonctionne.

---

## Astuces

**Restez honnête.** L'IA suivra ce qui est dans `AGENTS.md` — s'il contient une information obsolète, vous obtiendrez un comportement obsolète. Révisez-le quand la stack ou les conventions changent.

**Complétez-le au fil du temps.** N'essayez pas de rédiger le fichier parfait d'emblée. Ajoutez une règle dès que vous vous surprenez à corriger l'IA deux fois pour la même chose.

**Soyez précis sur les commandes.** « Lance les tests » est ambigu. `npx vitest run` ne l'est pas.

**Utilisez-le aussi pour les projets non liés au code.** Un projet de rédaction, un dossier de recherche, un modèle financier — n'importe quel dossier de projet peut avoir un `AGENTS.md` avec du contexte qui façonne la manière dont Fabric vous aide.
