# 05 — Process: Decide Before You Generate

The reason AI sites look alike isn't the model — it's that constraints get bolted on *after* generation, when it's too late to matter. Experienced teams treat the model as an **execution engine, not a creative brain**: they make the decisions first, then generate. This file is the loop, expanded from `DESIGN.md` §2.

---

## Why order matters

> "AI performs best when decisions are made *before* generation, not during." The same vague prompt always returns the same average. A structured, constrained prompt returns differentiated, predictable design.

So the work is front-loaded into the brief and the token system. By the time you write markup, every important choice is already made.

---

## The loop

### 1. Frame (write three sentences)
- **Subject:** what is this, concretely? ("A residential roofing company in Tampa that does fast insurance-claim work.")
- **Audience:** who decides? ("Homeowners with storm damage who want it handled now and trust signals fast.")
- **Job:** the page's single goal. ("Get the homeowner to send photos / book an inspection.")

Pull anything known from memory/project context (Kyle's vertical, the client, existing brand) and use it as a hint. If the brief is vague, **pin the gaps yourself and state your assumptions** rather than designing a generic thing.

> The strongest design skills run *20+ minutes of interrogation* on the brief before generating a line of code. You don't have to literally do 20 minutes, but the more the brief is pinned, the less the output averages out. When stakes are high, ask the user the gap-closing questions first.

### 2. Choose one aesthetic direction
One anchor from `aesthetic-directions/direction-templates.md`, locking palette + type + texture. One language for the whole page. (Different anchors per section = the "inconsistent aesthetic" tell.)

### 3. Gather references (3–6, specific)
- **Dribbble** → art direction, signature moves, the *feeling*. Extract specific moves, not whole comps. (`inspiration/dribbble-workflow.md`)
- **21st.dev** → production-ready component structure; use Magic MCP `/ui` and the inspiration fetcher. (`inspiration/21st-dev-workflow.md`)
- Save what you're stealing-with-pride as a short list: "hero stacking from X, divider style from Y, pricing layout from Z."

### 4. Write the token system (before markup)
A compact block:
- **Color:** 4–6 named hex (`references/02`).
- **Type:** 2–3 roles with named faces (`references/01`).
- **Layout:** spacing scale + radius scale (varied) + max-widths + a one-sentence layout concept + an ASCII wireframe to compare options (`references/03`).
- **Signature:** the *single* element this page is remembered by. Name it explicitly.

### 5. Critique the tokens against the brief (the key step)
Re-derive what you'd give *any* business in this category from a blank prompt. Wherever your token system matches that generic answer, **revise it and write down what you changed and why.** Proceed only when the system is specific to this subject. Do most of this in your head/notes; only show the user when confidence is high that it'll delight them.

### 6. Build from the tokens
- Every color/space/size derives from a token. No off-system values.
- Watch CSS specificity: type-selectors (`.section`) vs element/class selectors (`.cta`) can cancel each other's padding/margins, especially between sections. Structure specificity deliberately.
- If you have a browser/preview loop (Playwright, Claude Design preview), **screenshot and grade your own work** against the references at multiple viewport sizes, and iterate. A picture is worth 1000 tokens. A visual feedback loop is the difference between an agent that tries and one that ships.

### 7. Critique against the quality floor + Chanel rule
- Run `references/06-quality-floor.md`.
- Then remove one accessory — cut the single least-necessary flourish. Restraint is the signal of intent.

### 8. Keep notes between passes
Jot what you tried and rejected. Human designers don't repeat themselves because they remember; give yourself the same memory so each pass moves forward instead of circling.

---

## Anti-patterns in the process itself
- **The prompt loop:** spending hours re-prompting a bad generation. If the structure/copy comes back generic, *stop* and restart from the tokens, don't patch.
- **Designing the whole site at once:** generate section by section against the locked system, not one giant blind pass.
- **Skipping the brief because "it's obvious":** that's exactly when the output averages out.
