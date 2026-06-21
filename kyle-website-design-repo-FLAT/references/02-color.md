# 02 — Color: Escape Indigo

The purple/indigo gradient is the loudest AI tell there is — a single Tailwind default (`indigo-500`) that propagated across the whole web and into model training data. Refusing it is the fastest single win. But "not purple" isn't a system. This file is how to derive a palette that belongs to *this* subject.

---

## Derive color from the subject, not from a swatch picker

The most distinctive palettes come from the client's real world — their materials, environment, product, and brand artifacts — not from a trendy default.

- **Roofing / construction:** weathered metal, asphalt, safety-orange, blueprint cyan, raw timber, concrete grey. A confident industrial palette beats a soft SaaS gradient.
- **HVAC:** the temperature duality (cool blue / warm amber) is *meaningful* here — use it as structure, not decoration.
- **Boat / jet-ski rental:** real water tones (not the AI blue→purple), sun-bleached deck, life-vest orange, marine teal, sand.
- **Equipment rental:** machine yellow/black, hi-vis, steel.
- **E-commerce (Shopify):** pull from the *product photography* — extract 2–3 dominant tones from real hero images so the UI and product feel like one object.

If the client has a logo/brand, sample from it and extend; don't invent a parallel palette.

---

## The structure of a palette (4–6 named values)

Define and name every value. A workable system:

```css
:root {
  --ink:        #1A1714;  /* near-black text — warm or cool, never pure #000 */
  --paper:      #FBFAF7;  /* background — rarely pure #FFF; give it a temperature */
  --surface:    #F1EDE6;  /* cards / raised areas */
  --accent:     #C8501E;  /* THE color — used sparingly, with intent */
  --accent-2:   #1F6F6B;  /* secondary, for a second meaning only */
  --muted:      #8A8278;  /* captions, borders, de-emphasis */
}
```

Rules:
- **Never pure black or pure white.** Pure `#000`/`#FFF` is a flatness tell. Give ink and paper a slight temperature (warm greys, cool off-whites). It reads as considered.
- **One accent, used like punctuation.** The accent should appear rarely enough that it *means* something (primary action, key highlight). A page bathed in accent has no accent.
- **A second color only if it carries a second meaning** (e.g. success/warning, or the HVAC hot/cold duality). Don't add color for variety.
- **Borders and dividers** come from `--muted`, not from a new color.

---

## Contrast & accessibility (non-negotiable)

- Body text vs background: **≥ 4.5:1** (WCAG AA). Large display: ≥ 3:1.
- Don't rely on color alone to convey state — pair with icon/label/shape.
- Test the accent on its actual background, not on white.
- Dark mode (if built): it's a *separate* palette with its own contrast checks, not an inverted one. Pure-inverted dark mode is a tell.

---

## Gradients — allowed, but earn them

Gradients aren't banned; *lazy* gradients are. A good gradient is pulled from a real material or photo and is subtle. A bad gradient is the two-stop blue→purple every generator emits.
- Prefer same-hue or adjacent-hue gradients (depth) over rainbow jumps.
- Mesh/ambient gradients can work as a *signature* if they're the one bold move — and only then.
- Add subtle grain/noise over flat gradients to kill the "plastic" look.

---

## Shadows & elevation

- Banned: the uniform `0 1px 3px rgba(0,0,0,0.1)` on every card. It's invisible and identical.
- Instead: **vary elevation to express hierarchy.** Most elements flat; lift only what should feel interactive or primary. Use layered, tinted shadows (a shadow that borrows the accent or ink hue reads richer than flat black-alpha).

```css
--shadow-flat: none;
--shadow-raised: 0 2px 4px -1px rgb(26 23 20 / 0.08), 0 8px 24px -8px rgb(26 23 20 / 0.12);
--shadow-accent: 0 8px 30px -10px rgb(200 80 30 / 0.35); /* for the one hero CTA */
```

---

## Quick palette starting points by tone (none are AI defaults)

| Tone | Ink | Paper | Accent | Second |
|---|---|---|---|---|
| Industrial / trades | `#15140F` | `#F4F1E9` | `#E8541C` (safety orange) | `#2C5E63` (blueprint teal) |
| Marine / rental | `#0E1C24` | `#F6F4EE` | `#0F8A86` (marine teal) | `#E6A23C` (sun) |
| Premium remodel | `#211C18` | `#FAF8F4` | `#7A5C3E` (walnut) | `#3D4A3A` (sage) |
| Clean e-com | derive from product photo | warm off-white | product's dominant hue | neutral |
| Bold consumer | `#171717` | `#FFFDF8` | a saturated *non-purple* (coral, lime, cobalt) | — |

> Need a bigger library: the ui-ux-pro-max skill ships **97 color palettes** queryable by industry. Use it to source, then commit to one named system above.
