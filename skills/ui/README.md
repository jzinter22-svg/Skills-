# UI Skills & Resources

Component libraries, design systems, and layout frameworks for building dashboards, forms, navigation, and other interface elements. Use these when you need production-ready, accessible building blocks instead of writing components from scratch.

## Best Repositories

### [shadcn/ui](https://github.com/shadcn-ui/ui)
- **Stars:** ~118,980 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

Not a traditional npm package but a code-distribution platform: copy-paste, ownable React components built on Radix UI primitives and Tailwind CSS. Extremely popular as the base layer for modern dashboards and SaaS UIs.

**Why included:** Best-in-class for teams that want full control over component source (no black-box dependency), strong accessibility defaults via Radix, and a huge ecosystem of community themes/blocks.

**Installation:**
```bash
npx shadcn@latest init
```

**Usage example:**
```bash
npx shadcn@latest add button card
```
```tsx
import { Button } from "@/components/ui/button"

export function Example() {
  return <Button variant="outline">Click me</Button>
}
```

---

### [Radix Primitives](https://github.com/radix-ui/primitives)
- **Stars:** ~19,061 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

Unstyled, accessible React primitives (dialogs, dropdowns, tooltips, tabs, etc.) implementing full keyboard and screen-reader support per WAI-ARIA patterns. Powers shadcn/ui and many other design systems.

**Why included:** The gold standard for accessible headless UI primitives in React — use it when you need full visual control but don't want to reimplement ARIA behavior.

**Installation:**
```bash
npm install @radix-ui/react-dialog
```

**Usage example:**
```tsx
import * as Dialog from "@radix-ui/react-dialog"

export default function Example() {
  return (
    <Dialog.Root>
      <Dialog.Trigger>Open</Dialog.Trigger>
      <Dialog.Portal>
        <Dialog.Overlay />
        <Dialog.Content>
          <Dialog.Title>Title</Dialog.Title>
          <Dialog.Close>Close</Dialog.Close>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  )
}
```

---

### [Material UI (MUI)](https://github.com/mui/material-ui)
- **Stars:** ~98,577 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

Comprehensive React component library implementing Google's Material Design, including a full theming system, data grid, and date pickers (some as paid add-ons).

**Why included:** One of the most mature, enterprise-adopted component libraries with the deepest set of ready-made dashboard components (tables, forms, navigation drawers).

**Installation:**
```bash
npm install @mui/material @emotion/react @emotion/styled
```

**Usage example:**
```tsx
import Button from '@mui/material/Button'

export default function App() {
  return <Button variant="contained">Hello World</Button>
}
```

---

### [Ant Design](https://github.com/ant-design/ant-design)
- **Stars:** ~98,696 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

Enterprise-class UI design language and React component library, widely used for admin dashboards and internal tools. Comes with an extensive suite (Table, Form, DatePicker, Layout, Charts via companion libs).

**Why included:** Best pick for admin/back-office dashboards needing rich, batteries-included components (advanced tables, forms with validation) out of the box.

**Installation:**
```bash
npm install antd
```

**Usage example:**
```tsx
import { Button, DatePicker } from 'antd'

export default function App() {
  return (
    <>
      <Button type="primary">Primary Button</Button>
      <DatePicker />
    </>
  )
}
```

---

### [Chakra UI](https://github.com/chakra-ui/chakra-ui)
- **Stars:** ~40,506 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

A component system built for speed with strong accessibility (WAI-ARIA) support and a simple style-prop API, plus built-in dark mode support.

**Why included:** Great balance of developer ergonomics, accessibility, and theming flexibility for building SaaS products quickly.

**Installation:**
```bash
npm install @chakra-ui/react @emotion/react
```

**Usage example:**
```tsx
import { ChakraProvider, Button } from '@chakra-ui/react'

export default function App() {
  return (
    <ChakraProvider>
      <Button colorScheme="blue">Click me</Button>
    </ChakraProvider>
  )
}
```

---

### [Mantine](https://github.com/mantinedev/mantine)
- **Stars:** ~31,420 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

A fully featured React components library (100+ components, 50+ hooks) with built-in dark/light theme support and strong TypeScript typings.

**Why included:** One of the fastest-growing libraries thanks to its very complete component set (rich text editor, charts, dates, notifications) and first-class dark mode.

**Installation:**
```bash
npm install @mantine/core @mantine/hooks
```

**Usage example:**
```tsx
import { MantineProvider, Button } from '@mantine/core'

export default function App() {
  return (
    <MantineProvider>
      <Button>Hello</Button>
    </MantineProvider>
  )
}
```

---

### [daisyUI](https://github.com/saadeghi/daisyui)
- **Stars:** ~41,643 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

A Tailwind CSS plugin adding semantic component classes (`btn`, `card`, `navbar`, etc.) on top of utility classes, plus 30+ built-in color themes.

**Why included:** Best option for teams using Tailwind who want pre-built component classes (cards, navigation) without adopting a full JS component library — framework agnostic (works with plain HTML, React, Vue, Svelte).

**Installation:**
```bash
npm install -D daisyui
```
```js
// tailwind.config.js
module.exports = {
  plugins: [require("daisyui")],
}
```

**Usage example:**
```html
<button class="btn btn-primary">Button</button>
<div class="card w-96 bg-base-100 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">Card title</h2>
    <p>Card content</p>
  </div>
</div>
```

## Notes
- All UI picks here are frontend-framework specific (mostly React); daisyUI is the exception and is framework-agnostic.
- For dashboards specifically, Ant Design and MUI ship the richest built-in data components (tables, grids); shadcn/ui and Radix are best when you want full visual/behavioral control.

## License Summary
| Repository | License |
|---|---|
| [shadcn/ui](https://github.com/shadcn-ui/ui) | MIT |
| [Radix Primitives](https://github.com/radix-ui/primitives) | MIT |
| [Material UI](https://github.com/mui/material-ui) | MIT |
| [Ant Design](https://github.com/ant-design/ant-design) | MIT |
| [Chakra UI](https://github.com/chakra-ui/chakra-ui) | MIT |
| [Mantine](https://github.com/mantinedev/mantine) | MIT |
| [daisyUI](https://github.com/saadeghi/daisyui) | MIT |
