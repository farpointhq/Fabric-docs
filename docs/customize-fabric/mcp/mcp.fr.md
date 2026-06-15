# Le Model Context Protocol (MCP) dans Fabric

🚧 Le tutoriel vidéo est en cours de préparation.

## Qu'est-ce que le Model Context Protocol (MCP) dans Fabric ?

L'intégration du **Model Context Protocol (MCP)** dans Fabric offre un moyen standardisé d'étendre les capacités de votre assistant IA grâce à des outils et services externes. Le MCP est un protocole ouvert qui permet une communication sécurisée et bidirectionnelle entre Fabric et des serveurs MCP externes, autorisant l'IA à accéder à des données en temps réel, à exécuter des outils spécialisés et à interagir avec des services tiers.

Via l'interface des paramètres MCP, vous pouvez configurer les connexions aux serveurs, gérer l'authentification, surveiller l'état des serveurs et contrôler quels outils sont disponibles pour l'assistant IA. Chaque serveur MCP peut exposer plusieurs outils qui apparaissent aux côtés des capacités natives de Fabric pendant les sessions d'utilisation d'outils.

Les serveurs MCP s'exécutent dans des processus de travail isolés dotés de leur propre modèle d'autorisations, garantissant que l'accès aux outils externes est explicite, auditable et sous votre contrôle.


## Quand utiliser le Model Context Protocol (MCP) dans Fabric

Utilisez le MCP dans Fabric lorsque vous souhaitez :

* **Vous connecter à des services externes** — Intégrer des sources de données en temps réel comme des bases de données, des API ou des services cloud que l'IA peut interroger pendant les conversations.
* **Étendre les capacités des outils** — Ajouter des outils spécialisés pour des tâches propres à un domaine (par exemple, intégration Jira, notifications Slack, flux de travail CI/CD personnalisés).
* **Activer des flux de travail multi-serveurs** — Configurer plusieurs serveurs MCP simultanément pour composer des pipelines d'automatisation complexes.
* **Maintenir des frontières de sécurité** — Utiliser le système d'autorisations du MCP pour approuver ou refuser explicitement l'accès aux outils serveur par serveur.


## Comment utiliser le Model Context Protocol (MCP) dans Fabric

### Étape 1 : Ouvrir les paramètres de l'application

Cliquez sur l'icône d'engrenage des paramètres en bas de la barre latérale gauche pour ouvrir la fenêtre des paramètres.

![Ouvrir les paramètres de l'application](../../assets/screenshots/mcp/1.png)

### Étape 2 : Accéder aux paramètres MCP

Cliquez sur l'onglet **MCP** dans la barre latérale de navigation des paramètres pour accéder au panneau de configuration du Model Context Protocol.

![Accéder aux paramètres MCP](../../assets/screenshots/mcp/2.png)

### Étape 3 : Aperçu du panneau des paramètres MCP

Le panneau des paramètres MCP affiche tous les serveurs configurés dans la section **MCP Servers** en haut. Utilisez les onglets de filtre par portée — **All**, **Project**, **Local** et **User** — pour afficher les serveurs selon l'emplacement où leur configuration est stockée.

![Aperçu du panneau des paramètres MCP](../../assets/screenshots/mcp/3.png)

### Étape 4 : Comprendre les fiches de serveur

Chaque fiche de serveur affiche son nom, sa version, le nombre d'outils et l'état de connexion en direct. Un badge vert **READY** signifie que le serveur est connecté et que ses outils sont disponibles. Utilisez les boutons **Disconnect**, **Edit** et **Remove** sur chaque fiche pour gérer le serveur.

![Comprendre les fiches de serveur](../../assets/screenshots/mcp/4.png)

### Étape 5 : Les boutons d'activation des fonctionnalités MCP

La section **MCP Features** contrôle la façon dont le MCP s'intègre à l'interface de chat. **Resource @ Mentions** vous permet de joindre des ressources MCP à l'aide de `@` dans le champ de saisie du chat. **Prompts as Slash Commands** expose les invites du serveur sous forme de commandes slash `/server/prompt`. **Enable MCP Tools** est l'interrupteur principal — lorsqu'il est désactivé, aucun outil MCP ne peut être invoqué, quels que soient les paramètres par serveur.

![Les boutons d'activation des fonctionnalités MCP](../../assets/screenshots/mcp/5.png)

### Étape 6 : Ajouter un nouveau serveur MCP

Cliquez sur **Add Server** pour ouvrir la boîte de dialogue de configuration permettant d'enregistrer une nouvelle connexion à un serveur MCP.

![Ajouter un nouveau serveur MCP](../../assets/screenshots/mcp/6.png)

### Étape 7 : Saisir un nom de serveur

Donnez à votre serveur un nom descriptif (par exemple, `github-mcp`, `postgres-tools`). Ce nom apparaît sur la fiche du serveur et dans les invites d'autorisation pendant les sessions de chat.

![Saisir un nom de serveur](../../assets/screenshots/mcp/7.png)

### Étape 8 : Choisir le type de serveur et la commande

Sélectionnez le **Transport Type** du serveur : utilisez **stdio** pour les processus locaux lancés par une commande (par exemple, `npx @modelcontextprotocol/server-github`), ou **http/sse** pour les points de terminaison HTTP distants. Pour les serveurs stdio, saisissez l'exécutable et ses arguments. Pour http/sse, saisissez l'URL du point de terminaison.

![Choisir le type de serveur et la commande](../../assets/screenshots/mcp/8.png)

### Étape 9 : Définir la portée de configuration

Choisissez la **Configuration Scope** pour contrôler l'emplacement où la configuration est enregistrée : **Project (shared via .mcp.json)** la valide dans votre dépôt afin que toute l'équipe la partage, **Local** stocke une substitution propre à la machine, et **User** l'enregistre dans votre profil Fabric global.

![Définir la portée de configuration](../../assets/screenshots/mcp/9.png)

### Étape 10 : Enregistrer ou annuler

Cliquez sur **Add Server** pour l'enregistrer et vous connecter immédiatement, ou sur **Cancel** pour annuler. Une fois enregistré, Fabric lance le processus du serveur et la nouvelle fiche apparaît dans la liste avec son état en direct.

![Enregistrer ou annuler](../../assets/screenshots/mcp/10.png)

### Étape 11 : Autorisations des outils

La section **Tool Permissions** offre un contrôle granulaire sur les outils MCP que l'IA est autorisée à appeler. Les règles d'autorisation sont créées automatiquement lorsque vous cliquez sur **Always Allow** sur une invite d'outil pendant une session de chat, et peuvent être examinées ou supprimées ici à tout moment.

![Autorisations des outils](../../assets/screenshots/mcp/11.png)

### Étape 12 : Fermer les paramètres

Cliquez sur le bouton **×** ou appuyez sur **Escape** pour fermer la fenêtre des paramètres. Tous les serveurs MCP connectés sont désormais actifs — leurs outils sont disponibles pour l'IA dans chaque session de chat.

![Fermer les paramètres](../../assets/screenshots/mcp/12.png)
