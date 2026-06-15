# Commande Fix dans Fabric

🚧 Le tutoriel vidéo est en cours de préparation.

## Qu'est-ce que la Commande Fix dans Fabric ?

La commande `/fix` lance un flux de travail structuré et piloté par les tests pour corriger des issues GitHub dans un arbre de travail git isolé. Elle orchestre un cycle de développement complet — de l'analyse de l'issue et de la planification jusqu'aux tests adversariaux et à la création de la PR — tout en gardant votre espace de travail principal propre. La commande impose les bonnes pratiques, notamment le développement isolé, la planification obligatoire avec des artefacts déployés, le développement piloté par les tests (TDD) et des points de contrôle d'approbation requis.

---

## Quand utiliser la Commande Fix

Utilisez `/fix` dans Fabric lorsque vous souhaitez :

* **Corriger des bogues signalés** : Travailler sur des issues GitHub avec une traçabilité complète, du plan à la PR.
* **Implémenter des fonctionnalités** : Suivre une approche structurée pour le développement de nouvelles fonctionnalités avec planification et tests.
* **Maintenir un espace de travail propre** : Développer dans des arbres de travail isolés sans affecter votre projet principal ni d'autres sessions.
* **Imposer un flux de travail TDD** : Garantir que les tests sont écrits avant l'implémentation, à chaque fois.
* **Générer des plans déployés** : Créer des plans visuels avec des diagrammes hébergés sur GitHub Pages pour une revue aisée.
* **Effectuer des tests adversariaux** : Tenter activement de casser votre propre code avant de soumettre une PR.
* **Créer des PR liées** : Générer automatiquement des pull requests liées aux issues avec un contexte complet.

**Évitez `/fix` pour** : Les corrections rapides d'une seule ligne, le travail exploratoire, ou les modifications qui ne bénéficient pas d'une planification et de tests formels.

---

## Comment utiliser la Commande Fix

### Étape 1 : Invoquer la Commande Fix

Tapez la commande de barre oblique avec le numéro de l'issue GitHub dans votre conversation :

```
/fix 42
```

Fabric récupère les détails de l'issue depuis GitHub et affiche le titre, la description et les étiquettes pour référence.

### Étape 2 : Création de l'arbre de travail

Fabric crée un arbre de travail git isolé sur une nouvelle branche (`fix/issue-42`) à partir de votre branche `dev`. L'arbre de travail est stocké dans `tmp_worktree/issue-42` et automatiquement ajouté au `.gitignore` afin de le maintenir hors du contrôle de version.

Toutes les opérations de fichiers ultérieures se déroulent dans cet environnement isolé.

### Étape 3 : Configuration de l'environnement

Fabric se déplace vers l'arbre de travail, copie `.env` depuis le projet principal (s'il est présent) et installe les dépendances :

```bash
cd tmp_worktree/issue-42
npm install
```

### Étape 4 : Détection du dépôt de plans

Fabric détecte le dépôt de plans frère de votre dépôt (`<repo>-plans`) et l'URL GitHub Pages à partir du dépôt distant `origin`. Si le dépôt de plans n'existe pas, il sera créé lors du déploiement.

### Étape 5 : Création du document de plan

Fabric analyse l'issue et crée un document de plan à l'emplacement `$PLANS_DIR/docs/plans/issue-42-plan.md` contenant :

* Résumé de l'issue
* Analyse de la cause racine (pour les bogues)
* Solution proposée
* Fichiers à modifier
* Stratégie de test
* Risques et considérations

### Étape 6 : Génération des diagrammes

Fabric génère des diagrammes visuels en utilisant HTML+CSS (par défaut) ou Mermaid pour les diagrammes de séquence/de classe :

* Des diagrammes d'architecture système montrant les relations entre les composants
* Des diagrammes de flux de données retraçant la manière dont les données circulent dans le système
* Des diagrammes de flux de processus avec des étapes numérotées et des branches
* Des diagrammes de machine à états pour les composants à état
* Des comparaisons avant/après pour les modifications de l'interface

### Étape 7 : Déployer le plan sur GitHub Pages

Fabric valide le plan dans le dépôt de plans et déclenche le déploiement de GitHub Pages :

```bash
cd $PLANS_DIR
git add -A
git commit -m "docs: Add plan for issue #42"
git push origin main
```

