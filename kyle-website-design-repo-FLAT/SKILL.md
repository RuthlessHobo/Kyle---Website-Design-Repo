---
name: kyle-website-design
description: Use whenever building, redesigning, or styling any website, landing page, marketing page, or web UI — for Stannect clients (home services, rentals), the Shopify store, or Stannect's own products. Enforces a decide-before-generate workflow and a strict anti-AI-slop standard so output does not read as AI-generated (no indigo gradients, no Inter-as-identity, no cookie-cutter card grids). Pulls art direction from Dribbble and component structure from 21st.dev. Trigger on any frontend/web design, "build a website/page," "make it look less AI," typography/color/layout direction, or landing-page work.
---

# Kyle — Website Design Skill

Build websites that look intentionally designed for *this specific client*, never templated or AI-generated. This skill enforces constraints **before** generation, because the only reason AI sites look alike is missing constraints — a model with no direction outputs the statistical average of its training data.

## Required first step
Read **`DESIGN.md`** in this repo in full. It is the master directive. Then read the reference files relevant to the task. Do not generate layout, palette, type, or code before doing so.

## The non-negotiable bans (full list + reasoning in `references/00-anti-ai-slop.md`)
- No purple/indigo/violet accent or blue→purple gradient (the #1 AI tell).
- No Inter/Roboto as the whole identity — pair a characterful display face with a restrained body face (`references/01-typography.md`).
- No three/four even feature-card grid as the default section; no uniform radius + padding + shadow on everything.
- No numbered markers on non-sequential content. No same fade-in-on-scroll on every element. No hover that hides the button. No cursor/scroll-following decoration.
- No AI illustrations or generic stock — use the client's real photos.
- Don't default to the three "designer-AI" clichés (cream+serif+terracotta / near-black+acid / broadsheet hairlines) unless the brief names one.

## The workflow (full version in `references/05-process.md`)
1. **Frame** the brief in 3 sentences: subject / audience / page-job. Pull client + vertical context from memory/project. Pin gaps, state assumptions.
2. **Choose one aesthetic anchor** from `aesthetic-directions/direction-templates.md` (locks palette+type+texture). For Kyle's verticals, start from `stannect-presets/vertical-presets.md`.
3. **Pull 3–6 references:** Dribbble for art direction (`inspiration/dribbble-workflow.md`), 21st.dev for component structure (`inspiration/21st-dev-workflow.md`). Extract specific moves, not whole templates.
4. **Write the token system** before markup: 4–6 named colors, 2–3 type roles, varied spacing/radius scales, and ONE signature element.
5. **Critique tokens against the brief** — revise anything that reads like the generic answer for any business in this category; note what changed.
6. **Build** deriving every value from tokens; watch CSS specificity between sections.
7. **Clear the quality floor** (`references/06-quality-floor.md`: responsive, a11y, performance, real copy, working forms), then remove one accessory (cut the least-necessary flourish).

## Principles
- Spend boldness in ONE place — the signature element; keep everything else quiet. Restraint signals intent.
- Structure must encode meaning, not decorate. Motion must aid understanding or be cut (`references/04-motion.md`).
- Copy is design material: user's-side-of-the-screen, active voice, specific, niche-matched voice — never AI filler.
- Color from the subject's real world, not a swatch picker (`references/02-color.md`).

## Companion skills/MCPs (`skills-and-tools/ecosystem.md`)
Pair with Anthropic `frontend-design`, Vercel `web-design-guidelines` (a11y lint), `ui-ux-pro-max-skill` (palette/type/UX database), and the **21st.dev Magic MCP** for live component pulls. Always pass your locked tokens into Magic MCP so variants inherit *this* project's identity, not the library's Inter/indigo defaults.

## The single test for any element
Does this choice help someone understand what the business does and trust it — or just make the page busier? Keep what carries meaning; cut the rest.
