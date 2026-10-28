# Claude Design System — Process, Skills and Workspace Handbook

Version: 1.0 · 2026-10-28
Suggested workspace location: `C:\Users\Admin\ClaudeWorkspace\docs\design-system-handbook.md`

This handbook describes the design system agreed in our work together: its purpose, nine-phase process, skills and tools, documents, quality standards and present implementation status. It is documentation, not proof that every capability is installed or working.

## 1. Purpose and scope

Create distinctive, coherent websites from a short natural-language brand brief, without asking the user to assemble skill invocations or detailed prompts each time.

Support service businesses, portfolios, agencies, products and other website types. Preserve the client's actual offering and factual content while improving clarity, hierarchy and natural expression.

The system combines:
- Shared technical quality standards.
- Reusable creative direction principles.
- Project-specific brand context and design guidelines.
- Reference discovery, visual inspection and retained reference knowledge.
- Implementation, meaningful graphics and motion.
- Rendered review, functional checks and human approval.

The system is not a single visual theme, a collection of fixed page layouts, or a promise that every first output will be beautiful. Its effectiveness must be established through user-reviewed rendered work.

## 2. Process versus tooling

**Process:** the decisions and work that must happen in sequence.

**Tooling:** skills, scripts, plugins and browser capabilities that help perform that work. A tool can be replaced without changing the process, provided the replacement supplies the required evidence.

A skill provides instructions and methodology. A script executes code. A plugin/MCP connection exposes capabilities or external data. An instruction file coordinates work but is not a technical enforcement mechanism.

| Process need | Supporting resources | Required human judgment |
| --- | --- | --- |
| Understand the brand | Project files, client brief, Claude synthesis | Confirm consequential unknowns |
| Explore visual approaches | Taste, reference discovery, Taste Vault, Explorer | Assess relevance and structural distinction |
| Select a direction | Rendered/reference-backed comparisons | User chooses |
| Establish guidelines | Direction definition and project DESIGN.md | Turn principles into concrete coherent decisions |
| Implement and refine | Claude, project stack, motion skills, inspection scripts | Judge actual visual quality |
| Validate | Browser checks, Taste critique, Impeccable | Resolve findings using evidence |

## 3. The nine-phase process at a glance

| Phase | Purpose | Primary skills/resources | Output / checkpoint |
| --- | --- | --- | --- |
| 1. Brand context | Establish business, audience, identity, content and goals | Workspace workflow; Taste brief-reading methodology | brief.md; facts, assumptions and gaps |
| 2. Design exploration | Find references and develop distinct approaches | Taste; A1/available discovery; browser; Taste Vault; direction definitions; Explorer | Three concise directions and recommendation |
| 3. Direction selection | Choose the approach to develop | Explorer/comparison presentation; Taste direction sheet where applicable | Explicit user choice |
| 4. Project guidelines | Make the chosen direction implementable | Taste concept/copy methodology; direction definition; shared principles; motion guidance | Draft project DESIGN.md and copy |
| 5. Visual sample | Prove the direction with realistic execution | Taste implementation; Claude; relevant motion/interaction skills | Normally hero plus two supporting sections |
| 6. Refinement and approval | Inspect, improve and approve the sample | Taste lint/inspect/critique; browser; selective Impeccable | Rendered evidence, corrected sample, explicit approval |
| 7. Full implementation | Extend the approved design coherently | Claude; Taste; installed motion skills; actual project stack | Agreed website scope implemented |
| 8. Review and validation | Check quality and behavior before handoff | Impeccable; browser; applicable automated checks; Taste critique | Findings resolved or disclosed; readiness statement |
| 9. Retained learning | Preserve useful evidence and decisions | Taste Vault; project guidelines; shared decision notes | Sources and approved lessons retained |

Default checkpoints: direction selection precedes detailed guidelines; sample approval precedes full implementation. User instructions can explicitly authorize another scope or sequence. Approval to design or build does not itself authorize deployment.

## 4. Phase 1 — Establish brand context

**Inputs:** short natural brief, existing project, verified website content, supplied assets and constraints.

**Skills/resources:** CLAUDE.md entry point; Taste brief-reading and subject-inventory methods; existing project files.

**Work:**
1. Identify business type, audience, personality, positioning, goals, primary visitor action and existing identity.
2. Inventory supplied services, messages, factual claims, copy and assets.
3. Separate confirmed facts, draft expression, assumptions and unknowns.
4. Identify subject-specific material that could inform a concept: actual tasks, artifacts, vocabulary, materials, people or processes. Do not fabricate exclusivity to satisfy an inventory count.
5. Ask only questions whose answers materially affect the design or factual scope.

