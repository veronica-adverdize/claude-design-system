# ClaudeWorkspace — Design Workflow

## Team setup

This workspace is a complete design system that auto-loads when anyone opens Claude Code in this folder. Everything — the process, skills, tokens, direction library, and quality tools — is ready to use immediately.

**What you get automatically:**
- A 9-phase design process (brief → exploration → direction → guidelines → sample → refinement → implementation → review → retention)
- 20+ installed skills for art direction, animation, motion, UI review, and more
- 6 reusable design directions with full specifications
- Shared design tokens, motion guidelines, and quality standards
- Taste skill as creative lead, Impeccable for review, A1 Gallery for reference discovery

**To start a new project**, just describe the client: "I need a website for a yoga instructor in L.A." — the workflow triggers automatically.

**To continue an existing project**, say: "Continue [project name]" — it reads the saved brief and guidelines.

**Key reference docs:**
- `docs/skills-index.md` — full inventory of every installed skill, what it does, when to use it
- `design-system/Design-System-Handbook.md` — detailed explanation of the 9-phase process, templates, glossary, and architecture
- `PRODUCT.md` — workspace capabilities and constraints

**Requirements:** Claude Code (CLI or desktop app) opened in `C:\Users\Admin\ClaudeWorkspace`. Skills and tools do not transfer to claude.ai web Projects — they need this workspace environment.

## Brief detection

When a message describes a client, business, or project needing a website — even without naming any skill — treat it as a **design brief** and start the workflow below. Typical signals: a person or business described with an audience, a tone, a goal, or a request for a website. Do not require the user to name skills or assemble structured prompts.

Examples that should trigger the workflow:
- "I need a fitness website. The client is a yoga instructor based in L.A. …"
- "Build a site for a ceramics studio in Portland …"
- "My client runs a small architecture firm …"

## Build mode detection

Before starting, determine which mode fits the request:

**Direct build** — The user wants a complete, working website delivered in one go. Use this when:
- The brief is clear and specific ("I need a website for a pet hotel with a booking system")
- The user describes what they want built, not what they want explored
- There is no mention of "options," "directions," "proposals," or "concepts"
- The request includes concrete features (booking system, contact form, gallery, etc.)

**Guided process** — The user wants creative exploration with options before building. Use this when:
- The brief is vague or open-ended ("I need a website, not sure what style")
- The user explicitly asks for options, directions, or proposals
- The project is complex with multiple stakeholders or unclear positioning
- The user says "explore," "show me options," or similar

**When in doubt, ask one question:** "Would you like me to build this directly, or show you a few design directions first?" Do not default to the guided process for every request.

### Direct build workflow

For direct builds, compress the process into a single delivery:

1. **Brand context** — Extract everything from the brief. State assumptions. Ask only if a critical detail is missing.
2. **Internal direction** — Choose the best-fit direction internally. Do not present options or wait for selection.
3. **Guidelines** — Define typography, colors, spacing, motion, and responsive behavior internally.
4. **Build the complete site** — Deliver a full, working, single-file HTML page with ALL sections and ALL requested features. No "coming soon" teasers. No "more sections planned." Every section the site needs should be built.
5. **Review** — Run quality checks. Present the finished site.

The direct build must include:
- Every feature the user requested (booking system, contact form, gallery, etc.)
- Enough sections to make the site feel complete (typically 6-10 sections)
- Real interactive functionality where requested (working forms, calendars, filtering, etc.)
- A complete responsive design that works at all widths

### Guided process workflow

For guided builds, follow the full phased workflow below.

## The workflow (guided process)

### Step 1 — Establish brand context

Extract from the brief and any existing project files:
- Business type, name, location
- Audience and their expectations
- Personality and positioning
- Goals (what the site must get someone to do)
- Existing identity (colors, fonts, logo) — note what exists vs. what is assumed
- Content and services offered
- Constraints (budget, timeline, content gaps, imagery availability)

Support: service businesses, portfolios, agencies, products, restaurants, events, nonprofits.

