# Questions de clarification

Parfois, l'IA a besoin d'une décision de votre part avant de pouvoir continuer — quel framework utiliser, faut-il inclure des tests, laquelle de deux approches vous préférez. Au lieu de deviner ou de s'arrêter pour demander en texte libre, Fabric peut présenter une question structurée à choix multiples directement dans la conversation, et vous répondez en cliquant.

---

## Comment ça fonctionne

![Une question de clarification à choix multiples avec des onglets et des options sélectionnables](../../../assets/screenshots/clarifying-questions/1.png)

Lorsque l'IA détermine qu'elle a réellement besoin d'une information qu'elle ne peut pas déduire, elle pose une question structurée. Une boîte de dialogue compacte apparaît en ligne dans le chat, avec :

- Le texte de la **question**
- Un ensemble d'**options sélectionnables**, chacune avec une courte description facultative
- Un choix **« Autre »** avec un champ de texte libre, au cas où aucune des options ne conviendrait

Vous choisissez une option (ou saisissez la vôtre), et votre réponse est renvoyée directement à l'IA, qui poursuit avec votre décision en main.

---

## Sélection unique et multiple

Les questions se présentent en deux modes :

- **Sélection unique** — de type bouton radio ; choisissez une option. Après votre choix, la boîte de dialogue peut avancer automatiquement.
- **Sélection multiple** — de type case à cocher ; sélectionnez autant d'options que pertinent, puis validez.

Un seul prompt peut regrouper plusieurs questions. Dans ce cas, la boîte de dialogue affiche des onglets en haut — un par question — avec un indicateur de progression comme `2 of 3 answered`. Parcourez chaque onglet ; une fois toutes les réponses données, l'ensemble est envoyé d'un coup.

---

## Répondre à une question

- **Cliquez sur une option** pour la sélectionner. Pour les questions à sélection multiple, cliquez sur chaque option souhaitée.
- **Choisissez « Autre »** et saisissez dans le champ si vous devez donner une réponse non listée.
- **Validez** avec le bouton en bas (les questions à sélection unique peuvent avancer/valider automatiquement une fois choisies).
- Vos réponses en brouillon sont conservées si vous passez d'un onglet à l'autre, vous ne perdez donc pas une sélection en naviguant.

---

## Pourquoi c'est mieux qu'une question en texte libre

- **Aucune ambiguïté.** Les options structurées rendent le choix explicite, de sorte que l'IA obtient une réponse nette et sans ambiguïté plutôt que d'analyser du texte libre.
- **Plus rapide.** Cliquer sur un bouton est plus rapide que rédiger une réponse complète.
- **Moins de fausses pistes.** Comme l'IA fait remonter la décision au lieu de la supposer, vous évitez la situation où elle construit avec assurance la mauvaise chose et où vous devez revenir en arrière.

---

## Quand vous la verrez

L'IA est conçue pour ne demander que lorsque c'est vraiment nécessaire — quand une décision change concrètement ce qu'elle fera ensuite et qu'elle ne peut pas raisonnablement choisir une valeur par défaut. Vous verrez généralement des questions de clarification :

- Au début d'une tâche ouverte comportant plusieurs approches valables
- Lorsqu'une demande est ambiguë et que les options mènent à des résultats sensiblement différents
- Avant une étape difficile à annuler, où confirmer la direction vaut un instant

Si vous préférez que l'IA avance simplement avec son meilleur jugement, dites-le-lui — elle s'appuiera sur des valeurs par défaut sensées au lieu de demander.

> Lors des exécutions entièrement autonomes, les questions de clarification sont complètement ignorées — l'IA avance avec son meilleur jugement plutôt que d'attendre une entrée qui ne viendra pas.
