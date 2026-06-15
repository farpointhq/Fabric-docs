# Compactage de la conversation

Au cours d'une longue conversation, l'historique de votre conversation s'étoffe — et le nombre de jetons (tokens) augmente avec lui. Chaque message, lecture de fichier et résultat d'outil reste dans la fenêtre de contexte du modèle. Vous finissez par approcher de la limite, et le modèle commence à perdre le fil des parties antérieures de la discussion.

Le **Compactage** résout cela en comprimant l'historique de votre conversation en un résumé concis. Fabric lit l'intégralité de la conversation, en extrait les décisions et les résultats clés, et remplace l'ensemble des échanges par une version raccourcie qui préserve l'essentiel.

---

## Comment ça fonctionne

Lorsque vous cliquez sur le bouton **Compacter** dans la barre d'outils de la conversation, Fabric :

1. Lit chaque message de la conversation en cours
2. Identifie les décisions, modifications de code et conclusions importantes
3. Génère un résumé compact qui capture le contexte essentiel
4. Remplace l'historique verbeux de la conversation par ce résumé

Le résultat est une empreinte en jetons beaucoup plus réduite, libérant de l'espace pour de nouveaux messages tout en gardant le modèle informé de ce que vous avez déjà accompli.

---

## Le bouton Compacter

![Bouton Compacter](../../../assets/screenshots/compaction/compact-button.png)

Le bouton **Compacter** se trouve dans la barre d'outils du compositeur de la conversation, entre les commandes du mode agentique et le sélecteur de modèle. Cliquez dessus à tout moment pendant une conversation pour déclencher le compactage.

---

## Quand utiliser le Compactage

* **Conversations de longue durée** — Lorsque vous travaillez sur la même tâche depuis des dizaines de messages et que la fenêtre de contexte se remplit
* **Avant un changement de cap majeur** — Lorsque vous êtes sur le point de poser une question entièrement nouvelle et que vous voulez préserver les résultats importants des échanges précédents sans en traîner toute la discussion
* **Après une session de revue ou de débogage** — Lorsque les échanges ont produit un résultat clair (un bogue corrigé, un fichier remanié) et que le raisonnement détaillé n'est plus nécessaire
* **Lorsque l'indicateur passe au jaune ou au rouge** — L'indicateur de fenêtre de contexte de Fabric vous avertit à mesure que vous approchez de la limite ; le compactage est le moyen le plus rapide de récupérer de l'espace sans perdre de contexte

Le compactage est non destructif dans le sens où la conversation complète reste visible dans l'historique de la conversation — mais le *modèle*, lui, ne voit désormais que la version compactée. Cela vous offre le meilleur des deux mondes : une transcription lisible pour vous-même, et un contexte efficace pour l'IA.
