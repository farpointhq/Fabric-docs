# Terminal intégré

Fabric est livré avec un terminal complet intégré directement dans l'application. Exécutez des commandes, gérez plusieurs sessions avec des onglets, divisez les volets côte à côte, et envoyez la sortie du terminal directement dans le chat IA — le tout sans jamais quitter la fenêtre.

---

## Ouvrir le terminal

Appuyez sur `Ctrl Maj ` ` (Windows/Linux) ou `⌃ Maj ` ` (Mac) pour ouvrir un nouveau terminal. Le panneau du terminal apparaît en bas de la fenêtre — une session shell complète qui s'exécute aux côtés de votre chat.

![Le terminal intégré](../../../assets/screenshots/built-in-terminal/1.png)

Vous pouvez réduire et développer le panneau à tout moment avec `Ctrl ` ` / `⌃ ` `.

---

## Commandes du terminal

L'en-tête du terminal vous donne un accès rapide aux actions courantes : créer une nouvelle session, diviser le volet actuel, copier la sortie et coller dans la zone de saisie du chat. La barre d'onglets à droite vous permet de basculer entre plusieurs sessions ouvertes.

![Commandes du terminal et barre d'onglets](../../../assets/screenshots/built-in-terminal/2.png)

- **Nouveau terminal** — Ouvre une session supplémentaire. Chaque terminal est indépendant avec son propre historique de défilement.
- **Diviser le volet** — Divise le terminal actuel pour que vous puissiez surveiller deux sessions côte à côte (par exemple, un serveur de développement dans l'une, un exécuteur de tests dans l'autre).
- **Copier** — Copie la sélection ou le contenu du terminal dans votre presse-papiers.
- **Coller dans le prompt** — Envoie la sortie du terminal directement dans la zone de saisie du chat, afin que vous puissiez interroger l'IA sur une erreur ou un résultat de commande sans copier-coller manuellement.

---

## Travailler avec l'IA

Le terminal intégré est étroitement lié au chat de Fabric. C'est ce qui en fait bien plus qu'un simple shell :

- Lorsque Fabric exécute des commandes en **mode agentique**, vous les voyez s'exécuter dans le terminal en temps réel.
- Utilisez **Coller dans le prompt** pour envoyer une trace de pile ou la sortie d'un test en échec directement dans la conversation : *« voici l'erreur — corrige-la. »*
- Exécutez votre serveur de développement ou un processus de surveillance dans un volet divisé pendant que l'IA effectue des modifications, afin de voir l'effet immédiatement.

---

## Raccourcis clavier

| Action | Mac | Windows / Linux |
|--------|-----|-----------------|
| Nouveau terminal | `⌃ Maj \`` | `Ctrl Maj \`` |
| Diviser le terminal | `⌘ \` | `Ctrl Maj 5` |
| Réduire / développer le panneau | `⌃ \`` | `Ctrl \`` |
| Focus volet suivant | `⌥ ⌘ →` | `Alt →` |
| Focus volet précédent | `⌥ ⌘ ←` | `Alt ←` |
| Focus onglets du terminal | `⌘ Maj \` | `Ctrl Maj \` |
| Coller dans le terminal | `⌘ V` | `Ctrl V` |
| Fermer le terminal (onglets actifs) | `⌘ ⌫` | `Suppr` |

---

## Astuces

- **Utilisez les volets divisés pour les processus de longue durée.** Gardez un serveur de développement ou un `tail -f` en cours d'exécution dans un volet pendant que vous travaillez dans l'autre.
- **Chaque onglet conserve son historique.** Le basculement entre les onglets du terminal préserve l'historique de défilement, vous ne perdez donc pas la sortie en passant d'une session à l'autre.
- **Les terminaux fermés restent visibles.** Lorsqu'un processus se termine, l'onglet s'estompe mais reste affiché afin que vous puissiez lire la sortie finale avant de le fermer.
