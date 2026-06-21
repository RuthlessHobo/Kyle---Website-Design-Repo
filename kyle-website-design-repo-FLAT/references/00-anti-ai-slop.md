# 00 — Anti-AI-Slop: The Tell List

The goal of this whole repo in one page. "AI slop" is the wave of identical, forgettable sites that all default to the same fonts, the same purple gradient, and the same rounded cards. The cause is not the model — it's *missing constraints*. A model with no direction outputs the statistical average of its training data. This file is the list of averages to refuse.

---

## Why it happens (so you can recognize it mid-build)

A model trained on the whole web optimizes for **probability, not originality**. Ask for "a modern SaaS site" and it returns the most common thing it has seen: hero → three feature cards → testimonials → pricing → CTA, in Inter, with an indigo gradient. It's doing exactly what it was trained to do. The fix is to make the design decisions *before* generation and feed them in as hard constraints — which is what `DESIGN.md` enforces.

A compounding cause: the training data now contains a lot of *previous* AI output, so the averages are getting more average over time. The famous example — Tailwind UI shipped `bg-indigo-500` as a neutral demo default years ago; it propagated through thousands of tutorials and starter templates; models learned "accent = indigo"; their output became training data; the web is now measurably more purple. Don't feed the loop.

---

## The bans, with the reasoning

### Color
| Banned by default | Why it's a tell | Do instead |
|---|---|---|
| Indigo/violet/purple accent | The single most recognizable AI signature; came from one Tailwind default | Derive an accent from the subject's real world (see `02-color.md`) |
| Blue→purple hero gradient | Median of every Tailwind landing page | A flat, confident color; or a gradient pulled from a real material/photo |
| Uniform `0.1`-opacity shadow on every card | "Technically clean, emotionally invisible" | Vary elevation intentionally; some elements flat, some lifted |

### Typography
| Banned by default | Why | Do instead |
|---|---|---|
| Inter/Roboto as the whole identity | Instantly recognized as the default stack | Characterful display face + restrained body face (`01-typography.md`) |
| 5+ type styles in one hero | A human typographer almost never lands here; it's visual noise | Max 3 visible roles; hierarchy through scale/weight, not new styles |
| Decorative extra label styles "to look designed" | The model adding cleverness that *reduces* clarity | If a style doesn't carry information, delete it |

### Layout & structure
| Banned by default | Why | Do instead |
|---|---|---|
| Three/four even feature cards | The default section shape | Asymmetry, varied card sizes, an editorial layout, a real screenshot |
| Identical radius + padding + card height everywhere | Flat, undifferentiated; "AI-built sites use identical everything" | Intentional variation creates hierarchy |
| Numbered markers (01/02/03) on non-sequential content | Decoration pretending to be structure | Only number things that are actually ordered (a real process/timeline) |
| Inconsistent aesthetic across sections | Happens when sections are generated separately | Lock one anchor up front (`aesthetic-directions/`) |

### Motion
| Banned by default | Why | Do instead |
|---|---|---|
| Same fade-in-on-scroll on every element | The model's reflex; reads as canned | One orchestrated moment > scattered effects (`04-motion.md`) |
| Cursor-chasing / scroll-following lines | "For no discernible reason" | Motion only where it explains the product |
| Hover that fades the button into the background | Opposite of what hover is for | Hover should make the target *more* prominent/clear |

### Imagery
| Banned by default | Why | Do instead |
|---|---|---|
| AI-generated illustrations | "Slightly too smooth, too symmetrical, plastic quality" | Real photography, real product shots, real screenshots, or hand-made/SVG marks |
| Generic stock photos | Says nothing; everyone has them | The client's actual work, places, people, tools |

### The "designer-AI" defaults (the second-order cliché)
When a model tries to *avoid* slop, it tends to land on one of three looks. They're legitimate for some briefs but have become their own defaults — don't reach for them unless the brief names them:
1. Cream (`~#F4F1EA`) + high-contrast serif + terracotta.
2. Near-black + single acid/vermilion accent.
3. Broadsheet: hairline rules, zero radius, dense columns.

---

## The single test for any element

> **Does this choice help someone understand what this business does and why to trust it — or does it just make the page busier / "look like a website"?**

Animations, labels, dividers, gradients, cards: each must pass. If it only adds polish-for-polish's-sake, it's slop. Keep what carries meaning; cut the rest. (This is also the Chanel rule from the build sequence: remove one accessory before shipping.)

---

## Sources
- Y Combinator design review (Gustaf Alströmer + Raphael Schaad) on vibe-coded sites — the hero-style-count and motion-purpose points.
- "Why every AI-built website looks the same (blame Tailwind's indigo-500)" — the color-propagation feedback loop.
- 925studios "AI slop web design guide" — identical padding/radius, plastic illustrations, dead hover states.
- Anthropic `frontend-design` skill — the three designer-AI default looks; spend-boldness-in-one-place; the Chanel rule.
