# Skills — A Curated Claude Skills & Developer Resource Repository

A categorized, verified index of mature, actively-maintained, well-documented open-source repositories, fonts, templates, and Claude/MCP resources for building interactive educational software, developer tools, and polished UIs.

Every entry was verified live against GitHub (stars, license, last-updated date) rather than guessed. Star counts and dates reflect **2026-07-13** and will drift — re-check the source repo before citing numbers as current. Non-permissive or ambiguous licenses (copyleft, non-commercial, "no LICENSE file") are called out explicitly inline and in each category's Notes/License Summary section — always verify a license yourself before shipping it in a commercial product.

## How this repo is organized

```
skills/
  mathematics/    physics/       chemistry/      graphics/
  charts/         icons/         frontend/       backend/
  ui/             ux/            themes/         colors/
  typography/     arabic/        documentation/  productivity/
```

Each folder has its own `README.md` with: category description, per-repo stars/license/last-updated, why it's included, install command, and a usage snippet — plus a License Summary table at the end.

## Quick navigation — when to use each category

| Category | Folder | Use it when you need to… |
|---|---|---|
| Mathematics | [`skills/mathematics`](skills/mathematics/README.md) | Typeset LaTeX/math notation, build calculators, plot functions, do symbolic algebra, or animate math concepts |
| Physics | [`skills/physics`](skills/physics/README.md) | Simulate rigid-body mechanics, build 3D scenes, or plot experiment/sensor data |
| Chemistry | [`skills/chemistry`](skills/chemistry/README.md) | Parse/draw molecules, convert chemical file formats, or render a periodic table |
| Interactive Educational Graphics | [`skills/graphics`](skills/graphics/README.md) | Build animated diagrams, 3D scenes, flowcharts, or programmatic illustrations |
| Data Visualization (Charts) | [`skills/charts`](skills/charts/README.md) | Render bar/line/pie/statistical charts and dashboards from tabular data |
| Icons | [`skills/icons`](skills/icons/README.md) | Add consistent, scalable SVG/font iconography to a UI |
| Frontend Skills | [`skills/frontend`](skills/frontend/README.md) | Scaffold a frontend project, pick a framework/style guide, or audit accessibility/PWA behavior |
| Backend Skills | [`skills/backend`](skills/backend/README.md) | Build a REST/GraphQL API, choose an ORM/auth/upload/websocket library |
| UI | [`skills/ui`](skills/ui/README.md) | Assemble a dashboard or SaaS UI from production-ready component libraries |
| UX | [`skills/ux`](skills/ux/README.md) | Decide *how* a component should behave — accessibility patterns, usability research, UX writing |
| Themes | [`skills/themes`](skills/themes/README.md) | Implement light/dark mode, Material/Fluent theming, or glassmorphism/neumorphism/retro styles |
| Color Systems | [`skills/colors`](skills/colors/README.md) | Define accessible UI color tokens or scientific/data-viz colormaps |
| Typography | [`skills/typography`](skills/typography/README.md) | Pick/self-host web fonts, build a fluid type scale, or fix cross-browser font-metric bugs |
| Arabic (Typography & RTL) | [`skills/arabic`](skills/arabic/README.md) | Build an Arabic or bilingual Arabic+Latin UI, convert LTR CSS to RTL, or process Arabic text |
| Documentation Skills | [`skills/documentation`](skills/documentation/README.md) | Write a README, stand up a docs site, record an ADR, or set a docstring style |
| Claude Code Productivity | [`skills/productivity`](skills/productivity/README.md) | Extend Claude Code with Skills/MCP servers, or adopt proven hooks/commands/prompt libraries |

## Full resource index

