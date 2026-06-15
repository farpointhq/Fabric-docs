# Les compétences d'agent dans Fabric

🚧 Le tutoriel vidéo est en cours de préparation.

## Que sont les compétences d'agent dans Fabric ?

Les **compétences d'agent** (Agent Skills) sont des ensembles d'instructions réutilisables que l'agent IA de Fabric charge à la demande lorsqu'une tâche correspond à leur portée. Chaque compétence est définie par un fichier `SKILL.md` contenant des directives d'invite système, des déclarations de capacités et des restrictions d'outils facultatives — et apparaît dans les paramètres sous forme de fiche activable/désactivable.

Les compétences vous permettent d'enseigner à l'IA le style de codage de votre équipe, les conventions d'un framework spécifique ou tout flux de travail spécialisé, sans avoir à réexpliquer le contexte à chaque conversation. Vous pouvez installer des compétences depuis la place de marché communautaire, indiquer à Fabric une URL ou un dossier local, ou déposer un `SKILL.md` directement dans votre projet.


## Quand utiliser les compétences d'agent dans Fabric

Utilisez les compétences dans Fabric lorsque vous souhaitez :

* **Spécialiser le comportement de l'agent** — Doter l'IA d'une expertise dédiée pour des rôles complexes (rédacteur de tests vitest, auditeur de base de données, refactoriseur de code) sans répéter le contexte à chaque session.
* **Standardiser les flux de travail de l'équipe** — Installer des compétences à portée de projet afin que l'agent de chaque membre de l'équipe génère du code conforme aux mêmes directives stylistiques et à la même structure de PR.
* **Tirer parti des invites de la communauté** — Déployer des ensembles d'instructions optimisés et validés par la communauté pour des frameworks, outils ou API spécifiques, au lieu de les rédiger vous-même.
* **Écrire des compétences personnalisées** — Déposez un `SKILL.md` dans le dossier `.fabric/skills/` de votre projet et Fabric le détecte automatiquement.


## Comment utiliser les compétences d'agent dans Fabric

### Étape 1 : Ouvrir les paramètres de l'application

Cliquez sur l'icône d'engrenage des paramètres en bas de la barre latérale gauche pour ouvrir la fenêtre des paramètres.

![Ouvrir les paramètres de l'application](../../assets/screenshots/skills/1.png)

### Étape 2 : Accéder à l'onglet Compétences

Cliquez sur **Skills** dans la barre latérale des paramètres pour ouvrir le panneau des compétences d'agent, où vous pouvez consulter et gérer toutes les compétences installées.

![Accéder à l'onglet Compétences](../../assets/screenshots/skills/2.png)

### Étape 3 : Aperçu du panneau des compétences

Le panneau des compétences répertorie toutes les compétences installées avec leur nom, leur description, leur version et leur portée. Utilisez **Browse Marketplace** pour découvrir des compétences communautaires, ou **Install from source** pour ajouter une compétence à partir d'une URL ou d'un dossier local.

![Aperçu du panneau des compétences](../../assets/screenshots/skills/3.png)

### Étape 4 : Filtrer les compétences par portée

Utilisez la barre de filtre par portée pour affiner la liste. **All** affiche tout, **Project** affiche les compétences stockées dans votre dépôt (`.fabric/skills/`), et **User** affiche les compétences de votre répertoire personnel disponibles dans tous les projets. Le bouton **Sources** vous permet de contrôler si Fabric lit également les compétences des dossiers `.claude/`, `.cursor/` ou `.agents/`.

![Filtrer les compétences par portée](../../assets/screenshots/skills/4.png)

### Étape 5 : Développer une fiche de compétence

Cliquez n'importe où sur une fiche de compétence pour la développer et voir tous les détails : chemin du fichier, portée, outils autorisés, fichiers groupés et le corps du SKILL.md affiché. Cliquez à nouveau pour la réduire.

![Développer une fiche de compétence](../../assets/screenshots/skills/5.png)

### Étape 6 : Détails de la fiche de compétence

La vue développée indique où se trouve le fichier de la compétence sur le disque, ses métadonnées de compatibilité et un aperçu affiché des instructions du SKILL.md. Utilisez le bouton **Edit** pour ouvrir le fichier directement dans Fabric, ou l'icône de **corbeille** pour le désinstaller. Une notification de confirmation avec une option **Undo** apparaît pendant 6 secondes après la désinstallation.

![Détails de la fiche de compétence](../../assets/screenshots/skills/6.png)

### Étape 7 : Installer une compétence depuis une URL ou un dossier

Cliquez sur **Install from source** pour ouvrir la boîte de dialogue d'installation, où vous pouvez coller une URL GitHub, une URL directe vers un SKILL.md, ou pointer vers un dossier local sur le disque.

![Installer une compétence depuis une URL ou un dossier](../../assets/screenshots/skills/7.png)

### Étape 8 : La boîte de dialogue d'installation

La boîte de dialogue d'installation comporte deux onglets : **Marketplace** pour parcourir le registre skills.sh, et **URL / Folder** pour l'installation directe. Collez n'importe quelle URL publique de `SKILL.md` ou une URL de dépôt GitHub pointant vers une compétence, choisissez la portée (**Project** ou **User**), puis cliquez sur **Install**.

![La boîte de dialogue d'installation](../../assets/screenshots/skills/8.png)

### Étape 9 : Fermer la boîte de dialogue d'installation

Cliquez sur le **×** ou appuyez sur **Escape** pour fermer la boîte de dialogue et revenir au panneau des compétences.

![Fermer la boîte de dialogue d'installation](../../assets/screenshots/skills/9.png)
