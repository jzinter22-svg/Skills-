# UX Skills & Resources

Guidance and reference implementations for usability, accessibility, and interaction design — use these when deciding how a component should behave, not just how it should look, and when auditing a flow against established heuristics or WCAG/WAI-ARIA standards.

## Best Repositories

### [WAI-ARIA Authoring Practices Guide (APG)](https://github.com/w3c/aria-practices)
- **Stars:** ~1,332 (as of 2026-07-13)
- **License:** W3C Document License (custom permissive terms; GitHub shows "Other" — see repo's `LICENSE.md`)
- **Last updated:** actively maintained, commits within the last day

The official W3C reference for accessible design patterns: keyboard interaction models, ARIA roles/states, and working examples for widgets like comboboxes, dialogs, menus, tabs, and trees.

**Why included:** This is *the* canonical source of truth for "how should this interactive component behave for keyboard and screen-reader users" — nearly every accessible component library (Radix, React Aria, Reach UI) implements these patterns directly.

**Installation:**
```bash
git clone https://github.com/w3c/aria-practices.git
```

**Usage example:**
```html
<!-- Example pattern: accessible disclosure button, per APG guidance -->
<button aria-expanded="false" aria-controls="panel1">
  Section heading
</button>
<div id="panel1" hidden>
  Panel content revealed on expand
</div>
```

---

### [Adobe React Spectrum / React Aria](https://github.com/adobe/react-spectrum)
- **Stars:** ~15,662 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, commits within the last day

A collection of libraries (React Aria hooks, React Stately state management, React Spectrum components) that implement adaptive, accessible interaction patterns tested across screen readers, touch, and keyboard.

**Why included:** The most rigorously tested accessible-pattern implementation in the React ecosystem — useful both as a component library and as a reference for how to correctly implement APG patterns in code.

**Installation:**
```bash
npm install react-aria-components
```

**Usage example:**
```tsx
import { Button } from 'react-aria-components'

export default function Example() {
  return <Button onPress={() => alert('Pressed')}>Press me</Button>
}
```

---

### [awesome-a11y](https://github.com/brunopulis/awesome-a11y)
- **Stars:** ~1,965 (as of 2026-07-13)
- **License:** CC0-1.0
- **Last updated:** actively maintained, commits within the last two months

A curated list of accessibility resources: articles, tools, screen-reader guides, checklists, and testing utilities.

**Why included:** A well-maintained entry point for discovering accessibility tooling and reading material beyond just component patterns (e.g. color contrast tools, screen reader testing guides).

**Installation:**
```
N/A — reference list, browse on GitHub
```

**Usage example:**
```
N/A (curated links, not a code library)
```

---

### [U.S. Web Design System (USWDS)](https://github.com/uswds/uswds)
- **Stars:** ~7,126 (as of 2026-07-13)
- **License:** Public domain / US government work (GitHub shows "Other"; see repo `LICENSE.md` — CC0-like terms)
- **Last updated:** actively maintained, commits within the last day

A design system built for US federal government websites with a strong emphasis on plain language, accessibility (Section 508/WCAG 2.1 AA), and mobile-first responsive patterns.

**Why included:** Battle-tested at massive scale for accessibility compliance; excellent reference for form design, error messaging, and plain-language UX patterns.

**Installation:**
```bash
npm install @uswds/uswds
```

**Usage example:**
```html
<button class="usa-button">Submit</button>
<div class="usa-alert usa-alert--info">
  <div class="usa-alert__body">
    <p class="usa-alert__text">Informational message</p>
  </div>
</div>
```

---

### [GOV.UK Design System](https://github.com/alphagov/govuk-design-system)
- **Stars:** ~651 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits within the last day

Styles, components, and UX patterns used across UK government digital services, including detailed "when to use" and research-backed guidance for each pattern (not just markup).

**Why included:** Unusually good documentation of the *why* behind each UX pattern (backed by user research), useful for teams that want rationale, not just code, for form and flow design decisions.

**Installation:**
```bash
npm install govuk-frontend
```

**Usage example:**
```html
<div class="govuk-form-group">
  <label class="govuk-label" for="event-name">Event name</label>
  <input class="govuk-input" id="event-name" name="eventName" type="text">
</div>
```

---

### [awesome-ux](https://github.com/batoreh/awesome-ux)
- **Stars:** ~536 (as of 2026-07-13)
- **License:** CC0-1.0
- **Last updated:** actively maintained, commits within the last two months

A curated list covering the broader User Experience discipline: research methods, information architecture, usability testing, and UX writing resources.

**Why included:** Good complement to component-focused a11y lists — covers process and research side of UX (personas, usability testing methodology) rather than just interface patterns.

**Installation:**
```
N/A — reference list, browse on GitHub
```

**Usage example:**
```
N/A (curated links, not a code library)
```

## Notes
- Several government design systems (USWDS, GOV.UK) show a non-standard license classification on GitHub ("Other"); both are effectively public-domain/permissive but you should read each repo's `LICENSE.md` before reuse in a commercial product.
- "Awesome list" entries are curated link collections, not code — use them for research and discovery rather than installation.
- For component-level accessibility implementation, prefer building on React Aria or Radix (see the UI category) rather than hand-rolling APG patterns.

## License Summary
| Repository | License |
|---|---|
| [WAI-ARIA Authoring Practices Guide](https://github.com/w3c/aria-practices) | W3C Document License (custom) |
| [Adobe React Spectrum / React Aria](https://github.com/adobe/react-spectrum) | Apache-2.0 |
| [awesome-a11y](https://github.com/brunopulis/awesome-a11y) | CC0-1.0 |
| [U.S. Web Design System](https://github.com/uswds/uswds) | Public domain (US gov work) |
| [GOV.UK Design System](https://github.com/alphagov/govuk-design-system) | MIT |
| [awesome-ux](https://github.com/batoreh/awesome-ux) | CC0-1.0 |
