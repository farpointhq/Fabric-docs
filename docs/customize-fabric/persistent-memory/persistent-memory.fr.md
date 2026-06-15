# Mémoire persistante

## Qu'est-ce que la mémoire persistante ?

La mémoire persistante est le moyen de donner à l'IA de Fabric un ensemble permanent d'instructions concernant votre projet — des choses qu'elle devrait toujours savoir, sans que vous ayez à les expliquer à chaque conversation.

Pour cela, vous placez un fichier **`AGENTS.md`** à la racine de votre projet. Chaque fois que vous démarrez un chat dans Fabric, l'IA lit ce fichier automatiquement avant toute autre chose. Considérez-le comme un briefing permanent : contexte du projet, normes de codage, décisions importantes et toutes les règles que l'IA doit suivre.

## Pourquoi AGENTS.md est important

Sans mémoire persistante, chaque nouvelle session de chat repart d'une page blanche. Vous finissez par répéter sans cesse le même contexte — « nous utilisons Vitest, pas Jest », « ne jamais faire de squash-merge », « ce service se trouve dans `src/main/services/` ».

Avec un `AGENTS.md` dans votre projet, ce contexte est toujours chargé. L'IA connaît vos conventions avant même que vous ne disiez un mot.

C'est aussi le bon endroit pour placer les **règles de sécurité et les exigences de flux de travail** que l'IA doit respecter pour chaque tâche — des choses comme « ne jamais exécuter `npm test` directement » ou « toujours créer une PR, ne jamais pousser sur main ». Ces instructions ont plus de poids qu'un message ponctuel, car l'IA les voit au début de chaque session.

## Comment l'utiliser

**1. Créez le fichier**

Ajoutez `AGENTS.md` à la racine de votre projet (à côté de `package.json`, `README.md`, etc.) :

```
my-project/
├── AGENTS.md        ← create this
├── package.json
└── src/
```

**2. Rédigez vos instructions en langage clair**

Aucune syntaxe particulière n'est requise — juste du markdown. Concentrez-vous sur les éléments que l'IA ne peut pas déduire en lisant votre code :

```markdown
# My Project Agent Instructions

## Project Overview
This is a Next.js app with a Postgres database. The backend API lives in
`src/api/` and the frontend components in `src/components/`.

## Coding Standards
- Use TypeScript everywhere. No `any` types.
- All database queries go through the service layer in `src/services/`.
- Write tests with Vitest. Test files live next to the code they test.

## Critical Rules
- Never push directly to `main`. Always open a PR.
- Never run the full test suite locally — it takes 10+ minutes. Run
  `npm run test:changed` instead.

## How We Work
When fixing a bug, always add a regression test before changing the code.
When adding a feature, update the relevant section in `docs/` when done.
```

**3. Fabric le charge automatiquement**

Vous n'avez rien d'autre à faire. La prochaine fois que vous ouvrirez une session de chat dans Fabric pointant vers ce projet, l'IA aura déjà lu votre `AGENTS.md` et suivra ses instructions tout au long de la conversation.

## Que mettre dans AGENTS.md

Bons éléments à inclure :

- **Aperçu du projet** — ce que fait le projet, ses principaux répertoires, comment il est structuré
- **Normes de codage** — règles de formatage, conventions de nommage, bibliothèques à utiliser
- **Règles de flux de travail** — fonctionnement des PR, nommage des branches, processus de revue
- **Règles de sécurité** — commandes à ne jamais exécuter, fichiers à ne jamais modifier, choses qui nécessitent l'approbation de l'utilisateur
- **Conventions de test** — quel exécuteur de tests, où se trouvent les tests, ce qu'il faut tester
- **Pièges courants** — éléments ayant déjà causé des bugs, écueils auxquels l'IA doit prêter attention

Évitez de mettre dans `AGENTS.md` des choses déjà évidentes à la lecture du code — réservez-le au contexte que l'IA ne peut vraiment pas déduire par elle-même.

## Portée : projet vs utilisateur

Vous pouvez avoir plusieurs `AGENTS.md` :

- **Niveau projet** (`<project-root>/AGENTS.md`) — s'applique uniquement à ce projet. Validez-le dans votre dépôt pour que toute l'équipe en profite.
- **Niveau utilisateur** (`~/.agents/AGENTS.md` ou `~/.claude/AGENTS.md`) — s'applique à tous les projets que vous ouvrez dans Fabric. Idéal pour les préférences personnelles comme « toujours expliquer ton raisonnement » ou « préférer des réponses concises ».

Lorsque les deux existent, Fabric les combine, les instructions de niveau projet ayant la priorité sur celles de niveau utilisateur.

## Conseils

- **Soyez direct.** L'IA prend les instructions au pied de la lettre. « Préférer les composants fonctionnels » est plus clair que « nous avons tendance à apprécier les composants fonctionnels ».
- **Restez concentré.** Un `AGENTS.md` de 50 lignes qui couvre les vrais risques est plus efficace qu'un de 500 lignes que l'IA doit parcourir laborieusement.
- **Mettez-le à jour quand les choses changent.** Si vous ajoutez un nouveau service, renommez un répertoire ou changez une convention, mettez à jour `AGENTS.md` en même temps.
- **Commencez par les règles de sécurité.** Les entrées les plus précieuses sont celles qui empêchent l'IA de faire quelque chose d'irréversible — ajoutez-les en premier.
