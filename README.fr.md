# [Keyviz](https://keyviz.org)

<div>
   <img src="https://img.shields.io/github/v/release/mulaRahul/keyviz?style=flat-square" alt="Versions">
   <img src="https://img.shields.io/github/downloads/mulaRahul/keyviz/total?style=flat-square" alt="Téléchargements">
   <img src="https://img.shields.io/github/stars/mulaRahul/keyviz?style=flat-square" alt="Étoiles">
   <img src="https://img.shields.io/github/license/mulaRahul/keyviz?style=flat-square" alt="Licence">
   <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS-lightgrey?style=flat-square" alt="Plateformes">
</div>

[English](README.md) · **Français**

Keyviz est un outil **libre et gratuit** qui affiche en temps réel les touches pressées et les actions de la souris. Montrez à votre public les raccourcis que vous utilisez pendant un tutoriel, une présentation, un travail à plusieurs, ou quand vous voulez.

## ⌨️ Touches et 🖱️ actions de la souris
En plus des touches ordinaires, Keyviz affiche les actions de la souris comme <kbd>Cmd</kbd> + <kbd>Clic</kbd>, <kbd>Alt</kbd> + <kbd>Glisser</kbd>, etc.

<img src="previews/visualization.png" alt="Affichage des touches" width="450">

Les clics et la molette s'affichent à côté du curseur.

<img src="previews/mouse-indicator.gif" alt="Indicateur de souris" width="450">

</br>

## ⚙️ Tout se règle
Rien n'est figé. Chaque aspect de l'affichage se règle :
- **Style :** couleurs (modificateurs et touches ordinaires), taille, disposition, bordure et fond.
- **Filtre :** choix des touches affichées, par raccourcis ou par filtre personnalisé.
- **Historique :** garde une trace visuelle des dernières saisies.
- **Position :** l'affichage se place n'importe où sur l'écran.
- **Animations :** entrée et sortie des touches au choix parmi des animations prédéfinies.
- **Claviers SVG :** les dessins des touches viennent d'un fichier SVG par clavier, modifiable dans Inkscape ou un éditeur de texte.
- **Langue :** interface en français ou en anglais.

</br>

<img src="previews/settings.png" alt="Fenêtre des réglages" width="600">

</br>

## 📥 Installation

### Windows et macOS
La dernière version de Keyviz se télécharge sur la page **[GitHub Releases](https://github.com/mulaRahul/keyviz/releases)**.

*   **Windows :** télécharger l'installeur `.msi` ou `.exe`, le lancer et suivre les étapes. La version portable (`_portable.exe`) se lance sans installation.
*   **macOS :** télécharger le `.dmg`. **Attention :** Keyviz a besoin des autorisations **Surveillance de l'entrée** et **Accessibilité**. Les activer ici : `Réglages > Confidentialité et sécurité > Surveillance de l'entrée et Accessibilité`

### Linux (X11)
Keyviz fonctionne sous Linux avec le protocole X11. Pour l'instant, il faut le construire soi-même en suivant les instructions ci-dessous.

</br>

## 🛠️ Construction

Pour contribuer ou construire les dernières fonctions depuis les sources, installer [Node.js](https://nodejs.org/) et [Tauri](https://v2.tauri.app/start).

1.  **Cloner le dépôt :**
    ```bash
    git clone https://github.com/mulaRahul/keyviz.git
    cd keyviz
    ```

2.  **Installer les dépendances :**
    ```bash
    npm install
    ```

3.  **Construire l'exécutable :**
    ```bash
    npx tauri build
    ```

<br/>


## 💖 Soutenir le projet

*   **Une étoile sur le dépôt :** elle aide d'autres personnes à découvrir le projet !
*   **GitHub Sponsors :** [soutenir @mularahul](https://github.com/sponsors/mulaRahul)
*   **Keyviz Pro :** des fonctions exclusives, tout en soutenant le développement de ce projet libre.

👉 **[Passer à Pro sur keyviz.org/pro](https://keyviz.org/pro)**

</br>

---

  Fait avec 🦀 et ❤️ grâce à <a href="https://v2.tauri.app/">Tauri</a>.
