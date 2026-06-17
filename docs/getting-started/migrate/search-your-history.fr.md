# Rechercher dans l'historique de vos conversations

Fabric indexe automatiquement vos conversations IA passées — depuis Fabric lui-même et depuis les autres outils que vous avez utilisés — et les rend consultables depuis n'importe quelle session de chat. Posez une question sur une décision prise le mois dernier, retrouvez un extrait de code d'une session il y a trois semaines, ou rappelez-vous comment vous avez résolu un problème déjà rencontré. La réponse revient sous forme d'un extrait clair avec une date et une source, prêt à l'emploi.

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../assets/videos/migrate.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>
</div>

---

## Ce qui est indexé

Fabric effectue des recherches dans les conversations provenant de :

- **Fabric** — toutes vos sessions de chat passées dans ce projet et dans d'autres
- **Claude** — les conversations depuis Claude desktop et Claude.ai
- **Cursor** — l'historique de chat du panneau IA de Cursor
- **Gemini** — les conversations depuis Google Gemini

L'index se construit automatiquement en arrière-plan. Rien à importer ni à configurer — ouvrez Fabric et votre historique est déjà disponible.

---

## Comment effectuer une recherche

Dans n'importe quelle session de chat, posez une question en langage naturel sur votre travail passé :

```
Qu'avons-nous décidé concernant le schéma de base de données pour la table des commandes ?
```

```
Comment ai-je résolu le problème CORS la dernière fois ?
```

```
Retrouve le script de migration que nous avons écrit pour le refactoring de l'authentification utilisateur.
```

Fabric recherche dans votre historique indexé et renvoie les extraits les plus pertinents avec la date et la conversation source. Les résultats sont classés par pertinence, récence et selon qu'ils proviennent du projet en cours.

---

## Portées de recherche

Vous pouvez contrôler l'étendue de la recherche :

| Portée | Ce qui est recherché |
|--------|---------------------|
| **Projet actuel** | Les conversations liées au projet ouvert |
| **Fabric uniquement** | Toutes les sessions de chat Fabric sur tous les projets |
| **Tous les outils** | Tout — Fabric, Claude, Cursor, Gemini |

Par défaut, Fabric donne plus de poids aux résultats du projet en cours, de sorte que le contexte pertinent remonte automatiquement sans que vous ayez à le préciser.

---

## Pourquoi c'est important

La plupart des sessions IA sont éphémères — vous fermez le chat et le contexte disparaît. Avec le temps, vous prenez les mêmes décisions deux fois, réexpliquez les mêmes choses et perdez le fil des solutions qui ont fonctionné.

La recherche dans l'historique des conversations change cela. Chaque session que vous avez eue devient une ressource exploitable. Plus vous utilisez Fabric (et les outils qu'il indexe), plus la recherche devient utile.

---

## Remarques

- L'index se met à jour en arrière-plan sur un cycle court — les nouvelles conversations sont consultables en une à deux minutes après leur fin.
- Seul le contenu des conversations est indexé — pas le contenu des fichiers de votre base de code, pas les identifiants, pas les variables d'environnement.
- L'historique est stocké localement dans le dossier de données de l'application Fabric. Il ne quitte pas votre machine.
