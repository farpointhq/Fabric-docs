# Commandes slash

<video controls playsinline width="100%">
  <source src="../../../../../assets/videos/slash-commands.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Que sont les Commandes slash dans Fabric ?

Les commandes slash sont de puissants raccourcis dans Fabric qui vous permettent de déclencher des flux de travail prédéfinis, des modèles ou des actions intégrées directement depuis la zone de chat. En saisissant une barre oblique initiale (`/`), vous ouvrez une liste déroulante d'autocomplétion contenant toutes les commandes intégrées disponibles, les modèles d'invite (prompt) personnalisés et les invites exposées par MCP.

Ces commandes aident à rationaliser les tâches de développement courantes — telles que l'explication de code, la génération de tests unitaires, les revues de code et la résolution de problèmes (issues) GitHub — sans avoir à écrire des instructions répétitives.

## Quand utiliser les Commandes slash

Utilisez les commandes slash dans Fabric lorsque vous souhaitez :

* **Exécuter rapidement des flux de travail** : Effectuer des opérations comme `/explain`, `/tests` ou `/simplify` sur des fichiers ou des fonctions spécifiques.
* **Automatiser les tâches Git et GitHub** : Générer des messages de commit avec `/commit` ou résoudre des problèmes avec `/fix`.
* **Renommer des conversations** : Renommer instantanément la session de chat en cours avec `/rename <new-title>`.
* **Étendre avec des invites personnalisées** : Ajouter des modèles de commande `.md` personnalisés dans votre répertoire de ressources ou utiliser les invites MCP en toute transparence.

---

## Commandes slash disponibles

Fabric inclut des commandes intégrées, des commandes de flux de travail/modèle personnalisées, et prend en charge l'extension des commandes via des serveurs MCP externes.

### Commandes intégrées

* **`/rename <new-title>`**
    * **Indication d'argument** : `<new-title>`
    * **Description** : Renomme la session de chat en cours avec le titre spécifié. Cela s'exécute localement sans génération par LLM, en injectant un message de l'assistant pour un retour immédiat.

### Commandes de flux de travail et de modèle personnalisées

Ces commandes chargent des modèles d'invite (prompt) basés sur Markdown depuis le répertoire de ressources de Fabric (`resources/commands` en développement, ou le dossier `commands` des paramètres utilisateur en production) et les développent, en s'appuyant sur les fichiers actifs de l'espace de travail et sur les arguments fournis.

| Commande | Indication d'argument | Description |
| :--- | :--- | :--- |
| **`/explain`** | `[file, function, or description]` | Explique en langage clair le fonctionnement du code cible. Se concentre sur l'onglet de fichier actuellement actif si aucun argument n'est fourni. |
| **`/tests`** | `[file, function, or description]` | Génère des tests unitaires complets (par exemple, Vitest) conformes au style et aux pratiques du projet. |
| **`/simplify`** | `[file, function, or description]` | Refactorise les blocs de code complexes pour les rendre plus propres, plus simples et plus efficaces. |
| **`/code-review`** | `[PR#, commit range, or description]` | Examine les modifications d'une PR ou d'une plage de commits pour la qualité, le style, la sécurité et les performances. |
| **`/commit`** | `[context]` | Analyse les modifications Git en zone de staging dans l'espace de travail et rédige un message de commit descriptif et sémantique. |
| **`/fix`** | `<issue-number>` | Automatise la résolution d'un problème (issue) GitHub dans un arbre de travail (worktree) Git isolé selon un flux de travail TDD strict. |
| **`/implement`** | `<plan-url>` | Implémente les modifications d'un document de planification approuvé dans un arbre de travail (worktree) isolé. |
| **`/implement_with_dag`**| `<plan-url>` | Implémente des modifications sur plusieurs fichiers à l'aide d'un orchestrateur de tâches en graphe orienté acyclique (DAG). |
| **`/issue`** | `<issue-number>` | Récupère et affiche les informations détaillées d'un problème (issue) GitHub. |
| **`/issue_plan`** | `<issue-number>` | Rédige un plan d'implémentation structuré pour traiter un problème (issue) GitHub spécifique. |
| **`/research`** | `<topic or description>` | Recherche un sujet ou un bogue dans la base de code ou via les capacités de recherche web. |
| **`/review`** | `[file, PR#, or commit range]` | Examine les modifications d'un fichier spécifique ou une pull request pour obtenir un retour. |
| **`/test_e2e`** | `[description]` | Génère ou exécute des tests d'intégration de bout en bout. |

> [!TIP]
> Vous pouvez créer vos propres commandes personnalisées en ajoutant des fichiers `.md` à votre répertoire de commandes personnalisées (configurable dans les paramètres). Tout fichier markdown comportant un simple bloc de métadonnées frontmatter YAML contenant une `description` et un `argument-hint` apparaîtra automatiquement comme une commande slash.

---

## Comment utiliser les Commandes slash

### Étape 1 : Ouvrir le sélecteur de modèle

Cliquez sur le sélecteur de modèle principal dans la barre d'outils du chat pour choisir un modèle approprié.

![Ouvrir le sélecteur de modèle](../../../assets/screenshots/slash-commands/1.png)

### Étape 2 : Sélectionner le modèle Fabric XLarge

Sélectionnez un modèle (comme « Fabric XLarge ») qui prend en charge l'orchestration des commandes slash.

![Sélectionner le modèle Fabric XLarge](../../../assets/screenshots/slash-commands/2.png)

### Étape 3 : Déclencher la liste déroulante d'autocomplétion

Cliquez dans la zone de texte du compositeur et saisissez une barre oblique (`/`). La liste déroulante d'autocomplétion s'ouvre en glissant, répertoriant toutes les commandes enregistrées, leurs descriptions et leurs indications d'argument.

![Déclencher la liste déroulante d'autocomplétion](../../../assets/screenshots/slash-commands/3.png)

### Étape 4 : Saisir la commande et les arguments

Saisissez le reste de la commande (par exemple `/explain template.yaml`). Le guide d'indication d'argument vous aide à formater correctement les paramètres.

![Saisir la commande et les arguments](../../../assets/screenshots/slash-commands/4.png)

### Étape 5 : Soumettre et exécuter

Appuyez sur Entrée ou cliquez sur le bouton Envoyer pour exécuter la commande slash. Fabric va développer le modèle de commande, analyser l'espace de travail pour trouver `template.yaml`, et lancer l'analyse.

![Soumettre et exécuter](../../../assets/screenshots/slash-commands/5.png)

### Étape 6 : Examiner les résultats de l'explication

Attendez la fin de l'exécution de la commande. Fabric présente une explication de code complète et magnifiquement structurée directement dans le fil de messages du chat.

![Examiner les résultats de l'explication](../../../assets/screenshots/slash-commands/6.png)
