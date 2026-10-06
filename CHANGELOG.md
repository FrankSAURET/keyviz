# Journal des modifications

## 2.1.2 (prochaine publication)

### Nouveauté

- Touche `< >` des claviers ISO (à gauche de W/Z) affichée, et présente dans le filtre des touches.
- Installeur MSI et version portable (exe seul, sans installation) en plus de l'installeur habituel.
- README en français (`README.fr.md`), lien entre les deux langues.

### Modification

- Les lettres suivent aussi Verr. Maj : majuscule avec Verr. Maj ou Maj, minuscule avec les deux. Windows, macOS et Linux.
- Numérotation revenue à celle du projet d'origine : 2.1.2 succède à 2.1.1.
- « Rechercher les mises à jour » ne propose plus une version plus ancienne que celle installée.
- Fichiers claviers SVG : tout contenu actif (scripts, gestionnaires d'événements, liens et ressources externes) est ignoré au chargement. Un clavier téléchargé ne peut plus exécuter de code dans keyviz.
- Installeur MSI : plus de case « Lancer keyviz » en fin d'installation. L'instance qu'elle lançait se figeait au premier clic sur l'icône de la zone de notification, et keyviz ne démarrait plus ensuite. Lancer keyviz depuis le menu Démarrer après l'installation.

## 2026.10.0 (6 octobre 2026)

### Nouveauté

- Interface en français ou en anglais, menu de la zone de notification et titre de la fenêtre des réglages compris.
- Choix du clavier dans Réglages > Touches : chaque clavier est un fichier SVG qui redessine les touches voulues (Ctrl, Échap, Maj…). Trois claviers fournis : « Icônes » (par défaut), « Icônes classiques » et « Glyphes ».
- Bouton « Dupliquer pour modifier » : crée une copie modifiable du clavier (planche de toutes les touches, à ouvrir dans Inkscape ou un éditeur de texte), puis ouvre le dossier des claviers.
- Bouton « Recharger » : prend en compte les retouches du fichier sans redémarrer.
- Réglages > Souris > « Afficher comme touches » : désactivé, les clics, le glissement et la molette ne s'affichent plus comme touches ; l'indicateur près du curseur reste.

### Modification

- Les lettres suivent la touche Maj : « a » seul, « A » avec Maj. Désactivable (« Lettres selon Maj »).
- Claviers SVG : le noir prend la couleur du texte choisie dans Keyviz ; les autres couleurs du dessin restent telles quelles.
- Claviers SVG : un dessin agrandi, déplacé ou tourné dans son cadre pointillé s'affiche tel quel.
- AltGr n'est plus affichée comme Ctrl + Alt sous Windows.
- AltGr a sa propre touche : libellé, icône, glyphe, filtre des touches et dessin dans les claviers SVG.
