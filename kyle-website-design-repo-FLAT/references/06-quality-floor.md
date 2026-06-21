# 06 — The Quality Floor

Distinctive design means nothing if the page is broken, slow, or inaccessible. These are the non-negotiables every build clears before it ships — build to this floor without announcing it. Much of this maps to the Web Interface Guidelines (100+ rules) that the Vercel `web-design-guidelines` skill checks automatically — install it to lint against the current set (`skills-and-tools/ecosystem.md`).

---

## Responsive
- [ ] Works from **320px** up. Test mobile first, then scale up.
- [ ] No horizontal scroll at any width.
- [ ] Touch targets ≥ **44×44px** with adequate spacing.
- [ ] Type readable on mobile (body ≥16px; check the chosen face's x-height at 14–16px).
- [ ] Images responsive (`srcset`/`sizes`), no layout shift (set width/height or aspect-ratio).
- [ ] The signature element degrades gracefully on small screens (doesn't break the layout).

## Accessibility (WCAG AA baseline)
- [ ] Color contrast ≥ **4.5:1** body, ≥ **3:1** large text/UI — tested on the *actual* background.
- [ ] **Visible keyboard focus** on every interactive element (don't remove outlines without replacing them).
- [ ] Full keyboard navigation; logical tab order; skip-to-content link.
- [ ] Semantic HTML: one `<h1>`, correct heading hierarchy, `<button>` for actions, `<a>` for navigation, landmarks (`<nav>`, `<main>`, `<footer>`).
- [ ] All inputs have associated `<label>`s; errors are programmatically associated and described.
- [ ] Images have meaningful `alt` (empty `alt=""` for decorative).
- [ ] State not conveyed by color alone (add icon/text/shape).
- [ ] `prefers-reduced-motion` respected (`references/04-motion.md`).
- [ ] Don't disable zoom; respect user font-size settings (use `rem`).

## Performance
- [ ] Fonts: ≤2 families, subset, `font-display: swap`, preconnect/self-host, variable where possible.
- [ ] Images: modern formats (WebP/AVIF), lazy-load below the fold, correctly sized (no 4000px hero scaled down).
- [ ] Animate only `transform`/`opacity`.
- [ ] Watch Core Web Vitals: LCP (hero image/text fast), CLS (no shifting), INP (responsive interactions).
- [ ] No giant unused JS/CSS; ship what the page needs.

## Semantics / SEO / "invisible" work (AI builds routinely skip these)
- [ ] Proper `<title>` and meta description.
- [ ] One `<h1>`; descriptive headings (not styled `<div>`s).
- [ ] Open Graph / Twitter card tags for sharing.
- [ ] Structured data (schema.org) where relevant (LocalBusiness for service clients; Product for e-com).
- [ ] Forms actually connect to the destination (CRM/GHL/email) — a beautiful disconnected form is a dead lead. Verify the wiring.
- [ ] Canonical URL; sensible, readable URLs.

## Pre-ship "pre-flight" (the human review AI skips)
- [ ] Open it on a real phone: do buttons work, do forms submit, is any text cut off?
- [ ] Click every CTA — does each go where it claims, with consistent naming end-to-end?
- [ ] Read the copy aloud — does it sound like *this* business or like a generated template?
- [ ] Does the page pass the 3-second "know / like / trust" test for a stranger?
- [ ] Apply the Chanel rule one last time — remove the one least-necessary element.
