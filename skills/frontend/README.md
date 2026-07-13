# Frontend Skills & Resources

Curated, verified open-source repositories, boilerplates, style guides, and Claude Skills for HTML/CSS/JavaScript/TypeScript, React, Vue, Svelte, Tailwind CSS, accessibility, PWAs, and performance. Use this list when scaffolding a new frontend project, enforcing code style, auditing accessibility, or equipping an AI coding agent with frontend design judgment.

## Best Repositories

### [Vite](https://github.com/vitejs/vite)
- **Stars:** ~82,000 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

Next-generation frontend build tool with instant dev-server startup and native ES modules HMR. It ships official templates for React, Vue, Svelte, Preact, Solid, and vanilla JS/TS.

**Why it's included:** the de facto standard scaffolding/build tool for modern frontend projects; fast, actively developed, huge ecosystem of plugins.

**Installation:**
```bash
npm create vite@latest my-app
cd my-app
npm install
npm run dev
```

**Usage example:**
```bash
# scaffold a React + TypeScript project
npm create vite@latest my-app -- --template react-ts
```

---

### [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss)
- **Stars:** ~95,958 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-09

A utility-first CSS framework for rapidly building custom, responsive user interfaces without leaving your HTML.

**Why it's included:** the most widely adopted utility-CSS approach today; pairs naturally with component frameworks (React/Vue/Svelte) and design systems, and is a common target for AI-assisted UI generation.

**Installation:**
```bash
npm install tailwindcss @tailwindcss/vite
```

**Usage example:**
```html
<div class="mx-auto max-w-sm rounded-xl bg-white p-6 shadow-lg">
  <h1 class="text-xl font-bold text-slate-900">Hello Tailwind</h1>
</div>
```

---

### [Svelte](https://github.com/sveltejs/svelte)
- **Stars:** ~87,619 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

A compiler-based UI framework that shifts work from the browser to build time, producing small, highly optimized vanilla JS with no virtual DOM overhead.

**Why it's included:** best-in-class developer ergonomics and runtime performance; a strong alternative to React/Vue for teams that want less boilerplate.

**Installation:**
```bash
npx sv create my-app
cd my-app
npm install
npm run dev
```

**Usage example:**
```svelte
<script>
  let count = $state(0);
</script>

<button onclick={() => count++}>
  Clicked {count} times
</button>
```

---

### [Vue.js (core)](https://github.com/vuejs/core)
- **Stars:** ~53,946 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

A progressive, incrementally adoptable JavaScript framework for building web UIs, with an approachable template syntax and a full-featured Composition API.

**Why it's included:** one of the three major component frameworks (alongside React and Svelte); excellent docs, gentle learning curve, strong for both small widgets and full SPAs.

**Installation:**
```bash
npm create vue@latest
```

**Usage example:**
```vue
<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<template>
  <button @click="count++">Count is: {{ count }}</button>
</template>
```

---

### [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- **Stars:** ~148,082 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-04-16

The most widely adopted JavaScript/React style guide in the industry, distributed as `eslint-config-airbnb` / `eslint-config-airbnb-base`.

**Why it's included:** a battle-tested baseline for linting rules and code conventions across JavaScript, ES6+, and React codebases — useful as a reference or as a drop-in ESLint config.

**Installation:**
```bash
npx install-peerdeps --dev eslint-config-airbnb
```

**Usage example:**
```json
{
  "extends": "airbnb"
}
```

---

### [axe-core](https://github.com/dequelabs/axe-core)
- **Stars:** ~7,307 (as of 2026-07-13)
- **License:** MPL-2.0
- **Last updated:** actively maintained, last push 2026-07-01

The accessibility engine that powers most automated a11y testing tools (Chrome DevTools, Lighthouse, Cypress, Jest, Storybook). Detects WCAG violations directly in the DOM.

**Why it's included:** the industry-standard way to catch accessibility regressions automatically in CI, unit tests, or browser extensions — essential for any serious a11y workflow.

**Installation:**
```bash
npm install axe-core --save-dev
```

**Usage example:**
```js
axe
  .run()
  .then(results => {
    if (results.violations.length) {
      throw new Error('Accessibility issues found');
    }
  })
  .catch(err => console.error('Something bad happened:', err.message));
```

---

### [Workbox](https://github.com/GoogleChrome/workbox)
- **Stars:** ~12,973 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-10

A set of JavaScript libraries from the Chrome team for building Progressive Web Apps — precaching, runtime caching strategies, offline support, and service-worker generation.

**Why it's included:** the standard toolkit for adding installable, offline-capable PWA behavior to a frontend app without hand-rolling service-worker logic.

**Installation:**
```bash
npm install -g workbox-cli
```

**Usage example:**
```bash
workbox wizard
workbox generateSW
```

---

### [React Starter Kit](https://github.com/kriasoft/react-starter-kit)
- **Stars:** ~23,633 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-03-02

Production-ready React monorepo starter kit built on Bun, TypeScript, Vite, Tailwind CSS, tRPC, shadcn/ui, and Cloudflare Workers.

**Why it's included:** a mature, opinionated full-stack boilerplate that saves weeks of setup for a new SaaS or web app — good reference for project structure and tooling choices.

**Installation:**
```bash
git clone https://github.com/kriasoft/react-starter-kit.git my-app
cd my-app
bun install
```

**Usage example:**
```bash
bun run dev
```

---

### [Superdesign Skill](https://github.com/superdesigndev/superdesign-skill)
- **Stars:** ~328 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

A Claude Code / Cursor agent skill that gives coding agents design judgment: it reads your codebase for styling context, establishes a design system, and generates polished UI drafts instead of generic "AI slop" layouts. Supports 70+ coding agents.

**Why it's included:** this is exactly the kind of "Claude Skill for frontend dev" the curation calls for — it directly improves AI-generated UI quality and is actively maintained by a real product team (superdesign.dev).

**Installation:**
```bash
npx skills add superdesigndev/superdesign-skill
npm install -g @superdesign/cli@latest
superdesign login
```

**Usage example:**
```
/superdesign help me redesign this settings page so it doesn't look like default AI slop
```

## Notes
- `facebook/react` could not be verified through the GitHub search tool available in this session (queries against that specific repo were rejected), so it was intentionally omitted rather than guessed. Vue, Svelte, and the React Starter Kit boilerplate are included instead to cover component-framework and React-ecosystem needs.
- Star counts and license data were pulled live via the GitHub API on 2026-07-13 and reflect that date only — check the repos directly for current numbers.
- axe-core is MPL-2.0 (a copyleft-lite, file-level license), not MIT/Apache — review its terms before bundling into proprietary tooling.
- The "Claude Skills for frontend" space is young and fast-moving (many repos were created in 2026); `superdesign-skill` was chosen for its real product backing, MIT license, and active commit history, but newer/better options may appear quickly — recheck periodically.

## License Summary
| Repository | License |
|---|---|
| vitejs/vite | MIT |
| tailwindlabs/tailwindcss | MIT |
| sveltejs/svelte | MIT |
| vuejs/core | MIT |
| airbnb/javascript | MIT |
| dequelabs/axe-core | MPL-2.0 |
| GoogleChrome/workbox | MIT |
| kriasoft/react-starter-kit | MIT |
| superdesigndev/superdesign-skill | MIT |
