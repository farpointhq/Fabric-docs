# Pièces jointes de documents

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../../assets/videos/document-attachments.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>
</div>

Vous n'avez pas à copier le texte d'un document pour interroger l'IA à son sujet. Fabric vous permet de joindre des **PDF, des documents Word, des feuilles de calcul Excel et des fichiers PowerPoint** directement au chat — Fabric lit leur contenu et le met à la disposition de l'IA comme contexte.

---

## Types de fichiers pris en charge

Vous pouvez joindre les formats de documents courants :

| Type | Extensions |
|------|------------|
| **PDF** | `.pdf` |
| **Word** | `.docx`, `.doc` |
| **Excel** | `.xlsx`, `.xls` |
| **PowerPoint** | `.pptx`, `.ppt` |

En plus de ceux-ci, vous pouvez joindre des fichiers texte et de code, et — avec un modèle capable de vision — des images. Cette page se concentre sur les formats de documents ci-dessus.

---

## Comment joindre un document

Cliquez sur l'**icône en trombone** dans la barre de saisie du chat pour ouvrir un sélecteur de fichiers, puis choisissez un ou plusieurs fichiers. Ils apparaissent sous forme de puces au-dessus du champ de texte. Tapez votre question autour d'eux et envoyez comme d'habitude.

---

## Ce que Fabric en fait

Lorsque vous joignez un document, Fabric ne se contente pas de remettre le fichier brut à l'IA — il **en extrait le contenu** sous une forme que l'IA peut réellement lire et analyser :

- **PDF** — le texte est extrait pour que l'IA puisse lire l'intégralité du document. (Les modèles prenant en charge le PDF nativement peuvent aussi voir les pages directement.)
- **Feuilles de calcul Excel** — chaque feuille est convertie en un tableau propre que l'IA peut lire, avec vos en-têtes et vos lignes intacts.
- **Documents Word** — le texte est extrait, ainsi que les images intégrées.
- **Fichiers PowerPoint** — le texte de chaque diapositive est extrait, ainsi que les images du diaporama.

Cela signifie que vous pouvez poser de vraies questions sur le contenu du document — le résumer, en extraire des chiffres précis, comparer des sections, ou le transformer en autre chose — sans rien copier-coller.

---

## Ce que vous pouvez en faire

- **Résumer un long PDF** — joignez un rapport, un contrat ou un article et demandez les points clés.
- **Travailler avec des données de tableur** — joignez un fichier Excel et demandez à l'IA d'analyser les chiffres, d'expliquer une tendance ou de rédiger une formule.
- **Extraire des détails d'un document** — « Quelle est la clause de résiliation de ce contrat ? » ou « Liste chaque action à mener dans ces notes de réunion. »
- **Reformater ou transformer** — transformez le contenu d'un diaporama en résumé écrit, ou une feuille de calcul en rapport.

---

## Remarques et limites

- **Taille de fichier** — documents jusqu'à **25 Mo** chacun.
- **Documents longs** — les très grands documents sont tronqués pour tenir dans le contexte de l'IA, et Fabric vous avertit lorsque cela se produit.
- **PDF numérisés** — Fabric lit la couche de texte d'un PDF. Les PDF numérisés ou contenant uniquement des images (sans texte sélectionnable) ne peuvent pas être lus, car il n'y a pas d'OCR intégré.
- **PDF protégés par mot de passe** — ils sont refusés ; retirez la protection et joignez-le à nouveau.
- **Confidentialité** — le contenu extrait est envoyé au modèle d'IA que vous avez sélectionné dans le cadre de votre conversation, comme le reste de votre message.
