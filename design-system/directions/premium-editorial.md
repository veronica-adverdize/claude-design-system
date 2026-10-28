# Premium Editorial — Foundation v1

Status: draft specification; not installed, visually validated, or approved.
Direction identity: `editorial` / Premium Editorial. Preserve the other five direction identities.
Scope: one reusable direction definition, project decision template, and minimal integration plan. This is design guidance, not an installed Claude skill or a finished website template.

## 1. Evidence from the supplied Explorer

Source inspected: uploaded projects/design-direction-explorer/index.html. Code inspection only; no browser testing of the Explorer performed for this document.

- DIRS.editorial describes literary serif, whitespace and palette, then supplies fixed typography and color values.
- buildEditorial uses a standard split hero with a decorative curve SVG, two feature entries, an attributed quote, shared stats, shared closing CTA and shared footer.
- Five builders reuse features3col(); all six use stats() and ctaBanner(). The section variation is real but limited.
- The editorial builder omits the shared third capability, Monitor outcomes. Thus comparisons do not preserve the same content inventory.
- Quote attributions, numerical claims and trust logos are demo content but are not visibly identified as fictional inside those sections. These must not be treated as evidence or copied into client work.
- The direction builders are local to the Explorer. No integration with Taste or an external direction specification was found in this file.

These observations explain limitations of the Explorer. They do not prove which instructions Claude loaded while creating earlier samples.

## 2. Core intent

Communicate through a carefully edited sequence of ideas, evidence and images. Make the brand's point of view legible and memorable. The page should feel composed for its particular subject, with relationships between headline, supporting copy, imagery, captions and action.

Editorial means intentional hierarchy and sequencing. It does not require a serif, beige ground, thin rules, italic headlines, sparse content or large empty areas.

### Fit and boundaries

Consider when the visitor benefits from a narrative, distinctive voice, visible expertise, considered work or a personal relationship. This may suit a service business, agency, cultural organization, publication, product or practitioner.

Reconsider when rapid comparison, dense task execution or frequent transactional use should dominate. Editorial presentation can introduce a complex product, but its operational controls still need functional UI.

Before selecting: name the audience question, the brand's distinctive point of view, and the strongest available supporting evidence. If these are unknown, keep the direction provisional.

## 3. Invariants and freedoms

Invariants:
- A visitor can identify the offering and intended next action without interpreting decorative elements.
- Prominence follows information importance, not the convenience of a component library.
- Layout relationships are intentional: shared alignments, controlled contrasts in scale and a readable sequence.
- Each major visual has a communication role.
- Important supplied content remains represented; layout does not silently delete facts.

Project freedoms:
- Serif, sans, mixed or custom lettering may lead; select for brand character and actual words.
- Light, dark or chromatic grounds are all possible. No mandatory cream or brown.
- Compact and expansive passages may coexist. No mandatory full-screen hero.
- Photography, illustrations, diagrams or product UI may carry the argument.
- Shared token names can remain stable while project values change. Existing shared files remain untouched.

## 4. Composition repertoire — choose, adapt, combine

These are possibilities, not complete reusable page skeletons. Select based on content and reference evidence.

| Composition | Relationships | Suitable evidence | Mobile transformation |
| --- | --- | --- | --- |
| Opening spread | Headline occupies a dominant grid span; a smaller image or graphic offsets it; introduction and action share an obvious reading path | A concise proposition plus one meaningful visual | Reorder into a deliberate headline/visual/introduction/action sequence; choose the order by message, not desktop coordinates |
| Annotated exhibit | One substantial image, artifact or interface becomes the exhibit; short annotations explain selected details | Actual work, process evidence or clearly labeled conceptual UI | Replace floating labels with a numbered legend beside or beneath the relevant detail; preserve meaning |
| Chaptered argument | A short opening claim leads into alternating dense and quiet chapters; chapter labels aid navigation | Services or an approach needing explanation | Keep chapter identities and reading sequence; remove ornamental offsets rather than shrinking everything |
| Typographic conversation | Contrasting text sizes establish proposition, response and supporting evidence across a grid | Strong supplied language, little usable imagery | Retune line breaks and lengths; keep supporting content and CTA readable instead of forcing poster proportions |

