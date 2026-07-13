# Typography Skills & Resources

Curated, verified open-source resources for web typography: font families, self-hosting tooling, variable-font engineering, fluid type scales, and font-metric utilities. Use these when picking a typeface for a project, self-hosting fonts for performance/privacy, building a responsive type scale, or fixing cross-browser line-height/font-metric inconsistencies.

## Best Repositories

### [google/fonts](https://github.com/google/fonts)
- **Stars:** ~20,231 (as of 2026-07-13)
- **License:** Mixed — the fonts themselves are predominantly SIL Open Font License 1.1 (OFL-1.1), a small number are Apache-2.0; check each font's `OFL.txt`/`LICENSE.txt` in its subdirectory
- **Last updated:** actively maintained, pushed 2026-07-13

The canonical source repository for every font family served by Google Fonts, plus the public issue tracker for font bugs and additions. This is the upstream/reference copy for most of the individual font repos below (Cairo, Tajawal, Amiri, Noto, etc. all have a corresponding directory here under `ofl/`).

**Installation:**
```bash
git clone --depth 1 https://github.com/google/fonts.git
# or just use the CDN for a single family, e.g. Inter:
# <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">
```

**Usage example:**
```html
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
<style>
  body { font-family: "Inter", system-ui, sans-serif; }
</style>
```

### [rsms/inter](https://github.com/rsms/inter)
- **Stars:** ~19,712 (as of 2026-07-13)
- **License:** OFL-1.1
- **Last updated:** 2024-11-19

Inter is a variable, highly legible sans-serif designed for UI text at small sizes on screens. It's one of the most widely deployed interface typefaces on the web (used by GitHub, Figma, Linear, and countless design systems).

**Installation:**
```bash
npm install @fontsource-variable/inter
```

**Usage example:**
```css
@import "@fontsource-variable/inter";

body {
  font-family: "Inter Variable", system-ui, sans-serif;
  font-feature-settings: "cv11", "ss03";
}
```

### [majodev/google-webfonts-helper](https://github.com/majodev/google-webfonts-helper)
- **Stars:** ~13,023 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, pushed 2026-02-27

A hassle-free way to self-host Google Fonts: generates `woff2`/`woff`/`ttf` files plus ready-to-use `@font-face` CSS, so you avoid a runtime dependency on fonts.googleapis.com (better privacy and often better performance).

**Installation:**
```bash
# Hosted instance, no install needed:
# https://gwfh.mranftl.com
# Or self-host the tool itself:
git clone https://github.com/majodev/google-webfonts-helper.git
```

**Usage example:**
```css
@font-face {
  font-family: 'Inter';
  font-style: normal;
  font-weight: 400;
  src: url('./fonts/inter-v13-latin-regular.woff2') format('woff2');
  font-display: swap;
}
```

### [fontsource/fontsource](https://github.com/fontsource/fontsource)
- **Stars:** ~6,013 (as of 2026-07-13)
- **License:** MIT (packaging tooling); bundled font files retain their own original licenses, typically OFL-1.1
- **Last updated:** actively maintained, pushed 2026-07-13

Self-hosts open-source fonts (Google Fonts and others) as neatly bundled NPM packages, so you can `import` a font directly into your JS/CSS build instead of depending on an external CDN. Best-in-class developer experience for font loading in modern bundlers (Vite, webpack, Next.js, Astro).

**Installation:**
```bash
npm install @fontsource/inter
```

**Usage example:**
```js
// In your app entry point:
import "@fontsource/inter/400.css";
import "@fontsource/inter/700.css";
```
```css
body { font-family: "Inter", sans-serif; }
```

### [fonttools/fonttools](https://github.com/fonttools/fonttools)
- **Stars:** ~5,165 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, pushed 2026-07-13

The foundational Python library for manipulating font files (TTF/OTF/UFO/variable fonts). Nearly every modern font-build pipeline (including Google Fonts' own tooling) is built on top of `fontTools`. Essential if you need to subset, instantiate static fonts from a variable font, or inspect font internals.

**Installation:**
```bash
pip install fonttools
```

**Usage example:**
```bash
# Subset a variable font down to only the Latin + weight axis you need
fonttools varLib.instancer -o Inter-Regular-static.ttf Inter-Variable.ttf wght=400
```

### [seek-oss/capsize](https://github.com/seek-oss/capsize)
- **Stars:** ~1,707 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, pushed 2026-07-06

Capsize uses font metrics to size and position text consistently across browsers and platforms, so your line-height and vertical spacing stop varying font-to-font and browser-to-browser. Best for design systems that need pixel-perfect, metric-driven typography.

**Installation:**
```bash
npm install @capsize/core @capsize/metrics
```

**Usage example:**
```js
import { createStyleObject } from '@capsize/core';
import interMetrics from '@capsize/metrics/inter';

const styles = createStyleObject({
  fontSize: 16,
  leading: 24,
  fontMetrics: interMetrics,
});
```

### [fonttools/fontbakery](https://github.com/fonttools/fontbakery)
- **Stars:** ~680 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, pushed 2026-07-12

A font quality-assurance command-line tool used by Google Fonts and Adobe Fonts to lint font binaries against hundreds of correctness checks (metadata, hinting, glyph coverage, OpenType table sanity). Best for anyone shipping their own font family and wanting CI-grade validation before release.

**Installation:**
```bash
pip install fontbakery
```

**Usage example:**
```bash
fontbakery check-googlefonts MyFont-Regular.ttf MyFont-Bold.ttf
```

### [trys/utopia-core](https://github.com/trys/utopia-core)
- **Stars:** ~136 (as of 2026-07-13)
- **License:** ISC
- **Last updated:** actively maintained, pushed 2026-07-10

The calculation engine behind [utopia.fyi](https://utopia.fyi), the well-known fluid-typography methodology. Generates `clamp()`-based CSS custom properties so font sizes (and spacing) scale smoothly between a minimum and maximum viewport rather than jumping at breakpoints.

**Installation:**
```bash
npm install utopia-core
```

**Usage example:**
```js
import { calculateTypeScale } from 'utopia-core';

const scale = calculateTypeScale({
  minWidth: 320,
  maxWidth: 1240,
  minFontSize: 16,
  maxFontSize: 19,
  minTypeScale: 1.2,
  maxTypeScale: 1.25,
});
```
```css
h1 {
  font-size: clamp(2.75rem, 2.29rem + 2.3vw, 4.21rem);
}
```

## Notes

- Google Fonts' repo (`google/fonts`) does not carry a single repo-level license because it bundles hundreds of independently-licensed font families — always check the specific font's own license file before redistributing.
- `rsms/inter`'s last push predates the other repos (2024-11-19); the project has reached a stable, low-churn maturity rather than being abandoned — releases and issue triage continue on a slower cadence.
- Prefer self-hosting (Fontsource, google-webfonts-helper, or `fonttools`-built subsets) over the Google Fonts CDN when privacy regulations (e.g. GDPR) or an offline-first requirement matter.
- Variable fonts (Inter, IBM Plex, many Google Fonts entries) let you ship one file instead of many static weights — use `fonttools varLib.instancer` to carve out static instances if your target only needs one or two weights.

## License Summary

| Repository | License |
|---|---|
| google/fonts | Mixed (mostly OFL-1.1, some Apache-2.0, per font) |
| rsms/inter | OFL-1.1 |
| majodev/google-webfonts-helper | MIT |
| fontsource/fontsource | MIT |
| fonttools/fonttools | MIT |
| seek-oss/capsize | MIT |
| fonttools/fontbakery | Apache-2.0 |
| trys/utopia-core | ISC |
