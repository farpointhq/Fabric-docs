# Graphe orienté acyclique (DAG)

🚧 Le tutoriel vidéo est en cours de préparation.

Lorsque vous donnez à Fabric une grande demande en plusieurs parties, il n'a pas à tout traiter en une seule ligne droite. Avec l'**orchestration DAG** activée, Fabric décompose le travail en un graphe de tâches plus petites, détermine lesquelles dépendent des autres, et exécute les indépendantes **en parallèle** — terminant un travail complexe plus rapidement tout en le gardant organisé.

DAG signifie *Directed Acyclic Graph* (graphe orienté acyclique) — un nom savant pour une idée simple : un ensemble de tâches reliées par « ceci doit se produire avant cela », sans boucles.

---

## L'activer

L'orchestration DAG est **expérimentale** et **désactivée par défaut**. Vous l'activez dans **Paramètres → Général**, sous **DAG Orchestration (Experimental)**, avec l'interrupteur intitulé **Enable DAG Orchestration** (activer l'orchestration DAG).

- **Désactivée** (par défaut) — Fabric traite une tâche de manière normale et séquentielle : une étape après l'autre.
- **Activée** — Pour les demandes en plusieurs parties, Fabric décompose le travail en un graphe de tâches et l'exécute avec des agents de découverte et d'implémentation dédiés, en exécutant les tâches indépendantes en même temps.

Comme la fonctionnalité se stabilise encore, vous pouvez la laisser désactivée pour le travail courant et l'activer lorsque vous avez une grande tâche parallélisable qui en bénéficierait.

---

## Ce qu'elle fait

Avec l'interrupteur activé, une demande complexe déclenche une autre façon de travailler :

- **Décomposition** — Fabric analyse la demande et la divise en tâches distinctes, chacune avec un objectif clair.
- **Dépendances** — Il enregistre quelles tâches dépendent d'autres. Une tâche qui a besoin du résultat d'une autre est marquée comme *bloquée* jusqu'à ce que ce prérequis soit terminé.
- **Exécution parallèle** — Les tâches qui ne dépendent pas les unes des autres s'exécutent **en même temps**, jusqu'à un certain nombre de créneaux simultanés, au lieu d'attendre dans une file.
- **Agents spécialisés** — Les agents de découverte explorent le code et établissent ce qui doit changer ; les agents d'implémentation réalisent les changements.

Vous pouvez suivre tout cela dans **Mission Control**, le tableau de bord de Fabric qui visualise le graphe de tâches et montre, en temps réel, quelles tâches sont prêtes, bloquées, en cours ou terminées.

---

## Le déroulement

À un niveau élevé, une tâche DAG passe par ces étapes :

1. **Planifier** — Fabric crée un plan et enregistre l'ensemble des tâches, ainsi que leurs dépendances.
2. **Ordonnancer** — Les tâches dont tous les prérequis sont satisfaits deviennent *prêtes* ; les autres restent *bloquées*. Les tâches prêtes sont placées pour s'exécuter.
3. **Exécuter en parallèle** — Les tâches prêtes et indépendantes s'exécutent simultanément. Les agents de découverte enquêtent ; les agents d'implémentation effectuent les changements.
4. **Débloquer** — À mesure que chaque tâche se termine, toute tâche qui l'attendait est revérifiée. Si ses dépendances sont désormais satisfaites, elle devient prête et démarre dès qu'un créneau se libère.
5. **Terminer** — Le graphe se vide tâche par tâche jusqu'à ce que tout soit terminé.

Le résultat est le même objectif final que celui que vous avez demandé, atteint plus efficacement — les parties qui *peuvent* se faire ensemble *se font* ensemble, et celles qui doivent attendre leur tour sont séquencées automatiquement.

---

## Quand l'utiliser

L'orchestration DAG est surtout utile pour les **grandes demandes à plusieurs composants** — un travail qui se divise naturellement en plusieurs morceaux qui ne dépendent pas tous les uns des autres (par exemple, toucher plusieurs modules indépendants, ou générer des tests pour plusieurs fichiers à la fois). Pour les petites tâches en une seule étape, le mode séquentiel normal est plus simple et le graphe n'apporte rien.
