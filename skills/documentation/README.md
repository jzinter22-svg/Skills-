# Documentation Skills

Curated, high-star, actively-maintained open-source tools and templates for writing and publishing better project documentation: README generators/standards, documentation site generators, architecture decision record (ADR) tooling, code comment/docstring style guides, and "awesome" documentation lists. Reach for these when scaffolding a new repo's README, standing up a docs site, recording an architectural decision, or setting a house style for code comments.

## Best Repositories

### [othneildrew/Best-README-Template](https://github.com/othneildrew/Best-README-Template)
- **Stars:** ~16,200 (as of 2026-07-13)
- **License:** Unlicense (public domain)
- **Last updated:** pushed 2026-04-18, still actively starred/forked as of 2026-07-13

The most popular fill-in-the-blank README template on GitHub, with sections for project badges, screenshots, getting-started, usage, roadmap, contributing, license, and contact.

Best for: quickly bootstrapping a professional-looking README for a new project without designing the layout from scratch.

**Installation:**
```bash
# Use as a GitHub template (click "Use this template" on the repo page), or:
git clone https://github.com/othneildrew/Best-README-Template.git
cp Best-README-Template/README.md ./README.md
```

**Usage example:**
```markdown
<!-- Fill in the placeholders in the cloned README.md -->
<a name="readme-top"></a>
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]

# Project Title

<!-- ABOUT THE PROJECT -->
## About The Project
A short description of your project.
```

### [RichardLitt/standard-readme](https://github.com/RichardLitt/standard-readme)
- **Stars:** ~6,326 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** pushed 2026-06-17

A specification (not just a template) for what sections a README should contain and in what order, plus a generator (`generator-standard-readme`) to scaffold compliant files.

Best for: teams/organizations that want a consistent, reviewable README structure across many repositories rather than a one-off template.

**Installation:**
```bash
npm install -g generator-standard-readme yo
yo standard-readme
```

**Usage example:**
```markdown
## Table of Contents
## Background
## Install
## Usage
## API
## Contributing
## License
```

### [facebook/docusaurus](https://github.com/facebook/docusaurus)
- **Stars:** ~65,600 (as of 2026-07-13)
- **License:** MIT (code); CC-BY-4.0 (docs content)
- **Last updated:** pushed 2026-07-10

React-based static site generator purpose-built for documentation: versioned docs, i18n, search, MDX support, and a large plugin ecosystem. Used by React, Jest, Supabase, and many other major OSS projects.

Best for: teams that want a full-featured, versioned documentation site and are comfortable with a React/Node toolchain.

**Installation:**
```bash
npx create-docusaurus@latest my-website classic
cd my-website
npm start
```

**Usage example:**
```mdx
---
title: Getting Started
sidebar_position: 1
---

# Getting Started

Welcome to the docs! This page uses **MDX**, so you can drop in
<CodeBlock language="bash">npm install</CodeBlock> components directly.
```

### [squidfunk/mkdocs-material](https://github.com/squidfunk/mkdocs-material)
- **Stars:** ~27,090 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** pushed 2026-07-06

A Material Design theme for MkDocs — turns plain Markdown files into a fast, searchable static docs site with minimal configuration. Powers docs for FastAPI, Kubernetes-adjacent projects, and countless others.

Best for: Python-centric or Markdown-only projects that want a polished docs site without a JavaScript build pipeline.

**Installation:**
```bash
pip install mkdocs-material
mkdocs new my-project
cd my-project
mkdocs serve
```

**Usage example:**
```yaml
# mkdocs.yml
site_name: My Docs
theme:
  name: material
  features:
    - navigation.tabs
    - content.code.copy
```

### [vuejs/vitepress](https://github.com/vuejs/vitepress)
- **Stars:** ~18,000 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** pushed 2026-07-13 (actively developed, currently on a v2 alpha line)

A Vite- and Vue-powered static site generator, spiritual successor to VuePress. Renders Markdown to fast, SPA-like documentation sites with built-in dev server and instant HMR.

Best for: JS/TS ecosystem projects (especially Vue-adjacent ones) that want a very fast dev/build experience and simple Markdown-first authoring.

**Installation:**
```bash
npm add -D vitepress
npx vitepress init
npm run docs:dev
```

**Usage example:**
```markdown
---
# docs/index.md
layout: home
hero:
  name: My Project
  text: Docs powered by VitePress
---
```

