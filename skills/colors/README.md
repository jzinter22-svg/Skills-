# Color Systems Skills & Resources

Libraries and tools for generating, converting, and validating color palettes — including accessible UI color scales, data-visualization colormaps, and color-manipulation utilities. Use these when defining a design system's color tokens or choosing colors for charts and data visualizations.

## Best Repositories

### [Radix Colors](https://github.com/radix-ui/colors)
- **Stars:** ~1,634 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last month

A set of 30 accessible color scales (12 steps each) designed for building UI, with matched light/dark-mode pairs and steps pre-tuned for specific use cases (backgrounds, borders, solid fills, text).

**Why included:** The most thoughtfully engineered accessible color-scale system for app UI — each step has a documented semantic purpose (e.g. step 9 = solid backgrounds, step 11 = low-contrast text), removing guesswork from picking accessible shades.

**Installation:**
```bash
npm install @radix-ui/colors
```

**Usage example:**
```css
@import '@radix-ui/colors/blue.css';
@import '@radix-ui/colors/blue-dark.css';

.button {
  background: var(--blue-9);
  color: white;
}
```

---

### [Open Color](https://github.com/yeun/open-color)
- **Stars:** ~5,540 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained (community-stable, low-churn)

An open-source color scheme with a curated set of colors and 10 shades per hue, distributed as SCSS, Stylus, and CSS custom properties.

**Why included:** A simple, dependency-free palette that's easy to drop into any project (plain CSS variables) without a build step or component framework.

**Installation:**
```bash
npm install open-color
```

**Usage example:**
```css
@import 'open-color/open-color.css';

.alert {
  background-color: var(--oc-red-6);
  color: var(--oc-gray-0);
}
```

---

