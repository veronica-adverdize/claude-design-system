# Expressive Brutalism — Direction Definition

**Status:** draft / unvalidated
**Explorer preset:** `brutalism`
**Motion axis:** confident

---

## Core Intent

Communicate conviction through bold type, high contrast, and hard edges. The visual language says "we have a point of view and we're not hedging." Expressive Brutalism does not require ugliness, broken grids, or anti-design posturing — it requires confident decisions made visible.

## Principle

Bold type, high contrast, hard edges, asymmetric compositions. Strip away everything that hedges. What remains is the message, presented with force.

---

## Invariants (non-negotiable)

- Border radius is zero — no rounding anywhere (buttons, cards, images)
- Borders are visible and structural — thick, dark, used as compositional elements
- Headline weight is maximum (900) with tight negative tracking (-0.05em)
- Hero text is large — `clamp(3rem, 7vw, 6.5rem)` — dominating the viewport
- Accent color is hot and unapologetic (red-orange in the demo, never pastel)
- No gradients — flat color fields only

## Freedoms (adapt per project)

- Specific font families (Outfit + DM Sans are Explorer demos)
- Accent hue — red-orange is the demo; any high-energy, high-contrast color works
- Background warmth — warm paper (#f5f0eb) or stark white
- Whether asymmetric layouts are literal (offset grids) or implied (weight imbalance)
- Level of "rawness" — from refined brutalism to deliberately rough

---

## Composition Repertoire

### 1. Split Hero with Geometric Abstract
Left column: kicker + oversized headline + subtitle + dual CTAs.
Right column: bold geometric shapes — overlapping rectangles, circles, thick lines.
Hero text is the dominant element. The visual supports, never competes.

### 2. Manifesto Statement
Full-width section with a single large statement.
Key word highlighted with accent color `<span>` treatment.
This section is the brand's voice at maximum volume — one sentence, no hedging.

### 3. Three-Column Feature Grid
Icon + title + description per card. Cards have zero radius and visible borders.
Bold section title above. Grid gap is tighter than other directions.

### 4. Stats Row
Numbers are oversized, displayed in heading font at maximum weight.
Hard lines or thick borders may separate stats instead of whitespace.

---

## Typography

| Role | Explorer Demo Value | Guidance |
|------|-------------------|----------|
| Headings | Outfit, 900, -0.05em | Maximum weight, tight tracking. Must feel bold. |
| Body | DM Sans, 16px | Clean and readable — the body balances the headline's intensity |
| Mono | Space Mono | For labels, metadata, technical details |
| Hero size | clamp(3rem, 7vw, 6.5rem) | The largest of all directions — headlines dominate |
| Section padding | clamp(48px, 6vw, 80px) | Tight — brutalism wastes nothing |

## Palette

| Token | Explorer Demo | Role |
|-------|--------------|------|
| `--d-bg` | #f5f0eb | Warm paper ground — not sterile white |
| `--d-surface` | #ffffff | Card surface — clean white against warm ground |
| `--d-text` | #0a0a0a | Near-black — maximum contrast |
| `--d-muted` | #5a5a5a | Secondary text — still high contrast |
| `--d-accent` | #ff3d00 | Primary accent — hot red-orange, unapologetic |
| `--d-accent-secondary` | #0a0a0a | Secondary accent — black itself, used as a color |
| `--d-hero-bg` | #f5f0eb | Same as background — no gradient, no fuss |
| `--d-border` | #0a0a0a | Borders are black and visible — structural, not decorative |
| `--d-radius` | 0px | Zero. Always zero. |

Demo palette is red-orange on warm paper. Project palettes can use any high-contrast, high-energy combination — the rule is "bold and unapologetic."

---

## Section Rhythm

1. **Nav** — Brand left, links center-right, CTA button right (all sharp corners)
2. **Split Hero** — Oversized text left, geometric abstract right
3. **Manifesto** — Single bold statement, full width
4. **Feature Grid** — 3-column on desktop, sharp-edged cards
5. **Stats Row** — Oversized numbers with hard dividers
6. **CTA Banner** — Centered headline + sharp-cornered buttons
7. **Footer** — Minimal, single line

The rhythm is punchy — statement, proof, statement, proof. No pauses for contemplation. No pull quotes softening the message.

---

## Graphics & Illustration

- Bold geometric shapes: overlapping rectangles, circles, thick structural lines
- Asymmetric compositions — elements deliberately overlap or break alignment
- SVG-based, using CSS custom properties for accent colors
- Thick structural lines as compositional elements (4px+ stroke weight)
- No photography unless the project brief supplies it
- No decorative illustration — geometry serves the composition's energy

## Motion

**Axis:** confident
- Transitions are direct and assertive — elements arrive with purpose
- Easing: ease-out with a slightly faster curve (per shared `motion.md` Layer 2)
- Duration budget: 100–200ms for micro-interactions, 200–350ms for section reveals
- Elements may slide in from hard edges (left/right, not fade-up)
- Manifesto text may animate word-by-word or letter-by-letter (sparingly)
- No spring physics, no bounce — that's playful territory

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Remove transform-based movement; keep content visible immediately.

```css
@media (prefers-reduced-motion: reduce) {
  .reveal, .slide-in, .manifesto-word {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
    animation: none !important;
  }
}
```

---

## Responsive

| Breakpoint | Adaptation |
|-----------|------------|
| ≥1024px | Full split hero, oversized type, 3-col features, geometric abstract at full scale |
| 768–1023px | Hero stacks (text above), type scales down but stays dominant, 2-col features |
| <768px | Single column, hero text fills width, manifesto wraps naturally, stats stack, geometric abstract simplifies or hides |

---

## Review Criteria

An Expressive Brutalism composition passes review when:

1. The page makes a strong first impression — you know the brand's stance immediately
2. Zero border radius everywhere — no rounded corners leaked through
3. Headline type dominates the viewport — it's the largest element on screen
4. Borders are visible and structural — they're part of the composition, not just edges
5. Accent color is used boldly but not everywhere — it's a shout, not background noise
6. The manifesto statement communicates the brand's conviction in one sentence
7. All text passes WCAG AA contrast on its background
8. Nothing feels tentative, soft, or hedging

---

## Integration Plan

1. Load this definition before developing an Expressive Brutalism proposal
2. Run `draw.mjs` to generate direction options — use this spec to evaluate fit
3. Derive project-specific fonts, palette, and level of rawness from the brief
4. Explorer values are demonstrations — they set the tone, not the exact tokens
5. Record chosen interpretation in the project's `DESIGN.md`
6. Validate with `lint.mjs` and `inspect.mjs` before presenting
