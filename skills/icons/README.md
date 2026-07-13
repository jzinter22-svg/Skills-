# Icons Skills & Resources

SVG/font icon sets for UI development — toolbars, navigation, buttons, and educational-interface iconography. Use these when a task calls for consistent, scalable icons rather than raster images or custom illustrations.

## Best Repositories

### [Font Awesome](https://github.com/FortAwesome/Font-Awesome)
- **Stars:** ~76,740 (as of 2026-07-13)
- **License:** Mixed — Icons: CC BY 4.0; Fonts: SIL OFL 1.1; Code: MIT (Font Awesome Free tier)
- **Last updated:** actively maintained, last push 2026-06-25

The original and most widely deployed icon toolkit on the web, offering thousands of icons as SVG, icon fonts, and CSS across solid/regular/brands styles.

Best for general-purpose UI iconography with the widest ecosystem support (frameworks, CMS plugins, design tools) — note the icon/font assets require attribution under their respective licenses even though the code is MIT.

**Installation:**
```bash
npm install @fortawesome/fontawesome-free
```
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free/css/all.min.css">
```

**Usage example:**
```html
<i class="fa-solid fa-star"></i>
```

### [Material Design Icons / Material Symbols](https://github.com/google/material-design-icons)
- **Stars:** ~53,600 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, last push recent (2026)

Google's official icon library, now centered on "Material Symbols" — a single variable font with adjustable optical size, weight, grade, and fill axes, alongside the older static Material Icons set (outlined/filled/rounded/sharp/two-tone).

Best for Material Design-styled interfaces and Android/iOS/web apps needing a permissively-licensed (Apache-2.0), Google-maintained icon system with variable styling.

**Installation:**
```bash
npm install material-icons
```
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" />
```

**Usage example:**
```html
<span class="material-symbols-outlined">home</span>
```

### [Heroicons](https://github.com/tailwindlabs/heroicons)
- **Stars:** ~23,670 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026 (from Tailwind Labs)

A focused, hand-crafted set of free MIT-licensed SVG icons in outline, solid, and mini variants, designed by the Tailwind CSS team to pair with Tailwind-based UIs.

Best for clean, minimal interface icons in React/Vue apps, especially those already using Tailwind CSS — official React and Vue packages are provided.

**Installation:**
```bash
npm install @heroicons/react
```

**Usage example:**
```jsx
import { BeakerIcon } from '@heroicons/react/24/solid';

function MyComponent() {
  return <BeakerIcon className="h-6 w-6 text-blue-500" />;
}
```

### [Lucide](https://github.com/lucide-icons/lucide)
- **Stars:** ~23,412 (as of 2026-07-13)
- **License:** ISC (Lucide additions) + MIT (icons derived from the original Feather set)
- **Last updated:** actively maintained, last push 2026-07-11

Lucide is a community-driven fork and continuation of Feather Icons, adding hundreds of new icons and active maintenance (unlike the now-stagnant original), with first-class React, Vue, Svelte, and Angular packages.

Best for modern app UIs needing a large, consistently-styled, actively-maintained icon set as a drop-in Feather replacement.

**Installation:**
```bash
npm install lucide-react
```

**Usage example:**
```jsx
import { Camera } from 'lucide-react';

function App() {
  return <Camera color="red" size={32} />;
}
```

### [Tabler Icons](https://github.com/tabler/tabler-icons)
- **Stars:** ~21,124 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

A large (6,000+) set of free MIT-licensed SVG icons drawn on a consistent 24x24 grid with 2px stroke, available in outline and filled variants with packages for React, Vue, Angular, Svelte, and a webfont.

Best for projects wanting a very large, stylistically consistent icon library with strong multi-framework component support.

**Installation:**
```bash
npm install @tabler/icons-react
```

**Usage example:**
```jsx
import { IconHeart } from '@tabler/icons-react';

function App() {
  return <IconHeart size={32} color="red" />;
}
```

### [Ionicons](https://github.com/ionic-team/ionicons)
- **Stars:** ~18,108 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026

A free, open-source icon set of 1,300+ icons built by the Ionic team, offered in both Material Design and iOS styles and packaged as web components (works framework-agnostically).

Best for cross-platform mobile/web apps that want a single icon set that adapts its look to iOS vs. Material conventions.

**Installation:**
```bash
npm install ionicons
```

**Usage example:**
```html
<script type="module" src="https://unpkg.com/ionicons@7/dist/ionicons/ionicons.esm.js"></script>
<ion-icon name="heart"></ion-icon>
```

### [Feather Icons](https://github.com/feathericons/feather)
- **Stars:** ~25,964 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** last release v4.29.2 (May 2024) — maintenance has slowed; see Lucide below for an actively-maintained fork

A collection of simple, consistent, open-source SVG icons on a 24x24 grid, focused on minimalism and clarity, with client-side JS, Node.js, and Figma integrations.

Best for minimalist interface icons in legacy projects already using Feather; for new projects, prefer Lucide (the actively-maintained continuation of this same icon language).

**Installation:**
```bash
npm install feather-icons
```

**Usage example:**
```html
<i data-feather="camera"></i>
<script src="https://unpkg.com/feather-icons"></script>
<script>feather.replace()</script>
```

### [Phosphor Icons](https://github.com/phosphor-icons/homepage)
- **Stars:** ~7,007 (as of 2026-07-13, homepage repo; the icon family spans several repos including [core](https://github.com/phosphor-icons/core) and [react](https://github.com/phosphor-icons/react))
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-11

Phosphor is a flexible icon family offering six weights (Thin, Light, Regular, Bold, Fill, Duotone) per icon, with packages for React, Vue, and plain web/CSS use.

Best for interfaces that need adjustable icon "weight" for visual hierarchy (e.g., emphasizing active/selected states) beyond simple outline-vs-filled toggles.

**Installation:**
```bash
npm install @phosphor-icons/react
```

**Usage example:**
```jsx
import { Smiley, Heart } from "@phosphor-icons/react";

function App() {
  return (
    <>
      <Smiley />
      <Heart size={32} color="hotpink" weight="fill" />
    </>
  );
}
```

## Notes

- **Font Awesome Free** is not a single license: code is MIT, but the icon SVGs are CC BY 4.0 and the icon fonts are SIL OFL 1.1 — both require attribution, which is embedded in downloaded files.
- **Feather Icons** has not had a new release since May 2024; **Lucide** is a drop-in, actively-maintained continuation with an expanded icon set and is generally the better choice for new projects.
- **Lucide's own additions are ISC-licensed**, while icons carried over from the original Feather project remain MIT — both are permissive.
- Star counts for split-package projects (Phosphor, Tabler, Heroicons) reflect the primary/homepage repository; framework-specific packages (e.g. `@phosphor-icons/react`) live in separate, smaller repos.

## License Summary

| Repository | License |
|---|---|
| [Font Awesome](https://github.com/FortAwesome/Font-Awesome) | Mixed: CC BY 4.0 (icons) / SIL OFL 1.1 (fonts) / MIT (code) |
| [Material Design Icons](https://github.com/google/material-design-icons) | Apache-2.0 |
| [Heroicons](https://github.com/tailwindlabs/heroicons) | MIT |
| [Lucide](https://github.com/lucide-icons/lucide) | ISC + MIT |
| [Tabler Icons](https://github.com/tabler/tabler-icons) | MIT |
| [Ionicons](https://github.com/ionic-team/ionicons) | MIT |
| [Feather Icons](https://github.com/feathericons/feather) | MIT |
| [Phosphor Icons](https://github.com/phosphor-icons/homepage) | MIT |
