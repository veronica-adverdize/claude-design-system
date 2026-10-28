# Playful Contemporary — Direction Definition

**Status:** draft / unvalidated
**Explorer preset:** `playful`
**Motion axis:** energetic

---

## Core Intent

Communicate personality through expressive color, rounded forms, and energetic composition. The visual language says "we're approachable and we enjoy what we do." Playful Contemporary does not require cartoons, mascots, or childish aesthetics — it requires warmth and energy channeled through confident design decisions.

## Principle

Expressive color, rounded forms, energetic personality. The palette does the talking. Shapes are soft. The experience should feel like the brand is genuinely happy to see you.

---

## Invariants (non-negotiable)

- Border radius is generous (20px) — the roundest of all directions
- Two distinct accent colors that create visual energy through contrast
- Background has warmth — not white, not grey, something with personality
- Typography is friendly — rounded or geometric sans-serif, never stern
- Decorative background elements exist (blobs, gradients, soft shapes)
- At least one section breaks the grid with personality (testimonial, callout)

## Freedoms (adapt per project)

- Specific font families (Outfit + Plus Jakarta Sans are Explorer demos)
- Accent hue pair — purple + amber is the demo; any energetic pair works
- Background hue — warm yellow (#fefce8) is the demo, any warm tint works
- Level of decoration — from subtle background blobs to expressive illustrations
- Whether testimonials use cards, bubbles, or inline quotes
- Gradient complexity — simple two-color to multi-stop rainbow

---

## Composition Repertoire

### 1. Centered Hero with Background Decoration
Centered text stack: kicker + headline + subtitle + dual CTAs.
Behind everything: large, soft, overlapping colored shapes (circles, blobs) at low opacity.
The decoration creates energy without competing with the message.
Hero headline at `clamp(2.5rem, 5.5vw, 4.5rem)`, weight 700, tracking -0.02em.

### 2. Three-Column Feature Grid
Icon + title + description per card. Cards have generous radius (20px) and sit on white.
Grid has comfortable spacing. Cards may have subtle colored borders or shadows.
Section has centered header with title + subtitle.

### 3. Testimonial Card
Single testimonial in a rounded card with avatar, name, and role.
Avatar uses a colored circle placeholder if no photo available.
This is the personality section — the human voice in the design.

### 4. Stats Row
Numbers in heading font at bold weight. May use accent color for numbers.
Playful but not silly — the numbers are real, the treatment is warm.

---

## Typography

| Role | Explorer Demo Value | Guidance |
|------|-------------------|----------|
| Headings | Outfit, 700, -0.02em | Rounded terminals, friendly weight. Approachable. |
| Body | Plus Jakarta Sans, 16px | Warm and readable. Slightly more character than Inter. |
| Mono | IBM Plex Mono | For technical contexts only — codes, data |
| Hero size | clamp(2.5rem, 5.5vw, 4.5rem) | Generous but not dominating — energy comes from color, not scale |
| Section padding | clamp(48px, 7vw, 96px) | Balanced — playful doesn't mean cramped |

## Palette

| Token | Explorer Demo | Role |
|-------|--------------|------|
| `--d-bg` | #fefce8 | Warm yellow tint — Yellow 50 |
| `--d-surface` | #ffffff | Clean white cards against warm ground |
| `--d-text` | #1e1b4b | Deep indigo text — Indigo 950 |
| `--d-muted` | #4f46e5 | Muted text is ALSO a purple — cohesive palette |
| `--d-accent` | #7c3aed | Primary accent — Violet 600 |
| `--d-accent-secondary` | #f59e0b | Secondary accent — Amber 500, warm and energetic |
| `--d-hero-bg` | gradient 135deg #fef3c7 → #ede9fe → #dbeafe | Multi-stop gradient — warm to cool transition |
| `--d-border` | #e0e7ff | Soft indigo border — Indigo 100 |
| `--d-radius` | 20px | Maximum rounding — soft and approachable |

The dual-accent system (violet + amber) creates energy through complementary contrast. Project palettes should always have two distinct accent colors that play off each other — single-accent Playful loses its spark.

---

## Section Rhythm

1. **Nav** — Brand left, links center-right, CTA button right (all rounded, warm)
2. **Centered Hero** — Text over decorative background blobs/gradient
3. **Feature Grid** — 3-column on desktop, rounded cards on white
4. **Testimonial** — Single testimonial card with avatar (personality moment)
5. **Stats Row** — Warm proof points, may use accent color on numbers
6. **CTA Banner** — Centered headline + dual buttons, warm background
7. **Footer** — Minimal, single line

The rhythm includes a "personality moment" (testimonial) that other directions skip. This section humanizes the brand — it's the voice of a real person, not the company's marketing copy.

---

## Graphics & Illustration

- Soft decorative shapes: circles, ellipses, blobs at low opacity (0.05–0.15)
- Multi-layered — shapes overlap to create depth without competing
- Background shapes use accent colors at very low opacity
- Multi-stop gradients for hero and CTA sections
- Avatar placeholders as colored circles with initials
- No hard-edged geometry — everything rounds and softens
- Illustrations, if used, should be warm and human (not corporate)

## Motion

**Axis:** energetic
- Transitions have more personality than other directions — subtle bounce or overshoot is allowed
- Easing: spring-like ease-out (per shared `motion.md` Layer 2, with slightly more energy)
- Duration budget: 150–250ms for micro-interactions, 300–500ms for section reveals
- Background blobs may drift slowly on scroll (parallax at 0.1–0.2 ratio)
- Cards may scale slightly on hover (1.02–1.03, not more)
- Stagger delays between cards can be slightly longer (80–120ms) for playful cascade
- Buttons may have a gentle press animation (scale 0.97 on active)

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Remove transform-based movement and parallax. Keep opacity transitions. Background blobs render static.

```css
@media (prefers-reduced-motion: reduce) {
  .reveal, .blob, .card-hover {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
    animation: none !important;
  }
  .blob { animation-play-state: paused !important; }
}
```
In JS, skip scroll-triggered parallax and make all decorative elements static.

---

## Responsive

| Breakpoint | Adaptation |
|-----------|------------|
| ≥1024px | Full centered hero, background blobs at full scale, 3-col features, testimonial card at comfortable width |
| 768–1023px | Background blobs scale down or reduce in number, 2-col features, testimonial card narrows |
| <768px | Single column, background blobs simplify to 1–2, features stack, testimonial full-width, stats stack, gradient simplifies |

On mobile, reduce the number of decorative background elements. Two overlapping blobs at phone width feels cluttered. One subtle blob or a simple gradient maintains the warmth without the noise.

---

## Review Criteria

A Playful Contemporary composition passes review when:

1. The page feels warm and approachable — you'd want to use this product
2. Two distinct accent colors create visual energy through their contrast
3. Border radius is generous (20px) throughout — no sharp corners leaked through
4. Background has personality — warm tint, gradient, or decorative shapes
5. At least one section has a human voice (testimonial, quote, personal touch)
6. Typography feels friendly — rounded terminals, comfortable weight
7. Decorative elements enhance without competing — they're background, not foreground
8. All text passes WCAG AA contrast on its background (critical with warm/colored backgrounds)
9. The energy level is confident adult, not childish — playful, not silly

---

## Integration Plan

1. Load this definition before developing a Playful Contemporary proposal
2. Run `draw.mjs` to generate direction options — use this spec to evaluate fit
3. Derive project-specific accent pair, background warmth, and personality level from the brief
4. Explorer values are demonstrations — they set the tone, not the exact tokens
5. Record chosen interpretation in the project's `DESIGN.md`
6. Validate with `lint.mjs` and `inspect.mjs` before presenting
