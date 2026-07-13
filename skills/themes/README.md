# Themes Skills & Resources

Systems and libraries for implementing visual themes — light/dark mode switching, Material Design and Fluent Design implementations, and stylistic treatments like glassmorphism, neumorphism, and retro UI skins. Use these when defining or switching the overall look-and-feel of an app rather than individual components.

## Best Repositories

### [Microsoft Fluent UI](https://github.com/microsoft/fluentui)
- **Stars:** ~20,145 (as of 2026-07-13)
- **License:** MIT (per repository `LICENSE` file; GitHub's automatic detector shows "Other" due to a custom license header — verify before reuse)
- **Last updated:** actively maintained, commits within the last day

Microsoft's official implementation of the Fluent Design System: React components, web components, and design tokens used across Microsoft 365 and Windows-style apps.

**Why included:** The authoritative Fluent Design implementation, including its theming engine (light/dark/high-contrast themes) and the "Fluent" acrylic/depth visual language.

**Installation:**
```bash
npm install @fluentui/react-components
```

**Usage example:**
```tsx
import { FluentProvider, webLightTheme, Button } from '@fluentui/react-components'

export default function App() {
  return (
    <FluentProvider theme={webLightTheme}>
      <Button appearance="primary">Hello Fluent</Button>
    </FluentProvider>
  )
}
```

---

### [Material Color Utilities](https://github.com/material-foundation/material-color-utilities)
- **Stars:** ~2,211 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, commits within the last three months

Google's official color libraries for Material You (Material Design 3): generates full light/dark tonal color schemes from a single seed color, including contrast-aware tone adjustments.

**Why included:** The reference implementation behind Android's dynamic "Material You" theming — best tool for programmatically generating a complete, accessible Material 3 theme from one brand color.

**Installation:**
```bash
npm install @material/material-color-utilities
```

**Usage example:**
```ts
import { argbFromHex, themeFromSourceColor } from '@material/material-color-utilities'

const theme = themeFromSourceColor(argbFromHex('#6750A4'))
console.log(theme.schemes.light.primary, theme.schemes.dark.primary)
```

---

### [next-themes](https://github.com/pacocoursey/next-themes)
- **Stars:** ~6,310 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last five months

A tiny, dependency-free theme-switching library for Next.js/React that handles system-preference detection, persistence, and no-flash-of-wrong-theme on load.

**Why included:** The de facto standard for adding light/dark/system theme toggling to a React app correctly (avoiding the common flash-of-unstyled-theme bug).

**Installation:**
```bash
npm install next-themes
```

**Usage example:**
```tsx
import { ThemeProvider, useTheme } from 'next-themes'

function ThemeToggle() {
  const { theme, setTheme } = useTheme()
  return (
    <button onClick={() => setTheme(theme === 'dark' ? 'light' : 'dark')}>
      Toggle theme
    </button>
  )
}

export default function App({ children }) {
  return <ThemeProvider attribute="class">{children}</ThemeProvider>
}
```

---

### [Neumorphism.io generator](https://github.com/adamgiebl/neumorphism)
- **Stars:** ~6,120 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, commits within the last day

An interactive tool (neumorphism.io) that generates CSS box-shadow pairs for the soft-UI/neumorphic visual style, with adjustable distance, blur, and intensity.

**Why included:** The most widely referenced neumorphism CSS generator — quickly produces the two-shadow soft-UI look without manually tuning shadow values.

**Installation:**
```bash
git clone https://github.com/adamgiebl/neumorphism.git
cd neumorphism && npm install && npm start
```

**Usage example:**
```css
/* Generated neumorphic style for a light background (#e0e0e0) */
.neumorphic-card {
  background: #e0e0e0;
  border-radius: 20px;
  box-shadow: 20px 20px 60px #bebebe,
             -20px -20px 60px #ffffff;
}
```

---

### [css.glass](https://github.com/miketromba/css.glass)
- **Stars:** ~441 (as of 2026-07-13)
- **License:** No `LICENSE` file detected in the repository at time of check — treat as "all rights reserved" by default and confirm terms with the author before reuse in a commercial project.
- **Last updated:** actively maintained, commits within the last day

An interactive glassmorphism CSS generator that produces `backdrop-filter`/`background` blur styling for frosted-glass card effects.

**Why included:** A focused, easy-to-use generator for the glassmorphism look (blurred translucent panels) that's widely linked from CSS design roundups.

**Installation:**
```
N/A — use the hosted generator at css.glass, or clone the repo to self-host
```

**Usage example:**
```css
/* Typical glassmorphism output */
.glass-panel {
  background: rgba(255, 255, 255, 0.2);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5.6px);
  -webkit-backdrop-filter: blur(5.6px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}
```

---

### [98.css](https://github.com/jdan/98.css)
- **Stars:** ~11,148 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last two years

A CSS design system that faithfully recreates the Windows 98 UI aesetic — buttons, title bars, sunken panels — for retro/nostalgic themed interfaces.

**Why included:** The standout example of a complete, well-documented "themed" UI system beyond flat modern design; useful for playful/educational or portfolio projects wanting a distinct retro theme.

**Installation:**
```bash
npm install 98.css
```

**Usage example:**
```html
<link rel="stylesheet" href="https://unpkg.com/98.css">
<button>Click me</button>
<div class="window">
  <div class="title-bar">
    <div class="title-bar-text">My First Program</div>
  </div>
  <div class="window-body">
    <p>Hello, world!</p>
  </div>
</div>
```

## Notes
- Some corporate-owned repos (Microsoft Fluent UI) show "Other" instead of a standard SPDX license tag on GitHub even though their `LICENSE` file is MIT — always double check the actual `LICENSE` file text, not just the GitHub metadata badge.
- `css.glass` had no detectable license file at time of review; verify reuse terms directly with the maintainer before shipping it in a commercial theme.
- For Apple-style ("Liquid Glass"/frosted) aesthetics, css.glass and general `backdrop-filter` glassmorphism techniques are the closest open-source equivalents; there is no official open-source Apple design-system repository to include here.

## License Summary
| Repository | License |
|---|---|
| [Microsoft Fluent UI](https://github.com/microsoft/fluentui) | MIT (verify LICENSE file; GitHub shows "Other") |
| [Material Color Utilities](https://github.com/material-foundation/material-color-utilities) | Apache-2.0 |
| [next-themes](https://github.com/pacocoursey/next-themes) | MIT |
| [Neumorphism.io generator](https://github.com/adamgiebl/neumorphism) | BSD-3-Clause |
| [css.glass](https://github.com/miketromba/css.glass) | None detected — verify with author |
| [98.css](https://github.com/jdan/98.css) | MIT |
