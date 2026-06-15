# Autorisations

Fabric fonctionne selon une **échelle de confiance** (trust-ladder) : un système d'autorisations à cinq niveaux qui contrôle précisément ce que l'agent IA est autorisé à faire sans vous demander au préalable. Chaque appel d'outil (modifications de fichiers, commandes shell, actions du navigateur, outils MCP) passe par ce système avant que quoi que ce soit ne se produise sur votre machine.

---

## Les cinq modes d'autorisation

Vous définissez le mode d'autorisation par session de chat à l'aide du sélecteur situé dans la barre d'outils du chat. Le mode est enregistré avec la session, de sorte qu'il est conservé après les redémarrages.

| Mode | Libellé | Signification |
| :---: | :--- | :--- |
| **0** | **Chat** | Lecture seule. Aucune écriture, aucune commande shell. Conversation pure. |
| **1** | **Confirm all** | Fabric demande avant *chaque* action — lectures, écritures, commandes bash, tout. Supervision maximale. |
| **2** | **Confirm writes** | Les lectures et le listage de fichiers se font en silence. Fabric demande avant d'écrire des fichiers et d'exécuter des commandes shell. |
| **3** | **Automatic writes** | Les modifications de fichiers se font sans demander. Fabric demande toujours avant d'exécuter des commandes shell et des mutations du navigateur. |
| **4** | **Fabric take the wheel** | Entièrement autonome. Tous les appels d'outils sont approuvés automatiquement. Aucune invite (sauf `AskUserQuestion`, qui demande toujours). |

> [!TIP]
> **« Fabric take the wheel »** est le mode par défaut pour les nouvelles sessions. Si vous travaillez sur une infrastructure sensible ou si vous souhaitez examiner chaque étape, passez à **Confirm writes** ou **Confirm all** avant d'envoyer votre premier message.

---

## Ce qui déclenche une invite d'autorisation

Même lorsque le mode autorise une catégorie, certaines circonstances spécifiques peuvent tout de même provoquer une invite. Le tableau ci-dessous associe les catégories d'outils au moment où elles demandent confirmation :

| Catégorie d'outil | Chat | Confirm all | Confirm writes | Auto writes | Take the wheel |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Lire un fichier / lister un répertoire | auto | **ask** | auto | auto | auto |
| Modifier un fichier (projet) | deny | **ask** | **ask** | auto | auto |
| Modifier un fichier (externe) | deny | **ask** | **ask** | **ask** | auto |
| Commande Bash / shell | deny | **ask** | **ask** | **ask** | auto |
| Capture d'écran | deny | **ask** | **ask** | **ask** | auto |
| Accès aux répertoires | **ask** | **ask** | **ask** | **ask** | auto |
| Outil MCP | deny | **ask** | **ask** | **ask** | auto |
| Mutation du navigateur | deny | **ask** | **ask** | **ask** | auto |
| Poser une question à l'utilisateur | **ask** | **ask** | **ask** | **ask** | **ask** |

> [!NOTE]
> `AskUserQuestion` demande **toujours** confirmation à l'utilisateur, quel que soit le mode — il s'agit d'une interaction délibérée, et non d'un effet secondaire.

---

## Ce qu'affiche la boîte de dialogue d'autorisation

Lorsque Fabric a besoin d'une approbation, une boîte de dialogue apparaît dans le chat avec le contexte complet avant qu'aucune action ne soit entreprise. Le contenu exact dépend du type d'outil :

### Modification de fichier
- Le chemin du fichier en cours de modification
- Une comparaison avant/après (diff) du changement proposé
- Si le fichier se trouve en dehors de la racine du projet (signalé comme « externe »)
- Options : **Approve**, **Deny** ou **Edit** (modifier le contenu avant de l'accepter)

### Commande shell (Bash)
- La chaîne de commande exacte que Fabric souhaite exécuter
- Options : **Allow once**, **Allow for session** (conserve ce préfixe de commande pour le reste de la session) ou **Deny**

### Accès aux répertoires
- Le chemin du répertoire et si l'opération est une lecture ou une écriture
- Si le chemin se trouve en dehors de la racine du projet
- Options : **Allow** ou **Deny**

### Outil MCP
- Le nom du serveur et le nom de l'outil
- Les arguments transmis
- Options : **Allow once**, **Always allow this tool** (conserve dans les métadonnées du chat) ou **Deny**

### Script de navigateur
- Le domaine ciblé par le script
- Un aperçu du contenu du script
- Options : **Allow** ou **Deny**

---

## Autorisations persistantes (« Always Allow »)

Certaines boîtes de dialogue proposent une option **Always allow**. Lorsqu'elle est sélectionnée, cette autorisation est enregistrée dans les métadonnées du chat et ne sera plus demandée pour le reste de cette session :

- **Bash** : enregistrée comme préfixe à portée de commande (par exemple, autoriser `npm run` approuve automatiquement toutes les commandes `npm run *`)
- **Outils MCP** : enregistrée par nom d'outil sur ce serveur
- **Modification de fichiers** : suivie comme un indicateur booléen (`fileEditingAllowed`) sur l'enregistrement du chat

Les autorisations persistantes sont **par session** — elles sont réinitialisées lorsque vous ouvrez un nouvel onglet de chat.

---

## Plancher de sécurité strict

Quel que soit le mode d'autorisation, certaines opérations sont **toujours bloquées** et ne peuvent pas être approuvées :

- `rm -rf /`, `rm -rf ~`, `rm -rf .` et leurs variantes
- L'écriture sur des périphériques bruts (`/dev/sda`, `/dev/nvme*`)
- Les commandes de destruction du système de fichiers (`mkfs`, `dd of=/dev/...`, `fdisk`, `parted`, `wipefs`)
- Les bombes à fourche (`:(){ :|:& };:`)
- L'écriture ou la suppression de fichiers dans des chemins système protégés (`/etc`, `/usr`, `/bin`, `/lib`, `/System`, etc.)

Ces règles sont appliquées par un garde-fou de sécurité qui s'exécute à l'étape de préparation de l'outil — avant même qu'une invite d'autorisation ne soit affichée. Elles ne peuvent être contournées par aucun mode d'autorisation.

> [!CAUTION]
> Même en mode **« Fabric take the wheel »**, le plancher de sécurité est toujours actif. Le mode contrôle ce sur quoi Fabric *demande* confirmation — le plancher de sécurité contrôle ce que Fabric *ne peut jamais faire*.

---

## Autorisations des sous-agents

Lorsque Fabric génère un sous-agent (via des tâches DAG ou `DelegateTask`), les demandes d'autorisation du sous-agent sont **transmises au chat parent** pour approbation. La boîte de dialogue d'autorisation indiquera :

- Quel sous-agent effectue la demande (par son nom)
- Le même contexte d'outil qu'une demande normale

Le mode d'autorisation de la session parente détermine si la demande du sous-agent est approuvée automatiquement, soumise à une invite ou refusée. Les sous-agents ne peuvent pas élever leurs propres autorisations au-delà de ce que la session parente autorise.

---

## Modifier le mode en cours de session

Vous pouvez modifier le mode d'autorisation à tout moment pendant une session à l'aide du sélecteur de mode dans la barre d'outils. Le changement prend effet immédiatement pour tous les appels d'outils suivants — y compris ceux qui sont actuellement en attente dans une file. Le nouveau mode est enregistré dans les métadonnées de la session et sera restauré si l'application redémarre.