**Output:** project brief.md with content inventory and gaps. Existing PRODUCT.md provides workspace background; it is not the client's brand brief.

**Quality check:** no invented credentials, pricing, results, services, testimonials or client history. Existing content remains the factual source, unless the user updates it.

## 5. Phase 2 — Explore design directions

**Inputs:** brand context and available evidence.

**Skills/resources:** Taste; draw.mjs where applicable; installed A1 Gallery discovery capabilities or supported alternatives; browser screenshots; Taste Vault; reusable direction definitions; Explorer previews.

**Work:**
1. Reuse relevant saved analysis before repeating research.
2. Automatically curate a small relevant reference set. The user should not need to browse thousands of entries.
3. Inspect actual rendered references when possible. Record source, inspection method, observed principle and uncertainty.
4. Write a concise section argument: what each section communicates and what supports it.
5. Use Taste's exploration methodology and direction script where applicable. Record a reason if a supported manual alternative is more appropriate.
6. Develop three structurally different approaches using the same factual content constraints.
7. Compare hero arrangement, content hierarchy, section treatment, graphic language, density, mobile transformation and interaction—not just colors and fonts.

**Output:** three concise directions, reference evidence, trade-offs and recommendation.

**Limits:** WebSearch finds sources; WebFetch returns whatever text/structure is available. Neither proves visual quality without rendered evidence. Numerical gallery norms are descriptive, not mandatory design dimensions.

**Fallback:** if authentication or screenshot capture fails, use available permitted alternatives and label the resulting proposal provisional. Do not claim visual inspection from fetched text.

## 6. Phase 3 — Choose a direction

**Skills/resources:** comparison presentation, Explorer and Taste direction sheet where useful.

Explain the creative idea, brand fit, content treatment, asset requirements, responsive approach and meaningful trade-offs. If the options cannot be judged from prose, provide appropriately representative visual studies and state their fidelity.

**Checkpoint:** wait for user selection before detailed project styling or sample implementation, unless explicitly authorized otherwise.

A direction sheet is a candidate plan, not an approved design. Do not silently change the selected direction during implementation.

## 7. Phase 4 — Create project guidelines

**Skills/resources:** Taste concept and copy methods; selected direction definition; shared principles; installed motion guidance. Impeccable may assist documentation, but should not silently establish a different visual world.

**Work:**
- State a subject-specific creative concept. Test whether it could be reused unchanged for any competitor; if so, refine its specificity without inventing claims.
- Draft headlines and supporting copy as plain text before markup. Character counts are heuristics; actual typography and viewport determine wrapping.
- Resolve conflicts among project constraints, Taste guidance and direction principles. User requirements take precedence. Document reasoned project choices rather than silently ignoring rules.
- Specify concrete typography, color pairs, spacing, grid, component states, graphics, responsive transformations and motion.
- Plan each substantial graphic around a specific message. Distinguish established capabilities from conceptual UI and illustrative data.

**Output:** draft project DESIGN.md plus concise concept/copy notes in existing project documents.

**DESIGN.md contents:**
1. Direction, status and creative thesis.
2. Reference evidence and source locations.
3. Composition and content sequence.
4. Type roles, families/fallbacks, weights, sizes, line heights, tracking and measures.
5. Semantic colors and foreground/background pairs.
6. Layout, spacing, density and section rhythm.
7. Components and interaction states.
8. Graphics/UI/image treatment and evidence labels.
9. Motion purpose, trigger, timing, easing and reduced-motion equivalent.
10. Responsive content order and transformations.
11. Resolved conflicts, remaining gaps and approval state.

## 8. Phase 5 — Build a visual sample

**Skills/resources:** Taste implementation methodology; Claude; actual project stack; installed motion/interaction skills; permitted asset-discovery tools where needed.

Default scope: hero plus two supporting sections. A smaller hero study may be explicitly requested. Inspect existing source and preserve work before creating or replacing files.

Implement tokens → hero → supporting sections within the selected scope. Make intentional choices about scale, alignment, imagery, graphics, rhythm and action placement. Do not force an existing shared page skeleton onto every direction.

Use natural draft copy and representative assets so quality can be judged. Unknown factual details remain explicit, but do not turn every sentence into bracketed instructions.

Include one useful demo interaction where it supports the concept. It may operate entirely locally. Clearly label conceptual behavior and never imply that a demo sent real messages or changed external systems.

