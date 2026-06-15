# Bonnes pratiques

Un ensemble d'habitudes et de schémas qui rendent le travail avec Fabric plus efficace. Aucun n'est obligatoire — Fabric fonctionne tel quel — mais ils font une différence notable une fois les bases acquises.

---

## Donnez à l'IA le bon contexte

La qualité des résultats de Fabric est directement liée à la qualité du contexte dont il dispose. Trop peu, et il fait des suppositions. Trop, et les détails importants se retrouvent noyés.

**Ajoutez les fichiers qui comptent, pas tous.** Utilisez l'explorateur de fichiers ou le trombone pour joindre les fichiers spécifiques liés à votre tâche. Joindre tout votre projet pour une modification d'une ligne ralentit les choses et peut embrouiller le modèle.

**Soyez précis sur ce que vous voulez modifier.** « Corrige le bug dans le module d'authentification » est plus difficile à exploiter que « la fonction `validateToken` dans `src/auth/token.ts` renvoie `null` quand le jeton a expiré au lieu de lever une exception — corrige ça ».

**Incluez les messages d'erreur mot pour mot.** Collez la trace de pile complète ou la sortie d'erreur. Ne la résumez pas — la formulation exacte contient souvent le signal dont l'IA a besoin.

**Partagez le schéma pertinent quand vous travaillez avec des données.** Si vous demandez une requête ou une migration, sélectionnez d'abord les tables dans l'explorateur de base de données. Sans le schéma, l'IA devine les noms et les types des colonnes.

---

## Configurez AGENTS.md pour chaque projet

La chose la plus rentable que vous puissiez faire est de créer un fichier `AGENTS.md` à la racine de votre projet. Fabric le lit au début de chaque session de discussion, donc tout ce que vous y mettez s'applique automatiquement — inutile de réexpliquer vos conventions à chaque fois.

Bonnes choses à inclure :

- **Aperçu du projet** — ce qu'est le projet et ce qu'il fait, en 2-3 phrases
- **Stack technique** — langages, frameworks, bases de données, dépendances clés
- **Conventions de code** — schémas de nommage, structure des fichiers, tout ce que l'IA doit respecter
- **Règles de test** — comment lancer les tests, quel framework de test vous utilisez, les commandes à éviter
- **Règles de sécurité** — fichiers ou dossiers à ne pas toucher, opérations nécessitant une confirmation
- **Flux de travail courants** — comment ajouter une nouvelle fonctionnalité, comment lancer le serveur de développement, comment déployer

Plus vous êtes précis, moins vous aurez de corrections à apporter. Commencez simple et complétez dès que vous vous surprenez à réexpliquer quelque chose.

---

## Utilisez le mode agentique pour le travail en plusieurs étapes

Le mode agentique débloque la capacité de lire des fichiers, d'exécuter des commandes, de modifier du code et de réessayer après un échec. Utilisez-le pour tout ce qui implique plus d'une étape.

**Laissez-le planifier avant d'agir.** Demandez à Fabric de décrire son approche avant d'apporter des modifications : *« Avant de commencer, dis-moi quels fichiers tu vas toucher et quelle est l'approche globale. »* Cela fait remonter les malentendus tôt, avant qu'ils ne deviennent des modifications à annuler.

**Examinez les différences (diffs) avant d'accepter.** Fabric vous montre chaque modification de fichier dans une visionneuse de différences. N'acceptez pas tout en bloc — repérez les modifications involontaires, surtout dans les fichiers que vous n'avez pas mentionnés.

**Utilisez « Fabric prend le volant » pour les tâches bien définies.** Le mode entièrement autonome est idéal quand la tâche est claire et le rayon d'impact restreint — générer des tests, mettre à jour une configuration, reformater un fichier. Réservez-le aux tâches où les surprises sont faciles à repérer et à annuler.

**Gardez les tâches ciblées.** « Refactorise toute la base de code » est difficile à bien faire. « Renomme `getUserData` en `fetchUserProfile` partout où il est utilisé et mets à jour les tests » est faisable.

---

## Choisissez le bon modèle pour la tâche

Toutes les tâches n'ont pas besoin du modèle le plus puissant. Adapter le modèle à la tâche permet d'économiser des coûts et donne généralement des résultats plus rapidement.

| Type de tâche | Niveau recommandé |
|-----------|-----------------|
| Décisions d'architecture, débogage difficile, refactorisations complexes | Large / XLarge |
| Développement de fonctionnalités, revue de code, rédaction | Medium |
| Modifications rapides, renommage, formatage, questions simples | Small |
| Tâches d'assistance en arrière-plan (nommage d'onglets, suggestions de fichiers) | Fabric sélectionne automatiquement |

Changez de modèle en cours de conversation quand la tâche change. Si vous avez commencé à explorer avec un modèle rapide et que vous êtes maintenant prêt à implémenter quelque chose de complexe, montez en gamme — le contexte est conservé.

---

## Utilisez les onglets pour rester organisé

Chaque onglet est une conversation indépendante avec son propre contexte. Tirez-en parti.

- Gardez **un onglet par tâche**, pas un seul onglet pour tout. Un onglet pour la fonctionnalité que vous construisez, un autre pour le bug que vous investiguez.
- Lancez les **tâches agentiques longues dans un onglet en arrière-plan** pendant que vous continuez à travailler dans un autre.
- Ouvrez un **onglet de recherche** pour parcourir la documentation ou lire des articles, afin de ne pas polluer votre contexte de codage.
- Utilisez **Compact** quand une conversation devient longue mais que vous voulez la poursuivre — il résume les anciens messages et libère de l'espace dans la fenêtre de contexte sans tout recommencer.

---

## Rédigez des invites efficaces

Fabric est une IA performante, mais une invite bien formulée donne tout de même de meilleurs résultats qu'une invite vague.

**Dites ce que vous voulez, pas seulement ce qui ne va pas.** « Cette fonction est lente » est moins utile que « Cette fonction est lente — réécris-la pour réduire le nombre d'appels à la base de données ».

**Donnez les contraintes d'emblée.** Si vous avez besoin que quelque chose soit fait sans dépendances externes, dites-le. Si cela doit correspondre à un schéma existant, indiquez ce schéma. Des contraintes énoncées au départ évitent les allers-retours à la fin.

**Demandez des explications quand vous apprenez.** Si vous êtes en terrain inconnu, demandez à Fabric d'expliquer ce qu'il fait au fur et à mesure. Vous repérerez les malentendus plus tôt et apprendrez plus vite.

**Itérez.** Une bonne première réponse est souvent à 80 % du résultat. Relancez : « La logique semble bonne mais la gestion des erreurs manque — ajoute-la. » Inutile de démarrer une nouvelle conversation pour affiner.

---

## Gardez votre contexte propre

L'espace de la fenêtre de contexte est une ressource limitée. Bien le gérer maintient l'IA précise sur de longues sessions.

- **Utilisez Compact** avant une longue tâche agentique pour évacuer les échanges antérieurs qui ne sont plus pertinents.
- **Démarrez un nouvel onglet** quand la conversation actuelle s'est beaucoup éloignée du sujet d'origine.
- **Retirez les fichiers joints** (cliquez sur le × d'une puce) quand ils ne sont plus nécessaires à la question en cours.
- **Surveillez l'indicateur de contexte** dans la barre de discussion — quand il se remplit, compactez ou continuez dans un nouvel onglet.
