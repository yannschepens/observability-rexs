# BRIEF — Conférence NettoieLogs2000

## Contexte du projet

Présentation de conférence technique sur la **gestion et le nettoyage de logs / métriques**.
Outil : **RevealJS** (HTML/CSS/JS).

---

## Entreprise fictive : NettoieLogs2000

> *"The Log Laundry Specialists"*

**Concept** : Une blanchisserie / pressing pour les logs et métriques. Métaphore du nettoyage industriel appliquée à la data engineering.

- **Nom** : NettoieLogs2000
- **Slogan** : *CLEAN LOGS. FRESH METRICS.*
- **Fondée** : 1987 (badge rétro)
- **Secteur fictif** : Log hygiene & metric laundering

---

## Direction artistique

### Style général
- **Rétro années 80-90** — esthétique pressing / blanchisserie industrielle
- Texture papier crème, grain, motifs géométriques
- Typographie **serif bold** pour les titres (Georgia ou équivalent), **monospace** pour les éléments techniques et taglines
- Pas de gradients — aplats francs, contrastes forts

### Palette de couleurs
| Rôle | Couleur | Hex |
|------|---------|-----|
| Principal (fond sombre, titres) | Bleu marine | `#1a3a5c` |
| Accent / alerte | Rouge pressing | `#c0392b` |
| Fond de slide | Crème papier | `#F2E8D5` |
| Fond alternatif | Crème chaud | `#F5EDD8` |
| Blanc cassé | — | `#FAF6EE` |

### Éléments graphiques récurrents
- Hublot de machine à laver (logo NettoieLogs2000)
- Lignes de log stylisées (rectangles empilés)
- Badges rétro avec coins arrondis et double bordure
- Motif grille fine en arrière-plan (opacité ~8%)
- Points discrets en pattern (opacité ~12%)
- Coins décoratifs en L sur les slides

---

## Structure du thème RevealJS

### Fichiers à créer / modifier
```
presentation/
├── index.html              ← fichier principal RevealJS (modifier)
├── BRIEF.md                ← ce fichier
├── styles/
│   └── nettoielogs2000/
│       ├── NettoieLogs2000.css         ← thème custom à créer
│       ├── logo-NettoieLogs2000.svg    ← logo SVG standalone
│       ├── bg-slide.svg        ← fond de slide SVG
│       └── illustrations/
│           ├── log-corrompu.svg
│           ├── cycle-lavage.svg
│           ├── metriques-propres.svg
│           └── pipeline-realtime.svg

```

### Paramètres RevealJS recommandés
```javascript
Reveal.initialize({
  hash: true,
  transition: 'fade',
  transitionSpeed: 'slow',
  backgroundTransition: 'fade',
  width: 1280,
  height: 720,
  margin: 0.08,
});
```

### CSS du thème (NettoieLogs2000.css) — specs

**Slide de titre (section.title-slide)**
- Fond : `#1a3a5c`
- Titre : Georgia serif, très grand, blanc, letter-spacing négatif
- Sous-titre : Courier New, rouge `#c0392b`, majuscules, letter-spacing large
- Logo NettoieLogs2000 centré en haut

**Slides standard**
- Fond : `#F2E8D5` avec texture grille SVG inline
- Bande header : `#1a3a5c` (52px), avec logo miniature à gauche
- Bande accent rouge sous le header : 8px, `#c0392b`
- Bande footer : `#1a3a5c`, tagline centrée + numéro de slide à droite
- Coins décoratifs en L (bleu marine, opacité 50%)
- Titre h2 : Georgia, `#1a3a5c`, gras
- Ligne décorative sous le titre : 2.5px rouge + 1px bleu en dessous

**Code / logs**
- Fond : `#1a3a5c`
- Texte : `#7ab3d4` (bleu clair) ou blanc
- Font : Courier New, monospace
- Bordure gauche rouge `#c0392b` (4px)

---

## Illustrations à générer (SVG)

### 1. `log-corrompu.svg`
Fichier log froissé avec lignes rouges (erreurs), bruit, caractères parasites. Style document papier années 80 avec coin replié.

### 2. `cycle-lavage.svg`
Diagramme en 4 étapes style machine à laver : **Ingest → Filter → Normalize → Output**. Chaque étape = tambour de machine. Flèches rétro entre les étapes.

### 3. `metriques-propres.svg`
Dashboard minimaliste rétro : graphique en barres bleu marine avec accent rouge sur la barre "propre". Style affichage terminal années 80.

### 4. `pipeline-realtime.svg`
Architecture pipeline en flux : sources de logs → NettoieLogs2000 Engine → sorties propres. Icônes stylisées pressing (cintres, hublots, étiquettes).

---

## Slides prévues (structure indicative)

Regarde dans la structure du repertoire pages, tu auras toutes les pages.

---

## Instructions pour Claude Code

Quand tu travailles sur ce projet :

1. **Lis ce BRIEF en premier** avant toute génération
2. **Respecte strictement la palette** — pas d'autres couleurs sans validation
3. **Tous les SVG** doivent être standalone (viewBox défini, pas de dépendances externes)
4. **Le thème CSS** doit être compatible RevealJS 4.x
5. **Les illustrations** doivent pouvoir s'intégrer en `<img src="...">` ou inline `<svg>`
6. **Teste le rendu** en ouvrant `index.html` dans un navigateur local après chaque modification majeure
7. **Conventions de nommage** : kebab-case pour tous les fichiers assets