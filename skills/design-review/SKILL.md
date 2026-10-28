---
name: design-review
description: Coordinates art direction, asset generation, animation, and UI refinement across a project. Use when starting a new surface, reviewing an existing design, or running a full quality pass. Sequences the installed skills in the correct order without duplicating their functionality.
---

# Design Review Orchestration

A coordination skill that sequences the workspace's installed tools for end-to-end design review and build workflows. It does not implement animations, generate images, or run audits itself — it delegates to the appropriate skill at each step.

## Available Skills (verified installed)

### Reference & Discovery
- **Taste Vault** (`tools/taste-vault/`) — Local design reference gallery with 46 entries across 12 collections. Browse at `http://127.0.0.1:4610` after starting `python server.py --port 4610`. Each entry has vocabulary, image recipe, and hero usage notes. "Copy design brief" generates a paste-ready prompt from any reference.
- **`reference-to-design`** (`.agents/skills/reference-to-design/SKILL.md`) — Guidance document for screenshot-led design exploration. Claude reads and follows this when the user provides references. Not auto-invoked; read it when starting step 2 below. Source: [cth9191/taste-vault](https://github.com/cth9191/taste-vault).
- **A1 Gallery** (`a1-gallery:reference`, `a1-gallery:tokens`, `a1-gallery:pairings`, `a1-gallery:design-reference`, `a1-gallery:section-rebuild`) — MCP-backed discovery of curated websites, font pairings, design tokens, and section patterns.

### Direction & Refinement
- **`design-taste-frontend`** (Taste Skill v2, `.agents/skills/design-taste-frontend/`) — Art direction for landing pages, marketing sites, portfolios, and app screens. Deals researched directions from a library of 247 curated sites via `scripts/draw.mjs`, enforces a no-slop house style via `scripts/inspect.mjs`, and finds open-archive imagery via `scripts/assets.mjs`. Requires Node 22+ and Chrome/Edge/Chromium.
- **`frontend-design:frontend-design`** — Aesthetic direction and typography guidance.
- **`impeccable:impeccable`** — UI refinement: `shape`, `critique`, `audit`, `polish`, `bolder`, `quieter`, `animate`, `adapt`, `harden`, `clarify`, `document`, and more. See Impeccable's command table for the full list.

### Motion — Three Layers
- **Layer 1 — Pattern catalog:** `interaction-design` — Microinteractions, state transitions, feedback, gestures, scroll reveals, navigation patterns.
- **Layer 2 — Timing and feel:** Easing guidance from `animation-vocabulary` (naming) and `animate` §5 (curve selection, duration budgets, spring configs). Shared tokens in `design-system/tokens.css`.
- **Layer 3 — Implementation and review:**
  - `animate` — Build animations from scratch.
  - `animation-performance` — Diagnose and fix jank.
  - `review-animations` — Critique specific animations.
  - `improve-animations` — Audit codebase-wide.
  - `find-animation-opportunities` — Scan for missing motion.

### Asset Generation
- **`nano-banana:generate`** — Image generation via Google Gemini (Flash, Pro, or Nano Banana 2). Requires `GEMINI_API_KEY`.

### Supporting Skills
- `animation-vocabulary` — Name identification for motion effects.
- `apple-design` — Apple HIG patterns.
- `pick-ui-library` — Component library selection.
- `prototype` — Build prototypes.
- `break-ui` — Stress-test UI edge cases.
- `context-engineering-collection` — Agent orchestration patterns.

## Workflow: New Surface

Use when creating a new page, feature, or project surface.

```
1. PRODUCT CONTEXT
   └─ Verify PRODUCT.md exists (run /impeccable init if not)

2. REFERENCES (optional but recommended)
   ├─ Browse Taste Vault for relevant references (by collection, vocabulary, or industry)
   ├─ Or: a1-gallery:reference → discover new sites matching the brief
   ├─ Read .agents/skills/reference-to-design/SKILL.md for the exploration process
   ├─ Inspect actual screenshots, record observations, write direction cards
   ├─ Handoff to step 3: vocabulary and direction cards inform draw.mjs arguments
   └─ Output: evidence-grounded direction cards with carry-over and invent decisions

3. ART DIRECTION
   ├─ design-taste-frontend → deal visual directions via draw.mjs:
   │     node .agents/skills/design-taste-frontend/scripts/draw.mjs \
   │       --sector <sector> --brief "<one line>" --sections <roles> \
   │       [--tone quiet|bold|warm|technical|playful|luxury|editorial] \
   │       [--have photography,product-ui,...] --options 3
   │     Then: --direction <chosen id> for the full sheet
   ├─ Informed by reference direction cards when available
   ├─ Choose a direction
   └─ For comp-first surfaces: nano-banana:generate → hero/key visual

4. PATTERN SELECTION (Layer 1)
   └─ interaction-design → select behavioral patterns
      (loading states, feedback, gestures, transitions, scroll reveals)

5. TIMING & FEEL (Layer 2)
   ├─ animation-vocabulary → name the effects being used
   ├─ animate §5 → choose easing curves and durations
   └─ Verify against design-system/tokens.css shared values

6. IMPLEMENTATION (Layer 3)
   ├─ animate → build each animation
   ├─ animation-performance → verify frame budget
   └─ Reduced motion and hover gating ship with each animation

7. REFINEMENT
   ├─ impeccable:impeccable critique → UX heuristic review
   ├─ impeccable:impeccable polish → final quality pass
   └─ impeccable:impeccable adapt → responsive verification

8. VALIDATION
   ├─ Browser: screenshots at 375px, 768px, 1280px
   ├─ Accessibility: keyboard navigation, contrast, screen reader
   ├─ Reduced motion: toggle prefers-reduced-motion, verify
   └─ Performance: no jank, no layout shift
```

## Workflow: Animation Review

Use when reviewing or improving animations in an existing project.

```
1. AUDIT
   ├─ find-animation-opportunities → where motion is missing
   └─ improve-animations → what existing motion needs work

2. DIAGNOSE
   └─ animation-performance → find dropped frames, wrong properties

3. NAME & ALIGN
   └─ animation-vocabulary → confirm correct terminology

4. FIX
   ├─ animate → rebuild problem animations
   └─ review-animations → verify fixes meet quality bar

5. VALIDATE
   ├─ Reduced motion behavior
   └─ Performance on mid-range device
```

## Workflow: Design Quality Pass

Use before shipping or for periodic quality review.

```
1. impeccable:impeccable critique → UX heuristic scoring
2. impeccable:impeccable audit → a11y, perf, responsive checks
3. review-animations → motion quality review
4. animation-performance → frame budget verification
5. impeccable:impeccable polish → final refinements
6. Browser validation at target widths
```

## What This Skill Does Not Do

- Does not implement animations — delegates to `animate`.
- Does not generate images — delegates to `nano-banana:generate`.
- Does not run UI audits — delegates to `impeccable:impeccable`.
- Does not invent slash commands or duplicate existing skill functionality.
- Does not impose a visual style — each project owns its art direction.
