# Différences de code

Lorsque l'IA modifie vos fichiers, rien n'est écrit à l'aveugle. Chaque changement proposé est présenté dans une visionneuse de différences interactive où vous l'examinez, acceptez les parties souhaitées, rejetez celles que vous ne voulez pas, et gardez le contrôle total de ce qui finit réellement sur le disque.

---

## Comment ça fonctionne

![La visionneuse de différences interactive montrant les changements proposés](../../../assets/screenshots/code-diff/1.png)

Lorsque l'IA utilise son outil d'édition, Fabric capture le fichier d'origine aux côtés de la version proposée et présente la différence. Vous voyez le changement en contexte — ce qui est ajouté, ce qui est supprimé — et décidez bloc par bloc de ce qu'il faut garder.

Rien n'est définitif tant que vous n'agissez pas. Vous pouvez accepter des changements individuels, les rejeter, tout accepter d'un coup, ou annuler une décision déjà prise.

---

## Accepter et rejeter les changements

La visionneuse fonctionne au niveau des **blocs** (hunks) — des blocs contigus de changement au sein d'un fichier. Pour chaque bloc, vous disposez de commandes pour :

- **Accepter** le changement (✓) — conserver la modification proposée
- **Rejeter / annuler** le changement (✗) — l'écarter et conserver l'original
- **Ouvrir le fichier** à cet endroit — sauter à l'emplacement exact dans l'éditeur

Vous pouvez aussi accepter ou rejeter **tous** les changements d'un fichier d'un coup depuis les commandes au niveau du fichier, et annuler des décisions si vous changez d'avis — la visionneuse conserve une pile d'annulation, donc rien n'est verrouillé.

---

## Raccourcis clavier

Lorsqu'un bloc de différences a le focus, vous pouvez le parcourir sans toucher la souris :

| Touche | Action |
|--------|--------|
| `A` | Accepter le changement en surbrillance |
| `D` | Écarter / rejeter le changement en surbrillance |
| `W` | Défiler vers le changement précédent |
| `S` | Défiler vers le changement suivant |

Cela rend la revue d'un grand ensemble de modifications rapide : naviguez avec `W` / `S`, décidez avec `A` / `D`.

---

## Examiner les changements sur plusieurs fichiers

![La vue de revue listant chaque fichier modifié avec des commandes d'acceptation et d'annulation par fichier](../../../assets/screenshots/code-diff/2.png)

Lorsque l'IA modifie plusieurs fichiers en une seule tâche, les changements sont regroupés pour que vous puissiez les traiter fichier par fichier. Un panneau latéral liste chaque fichier modifié avec ses propres commandes d'acceptation/rejet, de sorte que vous pouvez approuver un fichier entier d'un coup ou plonger dans des blocs individuels là où vous voulez regarder de plus près.

---

## Pourquoi examiner les différences

- **Repérer les modifications involontaires.** L'IA touche parfois plus que prévu. La différence est l'endroit où vous le remarquez avant l'enregistrement.
- **Conserver des changements partiels.** Ce n'est pas tout ou rien — acceptez les bons blocs et rejetez le reste.
- **Comprendre ce qui a changé.** Lire la différence est le moyen le plus rapide de comprendre exactement ce que l'IA a fait et pourquoi.

---

## Voir aussi

- [Revue de code](../code-review/code-review.md) — demandez une revue structurée d'un fichier, puis appliquez les correctifs suggérés via cette même visionneuse de différences.
- [Exécuter un flux de revue de code](../../../learn/cookbooks/ai-code-review-workflow/ai-code-review-workflow.md) — une recette complète sur le cycle revue-puis-application.
