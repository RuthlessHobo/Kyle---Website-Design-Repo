# Skills & Tools Ecosystem

Real, installable skills and MCP servers that make AI-built frontends look intentional instead of generated. These are for **Claude Code / agent (Cursor, Codex, Gemini CLI) environments** — that's where SKILL.md files and MCP servers plug in. **Claude Design** (claude.ai/design) doesn't install skills the same way; for it, you feed *this repo* as context (see `DESIGN.md` §5) and use the 21st.dev Magic MCP where connector support exists.

> ⚠️ Most of these are third-party. Skim a SKILL.md / repo before trusting it, and never hand an MCP server credentials you haven't vetted. Install commands change — verify against each repo's README. Star counts/installs are point-in-time (early–mid 2026).

---

## Tier 1 — Install these first

### Anthropic `frontend-design` (official)
The baseline. Breaks Claude out of "AI slop" — forces purpose/tone/constraints/differentiation thinking before code, names the cliché looks to avoid. This repo's `DESIGN.md` is built to sit *on top of* it and push further.
- In Claude Code: `npx skills add anthropics/claude-code --skill frontend-design`
- Source: `anthropics/skills` (path `skills/frontend-design/`) and `anthropics/claude-code` (path `plugins/frontend-design/`).

### Vercel `web-design-guidelines` (`vercel-labs/agent-skills`, MIT)
The correctness pass. Lints your UI against the Web Interface Guidelines (100+ rules: ARIA, focus states, labeled inputs, touch targets, reduced-motion, semantic HTML, keyboard nav, heading hierarchy). It fetches the latest rules from the source repo so they stay current. Pairs perfectly with `references/06-quality-floor.md`.
- `npx skills add vercel-labs/agent-skills` (then select `web-design-guidelines`).

### 21st.dev Magic MCP (`@21st-dev/magic`)
Live, production-ready component pulls via `/ui`. Setup + usage in `inspiration/21st-dev-workflow.md`.
- `npx @21st-dev/cli@latest install --api-key YOUR_KEY`

---

## Tier 2 — Design intelligence & systems

### `nextlevelbuilder/ui-ux-pro-max-skill` (MIT)
The most comprehensive design *database* skill: **50+ UI styles, 97 color palettes, 57 font pairings, 99 UX guidelines, 25 chart types** across 9 stacks, queryable via a bundled Python CLI (`scripts/search.py`). Use it as a lookup for `references/01` (type) and `02` (color), then commit to one system. Workflow: analyze requirements → `--design-system` for recommendations.
- `npx skills add nextlevelbuilder/ui-ux-pro-max-skill`

### Vercel `composition-patterns` (`vercel-labs/agent-skills`, MIT)
Teaches scalable component architecture: avoid boolean-prop proliferation, use compound components + context + explicit variants. Keeps generated component APIs clean (relevant once you're building real React).

### `superdesigndev/superdesign` (MIT, open-source design agent)
Open-source design agent that lives in the IDE — parallel agents, infinite-canvas UX, analyzes your existing React/Next codebase to match components. The only open-source IDE-native alternative to Claude Design.
- MCP wiring (no API key): `jonthebeef/superdesign-mcp-claude-code`.

### `Ilm-Alan/frontend-design`
Eight aesthetic anchors, each locking palette/typography/texture to specific CSS tokens — pick one per brief. Conceptually parallel to this repo's `aesthetic-directions/`; good cross-reference for more anchors.

---

## Tier 3 — Curated collections & DESIGN.md ecosystem

### `rohitg00/awesome-claude-design`
DESIGN.md prompts organized **by aesthetic family**, remix recipes (mix tokens across families for novel looks — single-brand clones go generic fast), skills, video teardowns, and honest community takes on Claude Design vs Lovable/Figma Make/Stitch/SuperDesign. Best source for *more anchors* and the DESIGN.md protocol.

### Google Labs Stitch skills (`google-labs-code`, via `VoltAgent/awesome-agent-skills`)
`design-md` (create/manage DESIGN.md), `enhance-prompt` (add design/UX vocabulary to prompts), `shadcn-ui`, `react-components` (Stitch→React), `stitch-loop` (design-to-code feedback loop). Google open-sourced the DESIGN.md spec; these operationalize it.

### `ConardLi/garden-skills` (web-design-engineer)
`web-design-engineer` skill (inspired by the Claude Design system prompt, preserved in the repo for reference) + a 23-theme token architecture.
- `npx skills add ConardLi/garden-skills -s web-design-engineer`

### `wilwaldon/Claude-Code-Frontend-Design-Toolkit`
A grab-bag of "things that actually make Claude Code output better frontends" — skills, plugins, MCP servers, CLAUDE.md tricks, Figma integration (`get_design_context`, `get_variable_defs`, Code Connect, "Send to Figma"/Code-to-Canvas).

### `VoltAgent/awesome-agent-skills` (1000+) / Antigravity Awesome Skills (1200+)
The mega-directories. Agent-agnostic (Claude Code, Cursor, Codex, Gemini CLI, Copilot). Browse by category; install via `npx skills add <org>/<repo>`.

---

## Motion & assets
- **GSAP agent skills** — full GreenSock ecosystem (timelines, ScrollTrigger, React, performance) for orchestrated motion (`references/04-motion.md`).
- **SVGL** — brand logos as SVG (also inside the 21st.dev Magic MCP via `logo_search`).
- **Figma MCP / Dev Mode** — if a client provides Figma, read frames/components/tokens directly (`get_design_context`, `get_variable_defs`); "Code to Canvas" sends a running UI back to Figma as editable layers.

---

## How the pieces fit
```
DESIGN.md (this repo)                  ← the directive that binds everything
   + frontend-design (Anthropic)       ← baseline anti-slop taste
   + web-design-guidelines (Vercel)    ← correctness / a11y lint
   + ui-ux-pro-max-skill               ← palette/type/UX lookup database
   + 21st.dev Magic MCP                ← real component structure on demand
   + Dribbble (manual reference)       ← art direction / signature moves
   + GSAP skills                       ← intentional motion
   = intentional, on-brand, accessible sites that don't read as AI-made
```

> **Install commands and repo paths drift.** Before installing, open the repo README and confirm the current command, license, and that the SKILL.md is verified. Vet any MCP before giving it credentials.
