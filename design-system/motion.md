# Motion Framework

This document defines the shared motion standards for the workspace. It consolidates guidance from three distinct, complementary layers — each with a clear role. No layer replaces another; they operate together.

## The Three Layers

### Layer 1: Interaction Design & Motion (`interaction-design` skill)

**Role:** Pattern catalog — *what to build.*

Provides ready-to-use behavioral templates for microinteractions, state transitions, feedback patterns, gesture interactions, scroll-triggered reveals, and navigation animations. When a project needs a loading button, toast system, drag-to-reorder, or page transition, this layer supplies the structural pattern.

**Source:** `~/.claude/skills/interaction-design/SKILL.md` and its `references/` directory (microinteraction-patterns, scroll-animations, animation-libraries).

**Use when:** selecting which interaction pattern fits a UX need.

### Layer 2: Intentional Easing (embedded in Emil Kowalski's skills)

**Role:** Timing and feel — *how motion should feel.*

Defines easing curve selection, duration budgets, spring physics, and the perceptual principles that make motion feel intentional rather than decorative. This is not a standalone installable skill; it is the easing and timing guidance distributed across:

- **`animation-vocabulary`** (`.agents/skills/animation-vocabulary/SKILL.md`) — Easing glossary: ease-out, ease-in, ease-in-out, linear, cubic-bezier, asymmetric easing. Spring physics: stiffness, damping, mass, bounce, perceptual duration, momentum, velocity, interruptible animation.
- **`animate`** (`.agents/skills/animate/SKILL.md` §5) — Situational easing decisions, canonical cubic-bezier values, element-specific duration budgets, spring configurations, and the hard rule "never ease-in on UI."
- External references: [easing.dev](https://easing.dev/) and [easings.co](https://easings.co/) for custom curves beyond the canonical set.

**Use when:** choosing easing curves, setting durations, deciding between CSS easing and springs, or evaluating whether motion timing feels right.

### Layer 3: Implementation & Review (Emil Kowalski's installed skills)

**Role:** Build and verify — *how to implement and audit.*

Provides the implementation engine and quality gate for animation code:

| Skill | Purpose |
|-------|---------|
| `animate` | Build animations following the decision sequence (gate → purpose → tool → properties → easing → interruption → reduced motion) |
| `animation-performance` | Diagnose dropped frames, jank, compositor issues; verify frame budgets |
| `review-animations` | Critique a specific animation or diff against quality standards |
| `improve-animations` | Audit an entire codebase for animation improvements |
| `find-animation-opportunities` | Scan for places that would benefit from motion |
| `animate-expo` | React Native (Expo) animation implementation |

**Use when:** writing animation code, reviewing a pull request's motion, auditing performance, or scanning for improvement opportunities.

## Shared Easing Tokens

Canonical values from Emil Kowalski's `animate` skill (`.agents/skills/animate/SKILL.md` §5). These are stronger than CSS built-in keywords and are the authoritative curves for this workspace.

```css
--ease-out:     cubic-bezier(0.23, 1, 0.32, 1);     /* entering, responding to user */
--ease-in-out:  cubic-bezier(0.77, 0, 0.175, 1);    /* moving between positions on screen */
--ease-drawer:  cubic-bezier(0.32, 0.72, 0, 1);     /* iOS-like drawer curve */
--ease-default: var(--ease-out);                      /* the safe default */
```

**Decision:** The `interaction-design` skill defines different cubic-bezier values for the same token names (e.g., `--ease-out: cubic-bezier(0.16, 1, 0.3, 1)`). This workspace adopts Emil Kowalski's values because they are enforced by the `animate` and `review-animations` quality pipeline. Projects using Layer 1 patterns should reference the shared tokens from `tokens.css` rather than hardcoding the interaction-design skill's curves.

## Easing Selection

From `animate` §5, in decision order:

| Situation | Easing |
|-----------|--------|
| Entering or exiting | `ease-out` (`--ease-out`) |
| Moving or morphing on screen | `ease-in-out` (`--ease-in-out`) |
| Hover or color change | `ease` (CSS built-in is acceptable here) |
| Constant motion (marquee, progress) | `linear` |
| Default when unsure | `ease-out` |

**Never use `ease-in` on UI.** It starts slow at the exact moment the user is watching for a response. `ease-out` at 200ms feels faster than `ease-in` at 200ms.

## Duration Budgets

Element-specific, from `animate` §5. UI animations stay under 300ms.

| Element | Duration | Token |
|---------|----------|-------|
| Button press feedback | 100–160ms | `--duration-press` (150ms) |
| Tooltips, small popovers | 125–200ms | `--duration-tooltip` (150ms) |
| Dropdowns, selects | 150–250ms | `--duration-dropdown` (200ms) |
| Modals, drawers | 200–500ms | `--duration-modal` (300ms) |
| Marketing / explanatory | Can be longer | Use `--duration-slow` (500ms) or custom |

## Spring Animations

Prefer springs over fixed-duration easing when the motion involves drag with momentum, an element that should feel alive, a gesture the user can interrupt, or decorative mouse-tracking.

```js
/* Apple-style — easier to reason about */
{ type: "spring", duration: 0.5, bounce: 0.2 }

/* Traditional physics — more control */
{ type: "spring", mass: 1, stiffness: 100, damping: 10 }
```

Keep `bounce` at 0.1–0.3. Reserve bounce for drag-to-dismiss and playful interactions; most UI should not bounce.

## Reduced Motion

**Approach:** Fewer and gentler animations, not zero. This follows the `animate` skill's guidance (§7): "Reduced motion means fewer and gentler animations, not zero — keep transitions that aid comprehension, remove movement and position changes."

**Decision:** The `interaction-design` skill uses a blanket `animation-duration: 0.01ms !important` override that kills all motion. This workspace does **not** adopt that approach. Instead:

- Keep opacity and color transitions that aid state comprehension.
- Remove transform-based movement (translate, scale, rotate).
- Shorten remaining transitions to near-instant.
- The shared `tokens.css` sets all `--duration-*` tokens to `0ms` under `prefers-reduced-motion: reduce`, so any animation using the shared tokens automatically collapses.

```css
@media (prefers-reduced-motion: reduce) {
  .element {
    animation: fade 0.2s ease;  /* keep opacity, drop transforms */
  }
}
```

```jsx
const reduce = useReducedMotion();
const closedX = reduce ? 0 : '-100%';
```

## Performance Rules

From `animation-performance` (`.agents/skills/animation-performance/SKILL.md`):

1. **`transform` and `opacity` only.** Anything else (`width`, `height`, `margin`, `padding`, `top`, `left`) triggers layout recalculation every frame.
2. **Never `transition: all`.** List exact properties. `all` animates whatever changes next, including layout properties nobody intended.
3. **Never `scale(0)`.** Start from `scale(0.9–0.97)` + `opacity: 0`.
4. **Never drive a child's transform from a CSS variable on the parent.** It recalculates styles for every descendant every frame.
5. **Keep animated `blur()` under 20px** (especially Safari).
6. **Use `will-change` only after measuring a problem**, not preventively. It costs GPU memory.
7. **CSS for motion during load; JS for interactive motion.** CSS transitions and keyframes run off the main thread. `requestAnimationFrame`-based animation drops frames when the page is busy.

## Coordination Patterns

- **Stagger:** 50–100ms delay between sequenced items. Never exceed 5 staggered items.
- **Exit before enter:** on route transitions, exit the current view before entering the next.
- **Symmetric paths:** a toast that slides in from the bottom exits through the bottom.
- **Asymmetric timing for deliberation:** slow on the user's phase (e.g., hold-to-confirm: 2s linear), snappy on the system response (200ms ease-out).
- **Transitions over keyframes** for anything triggered rapidly (toasts, toggles). Transitions retarget from the current value; keyframes restart from zero.
