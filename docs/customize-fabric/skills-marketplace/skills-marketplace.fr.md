# Place de marché des compétences d'agent

🚧 Le tutoriel vidéo est en cours de préparation.

## Qu'est-ce que la place de marché des compétences d'agent dans Fabric ?

La place de marché des compétences d'agent est un registre centralisé et un centre de découverte intégré directement dans Fabric pour trouver, installer et gérer des ensembles d'instructions réutilisables appelés **compétences**.

Les compétences agissent comme des profils de comportement spécialisés ou des modules complémentaires qui personnalisent les capacités de votre assistant IA pour des domaines, des langages ou des tâches spécifiques. Conceptuellement, une compétence est représentée sous la forme d'un fichier markdown structuré (`SKILL.md`) contenant des directives d'invite système, des déclarations de capacités et des restrictions d'outils. La place de marché récupère les compétences publiées depuis le registre global `skills.sh`, permettant aux développeurs de parcourir le catalogue, d'afficher des aperçus, de les installer dans des portées globales (utilisateur) ou locales (projet), et de les maintenir à jour de façon transparente sans duplication manuelle des invites.


## Quand utiliser la place de marché des compétences d'agent

Intégrez des compétences de la place de marché dans votre flux de travail lorsque vous avez besoin de :

* **Spécialiser le comportement de l'agent** : Éliminer la saisie répétitive de contexte en dotant votre agent de compétences dédiées pour des rôles complexes (comme un rédacteur de tests unitaires vitest, un refactoriseur de code ou un auditeur de base de données).
* **Standardiser les flux de travail** : Garantir que les agents locaux de tous les membres de l'équipe génèrent du code conforme aux mêmes directives stylistiques, règles de linting et structures de pull request en installant des compétences à portée de projet.
* **Tirer parti d'invites optimisées** : Déployer des invites système et des ensembles d'instructions validés par la communauté et hautement optimisés pour des frameworks, outils ou API spécifiques, sans avoir à les rédiger et à les peaufiner vous-même.


## Comment utiliser la place de marché des compétences d'agent

### Étape 1 : Ouvrir les paramètres de l'application

Cliquez sur l'icône d'engrenage des paramètres en bas de la barre latérale gauche pour ouvrir la fenêtre des paramètres.

![Ouvrir les paramètres de l'application](../../assets/screenshots/skills-marketplace/1.png)

### Étape 2 : Accéder aux paramètres des compétences

Cliquez sur l'onglet « Skills » dans la barre latérale de navigation des paramètres pour afficher les compétences d'agent actuellement installées et les options de configuration.

![Accéder aux paramètres des compétences](../../assets/screenshots/skills-marketplace/2.png)

### Étape 3 : Lancer la place de marché des compétences

Cliquez sur le bouton « Browse Marketplace » dans la barre d'actions de l'en-tête supérieur pour ouvrir la superposition de la place de marché skills.sh.

![Lancer la place de marché des compétences](../../assets/screenshots/skills-marketplace/3.png)

### Étape 4 : Rechercher dans le catalogue de la place de marché

Saisissez une requête de recherche (par exemple, « git ») dans le champ de recherche en haut de la superposition de la place de marché pour filtrer les compétences par mots-clés.

![Rechercher dans le catalogue de la place de marché](../../assets/screenshots/skills-marketplace/4.png)

### Étape 5 : Sélectionner une compétence à prévisualiser

Cliquez sur la ligne d'une compétence dans les résultats de recherche de la colonne de gauche pour afficher son aperçu README, sa description, sa version et ses détails dans le volet d'aperçu à droite.

![Sélectionner une compétence à prévisualiser](../../assets/screenshots/skills-marketplace/5.png)

### Étape 6 : Installer la compétence

Cliquez sur le bouton « Install » en haut du volet d'aperçu de la compétence pour télécharger et enregistrer la compétence dans votre environnement.

![Installer la compétence](../../assets/screenshots/skills-marketplace/6.png)
