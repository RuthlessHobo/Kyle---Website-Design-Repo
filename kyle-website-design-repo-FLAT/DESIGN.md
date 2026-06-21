# DESIGN.md — Master Build Directive

> **Read this file first, in full, before generating any layout, palette, type choice, or line of code.**
> This is the operating contract for every website built using this repo. It exists to make output that does **not** read as AI-generated. If a choice you're about to make matches the "AI defaults" list below, stop and choose again.

---

## 0. The one rule everything else serves

**Every visual decision must be traceable to the specific subject — this client, this industry, this audience, this page's single job.** Generic looks come from making decisions about "a website" instead of decisions about *this* business. Before designing, name the subject in one sentence, name its audience in one sentence, and name the page's single job in one sentence. Design only after those three are written down.

If you find yourself reaching for a choice because it's "clean and modern," that is the tell that you're averaging instead of designing. Clean and modern is the floor, not the goal.

---

## 1. Hard bans — the AI-slop tells (never ship these unless the brief explicitly demands them)

These are the patterns that make a site instantly readable as machine-made. They are banned by default. (Sources and reasoning in `references/00-anti-ai-slop.md`.)

**Color**
- ❌ Purple / indigo / violet gradient accents (the Tailwind `indigo-500` default). This single color is the #1 AI tell.
- ❌ The blue→purple hero gradient.
- ❌ Shadows at a flat `0.1` opacity applied uniformly to every card.

**Type**
- ❌ Inter or Roboto as the *primary* face with no customization. (Inter is fine as a *body* workhorse only when paired with a characterful display face — never as the whole identity.)
- ❌ Five+ distinct type styles crammed into one hero (logotype + H1 + sub + label + decorative). Max **three** roles visible at once.

**Layout & structure**
- ❌ The "three or four feature cards in an even grid" as the default section pattern.
- ❌ Uniform `16px` border-radius and `24px` padding on *everything* — identical card heights, identical rounding, identical spacing throughout. Visual hierarchy requires intentional *variation*.
- ❌ Numbered markers (01 / 02 / 03) when the content is **not** an actual sequence.

**Motion**
- ❌ The same generic `fade-in-on-scroll` on every element.
- ❌ A decorative line that follows the cursor or the scroll for no reason.
- ❌ Hover states that make a button *fade into* the background (the opposite of what hover should do).
- ❌ Motion as decoration. Every animation must make the product easier to understand. If it doesn't, cut it.

**The three "designer-AI" default looks** (these are what a *good* model reaches for when trying to look non-generic — so they've become their own cliché). Do not default to any of them; only use if the brief names it:
1. Warm cream background (~`#F4F1EA`) + high-contrast serif display + terracotta accent.
2. Near-black background + single acid-green or vermilion accent.
3. Broadsheet layout: hairline rules, zero border-radius, dense newspaper columns.

---

## 2. The build sequence (do not skip steps, do not reorder)

This repo enforces *decide-before-generate*. The reason AI sites look the same is that constraints get added *after* generation. Here they come first.

**Step 1 — Frame the brief (write it, don't think it).**
Subject / audience / page-job in three sentences (Section 0). Pull anything known about Kyle's client, vertical, or brand from memory or the project. If the brief is vague, pin the gaps yourself and state your assumptions.

**Step 2 — Choose ONE aesthetic direction.**
Pick a single anchor from `aesthetic-directions/direction-templates.md` (or define a new one). An anchor locks palette + type + texture together so the whole page shares one visual language. Mixing anchors mid-page is the "different sections, different aesthetics" tell.

**Step 3 — Pull real references.**
Before building, gather 3–6 concrete references:
- **Dribbble** for the *vibe / art direction / signature moves* → `inspiration/dribbble-workflow.md`
- **21st.dev** for *production-ready component structure* → `inspiration/21st-dev-workflow.md`
- Extract specific moves ("the way this hero stacks the headline over a clipped photo," "this pricing table's row dividers"), not whole templates.

**Step 4 — Write the token system.**
A compact design-token block before any markup: 4–6 named hex values, 2–3 type roles (display / body / utility), a spacing scale, a radius scale (with *variation*, not one value), and **one signature element** — the single thing this page will be remembered by. See `references/01`–`04`.

**Step 5 — Self-critique the tokens against the brief.**
Re-run the brief mentally as if from scratch. If any token reads like the generic answer you'd give *any* business in this category, revise it and note what changed and why. Only proceed when the system is specific to *this* subject.

**Step 6 — Build, deriving every value from the tokens.**
No hard-coded colors, no off-system spacing. Watch CSS specificity (type-selectors vs element-selectors cancelling padding/margins between sections).

**Step 7 — Critique again, against the quality floor.**
Responsive to mobile, visible keyboard focus, reduced-motion respected, real copy (not lorem, not AI filler). See `references/06-quality-floor.md`. Then apply the Chanel rule: remove one accessory — cut the single least-necessary flourish.

---

## 3. Where boldness goes

Spend boldness in **one** place — the signature element — and keep everything around it quiet and disciplined. A page with one memorable move and restrained surroundings reads as designed. A page where every section competes reads as generated. Restraint is the signal of intent.

---

## 4. Copy is design material

AI copy makes a site feel as templated as AI layout. Write from the user's side of the screen: name things by what people do and recognize, not how the system works. Active voice. Sentence case. No filler. Specific beats clever. Match the tone to the client's actual industry voice (a roofer and a luxury boat-rental brand do not sound alike). Full guidance in `references/03-layout-and-sections.md` and the `frontend-design` skill's writing section.

---

## 5. How this repo is meant to be used

- **In Claude Design / claude.ai:** load this repo (or paste `DESIGN.md` + the relevant `references/*`) as context/project knowledge before a build. Claude Design reads it the way a designer reads a brief.
- **In Claude Code / agents:** `SKILL.md` mirrors this directive in skill format so it auto-triggers on frontend tasks. Install the companion skills/MCPs in `skills-and-tools/ecosystem.md` (especially the 21st.dev Magic MCP for live component pulls).
- **Per project:** start from a `stannect-presets/` vertical preset if the client fits one, then customize. Presets are *starting points*, not finish lines.

---

## 6. Map of this repo

```
DESIGN.md                          ← you are here (master directive)
SKILL.md                           ← same directive, skill format for Claude Code/agents
references/
  00-anti-ai-slop.md               ← the full "never do this" list + why
  01-typography.md                 ← escape Inter; font system, pairings, sourcing
  02-color.md                      ← escape indigo; deriving distinctive palettes
  03-layout-and-sections.md        ← section anatomy, hero theses, meaningful structure, copy
  04-motion.md                     ← motion that serves the message
  05-process.md                    ← the decide-before-generate loop, expanded
  06-quality-floor.md              ← a11y / performance / responsive non-negotiables
inspiration/
  dribbble-workflow.md             ← mining Dribbble for art direction
  21st-dev-workflow.md             ← Magic MCP setup + component pulls
  reference-sources.md             ← the wider inspiration/asset toolkit
aesthetic-directions/
  direction-templates.md           ← ready-to-pick anchors (none are AI defaults)
stannect-presets/
  vertical-presets.md              ← home services / rentals / Shopify starting systems
skills-and-tools/
  ecosystem.md                     ← real installable skills + MCPs w/ commands
```

---

*Maintained by Kyle. Treat every file here as a constraint, not a suggestion. The constraints are the whole point — they're what turn a model from a template machine into a design tool.*
