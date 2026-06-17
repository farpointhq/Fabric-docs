# Générer des documents (Word, PowerPoint, PDF)

**Durée :** 15 à 30 minutes  
**Difficulté :** Débutant  
**Ce que vous allez construire :** Un flux qui transforme une source de contenu unique en fichiers `.docx`, `.pptx` et `.pdf` soignés en une seule passe — un rapport, un jeu de diapositives et un PDF prêt à imprimer, le tout à partir du même matériau.

---

## Vue d'ensemble

Fabric ne génère pas de documents Office d'emblée — il n'y a pas de bouton intégré « exporter vers Word ». Ce qu'il *possède*, c'est un système de compétences. En installant des compétences de génération de documents depuis la [Place de marché des compétences](../../../customize-fabric/skills-marketplace/skills-marketplace.md), vous donnez à Fabric la capacité de créer de vrais fichiers `.docx`, `.pptx` et `.pdf`, et vous pouvez alors lui demander de produire les trois formats à partir d'une seule conversation.

Cette recette montre comment mettre cela en place et exécuter une génération multi-format dans un seul flux.

---

## Étape 1 : Installer les compétences de document

Ouvrez **Paramètres → Compétences**, cliquez sur **Browse Marketplace** et recherchez des compétences de génération de documents. Cherchez des compétences couvrant :

- **docx** — documents Microsoft Word
- **pptx** — présentations PowerPoint
- **pdf** — création de PDF (et remplissage de formulaires / fusion)

Installez celles dont vous avez besoin. Une fois installées, Fabric peut les invoquer automatiquement quand une tâche requiert ce format — vous n'avez pas à les appeler par leur nom.

!!! tip "Installez les trois"
    Si vous voulez une véritable sortie multi-format en une seule passe, installez les trois compétences dès le départ. L'IA ne peut produire qu'un format pour lequel elle a une compétence ; disposer de docx, pptx et pdf est donc ce qui rend possible le flux à prompt unique ci-dessous.

---

## Étape 2 : Préparer votre contenu source

Décidez de *quoi* parlent les documents et donnez à Fabric la matière première. Cela peut être :

- Un document ou des notes que vous joignez (trombone ou glisser-déposer)
- Du contenu déjà présent dans votre projet (un fichier markdown, un jeu de données)
- Ou simplement une description dans le prompt

Par exemple, joignez un `quarterly-summary.md` avec vos résultats du T2, ou collez directement les points clés.

Meilleur est votre contenu source, meilleures sont les trois sorties — elles ne valent que ce à partir de quoi elles sont générées.

---

## Étape 3 : Demander les trois formats en une seule passe

Les compétences installées et votre contenu prêt, faites une seule demande décrivant les trois livrables :

```
À partir du quarterly-summary.md joint, produis trois documents dans ./output :

1. Un rapport Word (quarterly-report.docx) — texte complet, des titres pour
   chaque section, et un tableau récapitulatif des indicateurs clés.
2. Un jeu de diapositives PowerPoint (quarterly-deck.pptx) — une diapositive de
   titre plus une par section, des puces concises, et le tableau des indicateurs
   sur sa propre diapositive.
3. Un PDF (quarterly-onepager.pdf) — un résumé exécutif d'une seule page avec
   les trois enseignements les plus importants.

Garde un message cohérent sur les trois.
```

Fabric traitera chaque livrable, en invoquant la compétence correspondant à chaque format. Comme tout se passe dans une seule conversation, les trois documents restent cohérents entre eux — les mêmes chiffres, le même cadrage, adaptés aux forces de chaque format (texte pour Word, puces pour les diapositives, brièveté pour la page unique).

---

## Étape 4 : Examiner le résultat

En mode agentique, Fabric écrit les fichiers dans votre projet. Ouvrez-les pour vérifier :

- Le `.docx` s'ouvre proprement dans Word avec des titres corrects et un vrai tableau
- Le `.pptx` s'ouvre dans PowerPoint avec les diapositives attendues
- Le `.pdf` s'affiche comme une page unique soignée

Si quelque chose ne va pas, dites-le simplement :

```
Le jeu de diapositives a trop de texte par diapositive. Réduis chaque diapositive
à 3 puces maximum et déplace les détails dans les notes de l'intervenant.
```

Fabric régénère le fichier concerné sans que vous ayez à recommencer.

---

## Étape 5 : Itérer sur un format sans toucher aux autres

Comme chaque document est un fichier distinct, vous pouvez les affiner indépendamment :

```
Laisse le rapport Word et le PDF tels quels. Pour le PowerPoint, ajoute une
diapositive de clôture avec les prochaines étapes et trois actions à mener.
```

---

## Variantes

**Format unique** — Vous n'êtes pas obligé de générer les trois. Installez seulement la compétence dont vous avez besoin et demandez uniquement ce format.

**À partir d'un modèle** — Joignez un `.docx` ou un `.pptx` existant et demandez à Fabric de suivre sa structure et son style pour le nouveau document.

**Piloté par les données** — Connectez une [base de données](../../../using-fabric/app/databases/databases.md) ou joignez une feuille de calcul et demandez à Fabric d'intégrer les chiffres directement dans le rapport, le jeu de diapositives et le PDF.

**Remplir un PDF existant** — La compétence PDF peut aussi remplir des formulaires et fusionner des fichiers, pas seulement créer de nouveaux PDF — utile pour peupler un modèle avec du contenu généré.

---

## Astuces

**Installez avant de demander.** L'IA ne peut pas produire un format pour lequel elle n'a aucune compétence. Si une demande de `.pptx` revient en texte brut, la compétence pptx n'est probablement pas encore installée.

**Soyez explicite sur les noms de fichiers et l'emplacement.** Dites à Fabric exactement comment nommer chaque fichier et où le placer, pour que la sortie atterrisse là où vous l'attendez.

**Décrivez la forme de chaque format.** Word veut du texte et des titres ; les diapositives veulent de courtes puces ; une page unique veut une brièveté impitoyable. Détailler la structure de chacun donne de bien meilleurs résultats que « fais un jeu de diapositives et un document ».

**Gardez une source de vérité unique.** Générer tous les formats à partir du même contenu source dans une seule conversation est ce qui les maintient cohérents. Si vous les générez dans des sessions séparées, ils peuvent diverger.
