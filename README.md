# ClaudeWorkspace

A shared workspace for designing and building websites with Claude Code. It keeps client projects, design guidance, visual references and automation tools organized in one place.

The goal is to turn a short client brief into a distinctive, usable website through deliberate exploration, clear guidelines, a small reviewable sample and visual refinement. The workspace supports service businesses, portfolios, agencies, products and other website types.

Tools help carry out the work. They do not replace design judgment, verify business claims automatically or guarantee good results.

## 1. Getting started

### What you need

- Access to this workspace on your computer.
- Claude Code installed and signed in.
- A client brief or an existing project to continue.
- For implementation review, a working browser or screenshot tool.

Existing scripts and plugins may have additional requirements. Check their installed instructions before running them; do not install everything again just to start.

### Open the workspace

In PowerShell or Windows Terminal:

```powershell
cd C:\Users\Admin\ClaudeWorkspace
claude
```

To select a previous conversation instead:

```powershell
claude --resume
```

Run these commands in the terminal. Once Claude Code is open, enter your brief at its prompt. Consult the installed version's help if a command is unavailable.

### Start a new project

Describe the business naturally. You do not need to name skills or write a technical specification.

> I need a website for a yoga instructor in Los Angeles. She is grounded and approachable and wants to attract new clients. The main goal is inquiries about private sessions.

Share any confirmed services, existing website, brand assets, copy, photographs, booking destination and constraints. Unknown details should remain explicit rather than becoming invented facts.

Claude should read the workspace's `CLAUDE.md`, establish brand context and explore directions. You choose a direction before detailed styling is finalized, then approve a rendered sample before the full build.

### Continue an existing project

Name the project and requested change:

> Continue Agentic Labs. Read the current brief and guidelines, check what is already saved, and resume the hero study without repeating completed work.

Use the existing project folder. Do not create another copy merely because the conversation is new.

## 2. Where things belong

These paths describe the established organization. Inspect the actual files before editing; some supporting folders may depend on the installed setup.

| Path | What belongs here | When to use it |
| --- | --- | --- |
| `README.md` | This introduction, process overview and glossary | When learning the workspace |
| `CLAUDE.md` | Instructions Claude follows: workflow, tool handoffs and project boundaries | At the start of work; when intentionally changing how the workspace operates |
| `PRODUCT.md` | Existing background about the workspace itself | To understand workspace context; not as a substitute for a client's brief |
| `design-system/` | Reusable principles and design guidance | When establishing project standards |
| `design-system/DESIGN.md` | Shared technical quality principles | For accessibility, responsive behavior and implementation standards |
| `design-system/tokens.css` | Shared CSS defaults and token names | As an optional starting point; client-specific values stay scoped to the project |
| `design-system/motion.md` | Animation and reduced-motion guidance | When planning and implementing interaction |
| `design-system/directions/` | Reusable direction definitions | When exploring an applicable art direction |
| `projects/` | Separate websites, client work and experiments | For all project-specific work |
| `projects/design-direction-explorer/` | Interactive examples of the six visual directions and the Mixer | To compare examples or copy a direction brief |
| `projects/token-preview/` | Existing token demonstration and inspection page | To examine shared token behavior |
| `tools/taste-vault/data/` | Saved reference records and style families | To reuse reference evidence; preserve its existing schema |
| `.agents/skills/` | Workspace skill locations | To read the relevant installed methodology |
| `.impeccable/config.json` | Existing Impeccable configuration | When configuring or diagnosing review behavior |
| `docs/` | Supporting workspace documentation | For confirmed shared decisions and setup notes |

### Inside a client project

Use the project's actual stack and structure. Not every project is a single HTML file.

| File or resource | Responsibility |
| --- | --- |
| `brief.md` | Business facts, audience, goals, content inventory, constraints and unresolved questions |
| `DESIGN.md` | Selected visual direction, concrete design decisions, responsive/motion behavior and approval status |
| Source files | The implemented website or application |
| Sample or study files | Limited experiments, clearly separated from the main implementation where appropriate |
| Reference assets and screenshots | Permitted supporting evidence and review captures, organized using the project's existing conventions |

The two `DESIGN.md` files have different roles: the file in `design-system/` contains shared principles; the file inside a client project records that client's visual decisions.

## 3. The process — nine steps

This is the sequence people follow, regardless of which tools are available. Tool-specific execution belongs in `CLAUDE.md` and the installed tool instructions.

