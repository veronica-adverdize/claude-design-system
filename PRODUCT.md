# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Delegated: recommend per project. Next.js/React for complex interactive apps, Astro for content-focused and marketing sites, static HTML/CSS/JS for lightweight sites. Preserve existing frameworks on established projects unless a change is explicitly approved.

## Users

Designers and developers using this workspace to create high-quality websites and web interfaces across multiple projects. Each project has its own requirements, visual identity, assets, and implementation.

## Product Purpose

A reusable AI-powered frontend design workspace that combines visual direction, shared design tokens, AI-generated visual assets (Nano Banana), motion design and animation skills, easing principles, and UI refinement tools. The workspace maintains quality and consistency across projects through shared skills and design standards, while allowing each project its own identity.

## Positioning

A multi-project design workspace where AI-generated imagery, interaction design skills, animation tooling, and design system infrastructure are pre-configured and reusable, so each new project starts with production-grade tooling rather than bootstrapping from scratch.

## Operating Context

Projects live under `projects/` with their own assets, code, and visual identity. Shared design tokens live in `design-system/`. Skills for image generation (Nano Banana), animation (emilkowalski), interaction design, context engineering, and UI refinement (Impeccable) are pre-installed. Generated assets land in project-specific or shared `assets/` directories.

## Capabilities and Constraints

- Nano Banana image generation via Gemini API (requires GEMINI_API_KEY)
- Impeccable for UI direction, critique, polish, and documentation
- emilkowalski skills for animation and motion design
- Interaction design skill for microinteractions and transitions
- Taste Vault (`tools/taste-vault/`) for design reference storage, browsing, vocabulary, and prompt generation. Start with `python server.py --port 4610`
- Taste Skill v2 (`design-taste-frontend`) for researched art direction via `draw.mjs`, browser inspection via `inspect.mjs`, and open-archive imagery via `assets.mjs`
- `reference-to-design` guidance (`.agents/skills/reference-to-design/SKILL.md`) for screenshot-led direction exploration
- A1 Gallery (MCP plugin) for curated website discovery, font pairings, and design tokens
- Context engineering collection for agent orchestration
- Must support responsive design and accessibility
- No single framework or visual style imposed across projects

## Evidence on Hand

No client content, testimonials, or case studies exist yet. This is a fresh workspace. Do not fabricate project examples or client references.

## Product Principles

1. **Per-project identity** — each project owns its visual world; shared infrastructure enables quality, not uniformity.
2. **Tool-ready from day one** — image generation, animation, design review, and refinement are pre-configured, not bootstrapped per project.
3. **Preserve what exists** — when working on established projects, respect their stack, identity, and architecture.
4. **Accessibility and responsiveness are non-negotiable** — every surface ships with both.
5. **Evidence over invention** — use real content and assets; never fabricate testimonials, benchmarks, or client claims.
