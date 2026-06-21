# Reference Sources — The Wider Toolkit

Dribbble and 21st.dev are the two anchors (separate files). This is the supporting cast — where to source live-site inspiration, real UX patterns, fonts, color, icons, and assets. The same rule applies everywhere: **extract a justifiable move, rebuild it against the quality floor, keep one coherent voice.**

---

## Live-site & landing-page inspiration (real, shipping sites — higher signal than mockups)
- **Land-book** — curated landing pages, filterable by style/industry. Best for full-page structure.
- **Godly** (godly.website) — "astronomically good" web design; bold, current art direction.
- **Refero** / **Mobbin** — real app & web UI flows; excellent for *patterns* (onboarding, pricing, checkout) and how real products solve a screen.
- **Lapa Ninja**, **SaaS Landing Page**, **One Page Love** — landing-page galleries.
- **Httpster**, **Awwwards**, **The FWA** — high-craft / experimental (use for ideas, not for conversion-page realism).
- **Minimal Gallery**, **SiteInspire** — for restrained/minimal directions done well.

## Component & code structure
- **21st.dev** (anchor — see its file), **shadcn/ui**, **Aceternity UI**, **Magic UI**, **HyperUI**, **Tailwind UI**. Treat all as structure; re-skin to the anchor (they share the generic defaults out of the box).

## Typography
- **Fontshare** (free, characterful — General Sans, Cabinet Grotesk, Clash Display, Satoshi).
- **Google Fonts** (free workhorses + display).
- **Fontesk**, **Velvetyne** (free, distinctive/experimental), **Pangram Pangram**, **Klim**, **Colophon**, **CoType** (premium hero faces).
- **Fontpair** / **Typewolf** — pairings and real-world type-in-use. `references/01-typography.md` has committed recipes.

## Color
- **Coolors**, **Realtime Colors** (preview a palette live on a UI), **Khroma** (AI palette from your taste), **Happy Hues** (palettes shown in context).
- Best source remains the **subject's own world / product photography** (`references/02-color.md`).

## Icons & logos
- **Lucide** (clean, consistent, the sensible default set), **Phosphor**, **Tabler**, **Heroicons**.
- **SVGL** (brand logos as SVG — also wired into the 21st.dev Magic MCP).

## Imagery & texture (kill the "AI plastic" look with real assets)
- **Unsplash**, **Pexels** — only as placeholder; replace with the client's *real* photos before ship.
- **Haikei**, **Shapefest**, **unblur/grain generators**, subtle **noise/grain** overlays to de-plasticize gradients.
- For service clients: insist on **real job-site / product / team photography** — it's the single biggest "this is a real business" signal.

## Motion
- **GSAP** + ScrollTrigger, **Motion** (Framer Motion / Motion One). Study Dribbble interaction shots for ideas; build the one that serves the message (`references/04-motion.md`).

---

## How to feed references into Claude Design / Claude Code

- **Claude Design (claude.ai):** paste reference screenshots/links and describe the *specific moves* to adapt into the locked tokens. Keep `DESIGN.md` loaded so anti-slop rules bind.
- **Claude in Chrome / web capture** (if available): point it at a specific URL to capture structure/styling as a starting point, then re-skin to the anchor.
- **Claude Code:** drop screenshots in the repo, reference them in-prompt, and pair with the 21st.dev Magic MCP for real component code.

> Cap the reference set at ~6 strong moves. The skill is *subtraction* — assembling a hundred references makes a collage; choosing six and unifying them makes a design.
