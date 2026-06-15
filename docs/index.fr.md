# Bienvenue dans Fabric

<div class="hero" markdown>

# ![Logo Fabric](assets/logo.png){ .no-lightbox width="42" style="vertical-align: middle; margin-right: 8px;" } Fabric

**Livrez plus vite. Gardez le contrôle. Ne naviguez jamais à l'aveugle.**

Cessez de choisir entre vitesse et qualité. Fabric vous donne des superpouvoirs de codage par IA tout en vous laissant aux commandes.

[Rejoindre la bêta](https://farpointalpha.com/fabric){ .md-button .md-button--primary }
[Voir ce qui est possible](#what-can-you-build){ .md-button }

</div>

---

## Pourquoi les développeurs adorent Fabric

**Vous avez essayé les outils de codage par IA.** Ils sont rapides — jusqu'à ce qu'ils hallucinent. Ils sont utiles — jusqu'à ce qu'ils ratent le contexte. Ils sont puissants — jusqu'à ce que vous perdiez le contrôle de votre base de code.

Fabric est différent. Nous l'avons conçu pour les développeurs qui veulent la **vélocité de l'IA** sans l'**angoisse de ne pas savoir ce qui se passe** sous le capot.

<div class="grid cards" markdown>

-   :material-eye:{ .lg .middle } **Voyez l'IA réfléchir, pas seulement produire**

    ---

    Observez l'IA raisonner sur votre problème en temps réel. Plus de boîtes noires — comprenez *pourquoi* elle suggère ce qu'elle suggère, afin de pouvoir faire confiance à ses décisions (ou les corriger).

    [:octicons-arrow-right-24: Comment ça marche](features/agentic-mode.md)

-   :material-swap-horizontal:{ .lg .middle } **Choisissez le bon modèle pour la tâche**

    ---

    Utilisez des modèles rapides pour les tâches simples, des modèles puissants pour les raisonnements complexes. Changez en cours de conversation. Vous contrôlez le compromis coût-qualité.

    [:octicons-arrow-right-24: Sélection de modèle](features/models.md)

-   :material-tab:{ .lg .middle } **Travaillez sur tout à la fois**

    ---

    Jonglez avec les corrections de bugs, le développement de fonctionnalités et l'exploration de code en parallèle. Chaque conversation conserve son contexte — fini de perdre le fil de vos pensées.

    [:octicons-arrow-right-24: Espace de travail de conversation](guide/chat.md)

-   :material-shield-check:{ .lg .middle } **Votre code, votre contrôle**

    ---

    Chaque modification de fichier requiert votre approbation. Piste d'audit complète des actions de l'IA. Vos clés API, vos données, vos règles.

    [:octicons-arrow-right-24: Sécurité et confidentialité](getting-started/configuration.md)

</div>

## Que pouvez-vous construire ?

### Livrez des fonctionnalités en heures, pas en jours

Fabric ne se contente pas d'écrire du code — il comprend votre base de code. Demandez-lui d'ajouter une fonctionnalité et il sait où placer les choses, quels motifs vous utilisez et comment les intégrer correctement.

!!! example "Flux de travail réels de développeurs"
    - « Ajoute l'authentification JWT à mon API Express, en suivant mes motifs de middleware existants »
    - « Trouve tous les endroits où nous gérons les autorisations utilisateur et ajoute la prise en charge du rôle administrateur »
    - « Refactorise cette classe pour utiliser l'injection de dépendances — et mets à jour les tests »

### Choisissez le modèle parfait pour chaque tâche

Pourquoi payer le prix fort pour un simple renommage ? Pourquoi utiliser un modèle rapide pour des décisions d'architecture complexes ? Fabric vous laisse choisir :

| Quand vous avez besoin de… | Utilisez | Pourquoi |
|------------------|-----|-----|
| Réponses rapides, corrections simples | Modèles rapides | Réponse instantanée, coût minimal |
| Raisonnement complexe | Modèles puissants | Meilleure architecture, moins d'erreurs |
| Revue de code | Votre choix | Adaptez la profondeur à l'importance |

!!! tip "Optimisez les coûts sans sacrifier la qualité"
    Changez de modèle en cours de conversation. Commencez avec un modèle rapide pour explorer, puis passez à un modèle puissant lorsque vous avez besoin d'un raisonnement approfondi.

### Laissez l'IA gérer les parties ennuyeuses

Certaines tâches sont fastidieuses mais importantes : mettre à jour les tests après une refactorisation, appliquer une correction à 50 fichiers, migrer vers une nouvelle API. Le mode agentique de Fabric gère les tâches en plusieurs étapes tout en vous laissant le contrôle :

```
"Update all API endpoints to use the new error handling pattern,
and make sure the tests still pass."
```

Vous verrez exactement ce qu'il prévoit de faire, approuverez chaque étape et le regarderez travailler. Pas de surprises, pas de commits mystérieux, pas de « qu'est-ce qu'il vient de faire ? ».

[:octicons-arrow-right-24: Voir le mode agentique en action](features/agentic-mode.md)

### Votre base de code, parfaitement comprise

Fabric construit un modèle mental de votre projet. Il sait :

- **Où se trouvent les choses** - Posez une question sur le code d'authentification et il sait qu'il faut regarder dans `src/auth/`
- **Comment vous faites les choses** - Il apprend vos motifs, conventions et style
- **Ce qui se connecte à quoi** - Il comprend les relations entre fichiers et modules

!!! success "Fini d'expliquer votre base de code"
    Vous n'avez pas besoin de coller du contexte dans chaque invite (prompt). Fabric s'en souvient.

## Au-delà du code

Fabric ne sert pas qu'à écrire des logiciels. Parce qu'il combine une IA performante avec un navigateur, un système de fichiers et un contexte persistant, il est tout aussi utile pour la réflexion et la recherche qui entourent le travail.

### Faites des recherches sans quitter votre flux

Le navigateur intégré permet à Fabric de lire n'importe quelle page que vous consultez et de l'amener directement dans la conversation. Demandez-lui de résumer une longue RFC, de comparer deux bibliothèques côte à côte ou d'extraire la section pertinente d'un fil Stack Overflow — sans rien copier-coller.

!!! example "Flux de travail de recherche"
    - « Lis cette page de documentation Stripe et montre-moi la configuration minimale dont j'ai besoin pour les paiements uniques »
    - « Compare ces deux paquets npm et dis-moi lequel est le mieux maintenu »
    - « Résume les principaux changements incompatibles dans ce guide de migration »

### Rédigez une documentation technique qui reflète vraiment le code

Pointez Fabric vers un module et demandez-lui d'écrire le README, la référence d'API ou l'entrée de journal des modifications. Parce qu'il lit le vrai code, il n'invente rien — il décrit ce qui est réellement là.

!!! example "Flux de travail de rédaction"
    - « Écris un README pour ce dépôt en fonction de ce que le code fait réellement »
    - « Génère une entrée de journal des modifications à partir des commits depuis la dernière version »
    - « Écris un runbook pour déployer ce service, à partir des scripts dans /deploy »

### Réfléchissez aux problèmes avant d'écrire une seule ligne

Utilisez Fabric comme partenaire de réflexion pour les décisions d'architecture, les compromis produit ou les analyses post-mortem d'incidents. Joignez les fichiers pertinents et menez une vraie conversation sur le problème avant de vous engager dans une direction.

!!! example "Flux de travail de planification"
    - « Je dois ajouter des notifications en temps réel à cette application. Explique-moi les compromis entre WebSockets et SSE compte tenu de ce que nous avons déjà »
    - « Nous avons eu une panne la nuit dernière. Voici le journal. Aide-moi à rédiger un post-mortem »
    - « Je dois intégrer un nouvel ingénieur à cette base de code la semaine prochaine. Aide-moi à rédiger un document de présentation »

---

## Démarrez en 5 minutes

<div class="grid cards" markdown>

-   :material-download:{ .lg .middle } **1. Téléchargez**

    ---

    Disponible pour macOS, Windows et Linux. Installation en un clic, sans dépendances.

    [:octicons-arrow-right-24: Télécharger Fabric](getting-started/installation.md)

-   :material-key:{ .lg .middle } **2. Connectez votre IA**

    ---

    Ajoutez une clé API d'Anthropic, OpenAI, Google ou d'autres. Des paliers gratuits sont disponibles chez Google, Mistral et OpenRouter.

    [:octicons-arrow-right-24: Guide de configuration](getting-started/configuration.md)

-   :material-rocket-launch:{ .lg .middle } **3. Ouvrez un projet**

    ---

    Pointez Fabric vers votre base de code et commencez à poser des questions. Il apprend votre code au fur et à mesure.

    [:octicons-arrow-right-24: Démarrage rapide](getting-started/quickstart.md)

</div>

!!! tip "Gratuit pour commencer"
    Vous ne voulez pas encore payer pour l'accès à une API ? Utilisez des fournisseurs à palier gratuit comme Google, Mistral ou OpenRouter.

## Que construirez-vous aujourd'hui ?

=== "Corriger ce bug"

    ```
    I'm getting "Cannot read property 'id' of undefined"
    in UserProfile.tsx. Find the bug and fix it.
    ```

=== "Ajouter une fonctionnalité"

    ```
    Add a dark mode toggle to the settings page.
    Store the preference in localStorage and apply
    it app-wide.
    ```

=== "Comprendre du code hérité"

    ```
    Explain how the payment processing flow works.
    I need to add a new payment method and don't
    know where to start.
    ```

=== "Réviser avant de livrer"

    ```
    Review this PR for security issues, edge cases
    I might have missed, and potential performance
    problems.
    ```

## Rejoignez la communauté

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **En savoir plus**

    ---

    Plongez plus en profondeur dans les fonctionnalités de Fabric grâce à nos guides.

    [:octicons-arrow-right-24: Parcourir la documentation](guide/overview.md)

-   :material-github:{ .lg .middle } **Participez**

    ---

    Partagez vos commentaires, demandez des fonctionnalités et aidez à façonner l'avenir de Fabric.

    [:octicons-arrow-right-24: GitHub Discussions](https://github.com/farpointhq/Fabric/discussions)

-   :material-keyboard:{ .lg .middle } **Astuces pour utilisateurs avancés**

    ---

    Maîtrisez les raccourcis clavier pour filer à travers votre flux de travail.

    [:octicons-arrow-right-24: Référence des raccourcis](reference/shortcuts.md)

</div>

---

<div class="footer-cta" markdown>

**Prêt à coder plus vite sans le chaos ?**

[Obtenir Fabric gratuitement](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>
