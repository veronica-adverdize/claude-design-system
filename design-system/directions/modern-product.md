# Modern Product — Direction Definition

**Status:** draft / unvalidated
**Explorer preset:** `product`
**Motion axis:** systematic

---

## Core Intent

Communicate reliability through clean hierarchy, systematic components, and polished interaction states. The visual language says "this product works well" before the user reads a word. Modern Product does not require blue, card-based layouts, or SaaS clichés — it requires systematic thinking made visible.

## Principle

Clean hierarchy, systematic components, polished states. Every element belongs to a system. Consistency builds trust faster than novelty.

---

## Invariants (non-negotiable)

- Light ground with clear content hierarchy (headline → body → metadata)
- Components feel systematic — consistent spacing, radius, and elevation
- Border radius is generous (12px) — approachable, polished, modern
- Trust signals appear early (logos, stats, or social proof near the hero)
- Typography uses a workhorse sans-serif — readable at every size, every weight
- Motion is systematic — same easing, same duration class, everywhere

## Freedoms (adapt per project)

- Specific font families (Plus Jakarta Sans + Inter are Explorer demos)
- Accent hue — blue is the demo; any confident, accessible color works
- Whether trust logos appear (depends on available social proof)
- Card density — from spacious marketing to denser product UI
- Gradient usage — hero gradient is optional, solid backgrounds work too

---

## Composition Repertoire

### 1. Centered Hero with Product Visual
Centered text stack: kicker + headline + subtitle + dual CTAs.
Below: product screenshot, dashboard mockup, or abstract product illustration.
Hero headline at `clamp(2.5rem, 5vw, 4rem)`, weight 800, tracking -0.03em.

### 2. Trust Logo Bar
"Trusted by teams at" label above a row of greyscale company logos.
Placed immediately after the hero — proof before features.
Logos are muted/desaturated, not competing with the product's own palette.

### 3. Three-Column Feature Grid
Icon + title + description per card. Cards sit on `--d-surface` (#f8fafc) against white.
Generous radius (12px) and subtle border. Even spacing throughout.
Section has centered header with title + subtitle.

### 4. Stats Row
Large numbers with small labels. Numbers use heading font at display weight.
Horizontal layout with section header above ("Trusted by teams who ship").

---

## Typography

| Role | Explorer Demo Value | Guidance |
|------|-------------------|----------|
| Headings | Plus Jakarta Sans, 800, -0.03em | Friendly but authoritative. Heavy weight signals confidence. |
| Body | Inter, 16px | The default workhorse. Clear at all sizes. |
| Mono | IBM Plex Mono | For technical contexts only — API keys, code snippets |
| Hero size | clamp(2.5rem, 5vw, 4rem) | Moderate — product speaks through UI, not giant text |
| Section padding | clamp(48px, 7vw, 96px) | Balanced rhythm — not rushed, not luxurious |

## Palette

| Token | Explorer Demo | Role |
|-------|--------------|------|
| `--d-bg` | #ffffff | Clean white ground |
| `--d-surface` | #f8fafc | Subtle card elevation — Slate 50 |
| `--d-text` | #0f172a | Near-black text — Slate 900 |
| `--d-muted` | #64748b | Secondary text — Slate 500 |
| `--d-accent` | #2563eb | Primary accent — Blue 600, confident and accessible |
| `--d-accent-secondary` | #0ea5e9 | Secondary accent — Sky 500, for highlights |
| `--d-hero-bg` | gradient 180deg #eff6ff → #ffffff | Subtle blue wash fading to white |
| `--d-border` | #e2e8f0 | Standard border — Slate 200 |
| `--d-radius` | 12px | Generous rounding — modern and approachable |

Demo palette uses Tailwind's blue/slate scale. Project palettes can use any hue — the rule is "systematic and accessible," not "must be blue."

---

## Section Rhythm

1. **Nav** — Brand left, links center, CTA button right
2. **Centered Hero** — Text stack, CTAs, product visual below
3. **Trust Bar** — Company logos with label (optional, depends on available proof)
4. **Feature Grid** — 3-column on desktop, stacked on mobile
5. **Stats Row** — Horizontal proof with header
6. **CTA Banner** — Centered headline + dual buttons
7. **Footer** — Minimal, single line

The rhythm alternates: claim → proof → claim → proof → convert. Every section either states value or proves it.

---

## Graphics & Illustration

- Product UI mockups: dashboard screenshots, app interfaces, data views
- Abstract product illustrations using SVG with clean geometric shapes
- Charts and graphs inside product mockups (line charts, bar charts)
- Trust logos in greyscale/muted treatment
- No photography unless the project brief supplies it
- Illustrations serve comprehension — they show what the product does

## Motion

**Axis:** systematic
- Every transition uses the same easing curve — no per-element variation
- Easing: ease-out for all entrances (per shared `motion.md` Layer 2)
- Duration budget: 150–200ms for micro-interactions, 250–350ms for section reveals
- Cards and features fade-up on scroll with staggered delay (50–100ms between items)
- Hover states are instant (opacity/color shift, no transform)

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Remove transform-based movement; keep fade-in for comprehension. All content visible immediately.

```css
@media (prefers-reduced-motion: reduce) {
  .fade-up, .reveal {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
  }
}
```

---

## Responsive

| Breakpoint | Adaptation |
|-----------|------------|
| ≥1024px | Full centered hero with product visual, 3-col features, trust logos in row |
| 768–1023px | Hero visual scales down, 2-col features, trust logos wrap |
| <768px | Single column throughout, hero visual may hide, stats stack vertically, trust logos scroll horizontally |

---

## Review Criteria

A Modern Product composition passes review when:

1. The page reads as a product — systematic, reliable, polished
2. Components feel like they belong to the same system (consistent radius, spacing, borders)
3. Trust signals appear before the fold or immediately after the hero
4. Typography hierarchy is effortless to scan — you can skim the page in 3 seconds
5. Accent color is used sparingly — for CTAs and key highlights only
6. Motion feels coordinated — everything moves the same way at the same speed
7. All text passes WCAG AA contrast on its background
8. No decorative elements exist without a communication purpose

---

## Integration Plan

1. Load this definition before developing a Modern Product proposal
2. Run `draw.mjs` to generate direction options — use this spec to evaluate fit
3. Derive project-specific fonts, palette, and component density from the brief
4. Explorer values are demonstrations — they set the tone, not the exact tokens
5. Record chosen interpretation in the project's `DESIGN.md`
6. Validate with `lint.mjs` and `inspect.mjs` before presenting
