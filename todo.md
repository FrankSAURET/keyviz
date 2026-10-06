# À faire

1. ⏳ Verr. Maj sous macOS et Linux : à essayer sur une vraie machine (compile sur les deux cibles par GitHub Actions, jamais lancé).

# Journal

## v2.1.2 (build 2.1.2.4) — release

1. ✅ `.github/workflows/build.yml` : lancement manuel (`gh workflow run build.yml -f tag=vX`), DMG universel (macos-latest) et deb/rpm/AppImage (ubuntu-22.04) par `tauri-action`, envoyés dans la release de l'étiquette.
2. ✅ `winget.yml` limité à `mulaRahul/keyviz` : le fork ne tente plus de publier sur Winget.
3. ✅ Release `v2.1.2` sur le fork : NSIS, MSI, portable exe et zip ; macOS et Linux par la construction GitHub.
4. ℹ️ DMG non signé : clic droit > Ouvrir au premier lancement.

## v2.1.2 (build 2.1.2.3)

1. ✅ Verr. Maj macOS : `CGEventSourceFlagsState(0) & 0x10000` (CoreGraphics, `kCGEventFlagMaskAlphaShift`). Linux : voyant `/sys/class/leds/*::capslock/brightness`, valable sous X11 et Wayland, sans droit particulier.
2. ✅ Erreur `TS2578` corrigée : `@ts-expect-error` inutile retiré de `vite.config.ts`.
3. ✅ Traductions : interface déjà complète (en/fr, aucune clé manquante, vérifié par script). `README.fr.md` créé, liens English · Français dans les deux README ; README anglais complété (claviers SVG, langue, MSI/exe/portable).
4. ℹ️ CHANGELOG laissé en français (règle de Frank).
5. ℹ️ Installeurs non reconstruits : le code Windows n'a pas changé depuis le build 2.1.2.2.

## v2.1.2 (build 2.1.2.2)

1. ✅ Verr. Maj : `caps_lock_on()` dans `src-tauri/src/app/event.rs` (`GetKeyState(VK_CAPITAL) & 1`, feature `Win32_UI_Input_KeyboardAndMouse`), champ `caps_lock` dans `InputEvent::KeyEvent`. Frontal : majuscule = Maj XOR Verr. Maj (`key_event.ts`).
2. ✅ `IntlBackslash` : `RawKey`, `keymaps.ts` (« < », symbole « > », ponctuation), bouton dans `custom-filter.tsx` entre Maj gauche et Z.
3. ✅ « À propos » : `buildNumber` injecté par Vite (`define` `__BUILD_NUMBER__` depuis `package.json`), affiché seulement en développement (`import.meta.env.DEV`). Recherche de mise à jour : comparaison numérique (plus de « nouvelle version » 2.1.1 pour un 2.1.2).
4. ✅ Version : retour au semver de l'auteur, `2.1.2` (`tauri.conf.json`, `about.tsx`), `buildNumber` `2.1.2.2`. Cibles `"all"` rétablies : MSI construit à nouveau.
5. ✅ Construction : installeurs NSIS et MSI, version portable (exe seul, WebView2 requis).
6. ℹ️ Erreur `TS2578` dans `vite.config.ts` (`@ts-expect-error` inutile) : antérieure, corrigée au build 2.1.2.3.

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
