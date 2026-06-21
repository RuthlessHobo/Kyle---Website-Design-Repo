# 01 — Typography: Escape the Inter Default

Typography is the highest-leverage way to make a site stop looking AI-made. Users in 2026 recognize default fonts on sight — Inter/Roboto with no customization reads as "generated" before a single word is read. The move is not "never use Inter"; it's **pair a characterful display face with a restrained body face**, and treat the type itself as a memorable part of the design rather than a neutral delivery vehicle.

---

## The system: three roles, used with discipline

1. **Display** — headlines, hero, the client's name-as-logo. This is where personality lives. Use a face with real character, *sparingly*.
2. **Body** — paragraphs, UI, the workhorse. Must be legible at 14–18px on mobile. Can be a "safe" face *because* the display face is carrying identity.
3. **Utility** (optional) — captions, data, labels, code-like metadata. Often a mono or a tight grotesk.

**Hard rule:** max three visible roles at once. Build hierarchy with **scale, weight, and spacing** — not by introducing more typefaces. (5+ styles in a hero is a documented AI tell.)

---

## Display faces with character (reach for these instead of defaults)

Free via **[Fontshare](https://fontshare.com)** (Indian Type Foundry) — no licensing friction, high quality:
- **General Sans** — Swiss precision with warmth; a robust Inter alternative with actual character. Great all-rounder.
- **Cabinet Grotesk** — bold, geometric, packed with personality. Excellent for large headings / name-as-logo.
- **Clash Display** — striking variable geometric display; commands a hero.
- **Satoshi**, **Switzer**, **Khand**, **Sentient** (serif) — all strong, all free.

Free via **Google Fonts**:
- **Fraunces** — variable serif with "wonky" optical features; old-meets-new tension. Distinctive at display sizes, elegant small.
- **Space Grotesk** — mono-inspired squared terminals; technical/aerospace character.
- **DM Serif Display** + **DM Sans** — share proportions; editorial elegance with near-zero effort.
- **Playfair Display** — high-contrast fashion-magazine serif (pair with a calm body).
- **Sora**, **Outfit**, **Plus Jakarta Sans** — geometric sans with more personality than Inter; render beautifully on mobile.
- **Spectral**, **Source Serif 4**, **IBM Plex Serif/Sans/Mono** — institutional weight without stuffiness.
- **Atkinson Hyperlegible** — distinctive *and* maximally accessible letterforms.

Premium (worth a hero license when budget allows): **Aeonik**, **Söhne**, **Neue Montreal**, **Mabry**, **Canela**, **Whyte**, **Ogg**, **Untitled Sans**.

Tech-forward but increasingly common (use deliberately, not as a new default): **Geist** (Vercel), **Manrope**, **JetBrains Mono**.

---

## Pairing recipes (copy-paste starting points)

Pick by the *tone* you wrote in the brief, not by habit.

| Tone / use case | Display | Body | Notes |
|---|---|---|---|
| Friendly professional (consumer-facing services) | **DM Sans** | DM Sans (one-family system) | Rounder than Inter; warm without whimsy |
| Editorial / trust / long-form | **Fraunces** or **Playfair Display** | **Source Serif 4** or Inter | Serif display does the identity work |
| Modern tech, but not generic | **Cabinet Grotesk** or **General Sans** | **General Sans** | Confident, wider than Inter |
| Technical / data / dashboards | **Space Grotesk** | **Manrope** | Mono-ish display + numerals that behave |
| Premium / luxury (boats, high-end remodels) | **Canela** or **DM Serif Display** | **Lato** or **Source Sans 3** | Restraint = expensive |
| Bold consumer brand (e-com, rentals) | **Clash Display** | **Plus Jakarta Sans** | Big personality hero, clean body |
| Zero-budget but distinctive | **Recife** (Velvetyne, free) | **Work Sans** | High-contrast serif that looks like it cost £500 |

> The "secret weapon" pattern: a **distinctive premium/Fontshare header** + a **ubiquitous free body font**. You get identity where it counts and reliability where it matters.

---

## Implementation details that separate good from great

- **Body size:** ≥16px desktop, 18px is better for reading. Mobile: confirm x-height works at 14–16px.
- **Line height:** body 1.5–1.7; tight headings ~1.05–1.15.
- **Type scale:** set an intentional scale (e.g. 1.2–1.333 ratio) — don't eyeball every size.
- **Measure:** 60–75 characters per line for body text.
- **Weights:** use the family's real weights for hierarchy; avoid faux-bold.
- **Performance:** limit to 2 families; subset and `font-display: swap`; prefer variable fonts to ship fewer files. Self-host or preconnect to the foundry.
- **Letter-spacing:** tighten large display slightly; never letter-space lowercase body.

### Loading example (self-hosted Fontshare display + Google body)
```css
/* Display: Cabinet Grotesk (Fontshare, self-hosted woff2) */
@font-face {
  font-family: "Cabinet Grotesk";
  src: url("/fonts/CabinetGrotesk-Variable.woff2") format("woff2");
  font-weight: 100 900;
  font-display: swap;
}
:root {
  --font-display: "Cabinet Grotesk", system-ui, sans-serif;
  --font-body: "General Sans", system-ui, sans-serif;
  --font-mono: "JetBrains Mono", ui-monospace, monospace;

  /* intentional scale, not arbitrary px */
  --step--1: clamp(0.83rem, 0.8rem + 0.15vw, 0.9rem);
  --step-0:  clamp(1rem, 0.95rem + 0.25vw, 1.125rem);
  --step-1:  clamp(1.33rem, 1.2rem + 0.6vw, 1.6rem);
  --step-2:  clamp(1.78rem, 1.5rem + 1.3vw, 2.55rem);
  --step-3:  clamp(2.37rem, 1.9rem + 2.4vw, 4rem);
}
```

> When in doubt, the [ui-ux-pro-max-skill](../skills-and-tools/ecosystem.md) ships **57 font pairings** queryable by industry/style — use it as a lookup, then commit to one.
