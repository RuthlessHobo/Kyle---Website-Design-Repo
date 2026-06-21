# Kyle — Website Design Repo

A design knowledge base that makes Claude (Design, Code, or any agent) build **aesthetic websites that do not look AI-generated**. It front-loads the constraints — palette, type, layout, motion, copy — so the model designs for *this specific client* instead of returning the statistical average (indigo gradients, Inter, cookie-cutter card grids).

It pulls **art direction from Dribbble** and **production-ready component structure from 21st.dev**, and points to the real installable skills/MCPs that reinforce it.

## Start here
**`DESIGN.md`** — the master build directive. Read it first, every time. Everything else supports it.

## What's inside
| Path | What it's for |
|---|---|
| `DESIGN.md` | Master directive: the bans, the build sequence, how to use the repo |
| `SKILL.md` | Same directive in skill format (auto-triggers in Claude Code/agents) |
| `references/00-anti-ai-slop.md` | The full "never do this" tell list + why it happens |
| `references/01-typography.md` | Escape Inter — font system, pairings, sourcing |
| `references/02-color.md` | Escape indigo — deriving distinctive palettes |
| `references/03-layout-and-sections.md` | Section anatomy, hero-as-thesis, meaningful structure, copy |
| `references/04-motion.md` | Motion that serves the message |
| `references/05-process.md` | The decide-before-generate loop, expanded |
| `references/06-quality-floor.md` | a11y / performance / responsive non-negotiables |
| `inspiration/dribbble-workflow.md` | Mining Dribbble for art direction |
| `inspiration/21st-dev-workflow.md` | 21st.dev Magic MCP setup + component pulls |
| `inspiration/reference-sources.md` | The wider inspiration/asset toolkit |
| `aesthetic-directions/direction-templates.md` | Ready-to-pick aesthetic anchors (none are AI defaults) |
| `stannect-presets/vertical-presets.md` | Home services / rentals / Shopify starting systems |
| `skills-and-tools/ecosystem.md` | Real installable skills + MCPs, with commands |

## How to use it

**With Claude Design (claude.ai/design)** — the primary use:
Load this repo (connect the GitHub repo, or paste `DESIGN.md` + the relevant `references/*`) as project knowledge before a build. Then brief the client. Claude Design reads it like a designer reads a brief and builds within the constraints.

**With Claude Code / agents (Cursor, Codex, Gemini CLI):**
`SKILL.md` auto-triggers on frontend tasks. Install the companion skills/MCPs in `skills-and-tools/ecosystem.md` (especially the **21st.dev Magic MCP**, Anthropic's `frontend-design`, and Vercel's `web-design-guidelines`).

**Per project:**
Start from a `stannect-presets/` vertical if the client fits → lock one anchor → pull 3–6 real references → write & critique tokens → build → clear the quality floor → remove one accessory.

## The one rule
Every visual decision must trace to *this* subject — this client, this industry, this audience, this page's job. The constraints in this repo are the point: they turn a model from a template machine into a design tool.

---
*Built for Kyle / Stannect. Treat each file as a constraint, not a suggestion. Customize the presets and anchors as the work teaches you what's true — ship and refine.*
