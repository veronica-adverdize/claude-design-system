# Design Guidelines — Yoga Instructor L.A.

**Direction:** The Place Carries It — adapted from The Frequency Architect
**Reference:** thefrequencyarchitect.co (A1 Gallery, measured tokens)
**Date:** 2026-10-28

## The idea

The photograph is the design. A full-bleed atmospheric image — golden L.A. light, outdoor practice, natural warmth — fills the hero and sets the emotional register. Text sits centered over the image, sparse and elegant: a light serif headline, a short descriptor, one action. Below the hero, the page breathes on warm blush grounds with generous spacing, centered typography, and thin decorative lines. The composition says: calm, personal, unhurried. The instructor's world does the talking; the design stays quiet enough to let it.

The reference (The Frequency Architect) uses this structure for a wellness practitioner — centered layout, atmospheric hero, elegant serif + clean sans, soft pink-lavender grounds, thin lines as ornament, scroll-triggered reveals. We keep the composition and adapt the palette to warmer earth tones that suit L.A. yoga.

## Typography

**Display:** Cormorant Garamond 300 (Google Fonts) — closest available match to PP Museum 300's character: light weight, high contrast, elegant serifs, negative tracking.

**Body:** DM Sans 400 (Google Fonts) — clean geometric sans, neutral and readable. Replaces Inter Tight from the reference.

```css
:root {
  --step-small: clamp(0.8125rem, 0.78rem + 0.15vw, 0.875rem);   /* 13–14px captions, credits */
  --step-body:  clamp(0.9375rem, 0.85rem + 0.4vw, 1.25rem);     /* 15–20px body */
  --step-lead:  clamp(1.25rem, 0.9rem + 1.5vw, 2rem);           /* 20–32px lead paragraphs */
  --step-h2:    clamp(2rem, 1rem + 4.5vw, 3.75rem);             /* 32–60px section headings */
  --step-h1:    clamp(2.5rem, 1.5rem + 6.5vw, 5.5rem);          /* 40–88px hero display */
}
```

| Role | Family | Weight | Size | Tracking | Leading |
|------|--------|--------|------|----------|---------|
| Hero display | Cormorant Garamond | 300 | `--step-h1` | -0.03em | 1.0 |
| Section heading | Cormorant Garamond | 300 | `--step-h2` | -0.03em | 1.1 |
| Lead paragraph | DM Sans | 400 | `--step-lead` | -0.01em | 1.3 |
| Body | DM Sans | 400 | `--step-body` | 0.01em | 1.5 |
| Button / label | DM Sans | 500 | 0.875rem | 0.06em | 1 |
| Caption / credit | DM Sans | 400 | `--step-small` | 0.01em | 1.3 |

**Scale ratios** (from reference measurements):
- Hero: 4:1 (heading 88px / body 20px)
- Sections: 3:1 (heading 60px / body 20px)
- Features: 1.4–1.9:1 (heading 26–32px / body 18–20px)

**Rules:**
- Headings: sentence case, never all-caps (except nav items and button labels)
- One italic use allowed per page: a single pull-quote or emphasis line in Cormorant Garamond 300 italic
- Maximum two lines for any headline at any viewport

## Color

```css
:root {
  --ground:       #faf8f6;    /* warm white page background */
  --ground-blush: #f5ece8;    /* warm blush section ground */
  --ink:          #0a0a0b;    /* near-black primary text */
  --ink-soft:     #3a3636;    /* secondary text, used sparingly */
  --accent:       #b07a5a;    /* warm terracotta — labels, lines, hover */
  --accent-light: rgba(176, 122, 90, 0.15); /* accent tint for subtle fills */
  --white:        #ffffff;    /* text on dark/photo backgrounds */
  --white-muted:  rgba(255, 255, 255, 0.8); /* secondary text on photos */
}
```

