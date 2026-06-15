# Bases de données

Fabric peut se connecter directement à votre base de données, parcourir son schéma et inclure automatiquement les définitions de table pertinentes comme contexte lorsque vous demandez à l'IA d'écrire des requêtes, des migrations ou du code de couche de données.

---

## Bases de données prises en charge

| Base de données | Statut |
|----------|--------|
| PostgreSQL | Prise en charge |
| MySQL | Prise en charge |

---

## Se connecter à une base de données

![Le panneau de l'explorateur de base de données](../../../assets/screenshots/databases/1.png)

Ouvrez le **DB Browser** depuis la barre latérale gauche (l'icône de base de données). Remplissez le formulaire de connexion :

- **Type** — PostgreSQL ou MySQL
- **Host** — Le nom d'hôte ou l'adresse IP de votre base de données
- **Port** — Par défaut `5432` pour Postgres et `3306` pour MySQL
- **Username / Password** — Vos identifiants de base de données
- **Database** — Le nom de la base de données à laquelle se connecter
- **Schema** — Le schéma à utiliser (Postgres uniquement ; par défaut `public`)
- **SSL** — Activez ou désactivez le SSL. Fabric essaie d'abord le SSL et bascule automatiquement vers une connexion simple si le SSL n'est pas disponible

![Fabric avec le panneau de base de données ouvert](../../../assets/screenshots/databases/2.png)

Cliquez sur **Connect**. Fabric vérifiera la connexion et chargera votre schéma. Si la connexion échoue, un message d'erreur décrit ce qui n'a pas fonctionné (identifiants incorrects, hôte injoignable, etc.).

Cliquez sur **Disconnect** à tout moment pour fermer la connexion et vider le schéma mis en cache.

---

## Parcourir votre schéma

Une fois connecté, le DB Browser répertorie toutes les tables de votre base de données. Cliquez sur n'importe quel nom de table pour la développer et voir ses colonnes, types de données, clés primaires, index et contraintes — les mêmes informations que vous obtiendriez avec `\d tablename` dans psql ou `DESCRIBE` dans MySQL.

Fabric récupère cette structure en interrogeant directement le schéma d'information de la base de données, de sorte qu'elle reflète toujours l'état actuel de votre schéma.

---

## Fournir un contexte de base de données à l'IA

C'est là que la fonctionnalité des bases de données devient utile pour le travail quotidien. Vous pouvez sélectionner une ou plusieurs tables à l'aide des cases à cocher situées à côté de chaque nom de table. Lorsque des tables sont sélectionnées, Fabric inclut automatiquement leurs définitions `CREATE TABLE` complètes — colonnes, types, contraintes et index — dans le contexte qu'il envoie à l'IA.

Cela signifie que vous pouvez demander des choses comme :

- *« Écris une requête qui joint `orders` et `customers` et renvoie le chiffre d'affaires par région pour les 30 derniers jours »*
- *« Ajoute une migration qui ajoute une colonne timestamp `deleted_at` à `users` avec un index correspondant »*
- *« Examine cette requête pour la performance — voici le schéma pertinent »*

Sans sélectionner de tables, l'IA n'a aucun moyen de connaître vos noms de colonnes, vos types ou vos relations. Sélectionner les tables qui comptent pour une tâche est le moyen le plus rapide d'obtenir du code précis et conscient du schéma.

Ne sélectionnez que les tables pertinentes pour la tâche en cours. Envoyer un grand schéma avec des dizaines de tables dont vous n'avez pas besoin gaspille l'espace de contexte et peut diluer l'attention de l'IA.

---

## Flux de travail pratiques

**Écrire des requêtes** — Sélectionnez les tables que votre requête va utiliser, puis demandez à l'IA d'écrire ou d'optimiser le SQL. Elle utilisera les noms de colonnes et les contraintes réels de votre schéma.

**Écrire des migrations** — Sélectionnez la table que vous modifiez. Décrivez le changement souhaité (ajouter une colonne, renommer un champ, ajouter une clé étrangère), et l'IA générera le fichier de migration dans le format utilisé par votre projet (SQL brut, Alembic, Flyway, etc.).

**Se familiariser avec un schéma inconnu** — Connectez-vous, développez les tables qui vous intéressent et demandez à l'IA d'expliquer le modèle de données. Elle peut décrire les relations, mettre en évidence les choix de conception inhabituels et suggérer comment interroger les motifs courants.

**Déboguer des problèmes de données** — Joignez une requête qui renvoie des résultats inattendus avec les schémas de table pertinents. L'IA peut repérer les incompatibilités de type, les index manquants ou les erreurs de logique.

---

## Remarques

- Les paramètres de connexion sont enregistrés par projet, vous n'avez donc pas besoin de saisir à nouveau les identifiants à chaque fois que vous ouvrez le projet.
- Les mots de passe ne sont jamais journalisés ni envoyés à l'IA. Seul le DDL du schéma (structure des tables) est inclus dans les prompts — jamais les données réelles de vos tables.
- Fabric n'exécute pas de requêtes en votre nom, sauf si vous lui demandez explicitement d'exécuter une commande en mode agentique via le terminal.