### Mathematics
| Resource | License | One-liner |
|---|---|---|
| [KaTeX](https://github.com/KaTeX/KaTeX) | MIT | Fast synchronous LaTeX-to-HTML math typesetting |
| [MathJax](https://github.com/mathjax/MathJax) | Apache-2.0 | Accessible math display engine (LaTeX/MathML/AsciiMath) |
| [mathjs](https://github.com/josdejong/mathjs) | Apache-2.0 | Extensive JS math library — matrices, units, expression parser |
| [JSXGraph](https://github.com/jsxgraph/jsxgraph) | LGPL/MIT (dual) | Interactive geometry, plotting, and charting |
| [SymPy](https://github.com/sympy/sympy) | BSD-3-Clause | Python computer algebra system (symbolic calculus/algebra) |
| [Manim (Community)](https://github.com/ManimCommunity/manim) | MIT | Programmatic mathematical animation engine |
| [function-plot](https://github.com/mauriciopoppe/function-plot) | MIT | Lightweight D3-based 2D function plotter |
| [D3.js](https://github.com/d3/d3) | ISC | Low-level data-binding/SVG library underlying custom math diagrams |

### Physics
| Resource | License | One-liner |
|---|---|---|
| [Matter.js](https://github.com/liabru/matter-js) | MIT | 2D rigid-body physics engine for canvas |
| [three.js](https://github.com/mrdoob/three.js) | MIT | 3D WebGL/WebGPU scene library |
| [cannon-es](https://github.com/pmndrs/cannon-es) | MIT | Maintained 3D physics engine, pairs with three.js |
| [p5.js](https://github.com/processing/p5.js) | LGPL-2.1 | Beginner-friendly creative-coding canvas library |
| [PhET / scenery](https://github.com/phetsims/scenery) | MIT (libs) / GPL-3.0 (sims) | Gold-standard interactive physics/chemistry/math sims |
| [Plotly.js](https://github.com/plotly/plotly.js) | MIT | WebGL-accelerated scientific charting |
| [Sandboxels](https://github.com/R74nCom/sandboxels) | ⚠ None/NOASSERTION | Falling-sand physics/chemistry sandbox (reference only) |

### Chemistry
| Resource | License | One-liner |
|---|---|---|
| [RDKit](https://github.com/rdkit/rdkit) | BSD-3-Clause | The standard cheminformatics toolkit (Python/C++) |
| [RDKit.js](https://github.com/rdkit/rdkit-js) | BSD-3-Clause | WebAssembly RDKit for in-browser molecule parsing |
| [3Dmol.js](https://github.com/3dmol/3Dmol.js) | BSD-3-Clause | WebGL 3D protein/molecule viewer |
| [Kekule.js](https://github.com/partridgejiang/Kekule.js) | MIT | In-browser 2D/3D chemical structure editor |
| [Open Babel](https://github.com/openbabel/openbabel) | ⚠ GPL-2.0 | Universal chemical file-format converter |
| [PyMOL (open-source)](https://github.com/schrodinger/pymol-open-source) | ⚠ Custom "Python License" | Publication-quality molecular rendering |
| [Avogadro Libraries](https://github.com/OpenChemistry/avogadrolibs) | BSD-3-Clause | Desktop-grade molecular editing/analysis engine |
| [periodic-table](https://github.com/andrejewski/periodic-table) | ISC | JSON dataset of periodic-table elements |

### Interactive Educational Graphics
| Resource | License | One-liner |
|---|---|---|
| [D3.js](https://github.com/d3/d3) | ISC | Foundational data-driven SVG/Canvas/HTML library |
| [Three.js](https://github.com/mrdoob/three.js) | MIT | Cross-browser 3D scene-graph library |
| [Mermaid](https://github.com/mermaid-js/mermaid) | MIT | Text-to-diagram (flowcharts, sequence, Gantt) rendering |
| [Manim (Community)](https://github.com/ManimCommunity/manim) | MIT | Programmatic math/science explainer animation |
| [p5.js](https://github.com/processing/p5.js) | LGPL-2.1 | Beginner-friendly creative-coding canvas |
| [GSAP](https://github.com/greensock/GSAP) | ⚠ Custom (free, non-OSI) | High-performance DOM/SVG/canvas animation engine |
| [Konva.js](https://github.com/konvajs/konva) | MIT | Interactive canvas scene graph (drag/drop, hit detection) |

### Data Visualization (Charts)
| Resource | License | One-liner |
|---|---|---|
| [Chart.js](https://github.com/chartjs/Chart.js) | MIT | Simple, well-documented canvas charting |
| [Apache ECharts](https://github.com/apache/echarts) | Apache-2.0 | GPU-accelerated charting with a huge chart-type catalog |
| [Plotly.js](https://github.com/plotly/plotly.js) | MIT | Declarative scientific/statistical charting |
| [Recharts](https://github.com/recharts/recharts) | MIT | Composable React chart components (D3-based) |
| [visx](https://github.com/airbnb/visx) | MIT | Low-level D3 visualization primitives as React components |
| [ApexCharts](https://github.com/apexcharts/apexcharts.js) | ⚠ Dual (revenue-based) | Polished, animated SVG charting |
| [Observable Plot](https://github.com/observablehq/plot) | ISC | Grammar-of-graphics exploratory charting |

### Icons
| Resource | License | One-liner |
|---|---|---|
| [Font Awesome](https://github.com/FortAwesome/Font-Awesome) | Mixed: CC BY 4.0 / OFL-1.1 / MIT | The original, most widely deployed icon toolkit |
| [Material Design Icons / Symbols](https://github.com/google/material-design-icons) | Apache-2.0 | Google's official variable-font icon system |
| [Heroicons](https://github.com/tailwindlabs/heroicons) | MIT | Hand-crafted icons from the Tailwind CSS team |
| [Lucide](https://github.com/lucide-icons/lucide) | ISC + MIT | Actively-maintained community fork of Feather Icons |
| [Tabler Icons](https://github.com/tabler/tabler-icons) | MIT | 6,000+ consistent 24×24 SVG icons |
| [Ionicons](https://github.com/ionic-team/ionicons) | MIT | Framework-agnostic web-component icon set (iOS/Material) |
| [Feather Icons](https://github.com/feathericons/feather) | MIT | Minimalist icon set (stale — see Lucide) |
| [Phosphor Icons](https://github.com/phosphor-icons/homepage) | MIT | Six-weight flexible icon family |

### Frontend Skills
| Resource | License | One-liner |
|---|---|---|
| [Vite](https://github.com/vitejs/vite) | MIT | Instant-startup frontend build tool/dev server |
| [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss) | MIT | Utility-first CSS framework |
| [Svelte](https://github.com/sveltejs/svelte) | MIT | Compiler-based UI framework, no virtual DOM |
| [Vue.js (core)](https://github.com/vuejs/core) | MIT | Progressive JS framework with Composition API |
| [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) | MIT | Industry-standard JS/React lint/style conventions |
| [axe-core](https://github.com/dequelabs/axe-core) | MPL-2.0 | Automated accessibility (WCAG) testing engine |
| [Workbox](https://github.com/GoogleChrome/workbox) | MIT | PWA service-worker/caching toolkit |
| [React Starter Kit](https://github.com/kriasoft/react-starter-kit) | MIT | Production React monorepo boilerplate |
| [Superdesign Skill](https://github.com/superdesigndev/superdesign-skill) | MIT | Claude Code skill giving agents real UI design judgment |

### Backend Skills
| Resource | License | One-liner |
|---|---|---|
| [Express](https://github.com/expressjs/express) | MIT | The default minimalist Node.js web framework |
| [Fastify](https://github.com/fastify/fastify) | MIT | Fast Node.js framework with schema validation |
| [Django](https://github.com/django/django) | BSD-3-Clause | Batteries-included Python web framework + ORM |
| [Flask](https://github.com/pallets/flask) | BSD-3-Clause | Lightweight Python micro-framework |
| [Prisma](https://github.com/prisma/prisma) | Apache-2.0 | Type-safe ORM for Postgres/MySQL/SQLite/MongoDB |
| [Auth.js (next-auth)](https://github.com/nextauthjs/next-auth) | ISC | Drop-in authentication for JS/TS full-stack apps |
| [Socket.IO](https://github.com/socketio/socket.io) | MIT | Real-time bidirectional WebSocket communication |
| [Multer](https://github.com/expressjs/multer) | MIT | Multipart/form-data file-upload middleware |
| [Apollo Server](https://github.com/apollographql/apollo-server) | MIT | Production-ready GraphQL server |
| [Convex Skills](https://github.com/waynesutton/convexskills) | Apache-2.0 | Claude/AI-agent skill package for Convex backend patterns |

### UI
| Resource | License | One-liner |
|---|---|---|
| [shadcn/ui](https://github.com/shadcn-ui/ui) | MIT | Copy-paste, ownable React components on Radix + Tailwind |
| [Radix Primitives](https://github.com/radix-ui/primitives) | MIT | Unstyled, fully accessible React UI primitives |
| [Material UI (MUI)](https://github.com/mui/material-ui) | MIT | Comprehensive Material Design React component library |
| [Ant Design](https://github.com/ant-design/ant-design) | MIT | Enterprise admin-dashboard component library |
| [Chakra UI](https://github.com/chakra-ui/chakra-ui) | MIT | Accessible component system with style-prop API |
| [Mantine](https://github.com/mantinedev/mantine) | MIT | 100+ components/50+ hooks, built-in dark mode |
| [daisyUI](https://github.com/saadeghi/daisyui) | MIT | Semantic component classes as a Tailwind plugin |

### UX
| Resource | License | One-liner |
|---|---|---|
| [WAI-ARIA Authoring Practices Guide](https://github.com/w3c/aria-practices) | W3C Document License | Canonical accessible interaction-pattern reference |
| [Adobe React Spectrum / React Aria](https://github.com/adobe/react-spectrum) | Apache-2.0 | Rigorously tested accessible React interaction hooks |
| [awesome-a11y](https://github.com/brunopulis/awesome-a11y) | CC0-1.0 | Curated accessibility tools/articles list |
| [U.S. Web Design System](https://github.com/uswds/uswds) | Public domain | Accessibility-first US gov design system |
| [GOV.UK Design System](https://github.com/alphagov/govuk-design-system) | MIT | UX patterns with research-backed rationale |
| [awesome-ux](https://github.com/batoreh/awesome-ux) | CC0-1.0 | Curated UX research/process resource list |

### Themes
| Resource | License | One-liner |
|---|---|---|
| [Microsoft Fluent UI](https://github.com/microsoft/fluentui) | MIT | Official Fluent Design System components + theming |
| [Material Color Utilities](https://github.com/material-foundation/material-color-utilities) | Apache-2.0 | Generates full Material You light/dark tonal schemes |
| [next-themes](https://github.com/pacocoursey/next-themes) | MIT | Flash-free light/dark/system theme switching for React |
| [Neumorphism.io generator](https://github.com/adamgiebl/neumorphism) | BSD-3-Clause | Soft-UI/neumorphic CSS shadow generator |
| [css.glass](https://github.com/miketromba/css.glass) | ⚠ None detected | Glassmorphism `backdrop-filter` CSS generator |
| [98.css](https://github.com/jdan/98.css) | MIT | Windows 98 retro UI aesthetic CSS system |

### Color Systems
| Resource | License | One-liner |
|---|---|---|
| [Radix Colors](https://github.com/radix-ui/colors) | MIT | 30 accessible 12-step light/dark UI color scales |
| [Open Color](https://github.com/yeun/open-color) | MIT | Simple curated palette as CSS variables |
| [chroma.js](https://github.com/gka/chroma.js) | BSD-3-Clause | Color conversion/manipulation across color spaces |
| [d3-scale-chromatic](https://github.com/d3/d3-scale-chromatic) | ISC | Sequential/diverging/categorical data-viz color schemes |
| [ColorBrewer](https://github.com/axismaps/colorbrewer) | Apache-2.0 | Original perceptually/statistically sound map color schemes |
| [viridis (R)](https://github.com/sjmgarnier/viridis) | MIT | Colorblind-safe perceptually uniform colormaps |
| [Color.js](https://github.com/color-js/color.js) | MIT | Spec-accurate color conversion (OKLCH, WCAG contrast) |
| [Poline](https://github.com/meodai/poline) | MIT | Smooth HSL-space palette/gradient generator |

### Typography
| Resource | License | One-liner |
|---|---|---|
| [google/fonts](https://github.com/google/fonts) | Mixed (mostly OFL-1.1) | Canonical source repo for every Google Fonts family |
| [rsms/inter](https://github.com/rsms/inter) | OFL-1.1 | Widely deployed variable UI sans-serif |
| [google-webfonts-helper](https://github.com/majodev/google-webfonts-helper) | MIT | Self-host Google Fonts with generated `@font-face` CSS |
| [fontsource](https://github.com/fontsource/fontsource) | MIT (tooling) | Self-hosted fonts as importable NPM packages |
| [fonttools](https://github.com/fonttools/fonttools) | MIT | Foundational Python font-manipulation library |
| [Capsize](https://github.com/seek-oss/capsize) | MIT | Font-metric-driven consistent line-height/spacing |
| [Fontbakery](https://github.com/fonttools/fontbakery) | Apache-2.0 | Font QA/linting CLI used by Google/Adobe Fonts |
| [utopia-core](https://github.com/trys/utopia-core) | ISC | Fluid `clamp()`-based responsive type-scale engine |

### Arabic (Typography & RTL)
| Resource | License | One-liner |
|---|---|---|
| Cairo (`Gue3bara/Cairo`) | OFL-1.1 | Geometric Kufi-style Arabic + Latin typeface |
| Tajawal (`googlefonts/tajawal`) | OFL-1.1 | Modern geometric Arabic sans-serif |
| IBM Plex Sans Arabic (`IBM/plex`) | OFL-1.1 | IBM's corporate type system, Arabic cut |
| Noto Sans/Naskh Arabic (`notofonts/arabic`) | OFL-1.1 | Universal-coverage UI and classical Naskh Arabic |
| Amiri (`aliftype/amiri`) | OFL-1.1 | Classical Naskh revival, best for long-form text |
| Readex Pro (`ThomasJockin/readexpro`) | OFL-1.1 | Reading-proficiency-tested variable Arabic font |
| Alexandria (`Gue3bara/Alexandria`) | OFL-1.1 | Arabic companion to Montserrat |
| Changa (`googlefonts/changa-vf`) | OFL-1.1 | Bold display/headline Arabic sans-serif |
| [rtlcss](https://github.com/MohammadYounes/rtlcss) | MIT | Mechanical LTR→RTL CSS conversion |
| [PyArabic](https://github.com/linuxscout/pyarabic) | ⚠ GPL-3.0 | Arabic text normalization/tashkeel processing |
| [CAMeL Tools](https://github.com/CAMeL-Lab/camel_tools) | MIT | Full Arabic NLP suite (morphology, NER, dialect ID) |

### Documentation Skills
| Resource | License | One-liner |
|---|---|---|
| [Best-README-Template](https://github.com/othneildrew/Best-README-Template) | Unlicense | The most popular fill-in-the-blank README template |
| [standard-readme](https://github.com/RichardLitt/standard-readme) | MIT | README structure specification + generator |
| [Docusaurus](https://github.com/facebook/docusaurus) | MIT | React-based versioned documentation site generator |
| [MkDocs Material](https://github.com/squidfunk/mkdocs-material) | MIT | Material Design theme for Markdown-only docs sites |
| [VitePress](https://github.com/vuejs/vitepress) | MIT | Vite/Vue-powered fast documentation site generator |
| [architecture-decision-record](https://github.com/joelparkerhenderson/architecture-decision-record) | ⚠ CC BY-NC-SA 4.0 | Large collection of ADR templates |
| [google/styleguide](https://github.com/google/styleguide) | ⚠ Unclear, verify per guide | Google's code style + docstring conventions |
| [beautiful-docs](https://github.com/matheusfelipeog/beautiful-docs) | MIT | Curated examples of genuinely great documentation |

### Claude Code Productivity
| Resource | License | One-liner |
|---|---|---|
| [anthropics/skills](https://github.com/anthropics/skills) | ⚠ No LICENSE file | Anthropic's official Agent Skills reference repo |
| [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | MIT | Claude Code skill that cuts ~65% of output tokens via terse "caveman-speak" |
| [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Apache-2.0/MIT/CC-BY (mixed) | Official MCP reference server implementations |
| [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | MIT | Large curated list of third-party MCP servers |
| [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | ⚠ CC BY-NC-ND 4.0 | Comprehensive Claude Code ecosystem directory |
| [awesome-claude-code-toolkit](https://github.com/rohitg00/awesome-claude-code-toolkit) | Apache-2.0 | Bundled agents/skills/commands/hooks/templates kit |
| [claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery) | ⚠ No LICENSE file | Worked examples of every Claude Code hook lifecycle event |
| [awesome-claude-prompts](https://github.com/langgptai/awesome-claude-prompts) | ⚠ No LICENSE file | Curated Claude-specific prompt library |

## License legend

- No mark = permissive (MIT / Apache-2.0 / BSD / ISC / ILP / OFL for fonts) — safe for most commercial use with attribution where required.
- ⚠ = flagged: copyleft (GPL/LGPL), non-commercial/no-derivatives (CC BY-NC-*), custom/non-OSI terms, or no LICENSE file at all. Read the actual license before shipping these in a commercial product — see each category's own License Summary table and Notes section for specifics.

## Contributing

Each category README follows the same structure: description → best repositories (stars/license/last-updated/description/install/usage) → Notes (caveats) → License Summary table. When adding a new resource, verify it live (stars, license, last commit) before adding an entry, and flag any non-permissive license explicitly rather than omitting it.