**Palette logic:**
- The reference uses cool lavender-pink (#f5e9ed, #f6eaed, #f8f1f5) with purple accent (#a369a3). We shift to warm blush (#f5ece8) with terracotta accent (#b07a5a) — grounded and L.A.-warm instead of ethereal.
- Near-black ink (#0a0a0b) for all body text — never grey for running copy.
- Accent appears only on thin lines, section labels, and hover states. Never on large fills.
- White text on photography uses a gradient scrim for legibility (see Surfaces).

**Contrast requirements:**
- Body text on ground: minimum 7:1
- Body text on blush: minimum 7:1
- Large text (≥24px or 18.66px bold) on photos with scrim: minimum 3:1
- Credits and hints: minimum 4.5:1 against their actual visual background

## Surfaces

```css
/* Page grounds */
--ground:       #faf8f6;    /* default page background */
--ground-blush: #f5ece8;    /* alternate section background */

/* Photo scrim — applied over hero and full-bleed images */
.scrim::after {
  background:
    linear-gradient(to bottom, rgba(10,10,11,0.25) 0%, rgba(10,10,11,0) 20%),
    linear-gradient(to bottom, rgba(10,10,11,0) 50%, rgba(10,10,11,0.15) 75%, rgba(10,10,11,0.5) 100%);
}
```

- No shadows anywhere
- No borders on containers
- No box-shadow, no elevation
- No gradients as decoration — only scrims over photographs for text legibility
- Sections alternate between `--ground` and `--ground-blush`

## Layout

**Container:** max-width 1128px, centered (`margin-inline: auto`). Matches the reference's measured container (1128–1260px).

**Alignment:** Center-aligned throughout — headings, body, buttons. This is the defining layout choice from the reference.

**Density:** Low. The reference measures 0.08–0.20 density across sections. Generous whitespace is structural, not decorative.

```css
:root {
  --container:   1128px;
  --gutter:      40px;       /* side margins desktop */
  --gutter-mob:  24px;       /* side margins mobile */
}
```

**Grid:** No visible grid. Single centered column or loose two-column for feature pairs. Content never spans full width except photographs and the footer.

## Spacing

```css
:root {
  --space-section:  clamp(100px, 8vw, 140px);   /* between sections */
  --space-inner:    clamp(28px, 3vw, 40px);      /* heading to body within a section */
  --space-element:  clamp(16px, 1.5vw, 24px);    /* between sibling elements */
  --space-hero-pad: clamp(120px, 10vw, 320px);   /* hero top padding above content */
}
```

Reference measurements:
- Section padding: 112–320px top/bottom
- Gap between elements: 16px
- Container max: 1128–1260px

## Navigation

- **Structure:** Centered logo (instructor name in serif uppercase) + hamburger button (circle outline, three thin lines) at top-left
- **Position:** Absolute over the hero, not fixed
- **Colors:** White on hero photograph. On scrolled sections (if implementing sticky): ink on ground
- **Logo:** Cormorant Garamond 300, 0.875rem, letter-spacing 0.14em, uppercase, centered, line-height 1.4
- **Hamburger:** 36×36px circle, 1px border rgba(255,255,255,0.3), three 14px lines

## Component states

| State | Treatment |
|-------|-----------|
| Default | Flat, no shadow, no border |
| Hover | `translateY(-1px)` + background lighten for buttons; `opacity: 0.6` for links |
| Focus | `outline: 2px solid var(--accent); outline-offset: 3px` |
| Active | `translateY(0)` + slight darken |
| Disabled | `opacity: 0.4`, no pointer events |

**Button:** One shape — solid rectangle, `--ground` background on photos, `--ink` background on light grounds. DM Sans 500, 0.875rem, letter-spacing 0.06em, uppercase. Padding: 16px 40px. No border-radius.

**Text links:** Underlined in `--ink` on light grounds, underlined in white on photos. No color change on hover, opacity shift only.

## Graphics system

**No client photography available.** Imagery plan:

1. **Illustrative reference images** from Unsplash/open collections — outdoor yoga, L.A. light, natural materials, studio spaces. All clearly marked as illustrative; final site requires the instructor's own photography.
2. **Thin decorative lines** — 1px strokes in `--accent` at 30% opacity, used as section dividers and ornamental elements. Inspired by the reference's line/pattern language.
3. **No illustrations, icons, or SVG decoration.** The design relies on photography and typography only.

**Photo treatment:**
- Full-bleed, edge-to-edge, always with scrim gradient for text legibility
- `object-fit: cover`, warm natural light preferred
- Never cropped to circles or rounded shapes
- One hero photograph per page; additional photos in content sections as full-width bands or centered within the container

**Minimum 4 photographs for a full page build, 6–8 preferred.**

## Motion

**Signature move:** Slow fade-up entrance — elements rise 24px and fade from 0 to 1 over 800ms with `ease-out`. Stagger children by 100ms.

```css
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

**Scroll triggers:** Each section's heading, body, and CTA animate on scroll-into-view using `IntersectionObserver` (threshold 0.15). The reference uses scroll animation throughout.

**Motion rules:**
- Transform and opacity only — no layout shifts
- Easing: `cubic-bezier(0.25, 0.1, 0.25, 1)` (ease-out family)
- Duration: 600–1000ms for entrances
- Stagger: 80–120ms between sibling elements
- Never animate horizontal movement — only vertical fade-up
- Hero content: visible immediately (no entrance delay on first screen)

**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Keep opacity transitions that aid comprehension; remove transform-based movement.
```css
@media (prefers-reduced-motion: reduce) {
  .reveal {
    opacity: 1;
    transform: none;
    transition: none;
  }
}
```
In JS, skip scroll-triggered animation and make all elements immediately visible.

**One muted video loop** where honest footage exists — the practice, the space, the light. Poster frame required. Pause when tab is hidden.

## Section sequence

1. **Hero** — Full-bleed photograph, centered name (serif uppercase) at top, centered display heading + descriptor + CTA at vertical center, scroll hint at bottom-left
2. **About** — Warm blush ground, centered serif heading, centered sans body (max 480px). Introduces the instructor and philosophy
3. **Practice / Classes** — Alternating ground, centered or loose two-column layout. [Class types placeholder — real content needed]
4. **Testimonials** — Centered pull-quotes in Cormorant Garamond italic, attribution below. [Real quotes needed — do not invent]
5. **Contact / Book** — Single centered CTA section, serif heading, one button. No form unless the instructor has a booking system
6. **Footer** — Minimal, centered: social links (uppercase sans) + legal + copyright. Matches reference's sparse footer structure

**Between sections:** Thin decorative line divider (1px, `--accent` at 30%, 80px tall, centered).

## Responsive

| Breakpoint | Container | Gutters | Heading scale |
|------------|-----------|---------|---------------|
| ≥1024px | 1128px centered | 40px | Full scale |
| 768–1023px | Fluid, 40px gutters | 40px | `--step-h1` caps at ~74px |
| ≤767px | Fluid, 24px gutters | 24px | `--step-h1` caps at ~40px |

**Mobile adjustments:**
- Hero: photograph fills viewport, text centered over it, CTA below descriptor
- Hamburger button: moves to 20px from left edge
- Section padding reduces to 100px top/bottom
- All text remains centered
- Headings: max 2 lines at any width
- Nav logo: 0.8125rem

## References that informed this direction

- **The Frequency Architect** (A1 Gallery, measured) — PP Museum 300 + Inter Tight, centered sparse layout, atmospheric hero, soft lavender-pink grounds (#f5e9ed), purple accent (#a369a3), thin decorative lines, scroll animation. Hero: 80px heading, 20px body, 4:1 scale, density 0.12, container 1260px. Sections: 60px heading, 112px padding, density 0.08–0.20.
- **Hero study v2** (this project) — Adapted reference with Cormorant Garamond + DM Sans, warm blush palette, same centered composition. Inspector-verified at 1440px, 768px, and 390px.

## Decisions log

| Date | Decision | Basis |
|------|----------|-------|
| 2026-10-28 | Direction: Place Carries It (Frequency Architect adaptation) | User selected reference site |
| 2026-10-28 | Type: Cormorant Garamond 300 + DM Sans | Closest Google Fonts match to PP Museum + Inter Tight |
| 2026-10-28 | Palette: warm blush + terracotta accent | Adapted from reference's lavender-pink to suit L.A. warmth |
| 2026-10-28 | Layout: centered, single column, 1128px container | Measured from reference |
| 2026-10-28 | Nav: centered logo + hamburger | Matches reference structure |