| Step | Work | Expected result |
| --- | --- | --- |
| 1. Establish brand context | Understand business, audience, personality, goals, content and constraints | A factual brief with assumptions and gaps identified |
| 2. Explore design directions | Research suitable references and develop structurally different approaches | A concise comparison supported by evidence actually inspected |
| 3. Choose a direction | Review the options and select an approach | An explicit direction choice |
| 4. Create project guidelines | Translate the selected approach into concrete visual and interaction decisions | Draft project `DESIGN.md` |
| 5. Build a visual sample | Implement enough of the design to judge it, normally a hero plus two supporting sections | A realistic, limited sample; smaller scope if explicitly requested |
| 6. Refine and approve | Inspect rendered views, correct weaknesses and incorporate feedback | An approved sample and updated guidelines |
| 7. Build the website | Extend the approved language across the agreed scope, including motion and interaction | A complete implementation for review |
| 8. Review and validate | Check visual quality, behavior, accessibility, responsiveness and relevant performance concerns | Corrected work with honest validation results and remaining limitations |
| 9. Retain useful lessons | Save selected references and approved decisions | Reusable evidence without unrelated project clutter |

**Checkpoints:** detailed guidelines follow direction selection. Full implementation follows sample approval. Visual approval is not the same as production readiness or permission to deploy.

Section arguments, concept notes and draft copy support these steps; they are not extra approval stages. Keep them concise in existing project documents.

## 4. The tooling — how parts of the process are assisted

A **skill** is a documented method Claude can follow. A **script** is executable code. A **plugin or MCP connection** exposes external capabilities. Their presence does not prove they were used successfully.

| Tool or resource | What it assists with | What it does not establish |
| --- | --- | --- |
| Taste | Creative exploration, concepts, composition, implementation and visual critique | That every resulting choice is appropriate or beautiful |
| Taste `draw.mjs` | Producing candidate direction sheets from a brief and available options | A final design or approval |
| Taste `lint.mjs` | Automated checks defined by the installed version | Overall design quality or complete accessibility |
| Taste `inspect.mjs` | Render capture and inspection checks where supported by the installed environment | That an untested viewport or interaction works |
| Taste `assets.mjs` | Asset discovery where supported and permitted | Client identity, factual relevance or blanket reuse rights |
| A1 Gallery / available reference-discovery tools | Finding reference material and available design analysis | Browser inspection unless rendered evidence was actually returned and inspected |
| Browser and screenshot tools | Viewing references and implementations at real viewport sizes and interaction states | Full functionality, performance or accessibility compliance from screenshots alone |
| Taste Vault | Retaining selected reference sources and reusable analysis | Automatic relevance to every new project |
| Design Direction Explorer | Comparing six visual presets and exporting direction context | That previews define every generated website's structure |
| Installed motion skills | Animation behavior, interaction feedback and reduced-motion alternatives | A need to animate every element |
| Impeccable | Focused review and refinement | That every warning is valid, or every intentional design choice is exempt |

Read the installed instructions for exact commands and supported options. Tool availability, authentication and execution status may change. A blocked tool should be reported; do not present text extraction as screenshot inspection or claim checks that did not run.

## 5. The six directions

Preserve these Explorer identities:

| ID | Name |
| --- | --- |
| `editorial` | Premium Editorial |
| `technical` | Technical Futurism |
| `product` | Modern Product |
| `brutalism` | Expressive Brutalism |
| `luxury` | Luxury Minimalism |
| `playful` | Playful Contemporary |

Explorer presets and Taste's compositional library are different systems. A project may interpret a visual direction using a suitable composition from Taste or another reasoned approach.

The Explorer's fonts, palettes and layouts are demonstrations. A direction definition describes broader principles. Project guidelines record the actual selection. None of these should force all clients into the same page template.

Current reported integration: `design-system/directions/premium-editorial.md` is connected to the workflow and Explorer brief export. Its ability to produce consistently strong results remains under evaluation; equivalent definitions for the other five directions are not established by this README.

## 6. Glossary