Ask only when a missing fact would materially change the design direction. State assumptions clearly — do not silently invent business details, testimonials, credentials, metrics, or integrations.

**Content placeholders.** When real content is not provided, use explicit placeholders that cannot be mistaken for real claims. Write `[Instructor name]`, `[Class name]`, `[Schedule placeholder]`, `[Testimonial — real quote needed]`. Never invent specific credentials, class limits, schedules, pricing, testimonials, or business promises — even for a hypothetical or test build.

Save the brand context to `projects/<project-slug>/brief.md` for continuity across sessions.

### Step 2 — Explore design directions

**Reference discovery.** Automatically curate references based on brand context — do not require the user to browse galleries or manually import references.

Discovery chain (use the first that works):
1. **A1 Gallery** (`a1-gallery:design-researcher` agent or `a1-gallery:reference` skill) — requires authentication. If it returns an auth error, skip to the next method and note the gap.
2. **WebSearch** — search Awwwards, One Page Love, and sector-specific roundups for real URLs. Fetch each URL with `WebFetch` to read page structure, loaded fonts, and layout decisions.
3. **Taste Vault** (`tools/taste-vault/data/gallery.json`, `styles.json`) — check existing entries for relevant references and style families.

Limitations to state honestly:
- `WebFetch` returns page text/markdown, not rendered visuals. It may or may not include font names, layout structure, or section order depending on how the site renders. Asset filenames suggest but do not confirm visual appearance. Report only what the response actually contained; do not infer colors from names, motion from filenames, or layout from guesses.
- Do not claim "visual inspection" when you only read page text. Say "assessed from page structure" or "inferred from markup" and note what was unavailable.
- The `claude-in-chrome` skill can capture browser screenshots if the Chrome extension is configured — this is a separate capability from A1 Gallery. Load it before attempting browser-based inspection.
- Never invent source URLs.

**Section argument.** Before exploring directions, list the page as claims with proof, one line per section — following Taste's Step 2 and `references/copy.md §1`. The claims decide which sections exist and in what order. Delete any section with no claim. Record this argument in `projects/<project-slug>/brief.md` under a "## Section argument" heading.

**Direction development.** Taste leads creative exploration. Use its direction script to deal options rather than choosing compositions manually:

```bash
node .agents/skills/design-taste-frontend/scripts/draw.mjs \
  --sector <sector> --brief "<one-line summary>" \
  --sections <roles from the argument> --tone <tone> \
  --have <assets that truly exist> \
  --options 3
```

A dealt sheet is a starting point for the project's composition, not proof of quality. When `draw.mjs` is unavailable or its output does not suit the subject, choose manually from available resources and state why in the report.

The Taste library has 20 compositional directions (in `library/directions.json`). The Design Direction Explorer has its own 6 visual-system presets (Premium Editorial, Technical Futurism, Modern Product, Expressive Brutalism, Luxury Minimalism, Playful Contemporary). These are separate systems — the Explorer's presets are styling themes; the Taste directions are compositional ideas. Both are available resources, not mandatory templates. Choose directions that suit this specific client.

**Direction definitions.** When a direction has a canonical definition in `design-system/directions/`, load it before developing the proposal. For Premium Editorial, load `design-system/directions/premium-editorial.md` — it defines invariants, composition repertoire, and review criteria. Explorer fonts, colors, and layouts are demonstrations, not mandatory values; Taste develops the brand-specific interpretation. Record the chosen interpretation in the project's DESIGN.md.

**Structural distinctness.** Directions must differ in hero composition, section sequencing, component choices, graphic language, density, and visual rhythm. Fonts and colors alone do not make a different direction. Compare these structural choices before presenting; revise substantially similar proposals.

### Step 3 — Present directions and wait

Present a concise comparison of the three directions with a recommendation. Include:
- The structural idea of each direction and why it suits this client
- How each handles the client's specific content and constraints
- Which references informed each direction
- A clear recommendation with reasoning

**Stop here and wait for the user's selection.** Do not create detailed guidelines or build anything until a direction is chosen.

### Step 4 — Create project guidelines

