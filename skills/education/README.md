# Education / Pedagogical Agent Skills

Curated resources for AI agents that assist with teaching, tutoring, curriculum design, and student-facing learning support. Reach for these when you want research-grounded pedagogical guidance baked into an agent's instructions, rather than generic teaching advice.

## Best Repositories

### [GarethManning/education-agent-skills](https://github.com/GarethManning/education-agent-skills)
- **Stars:** ~406 (as of 2026-07-13)
- **License:** CC BY-SA 4.0 (share-alike — forks/derivatives must carry the same license and attribution; not a permissive OSS license)
- **Last updated:** actively maintained (140+ commits on `main`); re-check before citing a specific date

An open-source library of 165 evidence-based teaching skills spanning 20 pedagogical domains — memory & learning science, explicit instruction, questioning/discussion, literacy & critical thinking, EAL/D & language development, curriculum design & assessment, wellbeing & motivation, teacher professional learning, cross-cultural pedagogy, AI learning science/literacy, Montessori & alternative approaches, historical and systems thinking, inclusive design, and student-facing study skills. Each skill is a `SKILL.md` with YAML frontmatter carrying an ID, domain, and an explicit evidence-strength rating ("Strong," "Moderate," "Emerging," "Original") with named research citations. The project explicitly documents excluded frameworks (e.g., learning-styles/VAK theory) in `EXCLUSIONS.md` rather than silently omitting them.

Best for: giving a tutoring/teaching agent a transparently-sourced pedagogy layer instead of ad hoc instructions, or building lesson-planning and assessment-design tools on evidence-rated skills.

**Installation:**
```bash
# Via Claude Code CLI
claude plugin install https://github.com/GarethManning/education-agent-skills

# Or via git, copying individual skill folders into .claude/skills/
git clone https://github.com/GarethManning/education-agent-skills.git
```

A hosted MCP server (169 tools: 165 skills + 4 discovery functions) is also available at `https://mcp-server-sigma-sooty.vercel.app/mcp`, but it now requires a signup-gated auth token — local plugin/git install remains the free, recommended path.

**Usage example:**
```text
"Use the retrieval-practice skill to design a 10-minute spaced-review
 warm-up for a Year 8 history unit on the Industrial Revolution"
```

## Notes
- CC BY-SA 4.0 is a copyleft-style license: fine to use and adapt, but any redistributed derivative must stay under the same license and credit the source — do not repackage these skills under a different license.
- The evidence-rating system ("Strong/Moderate/Emerging/Original") is a review aid, not a guarantee — verify a cited study yourself before treating a skill's claims as settled science, especially anything tagged "Original" or "Emerging."
- The hosted MCP server's auth-token requirement can change independently of the repo's git history; prefer the local plugin/clone install if you want to avoid a signup dependency.

## License Summary
| Repository | License |
|---|---|
| GarethManning/education-agent-skills | CC BY-SA 4.0 (share-alike, attribution required) |
