<div align="center">
    <p>
        <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/banner-draw.png" alt="DRAW Banner">
    </p>


<div>

[![DRAW2 Workflow](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml/badge.svg)](https://github.com/HichTala/draw2-plugin/actions/workflows/push.yaml)
[![Licence](https://img.shields.io/pypi/l/ultralytics)](../LICENSE)
[![Github](https://img.shields.io/badge/-github-181717?logo=github&labelColor=555)](https://github.com/HichTala/draw2)
[![Twitter](https://img.shields.io/badge/-twitter-000?logo=x&labelColor=555)](https://twitter.com/hichtala)
[![HuggingFace Downloads](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fhuggingface.co%2Fapi%2Fmodels%2FHichTala%2Fdraw2&query=%24.downloads&logo=huggingface&label=downloads&color=%23FFD21E)](https://huggingface.co/HichTala/draw2)
[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)
[![WandB](https://img.shields.io/badge/visualize_in-W%26B-yellow?logo=weightsandbiases&color=%23FFBE00)](https://wandb.ai/hich_/draw)

[🇬🇧 English](../README.md) | [🇧🇷 Português](README_pt-br.md) | [🇯🇵 日本語](README_jp.md) | [🇪🇸 Español](README_es.md)

</div>

</div>

DRAW est le tout premier détecteur d'objets entraîné à détecter les cartes Yu-Gi-Oh! dans tous types d'images,
et en particulier dans les images de duels.

Ce projet est la partie plugin du système DRAW 2. Il permet aux utilisateurs
d'intégrer de manière transparente le détecteur directement dans leurs streams ou leurs vidéos ;
et ceux **sans avoir de compétences techniques particulières**.
Le plugin peut afficher les cartes détectées en temps réel pour une expérience visuelle améliorée pour les spectateurs.

Ce projet est sous licence [GNU Affero General Public License v3.0](LICENCE) ; toutes les contributions sont les
bienvenues.

---
## <div align="center">📰 News</div>

> 🃏 **Dernière extension supportée:** `BLZD` --- mise à jour le `18-05-2026`  
> 🔧 **Dernière version:** `0.2.1-beta` --- mise à jour le `01-06-2026`

<table>
  <tr>
    <th>Date</th>
    <th>Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><b>01-06-2026</b></td>
    <td>🔧 Version de l'app</td>
    <td>Dernière version 0.2.1-beta --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.1">voir les notes de maj</a></td>
  </tr>
  <tr>
    <td><b>18-05-2026</b></td>
    <td>🃏 Pool de cartes</td>
    <td>Mise à jour du pool de cartes --- prend désormais en charge les cartes jusqu'à <i>Territoire Embrasé</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🃏 Pool de cartes</td>
    <td>Mise à jour du pool de cartes --- prend désormais en charge les cartes jusqu'à <i>Le Labyrinthe des Morts</i></td>
  </tr>
  <tr>
    <td><b>06-04-2026</b></td>
    <td>🔧 Version de l'app</td>
    <td>Dernière version 0.2.0-beta --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.2.0">voir les notes de maj</a></td>
  </tr>
  <tr>
    <td><b>09-03-2025</b></td>
    <td>🔧 Version de l'app</td>
    <td>Dernière version 0.1.5-alpha --- <a href="https://github.com/HichTala/draw2-plugin/releases/tag/0.1.5">voir les notes de maj</a></td>
  </tr>
  <tr>
    <td><b>24-08-2025</b></td>
    <td>🃏 Pool de cartes</td>
    <td>Mise à jour du pool de cartes --- prend désormais en charge les cartes jusqu'à <i>Les Chasseurs de Justice</i></td>
  </tr>
</table>

---

## <div align="center">📄Documentation</div>

### 🛠️ Installation

Suivez les instructions d'installation correspondant à votre système d'exploitation afin que tout fonctionne
correctement :

<details open>
<summary>🪟 Windows</summary>

1. Téléchargez le programme d'installation du plugin à partir de ce
   lien : [DRAW2 Plugin Installer](https://github.com/HichTala/draw2-plugin/releases/download/0.2.1/draw2-plugin-installer.exe)
2. Exécutez le programme d'installation et suivez les instructions à l'écran.
3. Une fois l'installation terminée, lancez OBS Studio. Si tout est correctement configuré, vous devriez voir dans le
   menu `Docks`
   une nouvelle option appelée `Draw 2`. Vous pouvez activer le dock et le placer où vous le souhaitez.

   Le téléchargement est terminé ! Bonne détection à tous!

</details>

<details>
<summary>🐧 Linux</summary>

À venir 👀

</details>

<details>
<summary>🍏 MacOS</summary>

Je ne connais pas suffisamment bien OBS sur macOS pour fournir un guide d'installation fiable.
Le plugin peut être compilé avec succès sur macOS, mais je ne l'ai pas testé de manière approfondie.
Si vous avez de l'expérience avec les plugins OBS sur macOS et que vous souhaitez contribuer à un guide d'installation,
n'hésitez pas à soumettre une demande d'extraction.

> ℹ️ Sur macOS, le backend Python tourne comme un **processus séparé** (le plugin n'embarque plus d'interpréteur). Dans **Select Python installation**, indiquez un préfixe Python qui contient le paquet `draw`, installé depuis la branche **`obs-plugin`** (`pip install "git+https://github.com/HichTala/draw2@obs-plugin"`). N'importe quel Python 3 récent convient — il n'a pas besoin de correspondre à la version du plugin. Voir la section macOS du [README en anglais](../README.md) pour les étapes complètes de compilation et de configuration.
</details>

### 🚀 Utilisation

Une fois le plugin installé et les poids du modèle téléchargés, vous pouvez lancer OBS Studio.

1. Ouvrez le menu `Docks` et sélectionnez `Draw 2` pour activer le dock du plugin.
2. Dans le dock `Draw 2`, vous pouvez configurer les paramètres du plugin en cliquant sur l'icône en forme d'engrenage à
   côté du bouton `Start DRAW` :
    - **Sélectionner les listes de deck** : choisissez les deck lists qui contiennent les cartes que vous souhaitez
      détecter — jusqu'à 3. Pour ajouter des deck lists, cliquez sur `Open Folder` et déposez vos fichiers `.ydk` dans le dossier ouvert.
    - **Durée minimale hors écran** : durée minimale pendant laquelle une carte qui vient d'être détectée peut être
      affichée à nouveau.
    - **Durée minimale d'affichage** : durée minimale pendant laquelle une carte est affichée.
    - **Seuil de confidence** : définissez le niveau de confiance minimum pour la détection des cartes. Les détections
      inférieures à ce seuil seront ignorées.
    - **Advanced features** (désactivées par défaut) : deux réglages optionnels de l'entrée du détecteur qui
      n'affectent que ce que voit le détecteur, pas votre sortie en direct. Activez-les ici, puis configurez les
      valeurs sur la source `Draw Display` :
      - **Enable two players** — ajoute un ensemble de deck lists **Player 2** et lance un **détecteur distinct par joueur**, permettant de traiter deux joueurs simultanément. Laissez cette option désactivée pour une configuration à un seul joueur.
      - **Enable detector input crop** — ajoute des champs **Crop (Left/Top/Right/Bottom, px)** à la source,
        pour cibler la zone où les cartes sont posées.
      - **Enable 180° input rotation** — ajoute un interrupteur **Rotate input 180°** à la source, pour une
        caméra montée à l'envers.
      - Lorsque l'une ou l'autre est activée, la source gagne également le bouton **Preview detector input** :
        activez-le pour que la source affiche l'image recadrée/pivotée qu'elle envoie au détecteur (afin de
        régler le recadrage directement dans l'aperçu de la source), puis désactivez-le pour revenir à
        l'affichage des cartes détectées.
    - **Enable debug logging** (désactivé par défaut) : affiche des diagnostics détaillés — le journal du dock
      montre le lancement exact du backend (chemins de deck résolus, canal, seuils) et chaque ligne du backend
      sans filtrage, et le journal OBS reçoit les détails de capture (source d'entrée, dimensions,
      recadrage/rotation). Pratique quand la détection ne se comporte pas comme prévu.
    - **Enable remote decklist** — charge un deck depuis une URL HTTP(S) au lieu d'un fichier `.ydk` local ; voir la note sous la source `Draw Display`.
3. Le plugin fournit une nouvelle source appelée `Affichage DRAW`. Vous pouvez l'ajouter à votre scène comme n'importe
   quelle autre source.
   Cette source affichera les cartes détectées à l'écran. Vous pouvez choisir la source/scène à partir de laquelle
   détecter les cartes. Avec le mode deux joueurs activé, utilisez la propriété **Detector / Player** de la source pour choisir de quel détecteur elle
   lit (**Player 1** ou **Player 2**) ; ajoutez un `Draw Display` par joueur pour afficher les deux simultanément.

   > 💡 Le plugin peut également charger une deck list depuis une **URL HTTP(S)** plutôt qu'un fichier `.ydk` local —
   > pratique lorsque votre liste de cartes est servie par une API distante ou un système de gestion de tournoi. Cette
   > fonctionnalité est **désactivée par défaut** — activez **Enable remote decklist** dans les paramètres de Draw 2
   > (*Fonctionnalités avancées*) ; les URLs se configurent ensuite dans un onglet dédié **Decklist**.
   >
   > Deux modes sont disponibles une fois activé :
   > - **Import deck from URL…** (bouton dans l'onglet **Decklist**) — récupère l'URL une seule fois et enregistre le
   >   résultat comme un fichier `.ydk` normal dans le dossier des deck lists, vous pouvez ainsi l'utiliser comme un deck
   >   fichier ordinaire.
   > - **Champ d'URL par joueur** — une URL par joueur (Player 1, plus Player 2 en mode deux joueurs). Lorsque l'option
   >   distante est active, ils remplacent les sélecteurs de fichier ; l'URL est récupérée en direct au clic sur Start
   >   DRAW. En cas d'échec, ce joueur démarre simplement sans filtre de deck.
   >
   > Formats de réponse acceptés : tableau JSON d'ID de carte (passcodes) ; objet JSON
   > `{ "main": [...], "extra": [...], "side": [...] }` ; texte `.ydk` brut ; ou texte brut contenant des ID numériques.
   >
   > Un en-tête d'authentification optionnel (nom + valeur, p. ex. `Authorization` / `Bearer …`) peut être configuré
   > et est envoyé avec chaque requête.
   >
   > ⚠️ Les URLs et la valeur de l'en-tête sont stockées en texte brut dans QSettings, comme tous les autres paramètres
   > du plugin — évitez d'y placer des secrets à longue durée de vie.
4. Cliquez sur le bouton `Start DRAW` pour lancer le processus de détection. Le plugin commencera à détecter les cartes
   en temps réel
   et les affichera à l'écran à l'aide de la source `Draw Display`. Le plugin commence la détection dès que le bouton
   `Stop DRAW` s'affiche.
   Si vous ne le voyez pas, cela signifie qu'il y a eu un problème.
5. Dans le cas contraire, vous pouvez profiter du plugin !

Voici un petit aperçu :)
<div align="center">
    <img src="https://raw.githubusercontent.com/HichTala/draw2/refs/heads/main/figures/overview.gif" width="960" height="540" />
</div>

---

## <div align="center">🔍Aperçu de la méthode</div>

Un blog medium expliquant le processus principal, de la collecte des données à la prédiction finale a été publié.
Vous pouvez le retrouver
[ici](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a).
Si vous avez des questions, n'hésitez pas à ouvrir une issue.

[![Medium](https://img.shields.io/badge/-Medium-12100E?style=flat&logo=medium&labelColor=555)](https://medium.com/@hich.tala.phd/how-i-trained-again-my-model-to-detect-and-recognise-a-wide-range-of-yu-gi-oh-cards-5c567a320b0a)

---

## <div align="center">💬Contact</div>

Vous pouvez me joindre sur Twitter [@hichtala](https://twitter.com/hichtala) ou par
mail [hich.tala.phd@gmail.com](mailto:hich.tala.phd@gmail.com).

---

## <div align="center">⭐Historique des Stars</div>

<a href="https://www.star-history.com/#HichTala/draw2&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=HichTala/draw2&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=HichTala/draw2&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=HichTala/draw2&type=date&legend=top-left" />
 </picture>
</a>