Attendez environ 30 à 60 secondes pour le déploiement, puis le plan est accessible à l'adresse :
`https://<org>.github.io/<repo>-plans/plans/issue-42-plan/`

### Étape 8 : Point de contrôle d'approbation — Revue du plan

**ARRÊT et attente de votre approbation.** Fabric affiche l'URL du plan déployé et demande :

> « J'ai créé un plan pour corriger l'issue #42. Veuillez examiner le plan. Faites-moi savoir :
> 1. **Approuvé** — procéder à l'implémentation
> 2. **Retour** — les modifications que vous souhaitez
> 3. **Annuler** — abandonner cette correction »

Si vous demandez des modifications, Fabric met à jour le plan et le redéploie. Répétez jusqu'à approbation.

### Étape 9 : Écrire les tests d'abord (TDD)

Une fois approuvé, Fabric écrit des tests unitaires qui vérifient le comportement attendu après la correction. Les tests sont placés dans le répertoire `tests/` approprié, en suivant les motifs existants.

### Étape 10 : Exécuter les tests (s'attendre à des échecs)

Fabric exécute la suite de tests. Les nouveaux tests **devraient échouer** à ce stade, confirmant qu'ils testent réellement quelque chose de pertinent.

### Étape 11 : Valider les tests

Les tests sont validés avec un message descriptif :

```bash
git add -A
git commit -m "test(issue-42): add failing tests for issue #42"
```

### Étape 12 : Implémenter la correction

Fabric implémente la correction avec des commits atomiques. Après chaque modification logique :

```bash
git add -A
git commit -m "fix(issue-42): <specific change description>"
```

### Étape 13 : Exécuter les tests après chaque modification

Les tests sont exécutés après chaque commit. S'ils échouent, Fabric analyse l'échec, corrige le code, valide et relance les tests jusqu'à ce que tous les tests réussissent.

### Étape 14 : Vérification complète

Une fois l'implémentation terminée, Fabric exécute la suite de tests complète et la vérification de types :

```bash
npm test
npm run typecheck
```

### Étape 15 : Auto-tests adversariaux

**Cette phase est requise.** Fabric adopte un état d'esprit de « QA hostile » et tente activement de casser le code en testant :

* **Cas limites** : Entrées vides, valeurs nulles, longueurs maximales, caractères spéciaux
* **Manipulation d'état** : Clics rapides, interruptions, transitions invalides
* **Attaques d'intégration** : Formes de données inattendues, pannes réseau, refus de permission
* **Comportement utilisateur** : Actions dans le désordre, saisies rapides répétées

Un rapport de test est créé à l'emplacement `$PLANS_DIR/docs/plans/issue-42-adversarial-testing.md`.

### Étape 16 : Point de contrôle d'approbation — Revue des tests

**ARRÊT et attente de votre approbation.** Fabric affiche le rapport de tests adversariaux et demande :

> « J'ai terminé les auto-tests adversariaux pour l'issue #42. Veuillez examiner le rapport de tests. Faites-moi savoir :
> 1. **Approuvé** — procéder à la création de la PR
> 2. **Davantage de tests nécessaires** — domaines spécifiques à tester
> 3. **Test manuel** — vous voulez le tester vous-même d'abord »

### Étape 17 : Créer la Pull Request

Après approbation, Fabric pousse la branche et crée une PR :

```bash
git push -u origin fix/issue-42
gh pr create --base dev --title "Fix #42: <issue title>" --body "..."
```

Le corps de la PR inclut des liens vers le plan déployé et le rapport de tests adversariaux.

### Étape 18 : Nettoyage

Fabric revient au projet principal, supprime l'arbre de travail et met à jour le statut du plan à « completed » :

```bash
cd <project-root>
git worktree remove tmp_worktree/issue-42
git worktree prune
```

---

## Exemple de session

```
User: /fix 42

Fabric: Fetching issue #42...
        "Login fails when password contains special characters"
        
        Creating worktree: fix/issue-42
        Installing dependencies...
        
        Analyzing issue and creating plan...
        Plan deployed: https://farpointhq.github.io/Fabric-plans/plans/issue-42-plan/
        
        Please review the plan and approve to proceed.
```

Après approbation, Fabric poursuit avec l'implémentation TDD, les tests adversariaux et la création de la PR.
