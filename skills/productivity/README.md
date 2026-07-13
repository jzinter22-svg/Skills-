# Claude Code Productivity Skills & Resources

Curated, high-star, actively-maintained repositories for getting more out of Claude Code and the broader Claude/agent ecosystem: Anthropic's Agent Skills format, official and community Model Context Protocol (MCP) servers, Claude Code slash-command/CLAUDE.md/hook collections, and prompt libraries. Reach for these when you want to extend Claude Code with new tools, adopt a proven project-config layout, or find a ready-made MCP server instead of writing one from scratch.

## Best Repositories

### [anthropics/skills](https://github.com/anthropics/skills)
- **Stars:** ~160,700 (as of 2026-07-13)
- **License:** No LICENSE file present in the repo as of this writing — treat contents as "all rights reserved" unless a specific skill states otherwise; verify before redistributing a skill commercially
- **Last updated:** pushed 2026-07-01

Anthropic's own public repository of Agent Skills — folders of instructions, scripts, and resources (each defined by a `SKILL.md` with YAML frontmatter) that Claude loads dynamically for specialized tasks, from document/PDF handling to enterprise workflows.

Best for: the canonical reference for the Skills format itself, and for installing Anthropic's official example/document skills directly into Claude Code.

**Installation:**
```bash
# Inside Claude Code:
/plugin marketplace add anthropics/skills
/plugin install document-skills@anthropic-agent-skills
```

**Usage example:**
```yaml
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name
Instructions that Claude follows when this skill is triggered.
```
```text
"Use the PDF skill to extract form fields from path/to/file.pdf"
```

### [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)
- **Stars:** ~88,400 (as of 2026-07-13)
- **License:** Apache-2.0 for new/spec code, MIT retained for legacy contributions, CC-BY-4.0 for docs (dual/triple-licensed, see repo LICENSE)
- **Last updated:** pushed 2026-07-10

The official reference implementations of the Model Context Protocol, maintained by Anthropic and the MCP community — servers for filesystem access, git, fetch, memory/knowledge-graph, sequential-thinking, and more, plus links out to hundreds of third-party servers.

Best for: the authoritative starting point for adding MCP tools to Claude Code, and for seeing idiomatic server implementations in TypeScript and Python.

**Installation:**
```bash
# TypeScript server via npx
npx -y @modelcontextprotocol/server-memory

# Python server via uvx
uvx mcp-server-git
```

**Usage example:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/files"]
    }
  }
}
```

### [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers)
- **Stars:** ~90,700 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** pushed 2026-07-13

A large, actively-updated curated list of third-party MCP servers across categories (databases, browsers, cloud infra, search, dev tools, etc.), with a companion hosted directory site.

Best for: discovering community MCP servers beyond the official reference set — check here before building a new MCP integration in case one already exists.

**Installation:**
```bash
# Not a package itself — browse the list, then npm/uvx install the specific
# server you choose, e.g.:
npx -y @modelcontextprotocol/server-github
```

**Usage example:**
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "<token>" }
    }
  }
}
```

### [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)
- **Stars:** ~49,900 (as of 2026-07-13)
- **License:** CC BY-NC-ND 4.0 (non-commercial, no derivatives — this is a curated reference list to read, not code to fork/modify/redistribute commercially)
- **Last updated:** pushed 2026-07-13

The most comprehensive hand-curated directory of Claude Code resources: slash commands, CLAUDE.md templates, hooks, status lines, developer tooling, and plugins, cross-linked to their source repos.

Best for: a single jumping-off point to browse the wider Claude Code ecosystem (commands, hooks, CLAUDE.md examples) before building your own.

**Installation:**
```bash
git clone https://github.com/hesreallyhim/awesome-claude-code.git
# Browse .claude/commands and docs/ for examples to adapt in your own project
```

**Usage example:**
```text
# Example entry structure: a linked slash command you can copy into
# your project's .claude/commands/ directory, e.g. /clean, /todo, /commit
```

### [rohitg00/awesome-claude-code-toolkit](https://github.com/rohitg00/awesome-claude-code-toolkit)
- **Stars:** ~2,306 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** pushed 2026-05-12

A large bundled toolkit for Claude Code: 135 agents, 35 skills, 42 slash commands, 176+ plugins, 20 hooks, 15 rules, 7 project templates, and 14 MCP configs, all organized and installable.

Best for: teams that want a big pre-assembled starter kit of agents/commands/hooks/templates rather than hand-picking individual pieces.

**Installation:**
```bash
git clone https://github.com/rohitg00/awesome-claude-code-toolkit.git
# Copy the desired agents/, commands/, hooks/, or templates/ subfolder
# into your project's .claude/ directory
```

**Usage example:**
```bash
cp -r awesome-claude-code-toolkit/templates/typescript-service/.claude ./.claude
```

### [disler/claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery)
- **Stars:** ~3,826 (as of 2026-07-13)
- **License:** No LICENSE file present — treat as reference/example code, confirm terms with the author before reuse in a product
- **Last updated:** pushed 2026-03-04

A worked example repo covering all Claude Code hook lifecycle events (PreToolUse, PostToolUse, SubagentStop, etc.) with logging, TTS notifications, and security-check hooks.

Best for: learning how to write Claude Code hooks in practice, with runnable examples for every hook event rather than just documentation.

**Installation:**
```bash
git clone https://github.com/disler/claude-code-hooks-mastery.git
cd claude-code-hooks-mastery
# Inspect .claude/settings.json and hooks/ to see wiring, then adapt into
# your own project's settings.json
```