**Output:** realistic limited sample with coherent visuals and representative motion.

**Boundaries:** no arbitrary image or animation quotas; no scope expansion to satisfy full-site checks. No dead controls presented as working functions. If a booking destination is missing, represent the prototype limitation clearly.

## 9. Phase 6 — Refine and approve the sample

**Skills/resources:** Taste lint.mjs, inspect.mjs and relevant critique methodology; browser; focused Impeccable checks where useful.

**Work:**
1. Run applicable automated checks. Record blocked tools and scope-inapplicable findings accurately.
2. Inspect actual rendered desktop, tablet and mobile views, using 1440px, 768px and 390px as initial sample targets. Include narrow/intermediate widths where risk warrants it.
3. Review hierarchy, brand fit, composition, crops, visual density, graphics, content continuity and responsive transformations.
4. Exercise relevant interactions with pointer and keyboard. Inspect focus, contrast, state changes and reduced-motion behavior.
5. Identify the highest-impact weaknesses, correct them and capture the revised result. A focused cycle may use up to three rounds before reporting unresolved problems.
6. Present final captures separately from earlier iterations.

**Evidence:** a viewport must be real, not a small mockup labeled with a larger size. CSS media queries alone do not verify mobile rendering. Present computed-style or rendered evidence before dismissing contrast warnings.

**Output:** refined sample, concise findings, actual check results and updated guidelines.

**Checkpoint:** explicit sample approval before full implementation. Do not claim readiness when the sample remains weak or essential checks are blocked.

## 10. Phase 7 — Implement the full website

**Skills/resources:** Claude, Taste, project stack, installed animation and interaction skills, approved project guidelines.

Extend the approved visual language across the agreed pages and content. Maintain typography, surfaces and interaction coherence without repeating the same section composition everywhere.

Implement purposeful transitions, entrances, hover/focus feedback, navigational behavior and relevant demo/product interactions. Preserve reading order, keyboard/touch access and reduced-motion alternatives. Content must not remain hidden if animation or its JavaScript fails.

Do not require four pictures or eight moving elements merely to satisfy a numerical floor. Project needs and the communication role of each asset determine what belongs.

**Output:** agreed website scope implemented, ready for review. This phase does not authorize publishing or deployment.

## 11. Phase 8 — Review and validate

**Skills/resources:** Impeccable focused review; browser/device emulation; applicable automated tools; Taste visual critique.

Review visual execution against approved guidelines alongside actual functionality, content accuracy, responsive behavior, accessibility and relevant performance concerns.

Triage findings with evidence:
- Fix demonstrated problems.
- Record deliberate project exceptions where justified.
- Report uncertainty instead of declaring a false positive without checking.
- Do not suppress every warning in dashboard UI simply because it is labeled data-ui.

Examples from the test work:
- A generic navigation-link selector overrode CTA text color; a claimed contrast false positive was an actual CSS specificity bug.
- Illustrative timing appeared as an unsupported page-level promise.
- Prototype controls looked functional but had no behavior.
- Desktop window limits were treated as proof mobile capture was impossible without confirming other supported capture methods.

These are review lessons, not universal bans on particular visual styles.

**Output:** validation summary, remaining limitations and clear readiness level. Static screenshots alone do not demonstrate accessibility compliance, behavior or performance.

## 12. Phase 9 — Retain useful references and lessons

**Skills/resources:** Taste Vault and existing schema; project DESIGN.md; shared decision notes.

Before writing reference records, inspect their schema, check duplicates and preserve provenance. Store observed details separately from inference. Do not invent source URLs or reference metadata.

Retain approved visual decisions and specific rejected-pattern lessons. Do not turn one rejection into an unconditional ban on serif type, cream palettes, split layouts or any other legitimate device.

Keep unrelated project histories out of new project context. Record a visual benchmark only after user approval.

## 13. Skills and tooling inventory

Status labels refer to reports shared in this conversation, not a fresh inspection of the Windows workspace.

