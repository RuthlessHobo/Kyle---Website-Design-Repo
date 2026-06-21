# Aesthetic Directions — Pick ONE Anchor

An anchor locks **palette + type + texture + signature** together so the whole page speaks one language. Choosing an anchor up front is what prevents the "different sections, different aesthetics" tell. Pick one per brief, then customize its tokens to the specific client — these are *starting systems*, not finished skins.

> None of these are the AI defaults (no indigo, no Inter-as-identity, and deliberately not the three "designer-AI" cliché looks — cream+serif+terracotta, near-black+acid, broadsheet hairlines). If a brief explicitly asks for one of those, that's allowed — the brief always wins.

How to use: read the anchor's intent, copy its token block, swap the accent/faces toward the client's real world (`references/02-color.md`, `01-typography.md`), then build.

---

## A. Grounded Industrial
**For:** roofing, construction, HVAC, contractors, equipment rental. Confident, capable, no-nonsense — looks like a crew that does the work well.
**Texture:** flat confident color blocks, slim borders, real job-site photography, minimal rounding. One bold structural rule line.
**Signature:** an oversized, tightly-tracked condensed headline over a full-bleed real photo, with a hard color block holding the CTA.

```css
:root {
  --font-display: "Cabinet Grotesk", system-ui, sans-serif; /* heavy, condensed feel */
  --font-body: "General Sans", system-ui, sans-serif;
  --ink: #15140F; --paper: #F4F1E9; --surface: #E7E2D6;
  --accent: #E8541C;      /* safety orange — used sparingly */
  --accent-2: #2C5E63;    /* blueprint teal — second meaning only */
  --muted: #857F72;
  --radius-sm: 2px; --radius-md: 6px; --radius-lg: 12px; /* tight, mechanical */
}
```

---

## B. Warm Service (friendly, trustworthy, human)
**For:** home services that win on *trust + responsiveness* — the homeowner-facing roofer/plumber/remodeler who wants to feel approachable and reliable.
**Texture:** warm off-white, soft-but-varied rounding, real team/customer photos, generous whitespace, one calm accent.
**Signature:** a proof-first hero — a real before/after or install photo beside a plain-spoken outcome headline and a single dominant CTA.

```css
:root {
  --font-display: "DM Serif Display", Georgia, serif; /* warmth + trust */
  --font-body: "DM Sans", system-ui, sans-serif;
  --ink: #211C18; --paper: #FAF8F4; --surface: #F1ECE4;
  --accent: #2F7D6B;      /* dependable green */
  --muted: #8A8278;
  --radius-sm: 6px; --radius-md: 14px; --radius-lg: 24px; /* friendly, but VARY use */
}
```

---

## C. Marine / Leisure (rental, experiential, sun-and-water)
**For:** jet-ski / boat rental, watersports, leisure experiences. Energetic, aspirational, "your day on the water starts here."
**Texture:** real water/sky photography, an airy layout, a saturated marine accent + a sun warm, subtle motion (a slow drift, not a circus).
**Signature:** a full-bleed water hero with a bold availability/booking action floating over it; an editorial split for "how it works."

```css
:root {
  --font-display: "Clash Display", system-ui, sans-serif;
  --font-body: "Plus Jakarta Sans", system-ui, sans-serif;
  --ink: #0E1C24; --paper: #F6F4EE; --surface: #E6EFEF;
  --accent: #0F8A86;      /* marine teal */
  --accent-2: #E6A23C;    /* sun */
  --muted: #7C8A8F;
  --radius-sm: 8px; --radius-md: 16px; --radius-lg: 28px;
}
```

---

## D. Premium Build (high-end remodels, luxury rentals, design-led)
**For:** premium kitchen & bath, luxury boat charters, high-ticket remodels. Restraint = expense. Quiet, confident, editorial.
**Texture:** lots of air, hairline detailing, a muted natural palette, large restrained serif, photography as the hero. Almost no motion.
**Signature:** a single hero photograph at full quality with a small, perfectly-set caption; type and spacing do all the talking.

```css
:root {
  --font-display: "Canela", "DM Serif Display", Georgia, serif; /* premium hero face */
  --font-body: "Source Sans 3", system-ui, sans-serif;
  --ink: #1F1A16; --paper: #FAF8F4; --surface: #EFEAE2;
  --accent: #7A5C3E;      /* walnut */
  --accent-2: #3D4A3A;    /* sage */
  --muted: #9A9286;
  --radius-sm: 0px; --radius-md: 4px; --radius-lg: 8px; /* near-sharp = refined */
}
```

---

## E. Bold Commerce (Shopify / DTC e-com)
**For:** Kyle's Shopify store and product brands. Punchy, product-first, conversion-focused, memorable.
**Texture:** color pulled from the *product photography*, big confident type, product shots as hero, clear single primary action per section. Distinctive non-purple accent.
**Signature:** an oversized product hero with the type wrapping/overlapping the product edge; a sticky add-to-cart that lifts on intent.

```css
:root {
  --font-display: "Clash Display", system-ui, sans-serif;
  --font-body: "Plus Jakarta Sans", system-ui, sans-serif;
  --ink: #171717; --paper: #FFFDF8;
  --surface: /* derive from product photo dominant tone */ #F2EDE6;
  --accent: /* product's hero hue — NOT purple */ #D6452F;
  --muted: #8C857C;
  --radius-sm: 4px; --radius-md: 12px; --radius-lg: 20px;
}
```

---

## F. Editorial Tech (SaaS, dashboards, Stannect's own products)
**For:** Stannect's dashboard/KPI product, SaaS-adjacent tools, anything data-forward that must read as *capable and calm*.
**Texture:** calm, generous spacing, a single family mastered across roles (Linear-style restraint), data as the hero, mono for metrics. Hierarchy from scale, not decoration.
**Signature:** a real (or convincing) product surface as the hero — an annotated dashboard — with metrics that count up *because the number is the point*.

```css
:root {
  --font-display: "General Sans", system-ui, sans-serif;
  --font-body: "General Sans", system-ui, sans-serif; /* one family, mastered */
  --font-mono: "JetBrains Mono", ui-monospace, monospace;
  --ink: #16181D; --paper: #FBFBFC; --surface: #F2F3F5;
  --accent: #1F6F6B;      /* calm non-purple */
  --muted: #8B9096;
  --radius-sm: 6px; --radius-md: 10px; --radius-lg: 16px;
}
```

---

## Defining a *new* anchor (when none fit)
Write four lines, then a token block:
1. **Intent** — the feeling + who it's for, in one sentence.
2. **Texture** — surfaces, borders, rounding, imagery style, motion level.
3. **Signature** — the one memorable element.
4. **Tokens** — 4–6 named colors, 2–3 type roles, a varied radius scale.

Then run it through `references/05-process.md` §5 (critique against the brief) to confirm it's specific, not a default in disguise.
