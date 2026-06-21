# 04 — Motion That Serves the Message

Motion is where AI sites most obviously betray themselves: the same fade-in-on-scroll on every element, decorative lines chasing the cursor, hover states that do nothing or hide the button. The test for every animation is one question:

> **Does this motion help someone understand the product, or does it just make the page feel busier?**

If it doesn't aid understanding, cut it. Sometimes less motion is the more sophisticated choice — and over-animation is itself a generated-look tell.

---

## What good motion looks like

The YC review's positive example: feature cards where two illustrated controllers connected by lightning animate on hover in a way that *reinforces* the product's multiplayer message. The animation was in service of meaning, on-brand, and would've been expensive to build before AI tools. That's the bar — motion that makes you understand what the thing does.

Good motion is usually **one orchestrated moment**, not scattered effects everywhere:
- A **page-load sequence** that reveals the hero with intent (staggered, purposeful — not everything fading at once).
- A **scroll-triggered reveal** that *demonstrates* something (a before→after wipe, a metric counting up *because the number is the point*, a process advancing).
- **Hover micro-interactions** that make the target clearer and more inviting — a button that lifts/brightens, a card that reveals its detail.
- **Ambient atmosphere** used as the single signature (a slow gradient drift, a subtle parallax) — only if it's *the* bold move and everything else stays quiet.

---

## What to cut

- ❌ Identical `fade-in-up` on every section as it scrolls into view. (The reflex. Reads as canned.)
- ❌ A line/shape that follows the cursor or scroll for no reason.
- ❌ Hover that *reduces* a button's prominence (fades it into the background).
- ❌ Buttons that snap with no easing — or animate so slowly they feel laggy.
- ❌ Motion on text the user is trying to read.
- ❌ Parallax everywhere (one considered parallax moment, maybe; a parallax circus, no).

---

## Craft details

- **Easing:** use real easing curves (`cubic-bezier`), not linear. Entrances ease-out, exits ease-in. A custom curve (e.g. `cubic-bezier(0.16, 1, 0.3, 1)`) reads more designed than the defaults.
- **Duration:** UI feedback 150–250ms; reveals 400–700ms; ambient slow. Too-slow reveals feel sluggish.
- **Stagger:** when revealing a group, stagger 40–80ms between items — it reads as choreography, not a dump.
- **Transform/opacity only** for performance (avoid animating layout properties).
- **Respect `prefers-reduced-motion`** — provide a reduced/zero-motion path. This is part of the quality floor, not optional.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

---

## Where to source *intentional* motion

- **GSAP** + ScrollTrigger for orchestrated, timeline-based sequences (there are dedicated GSAP agent skills — see `skills-and-tools/ecosystem.md`).
- Framer Motion / Motion One for React component-level micro-interactions.
- Study **Dribbble interaction shots** for *ideas you can justify* — then build the one that serves the message, not all of them (`inspiration/dribbble-workflow.md`).
