# Exécuter un flux de travail de revue de code avec Fabric

**Durée :** 10 minutes pour la mise en place, usage continu  
**Difficulté :** Débutant  
**Ce que vous allez construire :** Un flux de travail de revue de code reproductible utilisant la commande `/review` de Fabric et la visionneuse de différences.

---

## Aperçu

La commande `/review` de Fabric exécute une analyse structurée de n'importe quel fichier de votre projet selon six dimensions : exactitude, sécurité, performance, maintenabilité, tests et bonnes pratiques. Elle renvoie un rapport priorisé avec des évaluations de gravité et des suggestions concrètes.

Une fois la revue obtenue, vous pouvez demander à Fabric d'appliquer les corrections et inspecter chaque modification dans la visionneuse de différences interactive avant de valider quoi que ce soit.

Cette recette parcourt le cycle complet : revue → inspection des constats → application des corrections → vérification.

---

## Étape 1 : Ouvrez le fichier que vous voulez examiner

Dans l'explorateur de fichiers, accédez au fichier que vous voulez examiner. Cliquez dessus pour l'ouvrir dans l'éditeur, puis faites un clic droit et choisissez **Add to Chat** pour le joindre comme contexte.

Vous pouvez aussi sauter cette étape — la commande `/review` accepte directement un chemin de fichier en argument.

---

## Étape 2 : Lancez la revue

Dans le champ de saisie de la discussion, tapez :

```
/review src/auth/token.ts
```

Remplacez le chemin par celui de votre fichier. Fabric va lire le fichier, l'analyser et renvoyer un rapport structuré en flux continu.

Le rapport organise les constats par gravité :

- **Critical** — bugs, failles de sécurité, risques de perte de données
- **Major** — erreurs de logique, problèmes de performance, gestion d'erreurs manquante
- **Minor** — problèmes de style, nommage, violations du principe DRY

Chaque constat inclut la ligne ou la fonction exacte, une description du problème et une correction suggérée.

---

## Étape 3 : Lisez le rapport attentivement

Ne demandez pas immédiatement à Fabric de tout corriger. Parcourez les constats et décidez :

- Quels constats sont vraiment de réels problèmes que vous voulez corriger
- Lesquels relèvent de préférences stylistiques avec lesquelles vous n'êtes pas d'accord
- Lesquels nécessiteraient une refactorisation dépassant la portée de cette modification

Pour une revue de PR, concentrez-vous sur les constats Critical et Major. Les problèmes Minor méritent d'être corrigés mais ne devraient pas bloquer une fusion.

---

## Étape 4 : Demandez à Fabric d'appliquer des corrections précises

Au lieu de « corrige tout », soyez sélectif :

```
Applique la correction pour la validation manquante de l'expiration du jeton dans validateToken().
Laisse tout le reste tel quel.
```

Fabric utilisera son outil d'édition pour effectuer la modification ciblée et vous montrera le résultat dans la visionneuse de différences.

---

## Étape 5 : Inspectez la différence

La visionneuse de différences affiche le code d'origine à gauche et la modification proposée à droite. Pour chaque modification :

- Appuyez sur `A` pour **accepter** la modification en surbrillance
- Appuyez sur `D` pour la **rejeter**
- Utilisez `W` / `S` pour défiler entre les modifications
- Utilisez les commandes au niveau du fichier pour accepter ou rejeter toutes les modifications d'un coup

Prenez votre temps ici. Vous êtes la dernière ligne de défense avant que le code ne change.

---

## Étape 6 : Itérez

Après avoir appliqué les corrections, relancez la revue sur le même fichier :

```
/review src/auth/token.ts
```

Un second passage propre signifie que les problèmes sont résolus. Si de nouveaux constats apparaissent, ils ont probablement été introduits par la correction — cela vaut un rapide coup d'œil avant de poursuivre.

---

## Étape 7 : Lancez vos tests

Dans le terminal intégré :

```bash
npx vitest run src/auth/token.test.ts
```

Lancez toujours les tests du fichier que vous avez modifié avant de valider. Si vous n'avez pas de tests pour ce fichier, demandez à Fabric d'en écrire :

```
Écris des tests unitaires pour validateToken() couvrant le cas nominal, les jetons expirés et les entrées malformées.
```

---

## Variantes

**Faire la revue avant une PR, pas après** — Lancez `/review` sur chaque fichier que vous avez modifié avant d'ouvrir une PR, et pas seulement quand vous soupçonnez un problème. Cela attrape des choses faciles à manquer quand on a fixé le code des yeux trop longtemps.

**Examiner le code de quelqu'un d'autre** — Ouvrez le fichier depuis l'explorateur de fichiers et lancez `/review`. Utile pour comprendre un module inconnu ou auditer la PR d'un collègue.

**Cibler la revue** — Vous pouvez demander une revue ciblée plutôt que l'analyse complète :

```
Examine src/payments/stripe.ts uniquement pour les problèmes de sécurité.
```

**L'utiliser pour apprendre** — Si vous découvrez une base de code ou un langage, lancer `/review` sur un fichier que vous avez écrit est un moyen rapide d'obtenir un retour précis et exploitable sur votre code.