| Resource | Reported state | Assigned role / qualification |
| --- | --- | --- |
| Taste / design-taste-frontend | Installed; library reported as 20 directions | Creative lead; earlier sample execution skipped substantial methodology, so installation alone was insufficient |
| draw.mjs | Present; previously reported executed in an earlier yoga exploration | Direction-sheet generation; not evidence every later sample used it |
| lint.mjs | Later Agentic Labs report included lint results | Automated supporting checks; exclusions and WARNs still require judgment |
| inspect.mjs | Available; capabilities/requirements depend on local setup | Capture/check tool; mobile success was not established by the submitted desktop evidence |
| assets.mjs | Reported present; discovery execution not established here | Optional permitted asset search; not required when meaningful UI/graphics serve the brief |
| Taste Vault | Existing gallery collections and reference/style data reported | Reference retention; exact counts should be checked locally rather than hardcoded as permanent facts |
| A1 Gallery | Installed; OAuth difficulties reported, user subsequently reported setup complete | Verify with a successful operation; later reports described an inspected gallery screenshot |
| claude-in-chrome / browser tools | Used in reported desktop inspection and supplied captures | Browser review; mobile emulation/capture remains a capability to demonstrate |
| Impeccable | Installed; hooks/review findings present in reports | Focused review, evidence-based triage and refinement |
| Emil Kowalski skills | Installation reported; exact set requires local inspection | Motion/interaction guidance; relevant names reported include animate, animation-vocabulary, animation-performance, improve-animations and find-animation-opportunities |
| Intentional Easing | Captured as guidance in existing motion documentation, not established as a separate installed skill | Easing and motion vocabulary |
| Interaction-design plugin | Earlier setup reported installed | Relevant interaction guidance when actually available |
| Nano Banana | Earlier setup reported direct Gemini API integration | Optional image-generation capability; not authorized or required in the current design-system test |
| frontend-design | Used in an earlier standalone experiment | Historical experiment, not the designated creative lead in the agreed workflow |
| design-ref | Candidate discussed; not found installed in the reported workspace | Not a required dependency; do not confuse missing locally with nonexistent globally |

Read installed SKILL.md files and local help for exact commands, supported flags, model/API requirements and current behavior. This guide intentionally avoids duplicating version-sensitive command specifications.

## 14. Explorer and direction architecture

Preserve these six IDs and names:

| ID | Name |
| --- | --- |
| editorial | Premium Editorial |
| technical | Technical Futurism |
| product | Modern Product |
| brutalism | Expressive Brutalism |
| luxury | Luxury Minimalism |
| playful | Playful Contemporary |

Three different responsibilities:
- **Explorer presets:** interactive demonstrations, with swappable typography/color/layout/surface/motion axes.
- **Direction definitions:** reusable creative principles, repertoire, components/graphics, behavior and failure criteria.
- **Taste compositional library:** candidate arrangements and direction sheets supporting brand-specific interpretation.

The original supplied Explorer hardcoded its presets in DIRS and composition builders in one HTML file. Five builders reused the same feature function; all six reused stats and the closing CTA. Editorial omitted a capability included in the shared feature set. This explains limited comparison depth, not all causes of generated design quality.

Premium Editorial has one draft definition connected to CLAUDE.md and the reported brief-export path. The other five require equivalent development after a useful quality benchmark is established. Do not rename or discard the six identities.

A direction definition should cover intent, brand fit, invariants, freedoms, multiple composition possibilities, typography, color logic, components, graphics, responsive transformations, motion and review criteria. It should not prescribe one font/palette/page structure for every client.

## 15. Document and folder responsibilities

| Path | Responsibility |
| --- | --- |
| README.md | First-time reader orientation and glossary |
| CLAUDE.md | Operational workflow, tool coordination and scope boundaries |
| PRODUCT.md | Existing workspace context |
| design-system/DESIGN.md | Shared technical quality floor |
| design-system/tokens.css | Shared defaults and token naming; project overrides remain scoped |
| design-system/motion.md | Shared motion/reduced-motion guidance |
| design-system/directions/ | Canonical reusable direction definitions |
| projects/ | Separate project source and studies |
| projects/design-direction-explorer/index.html | Explorer/Mixer demonstrations and brief export |
| projects/token-preview/ | Shared token demonstration |
| projects/<project>/brief.md | Client facts, goals, content inventory and gaps |
| projects/<project>/DESIGN.md | Project visual decisions, conflicts, review results and approval state |
| tools/taste-vault/data/ | Existing reference storage; preserve schema |
| .agents/skills/ | Reported workspace skill locations |
| .impeccable/config.json | Existing Impeccable configuration |
| docs/design-decisions.md | Confirmed shared decisions |
| docs/design-system-handbook.md | This explanatory handbook |

Do not duplicate operational instructions across every document. If changing behavior, update CLAUDE.md deliberately and keep explanatory documents aligned. Preserve actual project conventions rather than creating duplicate structures.

## 16. Templates and reusable structures

Templates standardize information and review evidence, not every page's appearance. These outlines are documentation; they are not claims that separate template files have been installed.

### Brand brief outline