Before coding, explain why the chosen composition suits this brand and what distinguishes it from the other proposed directions. Do not choose solely because it is available in Taste's library.

## 5. Typography and palette decisions

Choose typography using the actual headline and representative body copy. Test line breaks, glyph character, weight, reading comfort and the relationship with UI text. Specify display, section-heading, body, caption and control roles. Several roles may share one family.

Record concrete project values in DESIGN.md, including fluid bounds, line heights, text measures and fallback fonts. Shared scales are starting points, not a ceiling or requirement to force all roles into the same proportions.

Select colors from the brand's identity or a deliberate interpretation of its context. Reference colors are evidence to assess, not automatically a client palette. Define semantic foreground/background pairs and verify their contrast. For text on imagery, test the actual crop and composited overlay. Do not dismiss a warning merely because a scrim exists.

## 6. Section rhythm and components

Map the available content before selecting section patterns. Describe why each transition changes scale, density, alignment or medium. Similar content may use repeated components where comparison benefits; unrelated sections should not default to the same card grid.

Possible treatments:
- Services: numbered entries with a short argument and relevant artifact, or a legible comparative list.
- Process: annotated sequence or narrative chapters; show dependencies where useful.
- Work: image/diagram with caption explaining the problem and approach, using only supplied outcomes.
- Evidence: verified quotation, supplied credential or actual example; omit unavailable proof instead of fabricating it.
- Conversion: specific next step near the relevant decision, with expected behavior clear.

Keep navigation recognizable and actions operable. Reuse button, field and focus behavior within a project. An unusual navigation position needs a demonstrated benefit.

## 7. Graphics, custom UI and imagery

For every substantial visual record: message supported, source, factual status, caption, desktop role and mobile treatment.

- Product/system brief: an editorial exhibit can show a substantial dashboard or workflow with readable labels and purposeful annotations. Build a coherent interface, not floating decorative cards. Conceptual functionality and illustrative values must be labeled near the visualization.
- Personal/service brief: portraits, materials, work or environmental details should reveal something specific. Stock atmosphere is illustrative and must not imply the pictured person is the client or the location is their premises.
- Limited imagery: use precise typography, meaningful native SVG diagrams or subject-specific illustration where appropriate. Do not let missing photography force generic abstract circles or empty gradients.
- Illustrative assets: check source and reuse permissions. Do not claim an image proves local geography or client identity without evidence.

Do not add dashboards to brands that have no reason to show one. Do not generate images or use paid services without the project's authorization.

## 8. Motion and responsive behavior

Motion should clarify sequence, relationships or interaction. Choose a small coherent vocabulary; do not animate every element by default.

For each behavior specify trigger, moving element, purpose, duration/easing, keyboard/touch equivalent and reduced-motion state. Use installed motion guidance to tune implementation. Content remains available if entrance animation or JavaScript fails.

Sticky exhibits are optional. Use them only when the adjacent reading sequence benefits; test short screens, zoom and mobile. Respect user scrolling. Avoid forced scrolling, mandatory hover content and motion that delays the primary action.

Build one responsive implementation. Capture actual target viewport sizes, including 1440px and 390px for the sample; inspect intermediate and narrow widths where wrapping indicates risk. A small duplicate mockup labeled 390px is not evidence of responsive behavior.

## 9. Content and reference evidence

Before exploration make a compact inventory: supplied fact / supplied copy / draft expression / unknown. Draft copy may express the supplied personality and goals without inventing service details, credentials, results or personal history. Keep unknown factual fields explicit.

Before detailed implementation, inspect a small relevant reference set visually when tools allow. For each source record what was actually inspected and one applicable principle. A source may contribute typography, composition or graphics rather than its whole page.

If screenshots are unavailable, say so. Mark visual judgments provisional; do not convert fetched text, library descriptions or numerical norms into claims of observed visual quality.

## 10. Sample review and approval

