# 21st.dev Workflow — Production-Ready Components

21st.dev is the source for **how components are actually built** — real, pre-vetted, production-grade React/TypeScript components rather than experimental code that breaks. Where Dribbble gives you the *vibe*, 21st.dev gives you the *structure*. Its **Magic MCP** ("Magic Component Platform") lets an agent generate and fetch components from the curated 21st.dev library via natural language — "like v0, but inside your IDE/agent."

---

## What it is

- A **curated component library** (navbars, heroes, pricing tables, forms, cards, modals, etc.) inspired by real-world design-engineer work.
- An **MCP server** (`@21st-dev/magic`) exposing tools to an AI agent:
  - **Component builder** (`/ui …`) — describe a component, get multiple production-ready variants to pick from. Clean TypeScript, proper props, responsive by default, typically Tailwind + shadcn/ui + Radix primitives.
  - **Inspiration fetcher** — pull existing components/previews from the library *without generating new code*, to browse structure.
  - **SVGL integration** (`logo_search`) — thousands of brand logos/icons as raw SVG.
- You **own** everything generated — no licensing restrictions; fully editable code.

---

## Setup (one-time)

1. Generate an API key from the **21st.dev Magic Console** (`21st.dev/magic`).
2. Install into your agent. CLI (auto-detects Cursor / Windsurf / Cline / Claude):
   ```bash
   npx @21st-dev/cli@latest install --api-key YOUR_KEY
   ```
   Or manual MCP config (Claude config at `~/.claude/mcp_config.json`):
   ```json
   {
     "mcpServers": {
       "@21st-dev/magic": {
         "command": "npx",
         "args": ["-y", "@21st-dev/magic@latest", "API_KEY=\"YOUR_KEY\""]
       }
     }
   }
   ```
   > For Claude Code: add via your MCP settings / `claude mcp add`. For Claude.ai connectors, check whether the Magic MCP is available as a remote connector in your plan; otherwise use it in Claude Code/Cursor and bring the output back.

---

## How to use it well

Type `/ui` (or `/21`) followed by a **specific** description. Specificity is everything — it's the same decide-before-generate principle.

- ❌ vague: `/ui card with hover effect`
- ✅ specific: `/ui pricing card, single highlighted tier, hairline border, shadow elevation only on hover with 300ms ease-out, no rounded-corner sameness — radius 10px`
- Reference the **locked anchor**: feed it your tokens (palette hex, font roles, radius scale) so generated variants match *this* project instead of the library default.
- Generate **multiple variants**, compare side by side, pick one, then customize. Don't ship variant #1 blind.
- Break complex UIs into **smaller components** — the agent handles focused components far better than whole pages.
- Use the **inspiration fetcher** first when you're unsure what you want: browse real structures, then build.

---

## Critical: 21st.dev defaults are still defaults

The Magic library leans Tailwind + shadcn/ui — which is *exactly* the stack that produces the generic look if you accept its defaults (Inter, indigo, uniform radius). So:

1. **Always pass your token system in the prompt** so variants inherit your palette/type/radius, not the library's.
2. After generating, **run it through the anti-slop checklist** (`references/00-anti-ai-slop.md`): kill indigo, replace Inter-as-identity, vary the radius/elevation, fix dead hover states.
3. Use 21st.dev for **structure and speed**, apply the locked **aesthetic** yourself. The component is a head start, not the finished design.

> **Division of labor:** Dribbble → what it should feel like. 21st.dev → a correct, fast structural starting point. `DESIGN.md` + the anchor → the identity that makes it not look generated.