Business; audience; personality; goals and primary action; verified offering/content; existing identity; usable assets; assumptions; unresolved facts; constraints; compact section argument.

### Direction proposal outline

Name; creative thesis; reference evidence; hero/composition; section rhythm; components; graphics/UI; typography/palette rationale; mobile/motion approach; content preservation; strengths/trade-offs; recommendation.

### Project guideline outline

Use Phase 4's fields. Keep values concrete and status explicit. Record approval and subsequent intentional changes.

### Sample review outline

Source version; scope; captures and actual viewport dimensions; observed strengths; largest weaknesses; interaction/accessibility checks; fixes made; blocked checks; approval status.

### Reference record outline

Source; inspected material; inspection method/date; applicable principles; observed versus inferred information; permissions/asset notes; project relevance. Map to the existing Vault schema rather than introducing incompatible fields.

## 17. Glossary

| Term | Meaning |
| --- | --- |
| Dealt sheet | A candidate direction brief produced by Taste's drawing script; not an approved design |
| Section argument | What a section claims and what supports the claim |
| Direction definition | Reusable creative principles for one direction |
| Composition repertoire | Multiple possible arrangements, not a required page skeleton |
| Creative concept | How subject-specific material becomes an organizing visual or interaction idea |
| Competitor test | A check for whether the idea is interchangeable with a competitor's page |
| Copy deck | Headings and body copy written before markup |
| Design token | Named value for typography, color, spacing or another design property |
| Annotated exhibit | Meaningful visual/interface/artifact accompanied by relevant explanation |
| Chaptered argument | Sections that build an explanation with deliberate pacing and treatment |
| Live thing | A useful visitor interaction, often a local conceptual demo |
| Visual sample | Limited implemented portion for evaluating a direction |
| Composition study | Focused visual exploration whose fidelity must be stated |
| Visual benchmark | User-approved example establishing a quality standard |
| Visual rhythm | Changes in scale, spacing, density and medium through a page |
| Viewport | Actual browser rendering area, not a mockup label |
| Reduced motion | Behavior adapted to a user's request for less animation |
| Provenance | Source and inspection/reuse history of a reference or asset |
| Sanctioned exception | Documented reasoned departure from guidance, without overriding user requirements |
| Gate | Evidence-based checkpoint before proceeding |
| Ready-made | A desired level of completeness; any readiness claim still needs a stated scope and supporting checks |

## 18. Current state and next work

**Reported implemented:** workspace workflow; Explorer; Taste Vault; skill setup; one connected Premium Editorial definition; draft Agentic Labs brief/guidelines; iterative sample with illustrative approval demo and reset; workspace README.

**Observed from supplied artifacts:** technical and functional improvements, but repeated split-hero composition, underdeveloped supporting layouts and incomplete mobile evidence. No sample has been established here as the approved visual benchmark.

**Latest requested deliverable:** separate Agentic Labs hero-composition.html, preserving sample.html. Editorial opening above a substantial decision-workspace exhibit, owner decision as focal point, actual desktop/mobile inspection. Check the Windows workspace before assuming it exists or is approved.

**Remaining priorities:**
1. Establish one visually convincing benchmark through actual rendered execution and review.
2. Demonstrate mobile/tablet inspection and interactions with final evidence.
3. Retain successful decisions without adding arbitrary bans.
4. Develop the other five direction definitions after validating the approach.
5. Keep shared guidance, tooling instructions and project-specific styling clearly separated.

No further broad setup audit is required by this handbook. It documents the agreed process; follow the current task's scope.

## 19. Getting started and resuming

Open PowerShell:

```powershell
cd C:\Users\Admin\ClaudeWorkspace
claude
```

To select an earlier session, use `claude --resume` if supported by the installed version.

New brief example:
> I need a website for a grounded, approachable yoga instructor in Los Angeles. Her main goal is inquiries about private sessions.

Continuation example:
> Continue Agentic Labs. Read the current brief and guidelines, inspect saved changes, and resume the last confirmed checkpoint without repeating completed work.

## 20. Boundaries and upkeep

Inspect before editing; preserve existing work; back up substantial changes. Keep clients in separate folders and project styling scoped. Do not overwrite shared tokens, unrelated projects, other direction identities or installed third-party skills while refining a sample.

This handbook does not authorize paid APIs, image generation, new dependencies, deployment or live-site modification. Use explicit user authorization and the current task scope.

Update documentation when confirmed decisions change. Label drafts, user approval and verification status honestly. Read current files rather than treating old reports as authoritative runtime state.
