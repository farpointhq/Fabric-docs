# Suivi de la fenêtre de contexte

Chaque modèle d'IA possède une **Fenêtre de contexte** — la quantité maximale de texte qu'il peut conserver dans sa « mémoire de travail » au cours d'une seule conversation. Pensez-y comme à un tableau blanc : une fois rempli, vous devez effacer quelque chose d'ancien avant de pouvoir écrire quelque chose de nouveau. La fenêtre de contexte comprend tout ce que le modèle voit en même temps — vos invites (prompts), le contenu des fichiers, l'historique de la conversation et les instructions système.

Fabric suit votre consommation de jetons (tokens) en temps réel et l'affiche directement dans le compositeur de la conversation.

---

## Comment ça fonctionne

Au fil de la conversation, chaque message, extrait de code, lecture de fichier et image que vous envoyez consomme des jetons. Fabric comptabilise ces jetons en continu et affiche votre consommation actuelle par rapport à la limite du modèle sélectionné. L'indicateur circulaire à côté du nom du modèle montre à quel point votre fenêtre de contexte est remplie :

![Indicateur de la fenêtre de contexte](../../../assets/screenshots/context-window/context-window-tooltip.png)

Survolez l'indicateur pour voir une ventilation détaillée :

* **Consommation totale** — Le nombre de jetons que vous utilisez actuellement sur la capacité totale du modèle
* **Description du projet** — Jetons provenant du paramètre de description de votre projet
* **Répertoire du projet** — Jetons provenant de l'arborescence des fichiers du projet
* **Tables de base de données** — Jetons provenant de tout contexte de schéma de base de données
* **Contenu des fichiers** — Jetons provenant des fichiers que vous avez ouverts ou joints
* **Invite utilisateur** — Jetons provenant de votre message actuel
* **Images utilisateur** — Jetons provenant des images que vous avez envoyées
* **Invite système** — Jetons provenant des instructions intégrées de Fabric
* **Historique de la conversation** — Jetons provenant de tous les messages précédents de la conversation

---

## Différences de taille des modèles

Les différents modèles ont des tailles de fenêtre de contexte différentes. Par exemple :

* **Fabric XLarge** — 230k jetons
* **Claude 3.5 Sonnet** — 200k jetons
* **GPT-4o** — 128k jetons
* **Modèles plus petits** — Souvent 8k à 32k jetons

Lorsque vous changez de modèle, Fabric recalcule automatiquement votre consommation par rapport à la limite du nouveau modèle. Une conversation qui tient confortablement dans un modèle peut être proche de la limite dans un autre.

---

## Ce qui se passe lorsque vous approchez de la limite

À mesure que votre conversation s'allonge, l'indicateur circulaire se remplit. Lorsque vous approchez de la limite :

* L'indicateur change de couleur pour vous avertir
* Le modèle peut commencer à « oublier » les parties antérieures de la conversation
* La qualité des réponses peut se dégrader, car le modèle peine à tout faire tenir en mémoire

Si vous atteignez la limite, vous avez quelques options : démarrer une nouvelle conversation, supprimer les pièces jointes de fichiers superflues, ou utiliser le **Compactage** pour comprimer l'historique de votre conversation tout en conservant les parties importantes.
