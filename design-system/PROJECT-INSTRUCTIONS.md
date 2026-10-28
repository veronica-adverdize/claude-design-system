# Design System — Team Quick-Start

## How this workspace works

This is a **Claude Code workspace**, not a regular folder of files. When anyone opens Claude Code (CLI or desktop app) in `C:\Users\Admin\ClaudeWorkspace`, the full design system loads automatically:

- **CLAUDE.md** loads as operational instructions (the 9-phase design workflow)
- **20+ skills** load from `.agents/skills/` (art direction, animation, review, etc.)
- **Design tokens, motion rules, and direction specs** are available as reference files
- **Project folders** under `projects/` keep each client's work separated

You don't need to invoke anything manually. Just describe a client and the workflow starts.

## Quick reference: what's installed

### Core creative tools
| Tool | What it does | How it's triggered |
|------|-------------|-------------------|
| **Taste** (design-taste-frontend) | Art direction lead. Deals directions, runs browser inspection, enforces quality. | Automatically during Steps 2-6 |
| **A1 Gallery** | Curated website discovery, font pairings, measured design norms. | Automatically during reference discovery (Step 2). Needs MCP auth. |
| **Impeccable** | UI review, critique, polish, accessibility checks. | Automatically during review (Step 8) |
| **Humanizer rules** | Removes AI-sounding copy patterns. | Built into CLAUDE.md Step 4 when writing copy |

### Animation and motion skills
`animate`, `animation-vocabulary`, `animation-performance`, `improve-animations`, `find-animation-opportunities`

### Design directions (in `design-system/directions/`)
1. Premium Editorial — serif, whitespace, narrative layouts
2. Technical Futurism — dark, monospace, data-forward
3. Modern Product — clean SaaS, product mockups
4. Expressive Brutalism — bold type, raw energy
5. Luxury Minimalism — sparse, architectural
6. Playful Contemporary — rounded, colorful, friendly

### Full skills list
See `docs/skills-index.md` for every installed skill with descriptions and usage triggers.

## Starting a new project

Just say something like:

> "I need a website for a personal trainer in Miami. He's energetic, targets young professionals, wants online booking."

The system will:
1. Extract brand context and save it to `projects/<project-slug>/brief.md`
2. Find design references automatically (A1 Gallery, web search, Taste Vault)
3. Present 3 structurally distinct directions with a recommendation
4. Wait for your choice before building anything
5. Create project guidelines and a visual sample (hero + 2 sections)
6. Run inspection and critique, then refine
7. Build the full site after you approve the sample
8. Review with Impeccable before handoff

## Continuing existing work

Say: "Continue the yoga instructor project" or "Add an About page to Agentic Labs"

The system reads the saved brief and guidelines before making changes.

## What the system handles vs. what you decide

**The system handles:** reference discovery, direction development, token application, copy humanization, motion planning, automated quality checks, responsive behavior, accessibility.

**You decide:** which direction to use, whether the sample looks right, when to expand to full implementation, any content or brand corrections.

## Folder structure

```
ClaudeWorkspace/
  CLAUDE.md              ← auto-loads the workflow (do not delete)
  PRODUCT.md             ← workspace capabilities
  design-system/         ← shared tokens, directions, motion rules
  projects/              ← each client gets their own folder
  .agents/skills/        ← installed skills (Taste, animation, etc.)
  tools/taste-vault/     ← reference storage (12 collections, 30+ entries)
  docs/                  ← skills index, decisions, handbook
  skills/                ← workspace orchestration skills
```

## Troubleshooting

- **A1 Gallery not returning results?** It needs MCP authentication. Run `/mcp` to check connection status.
- **inspect.mjs failing?** It needs Chrome/Chromium and Node 22+. Check both are installed.
- **Copy sounds AI-generated?** The humanizer rules are in CLAUDE.md Step 4. If copy still sounds off, load the humanizer skill directly: it's available as `anthropic-skills:humanizer`.
- **Need the full process explained?** Read `design-system/Design-System-Handbook.md` for the detailed 9-phase breakdown, templates, glossary, and architecture.
