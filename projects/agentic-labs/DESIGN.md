# Design Guidelines — Agentic Labs

**Direction:** Premium Editorial (definition: `design-system/directions/premium-editorial.md`)
**Status:** Draft — sample under construction, not approved
**Date:** 2026-10-28

## Creative thesis

Make Agentic Labs legible as a serious operational partner, not another AI chatbot. The design earns trust through intentional hierarchy: the dashboard UI is the exhibit — a purposeful, annotated interface that shows what the agents actually do. Typography and sequencing carry the argument; the page reads like a well-edited brief, not a feature grid. The composition suits an audience that doesn't browse tech products — it explains in plain English, one idea at a time.

**Chosen composition:** Annotated Exhibit (hero) + Chaptered Argument (supporting). From the definition's §4 repertoire. The exhibit works because the dashboard IS the offering — it's not decorative. The chaptered argument suits the three-problem structure and the before/after proof.

**Distinction from previous directions:** Direction-1-editorial used Instrument Serif and a split hero with a generic activity dashboard. This sample chooses a different type pairing (Newsreader + Inter), shifts the hero to a proposition-led layout with a deliberately annotated dashboard fragment, and structures the supporting sections as editorial chapters rather than card grids.

## Creative concept

On this page, **the owner's morning review list** becomes **the annotated exhibit the direction calls for**.

The morning review is specific to Agentic Labs' model: agents work overnight, the owner sees a short approval list over coffee. A competitor offering chatbots or DIY automation has no equivalent — their product has no "review and approve" moment. The review list passes the competitor test.

## Rule conflicts

| Taste house rule | Editorial definition | Resolution |
|---|---|---|
| No eyebrows (small label above heading) | Silent — does not require or ban them | **Remove kickers.** Put the information into the heading or first sentence. Taste is explicit; the definition doesn't need them. |
| No monospace outside code | Silent | **Keep monospace inside `data-ui` dashboard fragments only** (Taste exempts `data-ui` elements). Remove monospace from page-level labels, kickers, and trust signals. Use the text face (Inter) instead. |
| No index numbering (01/02/03) | §6 lists "numbered entries" as valid | **Remove numbering.** Taste bans it without exception. The problems section communicates order through position and the prose, not numbers. The definition lists it as an option, not a requirement. |
| No styled accent word in headline | Silent | **Remove italic emphasis from headlines.** Use one face, one weight. The words carry the emphasis — "You make the decisions" is strong without italic. |
| No thin rules / hairline dividers | Silent | **Replace problem-entry border-top with spacing and a tone step.** Use background colour change or increased gap instead of 1px borders. |

Inspector flags for conscious overrides: none needed after these resolutions. All Taste rules will be followed.

## Draft copy

**Hero headline:** "They handle the admin. You make the decisions." (48 chars — will check wrapping in browser at all widths; restructure if it exceeds two lines.)

**Hero supporting line:** "AI staff that handle quotes, scheduling, and follow-ups for your business — and check with you before anything goes out."

**Section 2 heading:** "The work that falls through" (27 chars)

**Section 3 heading:** "Your morning takes four minutes" (31 chars)

## Reference evidence

- **Calendly** (A1 Gallery, screenshot inspected): Editorial serif landing for scheduling/AI software. Centered serif headlines, product UI as hero visual, light ground, blue tones. Observed: Geist font, beige/blue palette, editorial + typographic + serif styles. Applicable principle: product interface as exhibit, not decoration.
- **A1 hero norms** (measured, 321 landing-page heroes): Median heading 64px, body 18px, scale 3.6:1, padding 120px, container 1272px. Informed our sizing decisions.

## Typography

**Display:** Newsreader 300 (Google Fonts) — editorial serif with character, lighter than Instrument Serif. Italic available for pull-quotes.
**Body:** Inter 400/500 (Google Fonts) — proven at small sizes, familiar, neutral.
**Mono:** JetBrains Mono 400 (Google Fonts) — labels, tags, agent identifiers.

| Role | Family | Weight | Size | Tracking | Leading |
|------|--------|--------|------|----------|---------|
| Hero display | Newsreader | 300 | clamp(2.8rem, 1.5rem + 5vw, 4.5rem) | -0.02em | 1.05 |
| Section heading | Newsreader | 300 | clamp(2rem, 1rem + 3.5vw, 3rem) | -0.02em | 1.1 |
| Body | Inter | 400 | clamp(1rem, 0.95rem + 0.2vw, 1.125rem) | 0 | 1.65 |
| Label / kicker | JetBrains Mono | 400 | 0.75rem | 0.08em | 1 |
| UI text (dashboard) | Inter | 400/500 | 0.75–0.85rem | 0 | 1.4 |

