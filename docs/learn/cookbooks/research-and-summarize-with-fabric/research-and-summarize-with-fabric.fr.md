# Rechercher et résumer avec Fabric

**Durée :** 5 minutes pour la mise en place  
**Difficulté :** Débutant  
**Ce que vous allez construire :** Un flux de travail pour lire, rechercher et résumer tout type de document ou de contenu web — sans quitter Fabric.

---

## Aperçu

Le navigateur intégré, les pièces jointes et le contexte de conversation persistant de Fabric en font un environnement de recherche performant. Cette recette couvre trois flux de travail de recherche courants : résumer des documents téléversés, faire des recherches avec le navigateur intégré, et construire un résumé évolutif à partir de plusieurs sources.

---

## Flux de travail 1 : Résumer un document

Le moyen le plus rapide de tirer parti d'un long document est de le joindre et de poser une question directe.

**Formats pris en charge :** PDF, fichiers texte brut, Markdown, fichiers de code et la plupart des formats de documents.

### Étape 1 : Joignez le document

Cliquez sur l'**icône de trombone** dans la barre de saisie de la discussion et sélectionnez votre fichier. Il apparaît sous forme de puce au-dessus du champ de texte.

### Étape 2 : Posez une question ciblée

Au lieu de « résume ça », demandez ce dont vous avez réellement besoin :

```
Quels sont les arguments clés de cet article, et quelles preuves utilise-t-il pour les étayer ?
```

```
Ceci est un contrat — quelles sont les clauses de résiliation et quel préavis est requis ?
```

```
Extrais tous les points d'action et leurs responsables de ce compte rendu de réunion.
```

Des questions précises obtiennent des réponses précises. « Résume ça » vous donne un résumé générique.

### Étape 3 : Relancez

Les résumés sont des points de départ. Relancez pour approfondir :

```
Tu as mentionné que la méthodologie avait des limites — lesquelles ?
```

```
Y a-t-il quelque chose dans le contrat qui serait inhabituel ou qui mériterait d'être signalé à un avocat ?
```

Fabric conserve l'intégralité du document dans le contexte tout au long de la conversation, vous pouvez donc poser autant de questions de suivi que nécessaire.

---

## Flux de travail 2 : Rechercher avec le navigateur intégré

Utilisez le navigateur intégré pour lire du contenu web sans changer d'application, et amenez-le directement dans la conversation.

### Étape 1 : Ouvrez le navigateur

Cliquez sur l'**icône du navigateur** dans la barre latérale gauche, ou passez à un onglet de navigateur depuis la barre d'onglets.

### Étape 2 : Accédez à votre source

Tapez une URL ou une requête de recherche dans la barre d'adresse. Le navigateur de Fabric fonctionne comme un navigateur classique — accédez à des pages de documentation, des articles, des publications ou n'importe quelle page web publique.

### Étape 3 : Demandez à Fabric de lire la page

Passez à l'onglet de discussion et demandez :

```
Lis la page que j'ai ouverte et résume les points clés.
```

En mode agentique, Fabric peut parcourir des pages en votre nom :

```
Trouve la page de tarification de ce produit et dis-moi ce qui est inclus dans l'offre gratuite.
```

```
Consulte le journal des modifications de cette bibliothèque et dis-moi ce qui a changé dans les trois dernières versions.
```

### Étape 4 : Comparez plusieurs sources

Naviguez entre les pages et construisez une vision comparative :

```
Je t'ai maintenant montré trois approches différentes de ce problème.
Quels sont les compromis entre elles ?
```

---

## Flux de travail 3 : Construire un résumé évolutif à partir de plusieurs sources

Lorsque vous menez une recherche plus approfondie sur plusieurs documents ou pages, utilisez un seul onglet comme session de recherche et construisez le contexte de manière incrémentale.

### Étape 1 : Démarrez un onglet de recherche dédié

Ouvrez un nouvel onglet (cliquez sur **+** dans la barre d'onglets) et désignez-le mentalement comme votre onglet de recherche. Gardez-le séparé de vos onglets de travail.

### Étape 2 : Joignez ou parcourez les sources une par une

Ajoutez chaque source à la conversation l'une après l'autre. Après chacune, demandez à Fabric de l'intégrer :

```
Voici le deuxième article. Comment sa méthodologie se compare-t-elle à celle du premier ?
```

```
Voici le troisième article. Soutient-il ou contredit-il quelque chose que nous avons abordé jusqu'ici ?
```

### Étape 3 : Demandez une synthèse

Une fois vos sources parcourues, demandez une synthèse de l'ensemble :

```
À partir de tout ce que nous avons lu, quel est le consensus actuel sur ce sujet,
et où subsiste-t-il encore des désaccords ?
```

```
Je dois rédiger une note d'une page sur ce sujet.
Rédige-la en t'appuyant sur les sources que nous avons examinées.
```

### Étape 4 : Compactez quand la conversation devient longue

Les conversations de recherche peuvent devenir longues. Quand l'indicateur de contexte montre que la conversation se remplit, cliquez sur **Compact** pour résumer les échanges plus anciens tout en gardant les conclusions clés dans le contexte.

---

## Astuces

**Collez du texte directement pour les questions rapides.** Pour de courts passages — un paragraphe, quelques points — inutile de joindre un fichier. Collez simplement le texte dans le message et posez votre question dans la foulée.

**Demandez un format de sortie précis.** « Donne-moi une liste à puces des principales affirmations » ou « Rédige ceci sous forme de résumé exécutif d'un paragraphe » vous donne quelque chose d'immédiatement exploitable.

**Utilisez-le pour du contenu non anglophone.** Joignez un document dans n'importe quelle langue et demandez à Fabric de le résumer en anglais (ou inversement).

**Enregistrez le résultat.** Demandez à Fabric d'écrire son résumé dans un fichier : *« Enregistre ce résumé sous `research-notes/paper-1-summary.md`. »* En mode agentique, il créera le fichier dans le dossier de votre projet.
