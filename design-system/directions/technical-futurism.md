# Technical Futurism — Direction Definition

**Status:** draft / unvalidated
**Explorer preset:** `technical`
**Motion axis:** precision

---

## Core Intent

Communicate credibility through data-oriented hierarchy, dark surfaces, and luminous accents. The visual language signals engineering depth — the brand understands technical audiences because it speaks their visual dialect. Technical Futurism does not require a dark theme, monospace everywhere, or gratuitous sci-fi decoration.

## Principle

Dark surfaces, luminous accents, data-oriented hierarchy. Information density is a feature, not clutter. Every element earns its place by serving comprehension.

---

## Invariants (non-negotiable)

- Dark ground with high-contrast text (minimum WCAG AA on all body copy)
- Accent colors are luminous — they draw the eye to interaction points and data
- Monospace appears in at least one functional context (code, data labels, status)
- Typography is geometric sans-serif — no serifs, no decorative faces
- Border radius is moderate (8px) — not sharp, not soft
- Motion is precision-timed — no bounce, no overshoot, no playful easing

## Freedoms (adapt per project)

- Specific font families (Space Grotesk is the Explorer demo, not a requirement)
- Exact dark palette values — any dark ground that reads as technical
- Accent hue — indigo/cyan is the demo; project brief determines the real palette
- Grid density — can range from spacious dashboard to dense data view
- Whether code blocks appear at all (depends on audience technical literacy)

---

## Composition Repertoire

### 1. Split Hero with Data Visualization
Left column: kicker + headline + subtitle + dual CTAs.
Right column: abstract data visualization (node graphs, flow diagrams, grid patterns).
Hero headline at `clamp(2.5rem, 5vw, 4.5rem)`, weight 700, tracking -0.04em.

### 2. Code Block Exhibit
Terminal-style container with dot indicators (red/yellow/green) and filename header.
Syntax-highlighted YAML/JSON/code showing the product's configuration language.
Serves as both social proof ("we speak your language") and feature demonstration.

### 3. Three-Column Feature Grid
Icon + title + description per card. Cards sit on `--d-surface` against `--d-bg`.
Grid gap and padding are tighter than editorial — information density matters.
Section title centered above.

### 4. Stats Row
Large numbers with small labels beneath. Numbers use heading font at display weight.
Horizontal layout with implicit dividers (spacing, not lines).

---

## Typography

| Role | Explorer Demo Value | Guidance |
|------|-------------------|----------|
| Headings | Space Grotesk, 700, -0.04em | Geometric sans-serif. Must feel engineered. |
| Body | Inter, 15px | Highly legible at small sizes. Neutral. |
| Mono | JetBrains Mono | For code blocks, data labels, technical metadata |
| Hero size | clamp(2.5rem, 5vw, 4.5rem) | Smaller than editorial — density over drama |
| Section padding | clamp(48px, 7vw, 100px) | Tighter rhythm than editorial or luxury |

## Palette

| Token | Explorer Demo | Role |
|-------|--------------|------|
| `--d-bg` | #0a0a0f | Dark ground — near-black with subtle blue undertone |
| `--d-surface` | #12121a | Elevated cards and containers |
| `--d-text` | #e4e4eb | Primary text — warm white, not pure white |
| `--d-muted` | #8d8da3 | Secondary text, labels, metadata |
| `--d-accent` | #6366f1 | Primary accent — indigo, luminous on dark |
| `--d-accent-secondary` | #22d3ee | Secondary accent — cyan, for data highlights |
| `--d-hero-bg` | gradient 170deg #0a0a0f → #0f0f2a | Subtle depth on hero section |
| `--d-border` | #1e1e2e | Subtle dividers — visible but not dominant |
| `--d-radius` | 8px | Moderate rounding — technical, not playful |

Demo palette is indigo + cyan. Project palettes derive from the brief — the rule is "luminous on dark," not "must be indigo."

---

## Section Rhythm

1. **Nav** — Brand left, links center-right, CTA button right
2. **Split Hero** — Text left, data visualization right
3. **Code Block** — Full-width terminal exhibit (optional, depends on audience)
4. **Feature Grid** — 3-column on desktop, stacked on mobile
5. **Stats Row** — Horizontal proof points
6. **CTA Banner** — Centered headline + dual buttons
7. **Footer** — Minimal, single line

Sections flow quickly — no pull quotes or editorial pauses. The rhythm is functional: present, prove, convert.

---

## Graphics & Illustration

- Abstract data visualizations: node graphs, grid overlays, connection lines
- SVG-based, using CSS custom properties for colors (theme-responsive)
- Grid overlays with intersection markers suggest precision and measurement
- No photography unless the project brief supplies it
- No decorative illustration — every visual element implies a system or dataset

## Motion

**Axis:** precision
- Transitions are exact and fast — no wobble, no spring, no overshoot
- Easing: ease-out for enters, ease-in for exits (per shared `motion.md` Layer 2)
- Duration budget: 150–250ms for micro-interactions, 300–400ms for section reveals
- Code blocks may use a typewriter-style line reveal (optional)
- Data visualizations may animate on scroll — lines drawing, nodes appearing sequentially

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Remove transform-based movement; keep content visible immediately. Data visualizations render in final state.

```css
@media (prefers-reduced-motion: reduce) {
  .reveal, .node, .line-draw {
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
| ≥1024px | Full split hero, 3-col features, code block at comfortable width |
| 768–1023px | Hero stacks (text above visual), 2-col features, code block scrolls |
| <768px | Single column throughout, code block horizontally scrollable, stats stack vertically |

---

## Review Criteria

A Technical Futurism composition passes review when:

1. Dark surfaces dominate — the page feels like a tool, not a brochure
2. Accent colors are luminous and purposeful — they highlight, not decorate
3. At least one element uses monospace in a functional way
4. Typography hierarchy is clear at a glance — heading/body/label are distinct
5. Information density feels intentional — not cramped, but not wasteful
6. Motion is crisp and fast — nothing bounces or lingers
7. All text passes WCAG AA contrast on its background
8. Code or data exhibits feel authentic (realistic syntax, not lorem ipsum)

---

## Integration Plan

1. Load this definition before developing a Technical Futurism proposal
2. Run `draw.mjs` to generate direction options — use this spec to evaluate fit
3. Derive project-specific fonts, palette, and density from the brief
4. Explorer values are demonstrations — they set the tone, not the exact tokens
5. Record chosen interpretation in the project's `DESIGN.md`
6. Validate with `lint.mjs` and `inspect.mjs` before presenting
