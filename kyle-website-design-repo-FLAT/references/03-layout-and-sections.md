# 03 — Layout, Sections & Copy

Structure should *encode* what's true about the content, not decorate it. This file covers section anatomy, the hero-as-thesis, layouts that escape the cookie-cutter, and copy (which makes a page feel as templated as the design if you let it).

---

## The hero is a thesis, not a template

Open with the most characteristic thing in the subject's world, in whatever form fits it best — a headline, a real photograph, a live demo, an interactive moment, a number that matters. The template hero (big number + small label + supporting stats + gradient accent) is the answer to use *only* if it's truly the best one for this brief, not the reflex.

Ask: *what is the single most convincing thing this business could show a stranger in three seconds?* Build the hero around that.

Hero patterns that aren't the default:
- **Proof-first:** a real before/after, a real install photo, a real dashboard — full-bleed, with the headline overlaid or beside it.
- **Outcome statement:** one sharp sentence about the result the customer gets, set large, with restrained support.
- **Editorial split:** asymmetric — headline column + image column at an unequal ratio (not 50/50).
- **Demo/interaction:** if there's something to *try*, let them try it above the fold.

---

## Section anatomy — escape the cookie-cutter stack

The default stack (hero → 3 feature cards → testimonials → pricing → CTA) is fine structurally but lethal visually when every section looks the same. Break it with **rhythm and variation**:

- Alternate **density**: a dense, information-rich section next to an open, breathing one.
- Alternate **alignment**: don't center everything. Left-align some, use asymmetry.
- Vary **card treatment**: not every group is "3 even cards." Try a feature *list* with a single supporting image, a wide editorial row, a comparison table, a real screenshot annotated with callouts.
- Use **full-bleed** moments sparingly to reset the eye.
- Let **section size express importance** — the most important section can be the biggest/loudest; supporting sections can be compact.

### Structural devices must carry information
- **Eyebrows / labels:** use to orient ("How it works," "Pricing") — not as decoration.
- **Numbered markers (01/02/03):** only when the content is genuinely sequential (a real process, a timeline). Otherwise they're fake structure.
- **Dividers / rules:** to separate genuinely different ideas, not to fill space.

---

## A spacing & grid system (so variation stays coherent)

Variation works only on top of a consistent system. Define once:
```css
:root {
  --space-2xs: 0.5rem;  --space-xs: 0.75rem; --space-sm: 1rem;
  --space-md: 1.5rem;   --space-lg: 2.5rem;  --space-xl: 4rem;
  --space-2xl: 6rem;    --space-3xl: 9rem;   /* section gaps */
  --radius-sm: 4px; --radius-md: 10px; --radius-lg: 20px; /* VARY radius, don't use one */
  --maxw: 72rem;        --maxw-prose: 38rem;
}
```
- **Radius:** use the *scale* intentionally (tight on data, soft on friendly cards) — never one identical value everywhere (that's the tell).
- **Whitespace is structural.** Generous, *unequal* whitespace reads as confident design; cramped-and-uniform reads as generated.
- **Vertical rhythm:** section gaps should be noticeably larger than in-section gaps so the page breathes.

---

## Layout moves that read as human/intentional

- **Asymmetry** over perfect symmetry.
- **Overlap**: let an image bleed under a heading, or a card overlap a section boundary (one signature overlap, not everywhere).
- **A real grid with deliberate breaks** — most content on grid, one element intentionally off it for emphasis.
- **Edge tension**: align something to the page edge / full-bleed to contrast with the contained content.
- **Optical alignment** over mathematical (nudge so it *looks* aligned).

---

## Copy: design material, not filler

AI copy is the other half of the slop problem. Rules:

1. **Write from the user's side of the screen.** Name things by what people do/recognize, not by how the system is built. "Get a quote," not "Initiate request flow."
2. **Active voice, specific verbs.** Buttons say exactly what happens: "Book the install," "See pricing," "Send my photos." The action keeps its name through the whole flow (button "Publish" → toast "Published").
3. **Specific beats clever.** "Roof leak fixed in 48 hours, guaranteed" beats "Solutions that exceed expectations."
4. **Sentence case, no filler, one job per element.** A label labels; an example demonstrates; nothing does double duty.
5. **Match the industry voice.** A roofer's site should sound like a roofer who's good at their job — direct, confident, plain. A premium boat-rental brand can be warmer and more aspirational. Never let two clients in different niches sound the same. (This mirrors Kyle's niche-matched, friendly-conversational copy standard.)
6. **Empty states and errors are direction, not mood.** Say what happened and what to do next, in the interface's voice. Errors don't apologize and are never vague.
7. **No lorem ipsum, no AI filler in deliverables.** Write real, plausible copy with the client's actual offer, or pull it from the brief.

---

## Conversion structure (for service & e-com clients)

The page still has a job — leads or sales. Distinctive design and conversion are not in tension; generic design *hurts* conversion because it fails the "know / like / trust" test on sight. Keep:
- **One primary action per section**, visually dominant (this is where accent color and elevation go).
- **Proof near the ask:** reviews, real photos, guarantees, credentials placed where the decision happens.
- **A frictionless primary path** (for Kyle's GHL/home-services clients, that's usually *capture the lead fast* — short form, click-to-call, "send photos for a quote"; speed-to-lead is the metric).
- **For Shopify/e-com:** product clarity, real imagery, trust signals (returns, shipping, reviews), and a checkout path that doesn't make people think.