**Usage example:**
```json
{
  "hooks": {
    "PreToolUse": [
      { "matcher": "Bash", "hooks": [{ "type": "command", "command": "./hooks/pre_tool_use.py" }] }
    ]
  }
}
```

### [langgptai/awesome-claude-prompts](https://github.com/langgptai/awesome-claude-prompts)
- **Stars:** ~5,333 (as of 2026-07-13)
- **License:** No LICENSE file present — treat prompts as reference examples, verify reuse terms before commercial use
- **Last updated:** pushed 2026-02-28

A curated collection of prompt examples specifically tuned for Claude models (as opposed to generic ChatGPT prompt lists), covering writing, coding, analysis, and role-play use cases.

Best for: a starting library of proven Claude-specific prompts to adapt for your own CLAUDE.md instructions or slash commands.

**Installation:**
```bash
git clone https://github.com/langgptai/awesome-claude-prompts.git
```

**Usage example:**
```text
Act as a senior code reviewer. Review the following diff for correctness,
security issues, and readability. Point out the single most important
issue first, then list minor nits separately.
```

### [JayZeeDesign/awesome-claude-skills](https://github.com/JayZeeDesign/awesome-claude-skills)
- **Stars:** ~167 (as of 2026-07-13)
- **License:** Apache-2.0 for the example skills themselves; `document-skills/` (docx/pdf/pptx/xlsx) is source-available, not open source — see the repo's `THIRD_PARTY_NOTICES.md` for bundled dependency licenses (BSD-2-Clause, GPL-3.0 for FFmpeg, MIT-CMU, SIL OFL v1.1 for fonts)
- **Last updated:** actively maintained mirror; verify against upstream before citing a date

A community-maintained mirror/redistribution of Anthropic's official `anthropics/skills` example Agent Skills, organized as ready-to-browse `SKILL.md` folders. Useful if you want to read a specific skill's instructions directly on GitHub without cloning the upstream repo.

Best for: browsing individual skill implementations one at a time; prefer installing from the canonical `anthropics/skills` (above) for production use.

**Skills included:**
| Skill | Purpose |
|---|---|
| `algorithmic-art` | Generative/algorithmic art with p5.js (seeded randomness, flow fields, particle systems) |
| `artifacts-builder` | Multi-component claude.ai HTML artifacts using React, Tailwind CSS, shadcn/ui |
| `brand-guidelines` | Apply Anthropic's official brand colors/typography to an artifact |
| `canvas-design` | Visual art in .png/.pdf driven by an explicit design philosophy |
| `document-skills/docx`, `/pdf`, `/pptx`, `/xlsx` | Create, edit, and analyze Word/PDF/PowerPoint/Excel files (tracked changes, formatting preservation, text extraction) |
| `internal-comms` | Draft status reports, newsletters, and FAQs in a company's preferred format |
| `mcp-builder` | Guide for building well-designed MCP servers (Python FastMCP or Node/TS SDK) |
| `skill-creator` | Guide for authoring or updating a Claude Agent Skill |
| `slack-gif-creator` | Composable animation primitives for Slack-compliant animated GIFs |
| `template-skill` | Blank starter scaffold (`SKILL.md` frontmatter only) for a new skill |
| `theme-factory` | Coordinated color/typeface theme packs for slides, docs, and HTML pages |
| `ui-design` | Single-file HTML/Tailwind UI exploration and inspiration |
| `webapp-testing` | Playwright-based toolkit for driving/screenshotting/debugging a local web app |

**Installation:**
```bash
git clone https://github.com/JayZeeDesign/awesome-claude-skills.git
# Copy an individual skill folder (e.g. skill-creator/) into your project's
# .claude/skills/ directory, or read its SKILL.md directly on GitHub
```

**Usage example:**
```text
"Use the webapp-testing skill to screenshot the login page and check the console for errors"
```

## Notes
- Several of the highest-value repos in this space (`anthropics/skills`, `disler/claude-code-hooks-mastery`, `langgptai/awesome-claude-prompts`) ship without a LICENSE file — GitHub's API confirms `license: null`. That does not make them public domain; treat them as "look but confirm before you reuse commercially."
- `hesreallyhim/awesome-claude-code` is CC BY-NC-ND 4.0, which explicitly disallows commercial use and derivative redistribution — fine for personal reference, not for repackaging.
- This ecosystem moves very fast (weekly releases are common for MCP-related repos); all repos listed had commits within the last few months as of the search date (2026-07-13), but re-verify star counts/dates before citing them in anything long-lived.
- `wong2/awesome-mcp-servers` (MIT, ~4,200 stars) is a smaller alternative curated MCP list and was considered but not included to avoid duplicating `punkpeye/awesome-mcp-servers`, which is larger and more active.

## License Summary
| Repository | License |
|---|---|
| anthropics/skills | None (no LICENSE file) |
| JayZeeDesign/awesome-claude-skills | Apache-2.0 (example skills); document-skills source-available, not OSS |
| modelcontextprotocol/servers | Apache-2.0 / MIT (dual) / CC-BY-4.0 (docs) |
| punkpeye/awesome-mcp-servers | MIT |
| hesreallyhim/awesome-claude-code | CC BY-NC-ND 4.0 (non-commercial, no derivatives) |
| rohitg00/awesome-claude-code-toolkit | Apache-2.0 |
| disler/claude-code-hooks-mastery | None (no LICENSE file) |
| langgptai/awesome-claude-prompts | None (no LICENSE file) |