After the user chooses a direction, deal the full sheet when a direction was dealt in Step 2:

```bash
node .agents/skills/design-taste-frontend/scripts/draw.mjs \
  --sector <sector> --brief "<summary>" \
  --sections <roles> --direction <chosen-id>
```

**Creative concept.** Before coding, write a one-sentence concept following Taste's Step 4: "On this page, **[something that belongs to the subject]** becomes **[the device the direction calls for]**." The first blank must pass the competitor test — if a direct competitor fits the same sentence, it belongs to the category, not the client. Record the concept in DESIGN.md under "## Creative concept."

**Conflict resolution.** Compare Taste's house rules, the direction definition (if any), and the project's constraints before implementation. Where they conflict (e.g., Taste bans monospace labels but a definition prescribes them), record a brief, reasoned resolution in DESIGN.md under "## Rule conflicts." Use `--allow <rule>` in the inspector for consciously overridden Taste rules. Do not silently override any instruction source.

**Draft copy.** Write the hero headline, supporting line, and section headings as plain text in DESIGN.md before markup. Check each headline against the two-line budget (~32 characters safe at a confident size; see Taste `references/copy.md §2`). Shorten or restructure headlines that exceed it.

Create or update `projects/<project-slug>/DESIGN.md` with:
- Typography: families, scale, weights, tracking, leading
- Semantic colors: ground, surface, ink, muted, accent, fields
- Surfaces and elevation
- Spacing scale and grid
- Component states (hover, focus, active, disabled)
- Graphics system — label what is conceptual vs. real clearly
- Responsive behavior
- Motion plan: purpose, timing, easing, triggers, mobile behavior, keyboard equivalents, reduced-motion alternatives

Keep brand facts and content constraints distinct from visual decisions. Keep project styling scoped — do not modify shared tokens or unrelated files.

### Step 5 — Build a visual sample

Inspect the project directory first. If the project already has files (an existing `index.html`, component structure, framework config), preserve them. Create the sample as a separate file (e.g., `sample.html` or `sample/index.html`) unless the project is new and empty.

Build a substantial preview of the chosen direction. The sample must be large enough for the user to evaluate the design confidently.

**Minimum sample scope:**
- Hero section
- 3-4 supporting sections that demonstrate different layout patterns
- At least one interactive element if the site requires functionality
- Enough content to show the design's rhythm and pacing

Do NOT add "more coming soon" teasers or placeholder sections that say content is planned. Every section in the sample should be complete and polished. If a section is not ready, leave it out entirely rather than teasing it.

Taste's picture floor (≥4 images) and motion floor (≥8 moving elements) apply at full-site scale (Step 7), not to the sample.

Requirements for the sample:
- A clear brand introduction in the hero (who this is, what they do)
- Deliberate visual hierarchy — the visitor's eye should move through the content in a purposeful order
- Purposeful section pacing — whitespace must frame content, not replace it
- Do not equate unconventional positioning, oversized imagery, or excessive whitespace with high-end design
- Use explicit content placeholders for anything not provided (see Step 1)

Follow Taste's build order (Step 6 in SKILL.md) within sample scope: tokens first, then the hero from its blueprint, then each section with this project's content. Include representative motion (entrance stagger, control feedback, one moving picture or scroll treatment where honest material exists) so the user can assess how the design feels.

Use the installed animation skills (`animate`, `animation-vocabulary`, `animation-performance`, `improve-animations`) for interaction implementation.

### Step 6 — Refine the sample

**Automated checks.** Run applicable Taste checks on the sample:

```bash
node .agents/skills/design-taste-frontend/scripts/lint.mjs <source files>
node .agents/skills/design-taste-frontend/scripts/inspect.mjs <path-to-sample>
```

`lint.mjs` scans source for banned patterns. `inspect.mjs` opens the page in a real browser at 1440, 768, and 390px, measures type, spacing, contrast, frame, and layout, and saves screenshots. Fix every FAIL. Defend each WARN in one sentence or fix it. If Chrome or Node 22+ is unavailable, report the error — do not skip inspection silently.

