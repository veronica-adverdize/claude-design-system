# Design Decisions

Approved shared decisions and project-specific exceptions. Each entry records what was decided, why, and its scope.

## Shared Decisions

| Date | Decision | Rationale | Status |
|------|----------|-----------|--------|
| 2026-10-22 | **Stack: delegated per project** | Next.js/React for interactive apps, Astro for content sites, static HTML/CSS/JS for lightweight sites. Existing frameworks preserved. | Active |
| 2026-10-22 | **Build path: comp-first** for landing/showcase surfaces | An AI-generated image (via Nano Banana) sets the visual bar before coding. Bolder composition; the build must match the image. App screens and documents are code-first. | Active |
| 2026-10-22 | **Per-project identity** | Each project owns its visual world. Shared tokens provide scale and rhythm, not a universal theme. | Active |
| 2026-10-22 | **Easing curves: Emil Kowalski's canonical values** | Adopted `cubic-bezier(0.23, 1, 0.32, 1)` for `--ease-out` and `cubic-bezier(0.77, 0, 0.175, 1)` for `--ease-in-out`. The `interaction-design` skill defines different values (`0.16, 1, 0.3, 1` and `0.65, 0, 0.35, 1`). Emil's curves were chosen because they are enforced by the `animate` and `review-animations` quality pipeline. Patterns from `interaction-design` use the shared tokens. | Active |
| 2026-10-22 | **Reduced motion: fewer and gentler, not zero** | The `animate` skill (Emil Kowalski) recommends keeping opacity/color transitions that aid comprehension while removing transform-based movement. The `interaction-design` skill uses a blanket kill (`animation-duration: 0.01ms !important`). This workspace adopts the gentler approach — it preserves accessibility information conveyed through motion. | Active |
| 2026-10-22 | **Three motion layers kept distinct** | Layer 1 (interaction-design): pattern catalog. Layer 2 (easing from animation-vocabulary + animate): timing and feel. Layer 3 (animate, review-animations, etc.): implementation and audit. No layer is merged or removed. Overlapping guidance is resolved in shared tokens; original skills are preserved unmodified. | Active |

## Project-Specific Exceptions

| Date | Project | Exception | Rationale | Status |
|------|---------|-----------|-----------|--------|
| — | — | None yet | — | — |

## How to Record Decisions

Add a row when:
- A shared token value is chosen over an alternative.
- A conflict between skills or guidelines is resolved.
- A project overrides a shared default.

Each row needs a date, the decision, the reasoning (including what was rejected and why), and whether it is active or superseded.
