# À faire

1. ⏳ Verr. Maj non pris en compte pour la casse (état de la bascule inconnu côté Rust).
2. ⏳ Touche `IntlBackslash` (`< >` des claviers ISO) absente de `keymaps.ts` : jamais affichée.
3. ⏳ Numéro interne à 4 segments (`buildNumber`) pas encore affiché hors production dans « À propos ».

# Journal

## v2026.10.0 (build 2026.10.0.1) — publication

1. ✅ `Icones.svg` de Frank intégré (`src/assets/keyboards/icones.svg`, `lib/builtin-keyboards.ts`) et clavier par défaut (`builtin:icones`). Le SVG intégré est lu depuis l'appli, pas depuis le magasin : il suit les mises à jour. Les icônes lucide deviennent « Icônes classiques ».
2. ✅ Traduction FR de toutes les nouvelles chaînes.
3. ✅ Version publique `2026.10.0` (`tauri.conf.json`), `buildNumber` `2026.10.0.1` (`package.json`). Installeur MSI retiré des cibles (majeur ≤ 255 refusé par WiX) : NSIS seul sous Windows.
4. ✅ CHANGELOG daté, corrections fondues dans Modification (demande de Frank).
5. ✅ Enregistrements séparés : code générique (branche `feature/i18n-svg-keyboards`, PR vers mulaRahul/keyviz) ; clavier de Frank, version, suivi dans `main` du fork `FrankSAURET/keyviz`.
6. ✅ Installeur `.exe` en release sur le fork.

## Lot 3 — souris sans touche

1. ✅ Réglage `showMouseKeys` (store `key_event`, persisté, actif par défaut) : désactivé, clics, glissement et molette ne deviennent plus des touches. L'indicateur près du curseur (`mouse-overlay.tsx`) reste alimenté (`pressedMouseButton`, `mouse.wheel`). Interrupteur « Show as Keys » dans Réglages > Souris > Event.
2. ✅ Traduction FR de « Show as Keys » et sa description (lot de publication).

## Lot 2 — AltGr et couleur des claviers SVG

1. ✅ AltGr : Windows envoie un faux Ctrl gauche (code de position `0x21D`) avec AltGr ; filtré dans `src-tauri/src/app/event.rs`.
2. ✅ AltGr ajoutée : `RawKey.AltGr` + `MODIFIERS` (`types/event.ts`), `keymaps['AltGr']` (libellé, glyphe ⌥, icône), bouton dans `custom-filter.tsx`.
3. ✅ Couleur : `followTextColor()` dans `lib/keyboard.tsx` remplace par `currentColor` le noir et la couleur `color` de la racine (Inkscape y fige `currentColor`), en attributs et dans `style`. Autres couleurs conservées. Planche modèle en `#000000`.
4. ✅ Construction Rust (permissions Tauri validées) et `npx tsc --noEmit` sans erreur.
5. ✅ Dessins en tout petit (Space, Return, Home, End, PageUp, PageDown, Escape) : agrandis dans Inkscape par la transformation du groupe, que le programme jetait. Désormais le cadre pointillé (rect suivi de la légende = nom de la touche, `findFrames()`) est la zone affichée, et le dessin garde sa transformation et celles de ses ancêtres (`inSheetSpace()`). Sans cadre : `data-viewbox` puis contour, comme avant.

## Lot 1 — casse des lettres et claviers SVG

1. ✅ Lettres : « a » seul, « A » avec Maj. `KeyEvent.shifted` relevé à l'appui (`key_event.ts`), appliqué dans `keycaps/base.tsx` et `keycaps/minimal.tsx`. Réglage `text.matchCase` (actif par défaut), interrupteur dans Réglages > Touches > Texte.
2. ✅ Claviers SVG : `src/lib/keyboard.tsx`. Un fichier SVG par clavier ; un élément `id="ControlLeft"`, `id="Escape"`… remplace l'icône de la touche. Attributs : `data-viewbox`, `data-label`, `data-short-label`, `data-icon-only`.
3. ✅ Claviers intégrés : « Icônes (par défaut) » et « Glyphes » (tiré des champs `glyph` de `keymaps.ts`). « Dupliquer » écrit une planche complète éditable dans `%APPDATA%/org.keyviz/keyboards/`.
4. ✅ Sélecteur dans Réglages > Touches (`settings/keyboard-picker.tsx`) : liste, Dupliquer, Ouvrir le dossier, Recharger. Le SVG choisi est stocké dans `key_style.keyboard` (synchronisé avec la fenêtre d'affichage, inclus dans l'export de style).
5. ✅ Style minimal : les dessins du fichier clavier s'affichent sur toutes les touches, pas seulement les modificateurs.
6. ✅ `npx tsc --noEmit` et `vite build` sans erreur.
