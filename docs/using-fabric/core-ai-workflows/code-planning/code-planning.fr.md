# Planification du code avec Fabric

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../../assets/videos/code-planning.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>
</div>

## Qu'est-ce que la Planification du code avec Fabric ?

Avant même d'écrire une seule ligne de code, Fabric peut produire un plan d'ingénierie complet pour votre fonctionnalité ou votre modification — en analysant votre base de code réelle, en comprenant ses motifs, et en livrant un plan structuré qui couvre tout, de l'architecture à la stratégie de test.

La Planification du code n'est pas un générateur de plan générique. Fabric lit les fichiers pertinents pour votre demande, analyse la façon dont votre base de code est actuellement structurée (stores, services, motifs d'interface, flux de données), et produit un plan **spécifique à votre projet**. Le résultat est un document détaillé que vous pouvez transmettre directement à `/implement` ou déléguer à des sous-agents parallèles.

### Ce que contient le plan

Un plan typique couvre :

| Section | Ce qu'elle contient |
| :--- | :--- |
| **Vue d'ensemble et objectifs** | Une reformulation précise de la fonctionnalité et de ses critères d'acceptation |
| **Résumé de l'étude de la base de code** | Ce que Fabric a découvert en lisant vos fichiers — motifs existants, stores pertinents, conflits potentiels |
| **Architecture proposée** | Où réside le nouveau code, de quoi il dépend, et pourquoi |
| **Modifications au niveau des fichiers** | Une liste ordonnée des fichiers à créer ou à modifier, avec une description de chaque modification |
| **Séquence d'implémentation** | Un ordonnancement étape par étape qui respecte les dépendances et évite les régressions |
| **Stratégie de test** | Recommandations de tests unitaires, d'intégration et E2E liées aux chemins de code spécifiques |
| **Risques et mesures d'atténuation** | Pièges connus, cas limites, et comment les gérer |
| **Vérification des principes SOLID** | Analyse de la manière dont la conception proposée respecte ou met à l'épreuve les principes SOLID |

---

## Comment fonctionne le processus de planification

### Étape 1 — Décrivez ce que vous voulez construire

Ouvrez un onglet de conversation et décrivez votre fonctionnalité en langage clair. Vous n'avez pas besoin d'utiliser une commande spéciale ou une syntaxe de barre oblique — écrivez simplement de manière naturelle. Fabric utilise votre message, ainsi que tous les fichiers ouverts dans votre espace de travail, pour rassembler tout le contexte dont il a besoin.

Plus vous êtes précis sur les **objectifs et les contraintes**, plus le plan est pointu. Par exemple :

> *« Crée un plan d'implémentation détaillé pour ajouter une fonctionnalité de gestion des préférences utilisateur. Il doit couvrir les paramètres de notification, les préférences de thème et les raccourcis clavier configurables. »*

![Saisissez votre demande de planification dans le champ de saisie de la conversation](../../../assets/screenshots/code-planning/1.png)

### Étape 2 — Fabric étudie votre base de code et planifie

Après votre envoi, Fabric ne génère pas immédiatement un plan générique. Au lieu de cela, il effectue une **étude active** avant d'écrire le moindre mot du plan :

* Il lit les fichiers pertinents — par exemple, les écrans de paramètres existants, les schémas de stores, les gestionnaires IPC et les composants d'interface associés.
* Il exécute des recherches ciblées (`grep`, lectures de fichiers) pour comprendre l'état actuel de l'implémentation.
* Il raisonne sur ce qui existe déjà par rapport à ce qui doit être construit.
* Une fois qu'il a une vision claire, il résume ses conclusions d'étude dans la conversation, puis produit le plan complet et structuré.

Vous pouvez suivre ce processus en direct dans la conversation — chaque appel d'outil (lecture de fichier, grep, etc.) est affiché en ligne, vous offrant une transparence totale sur ce que Fabric examine.

![Fabric lit activement les fichiers de la base de code avant de produire le plan](../../../assets/screenshots/code-planning/2.png)

---

## Construire le plan

Une fois le plan prêt, vous n'avez pas à le copier où que ce soit ni à lancer une commande à la main. Chaque plan généré est accompagné d'un bouton **Build** (Construire). Cliquez dessus, et Fabric reprend le plan et commence à l'implémenter directement — en préparant le travail et en transformant chaque changement prévu en code réel.

C'est le chemin en un clic du plan vers le code fonctionnel :

1. **Examinez** le plan dans le chat — développez les sections, demandez des modifications, ajustez la portée.
2. Quand il vous convient, cliquez sur **Build**.
3. Fabric implémente le plan, en traitant les changements au niveau des fichiers dans l'ordre établi par le plan, pour que vous puissiez voir la conception devenir du code.

Comme Build part du plan que Fabric a déjà étudié, l'implémentation suit l'architecture, la séquence et la stratégie de test que vous avez examinées — et non une nouvelle supposition.

---

## Une fois le plan généré

Outre le clic sur **Build**, une fois le plan dans le chat, vous avez plusieurs options :

* **L'affiner de manière conversationnelle** — Posez des questions de suivi pour développer une section, demander des approches alternatives, ou ajuster la portée. Fabric mettra à jour le plan sur place.
* **Le transmettre à `/implement`** — Enregistrez le plan dans un fichier markdown et transmettez son URL à la commande de barre oblique `/implement` pour l'exécuter dans un arbre de travail Git isolé.
* **Le déléguer à des sous-agents** — Utilisez le plan comme une décomposition de tâches et lancez des sous-agents parallèles (via `/implement_with_dag`) pour travailler simultanément sur différentes sections.
* **L'utiliser comme point de contrôle de revue** — Partagez le plan avec votre équipe avant d'écrire la moindre ligne de code, afin de détecter tôt les problèmes d'architecture.

> [!TIP]
> Ouvrez dans des onglets d'éditeur les fichiers les plus pertinents pour votre fonctionnalité avant de soumettre votre demande de planification. Fabric utilise le contexte de l'espace de travail — plus les fichiers pertinents sont visibles, plus le plan est précis.

> [!NOTE]
> La Planification du code fonctionne mieux avec des modèles dotés de solides capacités de raisonnement. **Fabric XLarge** est recommandé pour les demandes de planification complexes et multi-fichiers.