## Color

```css
:root {
  --ground:       #f7f5f2;   /* warm off-white page ground */
  --surface:      #ffffff;   /* card/container backgrounds */
  --ink:          #1a1a1a;   /* primary text */
  --muted:        #595959;   /* secondary text — 5.9:1 on ground */
  --accent:       #2d5a3d;   /* deep green — trust, operational, not flashy */
  --accent-light: #e8f0eb;   /* light green tint for subtle highlights */
  --border:       #e5e2dd;   /* warm grey borders */

  /* Dashboard (dark surface) */
  --dash-bg:      #0f1117;
  --dash-surface: #1a1d27;
  --dash-border:  #2a2d3a;
  --dash-text:    #c8cad0;
  --dash-accent:  #4a9eff;
  --dash-green:   #3ecf8e;
  --dash-amber:   #f0b429;
}
```

**Palette logic:** Deep green accent (not the previous warm orange) signals reliability and operational steadiness. Warm off-white ground keeps the editorial feel without defaulting to beige. Dashboard uses the same dark palette as the existing direction for continuity — it's proven and readable.

## Layout

**Container:** max-width 1200px, centered. Slightly wider than 1128px to give the annotated exhibit room.
**Hero:** Two-column asymmetric — text (55%) + annotated dashboard exhibit (45%). Not a centered split.
**Sections:** Single column, max-width 720px for body text. Wider for exhibits and comparisons.
**Density:** Low in text sections, high within dashboard exhibits. Contrast is intentional.

## Spacing

```css
:root {
  --section-gap:   clamp(100px, 8vw, 140px);
  --inner-gap:     clamp(24px, 2.5vw, 40px);
  --gutter:        clamp(20px, 3vw, 48px);
}
```

## Component states

| State | Treatment |
|-------|-----------|
| Default | Flat, thin borders where needed |
| Hover | translateY(-1px) + border-color shift for cards; opacity 0.7 for text links |
| Focus | outline: 2px solid var(--accent); outline-offset: 3px |
| Active | translateY(0) |

**Button:** Solid rectangle. `--ink` background, `--ground` text. Inter 500, 0.85rem, letter-spacing 0.02em. Padding: 14px 28px. Border-radius: 3px. Secondary: ghost with 1px border.

## Graphics system

**Dashboard UI is the primary visual.** It communicates what the agents actually do. Requirements:
- Must be labeled "Worked example — illustrative" near every dashboard
- Readable annotations explaining specific agent actions
- Real-feeling but obviously fictional data (agent names from the brief, Singapore-contextual scenarios)
- Dark-mode dashboard surface for contrast against light page ground
- Coherent interface, not floating decorative cards

**No photography available.** Typography and the dashboard carry the page.

## Motion

**Entrance:** Fade-up, 20px translateY, 600ms, ease-out. Stagger siblings by 80ms.
**Dashboard elements:** Sequential reveal within the dashboard on scroll — stats first, then activity items (stagger 60ms each).
**Hover:** Cards and buttons get subtle lift (translateY(-1px), 200ms).
**Reduced motion:** Fewer and gentler, not zero (per shared `motion.md` decision). Remove transform-based movement; keep content visible immediately.

```css
@media (prefers-reduced-motion: reduce) {
  .fade-up {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
  }
}
```

## Section sequence (sample scope)

1. **Hero** — Proposition text (left) + annotated dashboard fragment (right). Fixed nav. Kicker: "AI staff for Singapore businesses". Headline: "They handle the admin. You make the decisions." Sub: one-paragraph plain English explanation. Two CTAs.
2. **Problems** — "The work that never quite gets done" — three numbered editorial entries, each with a heading and a short paragraph. Alternating rhythm, not a card grid.
3. **How it works** — Annotated exhibit of the morning review flow. Dashboard fragment (left) + explanatory text (right). Shows the daily 10-minute approval process.

## Responsive

| Breakpoint | Container | Hero layout |
|------------|-----------|-------------|
| ≥1024px | 1200px centered | Two-column (55/45) |
| 768–1023px | Fluid, 40px gutters | Stacked, dashboard below text |
| ≤767px | Fluid, 20px gutters | Stacked, dashboard below text, full-width |