### [chroma.js](https://github.com/gka/chroma.js)
- **Stars:** ~10,572 (as of 2026-07-13)
- **License:** BSD-3-Clause (per repository `LICENSE` file; GitHub's detector shows "Other")
- **Last updated:** actively maintained, commits within the last two months

A JavaScript library for color conversion and manipulation across many color spaces (RGB, HSL, LAB, LCH), plus scale/interpolation helpers for building gradients and choropleth-style color ramps.

**Why included:** The most complete general-purpose color-manipulation toolkit in JS — widely used for programmatically deriving tints/shades or building custom sequential/diverging scales.

**Installation:**
```bash
npm install chroma-js
```

**Usage example:**
```js
import chroma from 'chroma-js'

const scale = chroma.scale(['yellow', 'red', 'black']).mode('lch')
console.log(scale(0.5).hex()) // interpolated midpoint color
```

---

### [d3-scale-chromatic](https://github.com/d3/d3-scale-chromatic)
- **Stars:** ~818 (as of 2026-07-13)
- **License:** ISC (per repository `LICENSE` file; GitHub's detector shows "Other")
- **Last updated:** maintained (stable, low-churn core D3 module)

Sequential, diverging, and categorical color schemes for data visualization, including implementations of ColorBrewer schemes and perceptually uniform maps like Viridis, Inferno, and Magma.

**Why included:** The standard scientific/data-viz colormap library for the JS ecosystem — directly usable with D3 or standalone for charting and heatmaps.

**Installation:**
```bash
npm install d3-scale-chromatic
```

**Usage example:**
```js
import { interpolateViridis, schemeCategory10 } from 'd3-scale-chromatic'

const color = interpolateViridis(0.5) // color at midpoint of the Viridis scale
console.log(schemeCategory10[0]) // first categorical color
```

---

### [ColorBrewer](https://github.com/axismaps/colorbrewer)
- **Stars:** ~1,091 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, commits within the last five months

The source data and web tool behind colorbrewer2.org — sequential, diverging, and qualitative color schemes designed specifically for maps and data visualization, with colorblind-safe and print-friendly variants flagged.

**Why included:** The original, most widely cited reference for choosing statistically/perceptually sound map and chart color schemes; many other libraries (d3-scale-chromatic, matplotlib) ship ColorBrewer schemes as a built-in option.

**Installation:**
```bash
git clone https://github.com/axismaps/colorbrewer.git
```

**Usage example:**
```js
// colorbrewer.json ships the raw scheme data
const colorbrewer = require('./colorbrewer.json')
console.log(colorbrewer.YlOrRd[7]) // 7-class Yellow-Orange-Red sequential scheme
```

---

### [viridis (R package)](https://github.com/sjmgarnier/viridis)
- **Stars:** ~310 (as of 2026-07-13)
- **License:** MIT (per package `DESCRIPTION`; GitHub's detector shows "Other")
- **Last updated:** maintained (stable, low-churn)

R implementation of the viridis, magma, plasma, and inferno colormaps — perceptually uniform and colorblind-friendly sequential palettes originally created for matplotlib.

**Why included:** Viridis-family colormaps are the standard choice for scientific visualization because they remain perceptually uniform in grayscale and for the most common forms of color blindness; this package brings them to R (they also ship built-in to Python's matplotlib).

**Installation:**
```r
install.packages("viridis")
```

**Usage example:**
```r
library(viridis)
library(ggplot2)

ggplot(faithfuld, aes(waiting, eruptions, fill = density)) +
  geom_raster() +
  scale_fill_viridis(option = "magma")
```

---

### [Color.js](https://github.com/color-js/color.js)
- **Stars:** ~2,260 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

A color conversion and manipulation library written by the editors of the CSS Color specifications, supporting modern color spaces (OKLCH, OKLab, Display-P3, Rec2020) alongside sRGB/HSL.

**Why included:** Written directly by CSS spec authors, making it the most spec-accurate library for working with cutting-edge CSS color spaces like OKLCH — useful for perceptually uniform palette generation and accurate WCAG contrast calculations.

**Installation:**
```bash
npm install colorjs.io
```

**Usage example:**
```js
import Color from "colorjs.io"

const blue = new Color("blue")
const contrast = blue.contrast("white", "WCAG21")
console.log(contrast) // WCAG 2.1 contrast ratio
```

---

### [Poline](https://github.com/meodai/poline)
- **Stars:** ~1,243 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

A small palette-generator library that interpolates colors in HSL space along a path defined in cartesian coordinates, producing smooth, aesthetically pleasing multi-stop gradients/palettes.

**Why included:** A creative-coding-friendly alternative to standard linear interpolation, good for generative art, gradient palettes, and dark-mode-aware palette variations.

**Installation:**
```bash
npm install poline
```

**Usage example:**
```js
import { Poline } from 'poline'

const poline = new Poline({ numPoints: 5 })
console.log(poline.colors) // array of [h, s, l] colors along the generated path
```

## Notes
- Several long-lived, spec-authored libraries (chroma.js, d3-scale-chromatic, viridis) show "Other" instead of a standard SPDX tag on GitHub's automatic detector; their actual `LICENSE` files use well-known permissive terms (BSD-3-Clause, ISC, MIT respectively) — verify the file directly before redistribution in a commercial product.
- For accessible UI color scales specifically, prefer Radix Colors or Open Color; for scientific/data-visualization colormaps, prefer d3-scale-chromatic, ColorBrewer, or viridis.
- Color.js is the best choice when you need precise WCAG/APCA contrast math alongside color conversion, since it's maintained by the people who write the CSS Color specs.

## License Summary
| Repository | License |
|---|---|
| [Radix Colors](https://github.com/radix-ui/colors) | MIT |
| [Open Color](https://github.com/yeun/open-color) | MIT |
| [chroma.js](https://github.com/gka/chroma.js) | BSD-3-Clause (verify LICENSE; GitHub shows "Other") |
| [d3-scale-chromatic](https://github.com/d3/d3-scale-chromatic) | ISC (verify LICENSE; GitHub shows "Other") |
| [ColorBrewer](https://github.com/axismaps/colorbrewer) | Apache-2.0 |
| [viridis (R)](https://github.com/sjmgarnier/viridis) | MIT (verify LICENSE; GitHub shows "Other") |
| [Color.js](https://github.com/color-js/color.js) | MIT |
| [Poline](https://github.com/meodai/poline) | MIT |
