# Référence de code

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../../assets/videos/code-reference.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>
</div>

Lorsque vous voulez interroger l'IA sur un morceau de code précis, vous n'avez pas à coller le tout dans le chat. Fabric vous permet de **référencer** les lignes exactes d'un fichier — sélectionnez-les, amenez-les dans le chat sous forme d'étiquette compacte, et l'IA sait précisément de quel code vous parlez.

---

## Comment ça fonctionne

Ouvrez un fichier dans l'éditeur et **sélectionnez les lignes** dont vous voulez parler. Ensuite, amenez-les dans le chat de deux façons :

**Copier-coller** — Copiez les lignes sélectionnées (`Ctrl/Cmd C`) et collez-les dans la zone de saisie du chat (`Ctrl/Cmd V`). Au lieu de déverser le code brut dans votre message, Fabric le transforme en une petite **puce de référence** indiquant le nom du fichier et la plage de lignes — par exemple `utils.ts:42-50`.

**Clic droit → Ajouter au chat** — Faites un clic droit sur le code sélectionné dans l'éditeur et choisissez **Add to previous chat** (ajouter au chat précédent). La puce de référence est ajoutée instantanément à votre saisie, sans quitter l'éditeur.

Dans les deux cas, vous obtenez une puce nette dans votre message au lieu d'un mur de code collé. Vous pouvez continuer à taper votre question autour, et ajouter autant de références que vous le souhaitez.

---

## Revenir au code

Une puce de référence est un lien bidirectionnel. **Cliquez dessus** — dans la saisie ou plus tard dans votre historique de chat — et Fabric ouvre ce fichier et défile directement jusqu'aux lignes référencées. Cela facilite la consultation de ce dont vous discutiez exactement, même des semaines plus tard quand vous rouvrez la conversation.

---

## Pourquoi c'est important

Référencer le code au lieu de le coller résout plusieurs problèmes réels :

- **Garde votre contexte propre.** Une référence n'est qu'un nom de fichier et une plage de lignes, elle ne remplit donc pas votre conversation (ni la fenêtre de contexte de l'IA) de gros blocs de code. Cela rend les réponses plus rapides et moins coûteuses — voir [Suivi des coûts](../../core-ai-workflows/cost-tracking/cost-tracking.md).
- **Toujours exact.** L'IA lit les lignes réelles du fichier au moment de répondre, elle voit donc le code réel et actuel — pas une copie périmée que vous auriez collée plus tôt.
- **Facile à naviguer.** Chaque puce est cliquable, votre historique de chat se transforme donc en un ensemble de signets vers la base de code.
- **Précis.** Au lieu de « la fonction vers le haut de ce fichier », l'IA reçoit les lignes exactes que vous avez pointées.

---

## Le copier-coller, en plus malin

Le plus agréable, c'est que le copier-coller fonctionne comme vous l'attendez — mais en plus malin. Quand vous copiez du code depuis l'éditeur de Fabric et le collez dans le chat, il devient automatiquement une puce de référence. Et si vous collez ce même code en dehors de Fabric, il arrive toujours sous forme de code brut, donc rien n'est perdu. Vous obtenez la référence légère à l'intérieur de Fabric et le copier-coller normal partout ailleurs.
