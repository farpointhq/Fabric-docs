# Intégration : rencontrez Visr

## Qu'est-ce que l'intégration dans Fabric ?

La première fois que vous ouvrez Fabric, vous êtes accueilli par **Visr** (qui rime avec « wiser », plus sage en anglais) — un agent de configuration vocal qui ajuste Fabric autour du travail que vous faites réellement. Au lieu d'une visite à cliquer, vous avez une courte conversation : vous dites ce sur quoi vous travaillez, Visr pose quelques questions rapides sur votre projet et votre façon de travailler, et pendant que vous parlez, il recherche discrètement votre empreinte publique et locale pour sauter les questions auxquelles il peut déjà répondre. Quand vous avez terminé, Visr ouvre un espace de travail conçu pour ce projet — souvent avec les premiers fichiers déjà échafaudés et le serveur de développement en cours d'exécution — de sorte que votre tout premier écran dans Fabric est votre propre projet, et non une page blanche.

Le tout est vocal en priorité, mais fonctionne tout aussi bien si vous tapez, et vous pouvez passer directement à un espace de travail vide à tout moment.

<div class="video-wrapper" markdown>
<video controls width="100%" style="border-radius: 8px; margin: 1rem 0;">
  <source src="../../../../assets/videos/onboarding.mp4" type="video/mp4">
  Votre navigateur ne prend pas en charge la balise vidéo.
</video>
</div>

## Quand utiliser l'intégration

L'intégration est surtout utile lorsque vous voulez :

* **Vous configurer rapidement au premier lancement** : Elle démarre automatiquement la première fois que vous ouvrez Fabric après l'avoir installé.
* **Lancer un tout nouveau projet** : Relancez-la quand vous voulez que Fabric crée et adapte un espace de travail neuf par la conversation plutôt que de le câbler à la main.
* **Laisser Fabric apprendre votre contexte** : Les faits que Visr recueille — votre stack, votre public, le niveau de détail que vous aimez — personnalisent les suggestions ultérieures de Fabric.

## Comment utiliser l'intégration

### Étape 1 : Dites bonjour à Visr

Au premier lancement, Visr se présente au-dessus de l'orbe lumineux et ouvre par une question simple : *« Alors, que cherchez-vous à faire ? »* L'orbe réagit quand il écoute et parle. Parlez simplement — ou tapez votre réponse dans la boîte — pour répondre. Une ligne de confidentialité précise que la recherche en arrière-plan reste sur votre machine et que vous pouvez l'arrêter à tout moment.

![Visr vous accueille au premier lancement](../../assets/screenshots/onboarding/1.png)

### Étape 2 : Dites à Visr ce sur quoi vous travaillez

Décrivez votre projet avec vos propres mots (« une application web de suivi d'habitudes, surtout un projet personnel »). Pendant que vous parlez, le panneau de recherche en arrière-plan se remplit à gauche — une carte « Done » (Terminé) avec ce que Visr a trouvé à votre sujet (nom, rôle, ce que vous construisez). C'est ce qui permet à Visr de sauter les questions auxquelles il peut déjà répondre, comme les langages et frameworks que vous avez tendance à utiliser. La recherche reste locale, et vous pouvez l'arrêter à tout moment.

![Visr vous recherche en arrière-plan](../../assets/screenshots/onboarding/2.png)

### Étape 3 : Confirmez les détails

Chaque chose que Visr apprend apparaît sous forme de petite carte de fait à droite — « Loisir / personnel », « Juste moi », et ainsi de suite. Visr vous répète les détails pour que vous puissiez corriger quoi que ce soit avant qu'il n'agisse en conséquence.

![Les faits s'accumulent à mesure que Visr vous comprend](../../assets/screenshots/onboarding/3.png)

### Étape 4 : Laissez Visr proposer votre configuration

Une fois qu'il en sait assez, Visr cesse de poser des questions et commence à proposer — en intégrant ce que la recherche a trouvé : *« …d'après votre travail précédent avec React et TypeScript, voulez-vous que je le configure ainsi ? »* Confirmez ou orientez-le ailleurs.

![Visr propose une stack d'après ce qu'il a trouvé](../../assets/screenshots/onboarding/4.png)

### Étape 5 : Regardez votre espace de travail se construire

Visr passe la main à Fabric, qui échafaude le projet pour de vrai — créant l'arborescence des fichiers, écrivant les fichiers de départ et installant les dépendances. Vous pouvez regarder le plan s'exécuter dans le chat pendant que l'explorateur de fichiers se remplit à gauche.

![Fabric échafaude le projet](../../assets/screenshots/onboarding/5.png)

### Étape 6 : Commencez à construire

Une fois terminé, vous arrivez dans un espace de travail fonctionnel : les fichiers du projet à gauche, un aperçu en direct de l'application en cours d'exécution à droite, et un résumé de vérification dans le chat (installation faite, serveur de développement démarré, un test de fumée rapide réussi). À partir de là, vous êtes dans Fabric normal — poursuivez la conversation pour ajouter la fonctionnalité suivante.

![L'espace de travail terminé avec un aperçu en direct](../../assets/screenshots/onboarding/6.png)

## Taper au lieu de parler

Vous préférez lire et taper ? Utilisez les bascules **Speak / Type** (Parler / Taper) et **Hear / Read** (Entendre / Lire) en haut de l'écran d'intégration pour changer indépendamment les modes d'entrée et de sortie. Tout fonctionne de la même façon — l'orbe, le panneau de recherche, les cartes de faits et le passage de relais.

## Passer ou refaire l'intégration

* **La passer** : Choisissez **Skip — open a project** (Passer — ouvrir un projet) à tout moment pour aller directement à un espace de travail vide ou ouvrir un dossier existant.
* **La refaire plus tard** : Ouvrez **Paramètres → Companion → Refaire l'intégration** et choisissez **Start onboarding again** (Recommencer l'intégration). L'application se relance et exécute le flux de bienvenue depuis le début. Tout ce que vous avez dit à Visr en conversation est effacé ; les faits que l'analyse en arrière-plan a déduits à votre sujet sont conservés.
