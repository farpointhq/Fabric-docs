# Mise en file d'attente des messages

Vous n'avez pas à attendre que l'IA ait terminé avant de préparer votre prochaine instruction. Pendant qu'une réponse se génère, tout ce que vous tapez peut être mis en file d'attente et envoyé automatiquement à la fin du tour en cours — vous gardez ainsi le fil de votre pensée au lieu de rester inactif.

---

## Mettre un message en file d'attente

![Un message mis en file d'attente pendant que l'IA génère encore](../../../assets/screenshots/message-queuing/1.png)

Pendant que l'IA génère, tapez votre prochain message et appuyez sur `Entrée`. Au lieu d'interrompre la réponse en cours, le message est ajouté à une **file d'attente** et apparaît sous forme de puce dans un petit popover juste au-dessus de la zone de saisie. La saisie se vide, prête pour le suivant.

Vous pouvez ainsi mettre plusieurs messages en file d'attente (jusqu'à 20 par session). Ils sont conservés dans l'ordre et envoyés l'un après l'autre dès que l'IA est libre.

---

## Gérer la file d'attente

Le popover de la file affiche chaque message en attente sous forme de puce. À partir de là, vous pouvez :

- **Modifier** un message en file d'attente sur place — cliquez sur l'icône d'édition, changez le texte et enregistrez.
- **Supprimer** un message — cliquez sur le × de sa puce pour le retirer de la file.
- **Forcer l'envoi** d'un seul message maintenant — cliquez sur son icône d'envoi pour interrompre la génération en cours et envoyer seulement celui-ci immédiatement.
- **Tout envoyer** — vider toute la file d'un coup.
- **Sélection multiple** — quand plus d'un message est en file, des cases à cocher permettent d'agir sur plusieurs à la fois (envoyer ou supprimer l'ensemble sélectionné).

Un raccourci rapide : pendant la génération, appuyer sur la **flèche du haut** avec le curseur au début d'une saisie vide ramène votre message le plus récemment mis en file dans la zone de saisie pour le modifier.

---

## Comment les messages en file sont envoyés

Lorsque la réponse en cours se termine, la file se vide automatiquement. Plusieurs messages texte en file sont combinés en un seul tour de suivi (séparés pour que l'IA puisse les distinguer), et toutes les images ou tous les fichiers joints les accompagnent.

Vous pouvez aussi vider la file manuellement : avec la saisie vide pendant que l'IA génère encore, appuyer sur `Entrée` envoie immédiatement toute la file.

Si vous forcez l'envoi d'un message en pleine génération, Fabric arrête d'abord le tour en cours, puis envoie votre message — utile quand vous réalisez qu'il faut corriger le cap tout de suite.

---

## Quand l'utiliser

- **Regroupez une séquence d'étapes.** Mettez en file « maintenant écris les tests », « puis mets à jour le README », « puis lance le linter » pendant que la première tâche s'exécute.
- **Capturez une idée avant de l'oublier.** Si quelque chose vous vient en pleine réponse, mettez-le en file au lieu d'attendre et d'oublier.
- **Corrigez le cap immédiatement.** Vous voyez l'IA partir dans la mauvaise direction ? Forcez l'envoi d'une correction plutôt que de la laisser terminer.

---

## Remarques

- La file contient jusqu'à 20 messages par session de chat. Tenter d'en mettre davantage affiche un bref avertissement « queue full » (file pleine).
- Chaque onglet a sa propre file indépendante — mettre en file dans une conversation n'affecte pas une autre.
- Les messages en file conservent leurs pièces jointes (images et fichiers), pas seulement le texte.