**Visual critique.** After the gate, open the inspector's screenshots (or browser screenshots from `claude-in-chrome`) at desktop, tablet (768px), and mobile (390px) widths. Apply Taste's critique passes from `references/critique.md`: focal point, squint test, cover-the-logo, edges, space/frame, type scale, colour proportions, images. Write findings concisely. Fix the highest-impact weaknesses — at most three per round, up to three rounds. Re-run the inspector after fixes.

If inspection tools are blocked (Chrome unavailable, viewport cannot resize), report which checks ran and which did not. Do not present an uninspected build as ready or declare it approved.

**Visual inspection is mandatory before presenting.** Render the sample in a browser (`claude-in-chrome` or local server + browser screenshot) and inspect the result at desktop width. Report what you see — does the hierarchy read clearly? Does the pacing feel right? Are images loading and placed well? If browser inspection is blocked, say so honestly; do not present an uninspected build as ready for review.

Present findings. Incorporate user feedback. Record approved decisions in DESIGN.md before extending.

**Wait for explicit approval of the refined sample before proceeding to full implementation.**

### Step 7 — Implement the full website

Only after the user approves the sample. Follow approved guidelines. Vary section composition purposefully — guidelines create coherence, not identical sections. Include animations, transitions, hover/focus states, and responsive interactions. Respect the project's existing structure and stack.

### Step 8 — Review with Impeccable

Use the `impeccable` skill for focused checks:
- Visual fidelity to approved direction
- Usability and accessibility
- Responsive behavior
- Performance

Preserve the approved art direction while correcting demonstrated problems.

### Step 9 — Retain useful references

Before saving to the Taste Vault:
1. **Read the existing vault** (`tools/taste-vault/data/gallery.json`) to understand the schema: `meta` (owner, version, imagesPath), `dna` (house constants), `collections` (id, name, description, deployFor, vocabulary, risk, accent, imageStyle), `entries` (id, file, title, collection, family, vocabulary, note, added, imageRecipe, heroUsage).
2. **Check for duplicates** — search existing entries by URL or title before adding.
3. **Preserve provenance** — record the source (Awwwards, One Page Love, WebSearch, etc.), the date found, and the evidence basis (e.g., "assessed from page structure via WebFetch" vs. "visually inspected via screenshot").
4. **Distinguish observation from inference** — in the `note` field, state what was directly observed and what was inferred. Do not present WebFetch text analysis as visual inspection.
5. **Match the existing schema exactly** — do not add new fields or omit required ones.

Record approved project decisions in the project's DESIGN.md.

Do not load unrelated project history into every task.

## Role assignments

| Role | Tool |
|------|------|
| Reference discovery | A1 Gallery (needs auth) → WebSearch + WebFetch → Taste Vault existing entries (see Step 2 for chain) |
| Reference storage | Taste Vault (`tools/taste-vault/data/gallery.json`, `styles.json`) |
| Art direction | Taste skill (`design-taste-frontend`) — leads direction, composition, type, palette, sections |
| Motion design | `animate`, `animation-vocabulary`, `animation-performance`, `improve-animations`, `find-animation-opportunities` skills |
| Review & refinement | `impeccable` skill |
| Design system tokens | `design-system/tokens.css` (shared) — do not modify for project-specific styling |

## Project continuity

When the user returns with a follow-up like "add an About page" or "change the hero":
1. Read `projects/<project-slug>/brief.md` and `projects/<project-slug>/DESIGN.md` before making changes
2. Follow the approved guidelines
3. Maintain the established direction and art direction decisions

## Quality rules

- Custom UI dashboards belong where they explain the actual offering. Other brands need photography, illustration, editorial compositions, or other appropriate visuals.
- Define a coherent graphics system. Label conceptual interfaces and illustrative data clearly.
- Preserve supplied content, services, and factual claims. Humanize wording without changing meaning.
- Never invent testimonials, credentials, metrics, integrations, results, schedules, class limits, pricing, or business promises — even in samples or test builds. Use explicit placeholders.
- Plan motion during art direction, not as an afterthought.
- Do not deploy, modify live websites, call paid APIs, or generate images during design setup.
- Do not install unreviewed tools or require paid reference subscriptions.

