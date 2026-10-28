# Luxury Minimalism — Direction Definition

**Status:** draft / unvalidated
**Explorer preset:** `luxury`
**Motion axis:** restrained

---

## Core Intent

Communicate quality through restraint. Generous negative space, whisper-weight typography, and muted tones signal that the brand doesn't need to shout — it has nothing to prove. Luxury Minimalism does not require fashion imagery, gold accents, or aspirational lifestyle photography — it requires the discipline to leave space empty.

## Principle

Clean sans-serif, wide tracking, generous negative space. What you remove communicates as much as what you keep. Every element that remains must justify its presence.

---

## Invariants (non-negotiable)

- Border radius is zero — sharp edges signal precision and intent
- Heading weight is light (300) with wide letter-spacing (0.12em)
- Section padding is the most generous of all directions — space is the luxury
- Palette is muted and neutral — stone/warm grey tones, no saturated color
- Accent color is the text color itself (#1c1917) — no separate "brand color"
- Borders are subtle — thin, warm grey, barely there

## Freedoms (adapt per project)

- Specific font families (Inter + DM Sans are Explorer demos)
- Whether any color accent exists at all (some luxury brands use none)
- Background temperature — cool white, warm white, or subtle cream
- Photography treatment — if photography exists, it should be full-bleed and editorial
- Density of content — can range from single-message pages to curated collections

---

## Composition Repertoire

### 1. Centered Hero with Breathing Room
Centered text stack: kicker (uppercase, tracked) + headline + subtitle + dual CTAs.
Optional: subtle abstract SVG above the headline (geometric, barely visible).
Hero headline at `clamp(2rem, 4.5vw, 3.5rem)` — the smallest hero of all directions. The restraint IS the statement.

### 2. Three-Column Feature Grid
Icon + title + description per card. Cards are barely differentiated from background — `--d-surface` (#fafaf9) is nearly white.
No visible card borders. Spacing between cards does the work of containment.
Section has centered header with title + subtitle.

### 3. Stats Row
Numbers in heading font at light weight with wide tracking.
Subtle section header above. Numbers speak quietly but clearly.

### 4. CTA Banner
Centered headline + description + dual buttons.
Buttons have zero radius, thin borders, generous padding.
The entire section breathes — padding is maximum.

---

## Typography

| Role | Explorer Demo Value | Guidance |
|------|-------------------|----------|
| Headings | Inter, 300, 0.12em | Light weight + wide tracking = quiet confidence |
| Body | DM Sans, 15px | Slightly smaller than other directions — refinement in scale |
| Mono | DM Mono | For metadata, timestamps, technical details only |
| Hero size | clamp(2rem, 4.5vw, 3.5rem) | The smallest hero — restraint is the point |
| Section padding | clamp(72px, 10vw, 160px) | The most generous — space is the luxury |

The wide tracking on headings (0.12em) is a signature. It transforms any sans-serif into a luxury voice. This is the single most important typographic decision in the direction.

## Palette

| Token | Explorer Demo | Role |
|-------|--------------|------|
| `--d-bg` | #ffffff | Pure white ground |
| `--d-surface` | #fafaf9 | Barely-there card elevation — Stone 50 |
| `--d-text` | #1c1917 | Warm near-black — Stone 900 |
| `--d-muted` | #78716c | Warm grey secondary — Stone 500 |
| `--d-accent` | #1c1917 | Accent IS the text color — no separate brand hue |
| `--d-accent-secondary` | #a8a29e | Warm stone — Stone 400, for subtle highlights |
| `--d-hero-bg` | #fafaf9 | Barely warmer than white — Stone 50 |
| `--d-border` | #e7e5e4 | Whisper-thin borders — Stone 200 |
| `--d-radius` | 0px | Zero. Sharp edges signal precision. |

The absence of a saturated accent color is a deliberate choice. The brand's confidence comes from restraint, not from a color shouting for attention. Projects may add a single muted accent if the brief requires it — but it should feel discovered, not imposed.

---

## Section Rhythm

1. **Nav** — Brand left, links center-right, CTA button right (all sharp, thin borders)
2. **Centered Hero** — Maximum breathing room, optional abstract SVG, tracked headline
3. **Feature Grid** — 3-column on desktop, generous gaps, barely-visible cards
4. **Stats Row** — Light-weight numbers with wide tracking
5. **CTA Banner** — Centered with maximum padding above and below
6. **Footer** — Minimal, single line

The rhythm is slow and deliberate. Each section has more vertical padding than any other direction. The page scrolls longer but feels calmer.

---

## Graphics & Illustration

- Abstract geometric SVGs: single circles, intersecting lines, minimal marks
- Extremely subtle — low opacity (0.15–0.3), thin strokes (0.3–0.5px)
- Graphics suggest precision and care, never demand attention
- Full-bleed photography if available (editorial treatment, desaturated)
- No icons unless absolutely necessary — text labels preferred
- No decorative elements — if it doesn't communicate, it's removed

## Motion

**Axis:** restrained
- Transitions are slow and graceful — the page unfolds, it doesn't snap
- Easing: ease-out with longer duration (per shared `motion.md` Layer 2)
- Duration budget: 200–300ms for micro-interactions, 400–600ms for section reveals
- Elements fade in with subtle opacity transition — no transform, no slide
- Hover states are gentle opacity shifts, not color changes
- Nothing should feel fast — speed implies urgency, and luxury has no urgency

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Already minimal — remove the fade transitions that remain. Content appears immediately.

```css
@media (prefers-reduced-motion: reduce) {
  .reveal, .fade {
    opacity: 1 !important;
    transition: none !important;
  }
}
```

---

## Responsive

| Breakpoint | Adaptation |
|-----------|------------|
| ≥1024px | Full centered hero, 3-col features, maximum section padding |
| 768–1023px | Hero padding reduces slightly, 2-col features, breathing room preserved |
| <768px | Single column, hero text stays small (restraint maintained), section padding reduces to clamp minimum, stats stack vertically |

On mobile, resist the urge to increase the hero text size. The restraint should hold at every viewport. The page should feel calm on a phone, not cramped.

---

## Review Criteria

A Luxury Minimalism composition passes review when:

1. The page feels calm — scrolling it is a quiet experience
2. Negative space is the dominant visual element — more empty than filled
3. Heading tracking is wide (0.12em+) — the signature is visible
4. Heading weight is light (300) — no bold headlines
5. Zero border radius everywhere — sharp edges, no exceptions
6. No saturated accent color screams for attention
7. Section padding is generous — the most of any direction
8. All text passes WCAG AA contrast (critical — low-contrast palettes are risky)
9. Nothing feels busy, urgent, or promotional

---

## Integration Plan

1. Load this definition before developing a Luxury Minimalism proposal
2. Run `draw.mjs` to generate direction options — use this spec to evaluate fit
3. Derive project-specific palette warmth and photography treatment from the brief
4. Explorer values are demonstrations — they set the tone, not the exact tokens
5. Record chosen interpretation in the project's `DESIGN.md`
6. Validate with `lint.mjs` and `inspect.mjs` before presenting
