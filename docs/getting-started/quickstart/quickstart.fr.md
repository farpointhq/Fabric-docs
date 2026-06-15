# Démarrage rapide

## Installation

**Télécharger → Installer → Commencer à coder. C'est tout.**

## Obtenir Fabric

<div class="grid cards" markdown>

-   :material-apple:{ .lg .middle } **macOS**

    ---

    Fonctionne sur Apple Silicon (M1/M2/M3/M4) et les Mac Intel. macOS 12 ou ultérieur.

    [Télécharger pour Mac](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-microsoft-windows:{ .lg .middle } **Windows**

    ---

    Windows 10 ou ultérieur (64 bits).

    [Télécharger pour Windows](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

-   :material-linux:{ .lg .middle } **Linux**

    ---

    Paquet AppImage ou .deb. Ubuntu 20.04+ ou équivalent.

    [Télécharger pour Linux](https://farpointalpha.com/fabric){ .md-button .md-button--primary }

</div>

!!! success "Gratuit pour commencer"
    Utilisez des fournisseurs à niveau gratuit comme Google, Mistral ou OpenRouter pour démarrer sans payer d'accès à l'API.

## Ce dont vous avez besoin

- **Une connexion Internet** (les modèles d'IA s'exécutent dans le cloud)
- **4 Go de RAM** minimum, 8 Go ou plus pour les grands projets
- Une **clé API** de n'importe quel fournisseur (niveaux gratuits disponibles chez Google, Mistral, OpenRouter)

---

## Étapes d'installation

=== "macOS"

    1. Ouvrez le fichier `.dmg` téléchargé
    2. Faites glisser **Fabric** dans votre dossier **Applications**
    3. Ouvrez Fabric depuis les Applications

    !!! tip "Premier lancement"
        macOS peut afficher un avertissement de sécurité. Faites un clic droit sur l'application → **Ouvrir** → **Ouvrir** à nouveau.

=== "Windows"

    1. Exécutez `Fabric-Setup.exe`
    2. Suivez l'installateur
    3. Lancez depuis le menu Démarrer

    !!! tip "Sécurité Windows"
        Si SmartScreen apparaît, cliquez sur **Informations complémentaires** → **Exécuter quand même**.

=== "Linux"

    **AppImage (le plus simple) :**
    ```bash
    chmod +x Fabric.AppImage
    ./Fabric.AppImage
    ```

    **Debian/Ubuntu :**
    ```bash
    sudo dpkg -i Fabric.deb
    ```

---

## Premier lancement

Ouvrez Fabric et vous verrez immédiatement l'interface de chat. Pas d'assistant de configuration, pas de formulaires de paramétrage.

### Essayez maintenant (aucune clé API requise)

Fabric inclut des jetons gratuits pour démarrer. Ouvrez un dossier de projet et posez une question :

```
What does this codebase do?
```

### Ajoutez vos propres clés API (facultatif)

Vous voulez davantage de contrôle sur les modèles que vous utilisez ? Ajoutez vos propres clés dans les Paramètres :

| Fournisseur | Où obtenir la clé |
|----------|------------------|
| **Anthropic** | [console.anthropic.com](https://console.anthropic.com/) |
| **OpenAI** | [platform.openai.com](https://platform.openai.com/api-keys) |
| **Google** | [aistudio.google.com](https://aistudio.google.com/app/apikey) |

!!! tip "Options à niveau gratuit"
    - **Google** — Niveau gratuit généreux pour les modèles Gemini
    - **Mistral** — Accès API gratuit pour démarrer
    - **OpenRouter** — Modèles gratuits comme DeepSeek R1

---

## Mises à jour

Fabric se met à jour automatiquement. Vous verrez une notification lorsqu'une nouvelle version est disponible.


## Lancez et c'est parti

### Étape 1 : Ouvrez Fabric

Lancez-le comme n'importe quelle autre application. Aucune commande de terminal, aucun fichier de configuration.

### Étape 2 : Pointez-le vers votre code

Cliquez sur **Fichier** → **Ouvrir un projet** et sélectionnez votre dossier de projet. Fabric commence immédiatement à apprendre votre base de code.

!!! success "C'est ici que la magie opère"
    Une fois que Fabric connaît votre projet, il cesse d'être une IA générique et devient *votre* IA :

    - Il sait où se trouve votre code d'authentification
    - Il respecte vos conventions de nommage
    - Il suggère les fichiers dont vous avez probablement besoin
    - Il comprend comment vos composants sont connectés

### Étape 3 : Choisissez votre modèle

Cliquez sur le menu déroulant des modèles et choisissez en fonction de ce que vous faites :

| Vous faites ceci ? | Utilisez ceci |
|-------------|----------|
| Question rapide, correction simple | Modèle rapide (Haiku, GPT Mini) |
| Problème complexe, revue de code | Modèle performant (Sonnet, GPT-4) |
| Pas sûr ? | Commencez par le rapide, changez si nécessaire |

!!! tip "Vous pouvez changer à tout moment"
    Commencez par un modèle rapide. Si la réponse n'est pas assez approfondie, passez à un modèle plus performant. Fabric conserve tout votre contexte.

### Étape 4 : Demandez n'importe quoi

Saisissez une question et appuyez sur Entrée. C'est tout. Pas de syntaxe spéciale, pas de commandes magiques.

---

## Essayez ceci dès maintenant

### « Pourquoi est-ce que ça ne marche pas ? »

Collez du code défectueux et regardez Fabric le résoudre :

```
This keeps crashing and I don't know why:

TypeError: Cannot read properties of undefined (reading 'map')
  at UserList (UserList.tsx:15:23)
```

**Fabric va :** trouver le bogue, expliquer pourquoi il se produit et vous proposer plusieurs façons de le corriger.

### « Construis-moi ça »

Décrivez ce dont vous avez besoin en langage clair :

```
Crée un hook React qui enregistre l'état dans localStorage.
Il doit gérer le JSON automatiquement et fonctionner avec TypeScript.
```

**Fabric va :** écrire du code prêt pour la production qui correspond aux modèles de votre projet.

### « Ce code est-il bon ? »

Obtenez un deuxième avis avant de livrer :

```
Passe ceci en revue pour les problèmes de sécurité et ce que j'aurais pu manquer :

app.post('/api/users', async (req, res) => {
  const { email, password } = req.body;
  const user = await db.users.create({ email, password });
  res.json(user);
});
```

**Fabric va :** repérer l'absence de validation des entrées, le mot de passe non chiffré et le manque de gestion des erreurs.
