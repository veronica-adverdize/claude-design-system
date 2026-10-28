# Setting Up the Cloud Project on Claude.ai

## Step 1 — Create the Project

1. Go to claude.ai
2. Click **Projects** in the sidebar
3. Click **Create Project**
4. Name it: **Design System**

## Step 2 — Set custom instructions

1. Open the Project settings
2. Find the **Custom Instructions** field
3. Open `CLOUD-PROJECT-INSTRUCTIONS.md` from this folder
4. Copy everything BELOW the `---` line (don't include the header above it)
5. Paste it into the Custom Instructions field
6. Save

## Step 3 — Upload knowledge files

Click **Add context** (or **Add knowledge**) and upload these files:

**From `design-system/`:**
- `DESIGN.md` — core design principles and quality floor
- `tokens.css` — CSS custom properties (colors, typography, spacing, motion)
- `motion.md` — animation guidelines, easing curves, duration budgets

**From `design-system/directions/`:**
- `premium-editorial.md`
- `technical-futurism.md`
- `modern-product.md`
- `expressive-brutalism.md`
- `luxury-minimalism.md`
- `playful-contemporary.md`

That's 9 files total.

## Step 4 — Enable required skills (each team member)

Each person who uses this Project needs these skills on their Claude.ai account.
Go to **Settings > Skills** (or check the skills panel) and enable:

**Must have:**
- design-taste-frontend
- humanizer
- frontend-design

**Highly recommended:**
- ui-ux-pro-max
- deep-research

**Nice to have (if available):**
- a1-gallery (reference, tokens, pairings)
- design (design-critique, accessibility-review)
- landing

## Step 5 — Test it

Start a new conversation inside the Project and type something like:

> I need a website for a personal trainer in Miami. He's energetic, targets young professionals, wants online booking.

The system should:
1. Extract brand context
2. Search for design references
3. Present 3 distinct directions
4. Wait for your choice before building

## What works in the cloud vs. the local workspace

| Feature | Cloud Project | Local Workspace |
|---------|:---:|:---:|
| 9-phase workflow | Yes | Yes |
| Design tokens + directions | Yes | Yes |
| Motion guidelines | Yes | Yes |
| Humanizer copy rules | Yes | Yes |
| Taste art direction | Yes | Yes |
| A1 Gallery references | Depends on plugin | Yes |
| Browser inspection (inspect.mjs) | No | Yes |
| Automated lint (lint.mjs) | No | Yes |
| Direction sheet dealing (draw.mjs) | No | Yes |
| Impeccable hooks | No | Yes |
| Taste Vault (local reference DB) | No | Yes |
| Project file persistence | Per conversation | Across sessions |

The cloud Project covers about 80% of what the local workspace does.
For the full experience, use Claude Code in the local workspace.