## Image and media rules

**When the user asks for "pictures," "photos," or "images":**
- Use placeholder photography from Unsplash (via `https://images.unsplash.com/photo-[id]?w=800`) or similar free sources
- Match the photos to the business concept (pets for a pet hotel, food for a restaurant, etc.)
- Combine with custom SVG illustrations if appropriate, but photos come first when explicitly requested
- Use `object-fit: cover` and proper aspect ratios
- Include `alt` text describing what the photo should show

**When the user asks for "icons" or "SVGs":**
- Build custom inline SVGs that match the design's visual language
- Do not rely solely on Font Awesome — create unique shapes when "custom-made" is requested
- Match stroke weight, corner radius, and color to the overall design system

**When the user asks for both pictures AND custom graphics:**
- Deliver both. Photos for realistic content (facility, products, team). Custom SVGs for icons, decorative elements, and illustrations.
- Do not substitute one for the other

## Feature implementation rules

**When the user requests specific functionality (booking system, contact form, shopping cart, gallery, calculator, etc.):**
- Build a working interactive version, not a static mockup
- The feature must be functional within the HTML file (client-side logic)
- For booking/calendar: build a working date picker with time slots and a confirmation flow
- For contact forms: build the form with validation (submission can show a success message)
- For galleries: build a working lightbox or filtering system
- For pricing: build interactive toggle (monthly/annual) if applicable

**Never skip a requested feature.** If it cannot be fully built in a single HTML file, build the best possible client-side version and note what would need a backend.

## Completeness rules

- Never deliver an incomplete page. Every page must feel finished.
- No "coming soon" sections, no "more chapters planned" teasers, no placeholder sections that admit they are placeholders.
- If you generate multiple direction samples, each must be structurally distinct — different layout, different section order, different component patterns. Color and font swaps alone do not count as a different direction.
- Never deliver duplicate files. Each file must contain meaningfully different content.

## Known limitations

- **A1 Gallery requires authentication.** The `a1-gallery:design-researcher` agent and plugin skills are installed but need `/mcp` authentication before they return gallery data. Connecting A1 provides curated gallery search and measured design norms — it does not provide browser screenshots of external sites. Those require the `claude-in-chrome` skill (separate capability).
- **WebFetch returns text, not visuals.** The content returned varies by site — some include font links and structured sections, others return little usable design information. Do not assume fonts, layout, or section order will be present. State what was actually returned.
- **`inspect.mjs` requires Chrome/Chromium + Node 22+ and a built HTML file.** It launches headless Chrome via CDP, takes screenshots, and measures computed styles. Untested in this environment — Chrome availability unconfirmed.
- **`assets.mjs` requires network access** for open image collections (Unsplash, museums, archives). Untested in this environment — network access to these services unconfirmed.
- **Brief detection depends on CLAUDE.md being loaded.** This file is at the workspace root. Claude Code auto-loads workspace-root CLAUDE.md, but fresh-session triggering from a natural brief has not been tested end-to-end.

## Existing assets

- **Design Direction Explorer:** `projects/design-direction-explorer/index.html` — interactive previews of 6 directions. The Explorer's directions are its own visual-system presets, distinct from the Taste library's 20 compositional directions. Explorer names (from implementation): **Premium Editorial**, **Technical Futurism**, **Modern Product**, **Expressive Brutalism**, **Luxury Minimalism**, **Playful Contemporary**. Preserve all six and their names.
- **Direction definitions:** `design-system/directions/` — canonical direction specifications. Currently: `premium-editorial.md`. These define invariants, composition options, and review criteria; Explorer values are demonstrations only.
- **Taste Vault gallery:** 12 collections, 30+ visual reference entries with image recipes and usage notes.
- **Direction library:** 20 researched directions in `.agents/skills/design-taste-frontend/library/directions.json`.
- **Style families:** 18 reference aesthetic families in `tools/taste-vault/data/styles.json`.
