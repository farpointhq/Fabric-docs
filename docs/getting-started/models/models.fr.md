# Modèles

Fabric fonctionne avec deux types de modèles : **les modèles hébergés par Fabric** (aucune clé API requise) et **les fournisseurs externes** que vous connectez avec votre propre clé API. Vous pouvez les combiner — utilisez les modèles Fabric pour le travail quotidien et faites appel à Anthropic ou OpenAI lorsque vous avez besoin d'une capacité spécifique.

---

## Changer de modèle

![Le panneau de paramètres Modèles](../../assets/screenshots/settings/2_models.png)

Ouvrez **Paramètres → Modèles** pour gérer votre configuration de modèles. Depuis cet écran, vous pouvez :

- Définir le **modèle assistant** — le modèle léger que Fabric utilise pour les tâches en arrière-plan comme l'édition de fichiers et la suggestion de noms d'onglets
- Définir le **modèle de sous-agent** — le modèle utilisé lorsque Fabric génère un sous-agent (par défaut, identique à votre modèle assistant)
- Ajouter des clés API pour les fournisseurs externes
- Voir et activer/désactiver les modèles disponibles pour chaque fournisseur

Vous pouvez aussi changer le modèle actif pour chaque conversation directement depuis le **sélecteur de modèle** dans la barre de saisie du chat, sans ouvrir les paramètres.

---

## Modèles Fabric

Les modèles propres à Fabric s'exécutent sur l'infrastructure de Fabric et sont disponibles dès que vous vous connectez — aucune clé API requise.

| Modèle | Idéal pour |
|-------|----------|
| **XLarge** | Problèmes difficiles, raisonnement complexe, décisions d'architecture |
| **Large** | Développement de fonctionnalités, revue de code, tâches à large contexte |
| **Medium** | Codage quotidien, refactorisation, explications |
| **Small** | Modifications rapides, nommage d'onglets, tâches assistantes en arrière-plan |

Tous les modèles Fabric prennent en charge la vision (entrée d'images), l'utilisation d'outils et des fenêtres de contexte longues jusqu'à 262K jetons.

---

## Fournisseurs d'API externes

Connectez votre propre clé API pour accéder aux modèles de n'importe quel fournisseur pris en charge. Accédez à **Paramètres → Modèles**, trouvez le fournisseur, collez votre clé, et les modèles deviennent disponibles dans le sélecteur.

### Anthropic

Les modèles Claude d'Anthropic excellent dans le raisonnement, le suivi d'instructions complexes et les tâches sur de longs documents.

- **Clé API** : Obtenez-en une sur [console.anthropic.com](https://console.anthropic.com)
- **Prend en charge** : Vision, entrée PDF, utilisation d'outils, réflexion étendue

Niveaux disponibles : Opus (le plus performant), Sonnet (équilibré), Haiku (rapide et léger)

### OpenAI

Les modèles GPT d'OpenAI sont largement utilisés et bien pris en charge dans tout l'écosystème.

- **Clé API** : Obtenez-en une sur [platform.openai.com](https://platform.openai.com)
- **Prend en charge** : Vision, entrée PDF, utilisation d'outils, recherche web, modes de raisonnement

Les niveaux disponibles vont des modèles de raisonnement très performants aux options rapides et économiques.

### Google

Les modèles Gemini de Google excellent dans le contexte long, l'entrée multimodale et les tâches qui bénéficient de l'exécution de code.

- **Clé API** : Obtenez-en une sur [aistudio.google.com](https://aistudio.google.com)
- **Prend en charge** : Vision, PDF, utilisation d'outils, recherche web, exécution de code, raisonnement

Niveaux disponibles : Pro (le plus performant) et Flash (rapide, économique).

### OpenRouter

OpenRouter vous donne accès à un large éventail de modèles tiers via une seule clé API — utile si vous voulez essayer des modèles de xAI, DeepSeek, Qwen et d'autres sans gérer plusieurs comptes.

- **Clé API** : Obtenez-en une sur [openrouter.ai](https://openrouter.ai)
- **Prend en charge** : Utilisation d'outils, streaming

### DeepSeek

DeepSeek propose de puissants modèles de codage et de raisonnement à faible coût.

- **Clé API** : Obtenez-en une sur [platform.deepseek.com](https://platform.deepseek.com)
- **Prend en charge** : Utilisation d'outils, raisonnement (activé/désactivé), streaming

### Cerebras

Cerebras exécute l'inférence sur du matériel personnalisé, offrant des vitesses de génération de jetons très élevées.

- **Clé API** : Obtenez-en une sur [cloud.cerebras.ai](https://cloud.cerebras.ai)
- **Prend en charge** : Utilisation d'outils, streaming

### Modèles locaux

Fabric peut se connecter à un serveur de modèles exécuté localement (Ollama, LM Studio, vLLM, LocalAI et autres points de terminaison compatibles OpenAI). Aucune clé API requise — Fabric détecte automatiquement ce qui s'exécute sur votre machine.

- **Configuration** : Démarrez votre serveur local et sélectionnez **Local** dans Paramètres → Modèles
- Fabric sonde automatiquement les ports courants et liste les modèles disponibles

---

## Choisir le bon modèle

Quelques règles générales :

- **Pour les tâches complexes** (architecture, débogage de problèmes difficiles, écriture de migrations) — utilisez un modèle de niveau Large ou XLarge. Plus lent et plus coûteux, mais moins d'erreurs.
- **Pour les tâches quotidiennes** (modifications rapides, réponses aux questions, reformatage) — un modèle Medium ou Small est plus rapide et moins cher sans perte de qualité.
- **Pour le travail en arrière-plan** (le modèle assistant et de sous-agent) — Fabric utilise automatiquement par défaut un modèle économique. Vous pouvez le modifier dans Paramètres → Modèles si vous souhaitez plus de puissance pour les étapes automatisées.
- **Options gratuites** — Google (Gemini Flash), Mistral et OpenRouter ont tous des niveaux gratuits ou des modèles gratuits. Parfait pour démarrer sans rien dépenser.

!!! tip "Changer en cours de conversation"
    Vous pouvez changer de modèle en pleine conversation depuis le menu déroulant de la barre de chat. Le nouveau modèle reprend à partir du contexte actuel — pas besoin de tout recommencer.