| Term | Meaning |
| --- | --- |
| Art direction | The overall creative approach connecting the brand, composition, typography, imagery, graphics and motion |
| Brand context | The business, audience, personality, positioning, goals, existing identity and constraints that guide decisions |
| Content inventory | A compact list of supplied facts, copy, assets and missing information |
| Section argument | A short statement of what each section needs to communicate and what supports it; an unsupported statement remains a draft or a gap, not proof |
| Direction definition | Reusable principles for one visual direction: suitable uses, composition possibilities, graphics, behavior and failure patterns |
| Explorer preset | One example combination of fonts, colors, surfaces, layout and motion shown in the Explorer |
| Compositional direction | A way of arranging content and visual relationships; distinct from a font-and-color preset |
| Composition repertoire | Several possible arrangements a direction can draw from, rather than a mandatory page skeleton |
| Direction sheet / dealt sheet | A candidate composition brief returned by Taste's direction-drawing script; “dealt” means selected from its available options, not approved or ready-made |
| Creative concept / idea sentence | A concise explanation of how something specific to the subject becomes the page's organizing device |
| Competitor test | Asking whether the concept could be reused unchanged for a competitor; a check for specificity, not a demand to invent uniqueness |
| Claim and proof | A message and the verified material supporting it; illustrative UI is explanation, not evidence of real customer outcomes |
| Copy deck | Headlines and body copy drafted as text before being fitted into markup |
| Design token | A named reusable value such as a color, spacing unit, type size or radius |
| Project guidelines | The concrete approved or draft decisions recorded in the project's `DESIGN.md` |
| Annotated exhibit | A meaningful image, interface or artifact accompanied by explanations of relevant details |
| Chaptered argument | A sequence of sections that builds an explanation, with deliberate changes in density, scale or medium |
| Visual sample | A small implemented portion used to judge a proposed design before extending it |
| Composition study | A focused exploration of visual arrangement; its fidelity must be stated so a wireframe is not presented as a finished design |
| Custom UI / dashboard | An interface designed to explain relevant tasks or information; conceptual versions must be labeled |
| Illustrative data | Fictional example values used to explain behavior, not reported results or verified product metrics |
| Live thing / demo interaction | A useful action the visitor can try, such as approving an illustrative task; it need not send real data or require a backend |
| Visual rhythm | How scale, spacing, density and section treatment change as a page unfolds |
| Viewport | The browser's actual page-rendering area; it is not a label on a smaller mockup or the outer desktop window size |
| Responsive transformation | Reorganizing layout, content and visual relationships for different screen conditions, rather than merely shrinking them |
| Reduced motion | An alternative experience respecting a user's preference to reduce animation |
| Lint finding | An automated rule result requiring interpretation; passing a linter does not prove strong design |
| Gate | A checkpoint that requires relevant evidence before proceeding; failing or blocked checks must be reported |
| Visual critique | Reviewing rendered output for brand fit, hierarchy, composition, graphics and execution, then correcting meaningful weaknesses |
| Sanctioned exception | A deliberate, documented deviation from guidance; it does not excuse accessibility failures or override user requirements |
| Provenance | Where a reference or asset came from, how it was inspected and what is known about its reuse |
| Visual benchmark | An example the user accepts as a quality standard for subsequent work |
| Production readiness | Relevant functionality, content, accessibility, responsive and operational checks supporting real use; separate from visual approval |

## 7. Quality and change boundaries

- Preserve supplied content and factual meaning. Draft natural copy without inventing services, credentials, testimonials, metrics or promises.
- Use references relevant to the brand and distinguish observation from inference.
- Vary structure and components purposefully. Different fonts and colors alone do not make a different direction.
- Use coherent graphics and dashboards when they explain the offering; other brands may need different visual media.
- Do not replace substantive design with placeholder blocks or arbitrary image/motion quotas.
- Inspect rendered output and actual computed styles before dismissing a warning. Intentional choices can still fail.
- Resolve conflicting guidance before implementation and record concise decisions. User requirements control the authorized scope.
- Preserve existing files, inspect before editing and back up substantial changes. Keep client-specific values scoped to the project.
- No deployment, live-site changes, paid APIs, image generation or new dependencies are authorized by this README.

## 8. Current work and maintenance

As of 2026-10-28, Agentic Labs is a test project for improving design quality. A separate `hero-composition.html` has been requested, with an editorial opening and a substantial decision-workspace exhibit. Check the current project and conversation before assuming it exists or is approved.

Earlier samples demonstrated functional progress but were not approved as the visual benchmark. Previously supplied desktop screenshots do not verify mobile behavior.

Keep one authoritative location for each responsibility:

- This README: orientation and terminology.
- `CLAUDE.md`: operational workflow and tool coordination.
- Project `brief.md`: client facts, goals and constraints.
- Project `DESIGN.md`: selected visual decisions and approval state.
- Direction definitions: reusable creative principles.

Update confirmed milestones when they change. Do not turn this guide into a duplicate instruction system or a transcript of every experiment.
