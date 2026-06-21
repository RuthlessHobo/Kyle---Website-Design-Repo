# Dribbble Workflow — Mining Art Direction

Dribbble is the source for **art direction and signature moves** — the *feeling* and the memorable details — not for production code. The job here is to extract specific, justifiable moves and bring them into the locked aesthetic, never to copy a comp wholesale.

> ⚠️ **Use as reference, not as source-of-truth.** Dribbble shots are often aspirational/non-functional and many are AI-made themselves. Extract a *move*, then rebuild it correctly against the quality floor. Respect creators' IP — take inspiration, not assets.

---

## How to search it well

Search by **subject + tone + element**, not just "website":
- `roofing website hero` / `home services landing page` / `boat rental web design`
- `[tone] landing page` → `editorial`, `industrial`, `brutalist`, `warm minimal`, `bold typographic`
- `[element] interaction` → `pricing table`, `navbar`, `testimonial section`, `hover card`, `before after`
- `[subject] branding` for palette/type identity ideas

Filter to **Popular** for craft, **Recent** for current trends. Open the designer's profile when a shot lands — the strongest references come in sets.

---

## What to extract (and what to ignore)

Pull **specific moves** you can name and justify:
- "The way this hero stacks an oversized headline over a clipped, full-bleed photo."
- "This pricing section uses a single highlighted column with a hairline border instead of cards."
- "This testimonial treats the quote as huge display type with the attribution tiny."
- "This nav tucks the CTA into a pill that lifts on hover."
- A **palette** sampled from a shot's real photography.
- A **type personality** (then find the actual licensable face — `references/01`).

Ignore: the exact pixels, the fake metrics, the stock-perfect models, anything that won't survive being made real and accessible.

---

## The capture-to-build pipeline

1. **Collect 4–8 shots** spanning the tone you wrote in the brief. Save a board/links.
2. **Write a one-line steal list:** "hero stacking from A, divider style from B, pricing layout from C, accent palette from D." (3–6 moves max — more than that and you're cloning, not designing.)
3. **Map each move to a token or section** in your design system. The moves must serve *this* subject; drop any that don't.
4. **Rebuild, don't trace.** Implement each move from scratch in your stack, against `references/06-quality-floor.md`. Add the client's real content.
5. **Critique:** does the assembled page feel like one coherent thing (your locked anchor) or like a collage of other people's shots? If it's a collage, cut moves until one voice remains.

---

## Using Dribbble *with* Claude Design / Claude Code

- In **Claude Design**: paste the shot image(s) or describe the specific moves precisely; ask it to adapt the *move* into the locked token system — not to "make it look like this shot." Pair the request with `DESIGN.md` loaded so the anti-slop rules still bind.
- In **Claude Code**: drop reference screenshots into the repo and reference them in the prompt; combine with the 21st.dev Magic MCP so you get real component code matching the referenced structure.
- If browsing tooling is available (e.g. Claude in Chrome / web capture), point it at specific shot URLs and ask for the extractable moves, then proceed through the pipeline above.

> **Rule of thumb:** Dribbble decides *what it should feel like*. 21st.dev decides *how the component is actually built*. The locked anchor + quality floor keep both honest.
