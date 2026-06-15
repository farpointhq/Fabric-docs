# Flux de travail multi-agents : sous-agents

<video controls playsinline width="100%">
  <source src="../../../../../assets/videos/sub-agents.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Qu'est-ce que les flux de travail multi-agents (sous-agents) dans Fabric ?

Les sous-agents permettent à une session de chat parente de déléguer des pistes de travail parallèles et indépendantes à des agents LLM d'arrière-plan spécialisés. Cela rend possible la réalisation de décompositions de tâches complexes — par exemple, faire examiner la qualité du code par un agent, vérifier les problèmes de sécurité par un autre, et rechercher des bogues par un troisième — puis de compiler leurs conclusions dans un seul fil de conversation.


## Quand utiliser les flux de travail multi-agents (sous-agents)

Utilisez les sous-agents dans Fabric lorsque vous souhaitez :

* **Effectuer des tâches en parallèle** : déléguez des processus concurrents (par exemple, audits de sécurité, profilage des performances, génération de tests) à des agents indépendants.
* **Tirer parti d'une expertise spécialisée** : exécutez simultanément plusieurs invites d'arrière-plan adaptées à des domaines spécifiques.
* **Examiner des bases de code complexes** : laissez les sous-agents analyser différents aspects de votre espace de travail et agréger un rapport unifié et clair.


## Comment utiliser les flux de travail multi-agents (sous-agents)

### Étape 1 : ouvrir l'explorateur de fichiers

Ouvrez le panneau de l'explorateur de fichiers dans la barre de navigation de gauche pour accéder aux fichiers du projet.

![Ouvrir l'explorateur de fichiers](../../../assets/screenshots/sub-agents/1.png)

### Étape 2 : ouvrir un fichier du projet

Ouvrez un fichier (par exemple, `template.yaml`) pour afficher son contenu dans un onglet d'éditeur distinct.

![Ouvrir un fichier du projet](../../../assets/screenshots/sub-agents/2.png)

### Étape 3 : revenir à l'onglet Chat

Laissez l'onglet du fichier ouvert pour référence, puis cliquez sur l'onglet « Chat » dans la barre d'onglets pour revenir à votre session de conversation principale.

![Revenir à l'onglet Chat](../../../assets/screenshots/sub-agents/3.png)

### Étape 4 : ouvrir le sélecteur de modèle

Cliquez sur le sélecteur de modèle principal dans la barre d'outils du chat.

![Ouvrir le sélecteur de modèle](../../../assets/screenshots/sub-agents/4.png)

### Étape 5 : sélectionner le modèle Fabric XLarge

Sélectionnez un modèle (comme « Fabric XLarge ») qui prend en charge l'utilisation d'outils pour l'orchestration des sous-agents.

![Sélectionner le modèle Fabric XLarge](../../../assets/screenshots/sub-agents/5.png)

### Étape 6 : envoyer une invite aux sous-agents dans le chat

Saisissez une invite demandant à Fabric de lancer trois sous-agents : un pour la revue de code, un pour le débogage et un pour la vérification de sécurité, afin d'examiner le projet.

![Envoyer une invite aux sous-agents dans le chat](../../../assets/screenshots/sub-agents/6.png)

### Étape 7 : soumettre et lancer la délégation

Appuyez sur Entrée ou cliquez sur le bouton Envoyer pour lancer la requête. Fabric interprétera la commande de délégation, lancera les sous-agents d'arrière-plan spécialisés et affichera leur progression.

![Soumettre et lancer la délégation](../../../assets/screenshots/sub-agents/7.png)

### Étape 8 : attendre et lire les résultats consolidés

Attendez que les sous-agents terminent leur exécution en arrière-plan. Une fois terminé, l'agent parent consolide les trois rapports et présente un résumé unifié dans le chat.

![Attendre et lire les résultats consolidés](../../../assets/screenshots/sub-agents/8.png)
