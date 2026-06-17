# Créer un serveur MCP avec Fabric

**Durée :** 30 à 60 minutes  
**Difficulté :** Intermédiaire  
**Ce que vous allez construire :** Un serveur MCP (Model Context Protocol) fonctionnel, échafaudé et implémenté par Fabric en mode agentique, puis reconnecté à Fabric pour que l'IA puisse utiliser ses outils.

---

## Vue d'ensemble

La [page MCP](../../../customize-fabric/mcp/mcp.md) traite de la connexion de Fabric à un serveur MCP qui existe déjà. Cette recette traite de l'autre moitié : **utiliser Fabric pour écrire un tout nouveau serveur MCP de zéro**.

Il n'y a pas de bouton dédié « échafauder un serveur » — et il n'en faut pas. Écrire un serveur MCP est une tâche de codage, et le codage est précisément ce que fait le mode agentique de Fabric. Cette recette décrit un flux fiable pour amener Fabric à en construire un, de bout en bout.

---

## Qu'est-ce qu'un serveur MCP ?

Un serveur MCP est un petit programme qui expose des **outils** (et éventuellement des ressources et des prompts) à un client IA via le Model Context Protocol. Une fois connecté, l'IA peut appeler ces outils — interroger votre API interne, accéder à une base de données, piloter un matériel, tout ce que vous implémentez.

Un serveur minimal comporte trois parties :

- Un **transport** (stdio pour les serveurs locaux, ou HTTP/SSE pour les distants)
- Une ou plusieurs **définitions d'outils** (nom, description, schéma d'entrée)
- Un **gestionnaire** pour chaque outil qui effectue le travail réel et renvoie un résultat

---

## Étape 1 : Décider ce que votre serveur doit faire

Avant d'écrire du code, précisez les outils que vous voulez. Des exigences floues produisent un serveur flou. Ouvrez un chat et décrivez l'objectif :

```
Je veux construire un serveur MCP qui expose l'API d'inventaire interne de mon
entreprise. Il devrait avoir trois outils :
- get_stock(sku) : renvoie le niveau de stock actuel d'un SKU
- list_low_stock(threshold) : liste les SKU sous un seuil de stock
- reserve_item(sku, quantity) : réserve du stock et renvoie un ID de réservation

L'API est à https://internal.acme.com/api, authentifiée avec un jeton bearer
issu de la variable d'environnement ACME_API_TOKEN.
```

Plus la liste d'outils et le contrat d'API sont clairs, meilleur sera le résultat.

---

## Étape 2 : Orienter Fabric vers une implémentation de référence

Les serveurs MCP suivent une forme cohérente. Donner à Fabric un bon exemple connu à copier améliore considérablement le résultat. Deux bonnes options :

- **Les exemples du SDK officiel** — demandez à Fabric d'utiliser les modèles du SDK `@modelcontextprotocol/sdk` (TypeScript) ou du paquet `mcp` (Python).
- **Un serveur existant dans votre stack** — si vous en avez déjà un, joignez-le comme contexte et dites « suis cette même structure ».

```
Utilise le SDK TypeScript @modelcontextprotocol/sdk avec le transport stdio.
Suis la structure de serveur standard : enregistre chaque outil avec un schéma
d'entrée Zod, et renvoie le contenu sous forme de texte. Mets en place un
package.json avec un script de build.
```

---

## Étape 3 : Laisser Fabric échafauder le projet

En **mode agentique**, demandez à Fabric de créer la structure du projet. Il créera des fichiers, installera les dépendances et écrira le code de base :

```
Échafaude le projet : package.json, tsconfig.json et src/index.ts avec le
squelette du serveur et les trois outils ébauchés. Installe le SDK et toutes
les autres dépendances nécessaires.
```

Examinez les différences au fur et à mesure. Vous verrez la structure du projet, la liste des dépendances et le squelette du serveur. Acceptez les changements qui vous conviennent.

---

## Étape 4 : Implémenter les outils

Faites maintenant remplir la logique réelle par Fabric, un outil à la fois. Procéder outil par outil garde chaque changement examinable :

```
Implémente get_stock. Il doit lire ACME_API_TOKEN depuis l'environnement,
appeler GET /api/stock/{sku} et renvoyer le niveau de stock. Gère un 404 en
renvoyant un message clair « SKU introuvable ».
```

Répétez pour chaque outil. Comme vous êtes en mode agentique, Fabric peut aussi lancer le build (`npm run build`) et corriger les erreurs de type qu'il introduit.

---

## Étape 5 : Tester le serveur localement

Demandez à Fabric de vérifier que le serveur démarre et répond :

```
Lance le build, puis démarre le serveur et confirme qu'il s'initialise sans
erreur. Si le SDK dispose d'un inspecteur ou d'un moyen de lister les outils,
utilise-le pour vérifier que les trois outils sont bien enregistrés.
```

L'inspecteur MCP officiel (`npx @modelcontextprotocol/inspector`) est un bon moyen d'exercer les outils manuellement avant de les brancher dans Fabric.

---

## Étape 6 : Le connecter à Fabric

Une fois que le serveur se compile et fonctionne, connectez-le comme n'importe quel autre serveur MCP. Ouvrez **Paramètres → MCP**, cliquez sur **Add Server** et configurez-le :

- **Transport** : stdio
- **Commande** : `node`
- **Arguments** : le chemin vers votre `dist/index.js` compilé
- **Environnement** : définissez `ACME_API_TOKEN`

Voir la [page MCP](../../../customize-fabric/mcp/mcp.md) pour la présentation complète de la boîte de dialogue Add Server. Une fois connecté, vos nouveaux outils apparaissent dans la liste d'outils de Fabric et l'IA peut les appeler.

---

## Étape 7 : Itérer

Utiliser votre serveur dans de vraies conversations fera apparaître des aspérités — un outil qui a besoin de meilleurs messages d'erreur, un paramètre manquant, un format de sortie difficile à lire. Décrivez simplement le problème à Fabric :

```
L'outil list_low_stock renvoie du JSON brut difficile à lire. Fais-lui plutôt
renvoyer un tableau markdown formaté, trié par niveau de stock croissant.
```

Recompilez, reconnectez (ou rechargez le serveur dans les paramètres MCP), et c'est terminé.

---

## Astuces

**Gardez des outils ciblés.** Un outil, une tâche. Une poignée de petits outils bien décrits vaut mieux qu'un outil géant avec une douzaine de modes.

**Rédigez d'excellentes descriptions.** L'IA décide quand appeler un outil d'après sa description et son schéma. Passez-y du temps — c'est la différence entre un outil utilisé correctement et un outil ignoré ou mal employé.

**Validez les entrées.** Utilisez une bibliothèque de schémas (Zod pour TS, Pydantic pour Python) afin qu'une mauvaise entrée soit rejetée avec un message clair plutôt que de faire planter le serveur.

**Ajoutez un AGENTS.md.** Si vous continuez à développer le serveur, déposez un [AGENTS.md](../set-up-agents-md/set-up-agents-md.md) dans son dépôt pour que Fabric se souvienne des conventions et des commandes de build d'une session à l'autre.
