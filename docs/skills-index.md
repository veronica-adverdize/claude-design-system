# Skills Index

What each installed skill does and when to use it. Skills live in `.agents/skills/` (and are mirrored in `.claude/skills/`). Workspace-level orchestration skills live in `skills/`.

## Art Direction and Design

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `design-taste-frontend` | Art direction for websites. Deals researched directions from a library of 247 curated sites, enforces a no-slop house style with a browser inspector, runs a look-and-fix loop on screenshots. Includes `draw.mjs`, `lint.mjs`, `inspect.mjs`, `assets.mjs`. | Building, designing, restyling, or reviewing any public-facing web page. When something looks generic or "AI-made." |
| `reference-to-design` | Turns visual website references into original frontend directions. Screenshot-led design exploration. | When working from reference screenshots to develop a new brand direction. Not for exact site cloning. |
| `emil-design-eng` | Emil Kowalski's philosophy on UI polish, component design, animation decisions, and invisible details. | General design engineering guidance, taste-level UI critique, component refinement. |

## Animation and Motion

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `animate` | Builds an animation from scratch following a decision sequence: gate, purpose, tool, properties, curve, duration, interruption, exit. | When asked to animate something, add motion, or build a transition. |
| `review-animations` | Reviews animation code against a high craft bar. Default to flagging; approval is earned. | Critiquing a specific animation or reviewing a diff for motion quality. |
| `improve-animations` | Surveys a codebase's animation code and produces a prioritized audit with implementation plans. Read-only. | When asked to audit all motion in a project or create a roadmap of animation fixes. |
| `find-animation-opportunities` | Searches a codebase or UI for places that should animate but don't. Proposes motion with exact values. Read-only. | When asked "what could be animated here?" or "make this feel more alive." |
| `animation-performance` | Diagnoses jank, dropped frames, compositor issues. Covers the layout/paint/composite pipeline, CSS vs JS animation, will-change, blur cost. | When an animation is janky, choppy, or drops frames. When choosing which property to animate for performance. |
| `animation-vocabulary` | Reverse-lookup glossary that turns vague animation descriptions into exact terms. | When someone describes a motion effect without knowing its name ("the bouncy thing when a popover opens"). |
| `animate-expo` | React Native (Expo) animation implementation with Reanimated, Gesture Handler, haptics. | Animating anything in an Expo app: gestures, sheets, screen transitions, press feedback. |

## Platform-Specific

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `apple-design` | Apple's approach to interface design and physical motion, translated for the web. Covers spring animations, gestures, translucent materials, depth, typography. | Building or reviewing gesture-driven UI, Apple-style interfaces, spring animations, or reduced-motion. |
| `mobile-native` | Makes a web app feel native on a phone. Covers sticky hover, tap highlight, 100vh bug, input zoom, pull-to-refresh, notch, long-press, carousels, status bars. | When a web app is built for mobile, when something "works in Chrome but feels wrong on my phone," PWAs, touch interactions. |
| `write-swift` | Modern Swift guidance: value types, Swift 6 concurrency, protocols, generics, API design, performance, testing, macros. | Writing, reviewing, or migrating Swift code. Fixing concurrency errors, hangs, data races, retain cycles. |

## Component and UI Tools

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `prototype` | Builds multiple genuinely different versions of a UI piece, rendered behind a visual picker to flip through live. Manual invocation only. | When exploring component variants ("show me three versions of this card"). |
| `break-ui` | Stress-tests UI with worst-case data: long names, missing fields, huge counts, emoji, non-Latin text. Renders behind a toggle and reports what broke. | When asked to stress-test, find edge cases, or "try the worst case" on a component. |
| `pick-ui-library` | Recommends the right library for a frontend task from a curated list: charts, command menus, drag-and-drop, toasts, etc. Manual invocation only. | When choosing a library for a specific frontend need ("what should I use for toasts?"). |
| `ask-sonner` | Guide to Sonner (React toast library): setup, styling, theming, troubleshooting. | When working with Sonner or fixing toast-related issues. |

## Agent and System

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `context-engineering-collection` | Guidance for building production-grade AI agent systems through context engineering, multi-agent architectures, memory, persistence, and evaluation. | Building new agent systems, optimizing agent performance, debugging context failures, designing multi-agent setups. |

## Workspace Orchestration (in `skills/`)

| Skill | What it does | When to use it |
|-------|-------------|----------------|
| `design-review` | Coordinates art direction, asset generation, animation, and UI refinement across a project. Sequences installed skills in the correct order. | Starting a new surface, reviewing an existing design, or running a full quality pass. |
| `nano-banana` | AI image generation via Gemini API. | When a project needs generated imagery. Requires GEMINI_API_KEY. Scripts not yet present. |
| `frontend-design-system` | (Empty — not yet built) | — |

## External Plugins and Tools

| Tool | What it does | When to use it |
|------|-------------|----------------|
| A1 Gallery | MCP plugin for curated website discovery, font pairings, measured design tokens, section patterns. | Reference discovery during direction exploration (Step 2). Requires authentication. |
| Taste Vault | Local web app for storing and browsing design references. 12 collections, 30+ entries, 18 style families. | Reusing reference evidence. Start with `python server.py --port 4610` in `tools/taste-vault/`. |
| Impeccable | UI refinement tool with commands: shape, critique, audit, polish, bolder, quieter, animate, adapt, harden, clarify, document. | Focused review, refinement, and documentation of UI work. |

## Duplication Note

`.agents/skills/` and `.claude/skills/` contain identical skill sets (20 skills). Both locations are read by Claude Code. This duplication is harmless but could be cleaned up by choosing one canonical location.