After direction choice and draft guidelines, build hero plus two supporting sections unless the user explicitly sets a smaller scope. Use enough realistic draft copy and authorized imagery to assess the design, with factual gaps clearly identified.

Assess the rendered sample against:
1. Brand fit: does the design express the agreed personality through specific visible decisions?
2. Clarity: can a visitor identify the offering and next action?
3. Composition: do scale, alignment, image placement and density form an intentional hierarchy?
4. Distinctness: does it differ structurally from other options while preserving the same key content?
5. Visual substance: do images/graphics explain something, and are essential assets representative enough to judge?
6. Execution: typography, crops, spacing, controls and responsive transformations hold together.
7. Integrity: business facts and conceptual elements are represented honestly.
8. Accessibility: review demonstrated contrast, focus, operability and reduced-motion behavior with suitable checks.

Report observed weaknesses plainly. A deliberate choice can still be unsuccessful. Do not defend a weak result using the direction label or reference measurements. Static screenshots alone do not prove interaction, performance or accessibility compliance.

State what ran, what failed and what is untested. Wait for explicit sample approval before full implementation. This definition remains unvalidated until a user-reviewed sample demonstrates it.

## 11. Project guideline template

Use the existing project DESIGN.md where present. Keep completed decisions concise; do not leave competing instructions unresolved.

### Identity and state
- Project; selected direction ID/name; status (draft/sample-approved/implementation).
- Relevant brand brief and content inventory locations.
- Direction changes explicitly authorized by the user.

### Creative thesis
- One sentence describing the intended impression and why it serves this audience.
- Selected composition and content sequence, with reasons.
- Distinction from the other explored options.

### Reference evidence
- Source URL or supplied asset; inspection method/date; applicable principle.
- What was observed versus inferred; assets and permission status.

### Concrete visual decisions
- Type roles: family/fallback, weight, size bounds, leading, tracking, measure.
- Color pairs and surface roles; contrast check results and limitations.
- Container, grid, spacing and density decisions.
- Component treatment and interaction states.
- Graphics/interface/image roles; conceptual labels and mobile versions.
- Motion behaviors and reduced-motion equivalents.
- Responsive transformations and content order.

### Scope and review
- Content preservation map and unresolved factual fields.
- Sample scope, capture dimensions and checks actually run.
- User feedback, approved decisions, unresolved weaknesses and approval state.

## 12. Minimal integration plan for the actual workspace

Proposed new canonical file: design-system/directions/premium-editorial.md. Inspect the destination before adding it; merge with an existing matching definition if present. This document is the draft content for that definition; its implementation notes need not be loaded during every project task.

Focused CLAUDE.md addition under direction exploration:

> For Premium Editorial, load design-system/directions/premium-editorial.md before developing the proposal. Treat Explorer colors, fonts and layouts as demonstrations, not mandatory values. Taste supports brand-specific composition development; its library does not replace this direction's principles. Preserve the approved brand facts and all key content. Record the chosen interpretation in the project's DESIGN.md. Do not claim a direction definition is integrated merely because a file exists: demonstrate that it was loaded and influenced a test proposal.

Explorer integration, staged:
1. Preserve all six IDs/names and Mixer behavior. Add a concise editorial principle summary and a pointer to the canonical definition in its existing presentation/export path. Confirm the actual export function before editing it.
2. Mark FlowStack demonstration content visibly as fictional. Do not transfer demo metrics or endorsements into project briefs.
3. Preserve Connect your tools, Automate workflows and Monitor outcomes across comparisons; vary their presentation rather than silently omitting a capability.
4. Only after the definition is reviewed, revise buildEditorial to demonstrate one intentional editorial composition. It remains an example, not the required structure for every editorial project.
5. Keep the other five builders and shared tokens unchanged in this first pass. Give the remaining directions equally concrete definitions after testing the first.

Do not add dependencies, rebuild the Explorer, overwrite existing project sites or deploy anything for this integration.

## 13. Validation status

Completed here: source inspection and drafting a reusable direction definition, project guideline template and integration plan.
Not completed: editing the user's Windows workspace, updating CLAUDE.md or the Explorer, executing Taste, reference research, browser tests or validation of design quality.
