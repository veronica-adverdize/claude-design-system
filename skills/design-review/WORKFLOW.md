# Design Review Workflow Reference

Detailed sequencing for the orchestration skill, with layer assignments and decision points.

## Layer Assignments

| Step | Layer | Skill | Decides |
|------|-------|-------|---------|
| Pattern selection | 1 — Interaction Design | `interaction-design` | Which behavioral pattern fits the UX need |
| Effect naming | 2 — Intentional Easing | `animation-vocabulary` | What the effect is called |
| Curve and timing | 2 — Intentional Easing | `animate` §5 | Which easing, which duration, spring vs. fixed |
| Token reference | 2 — Intentional Easing | `design-system/tokens.css` | Canonical CSS custom property values |
| Build animation | 3 — Implementation | `animate` | Code the animation following the decision sequence |
| Performance check | 3 — Implementation | `animation-performance` | Verify frame budget, diagnose jank |
| Quality review | 3 — Implementation | `review-animations` | Critique against quality standards |
| Codebase audit | 3 — Implementation | `improve-animations` | Find improvements across the project |
| Opportunity scan | 3 — Implementation | `find-animation-opportunities` | Identify where motion adds value |

## Decision Points

### Should this animate at all?

Before reaching for any layer, apply the frequency gate from `animate` §1:

| Frequency | Decision |
|-----------|----------|
| 100+ times/day (keyboard shortcuts, command palette) | No animation. Stop. |
| Tens of times/day (hovers, list navigation) | Near-imperceptible only |
| Occasional (modals, drawers, toasts) | Standard animation |
| Rare / first-time (onboarding, success) | Delight budget lives here |

### Which easing?

From `animate` §5. Decision order:

1. Entering or exiting → `--ease-out`
2. Moving on screen → `--ease-in-out`
3. Hover or color → CSS `ease`
4. Constant motion → `linear`
5. Default → `--ease-out`

Never `ease-in` on UI.

### CSS or JS?

From `animation-performance`:

- **CSS transitions/keyframes** for predetermined motion, especially during page load.
- **WAAPI** for programmatic control with CSS performance.
- **Motion (framer-motion)** for springs, layout animations, exit animations, gestures.
- **CSS for motion under load; JS for interactive motion.**

### Spring or fixed duration?

From `animate` §5:

Use springs when: drag with momentum, element should feel alive, gesture can be interrupted, decorative mouse-tracking.

Use fixed duration for everything else. Keep `bounce` at 0.1–0.3.

## Conflict Resolution Reference

| Topic | Layer 1 (interaction-design) | Layer 2 (Emil easing) | Resolution |
|-------|-----|------|------------|
| `--ease-out` value | `cubic-bezier(0.16, 1, 0.3, 1)` | `cubic-bezier(0.23, 1, 0.32, 1)` | **Layer 2 adopted** — enforced by review pipeline |
| `--ease-in-out` value | `cubic-bezier(0.65, 0, 0.35, 1)` | `cubic-bezier(0.77, 0, 0.175, 1)` | **Layer 2 adopted** — same reason |
| Reduced motion | Blanket kill (`0.01ms !important`) | Fewer and gentler, not zero | **Layer 2 adopted** — preserves comprehension aids |
| Duration model | Range-based table | Element-specific budgets with 300ms UI ceiling | **Layer 2 adopted** — more precise |

These resolutions are recorded in `docs/design-decisions.md`.