### [joelparkerhenderson/architecture-decision-record](https://github.com/joelparkerhenderson/architecture-decision-record)
- **Stars:** ~16,425 (as of 2026-07-13)
- **License:** CC BY-NC-SA 4.0 for the author's original content (individual templates within the repo may carry their own separate licenses — check before reusing in a commercial product)
- **Last updated:** pushed 2026-07-12

A large collection of ADR templates (Michael Nygard style, Y-statements, MADR, etc.), examples, and guidance on how and when to write architecture decision records.

Best for: teams that want to pick from several proven ADR template formats and adopt a lightweight process for recording "why we built it this way."

**Installation:**
```bash
git clone https://github.com/joelparkerhenderson/architecture-decision-record.git
mkdir -p docs/adr
cp architecture-decision-record/locales/en/templates/decision-record-template-by-michael-nygard/index.md docs/adr/0001-record-architecture-decisions.md
```

**Usage example:**
```markdown
# 1. Record architecture decisions

## Status
Accepted

## Context
We need a lightweight way to record architecturally significant decisions.

## Decision
We will use Architecture Decision Records, as described by Michael Nygard.

## Consequences
See ADR process docs.
```

### [google/styleguide](https://github.com/google/styleguide)
- **Stars:** ~39,441 (as of 2026-07-13)
- **License:** No single OSI license file at the repo root for the guides themselves (site content); treat as "read/reference," and check individual language sub-directories before redistributing
- **Last updated:** pushed 2026-06-03

Google's style guides for its open-source projects across languages (Python, C++, JavaScript, Java, Go, Shell, etc.), including detailed docstring and code-comment conventions (e.g. the Google Python docstring format used by Sphinx's Napoleon extension).

Best for: teams that want a battle-tested, widely-adopted reference for docstring/comment formatting instead of inventing an in-house convention.

**Installation:**
```bash
git clone https://github.com/google/styleguide.git
# Reference pyguide.md, jsguide.html, cppguide.html etc. directly, or link to
# https://google.github.io/styleguide/
```

**Usage example:**
```python
def fetch_smalltable_rows(table_handle, keys, require_all_keys=False):
    """Fetches rows from a Smalltable.

    Args:
        table_handle: An open smalltable.Table instance.
        keys: A sequence of strings representing the key of each row to fetch.
        require_all_keys: Optional; If require_all_keys is True only rows with
          all keys will be returned.

    Returns:
        A dict mapping keys to the corresponding table row data.
    """
```

### [matheusfelipeog/beautiful-docs](https://github.com/matheusfelipeog/beautiful-docs)
- **Stars:** ~9,507 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** pushed 2026-03-03

An "awesome list" of real-world documentation that is genuinely well-written and well-designed — pointers to docs from companies and OSS projects worth studying as examples, organized by category (APIs, style guides, open source, etc.).

Best for: getting inspiration and concrete examples before writing or redesigning your own docs, rather than a tool you install.

**Installation:**
```bash
# No install — browse the curated list directly on GitHub
git clone https://github.com/matheusfelipeog/beautiful-docs.git
```

**Usage example:**
```markdown
## API
- [Stripe API Reference](https://stripe.com/docs/api) — a benchmark for API docs
- [Twilio Docs](https://www.twilio.com/docs) — strong quickstarts and code samples
```

## Notes
- License names above were verified against each repository's GitHub API `license` field and, where GitHub reported "Other/NOASSERTION," the actual `LICENSE`/`LICENSE.md` file content was read directly — flag those cases before commercial reuse (`architecture-decision-record` is CC BY-NC-SA which is **non-commercial**, and `google/styleguide`'s guide text does not ship a single clear OSI license).
- Star counts and "last updated" dates are live snapshots taken 2026-07-13 and will drift over time; re-check before citing them as current in a report.
- All entries had commits within the last few months as of the search date, so all are actively maintained.

## License Summary
| Repository | License |
|---|---|
| othneildrew/Best-README-Template | Unlicense |
| RichardLitt/standard-readme | MIT |
| facebook/docusaurus | MIT (code) / CC-BY-4.0 (docs) |
| squidfunk/mkdocs-material | MIT |
| vuejs/vitepress | MIT |
| joelparkerhenderson/architecture-decision-record | CC BY-NC-SA 4.0 (non-commercial) |
| google/styleguide | Unclear/no single OSI license — verify per sub-guide |
| matheusfelipeog/beautiful-docs | MIT |
