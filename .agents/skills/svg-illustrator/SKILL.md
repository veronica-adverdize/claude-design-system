---
name: svg-illustrator
description: Hand-code custom SVG illustrations, scenes, characters, icons, maps and decorative shapes for websites. No API, no credits, no external tools. Use when a brief asks for custom-made graphics, illustrated scenes, storybook or playful styles, mascots, icon sets, or illustrated maps, or when existing illustrations look flat, clip-art-like, or like loose shapes stacked together.
---

# SVG Illustrator

Writes illustrations as inline SVG code directly in the page. Free, editable, recolorable, animatable, and sharp at every size. Pairs with `design-taste-frontend` (art direction) and `animate` (motion).

## When to use SVG vs photos

| Need | Use |
|------|-----|
| Scenes, characters, icons, maps, dividers, decorative shapes | Custom SVG (this skill) |
| Real facility, real people, real products, "lots of pictures" | Photography (Unsplash placeholders, labeled as placeholders) |
| User asks for both | Both. Never swap one for the other |

## Step 1: Build a style sheet before drawing anything

Write this down once per project, then every illustration follows it. Mismatched styles are the main reason a set looks amateur.

- **Line**: outlined or filled-only. If outlined: one stroke width (e.g. 3px), round caps and joins
- **Palette**: 5 to 7 colors max for the whole set. One ink color for outlines, never pure black
- **Shading**: one light direction (e.g. top-left). Shade shapes with a darker tone of their own color, placed bottom-right
- **Corner language**: all round, or all angular. Do not mix
- **Character proportions**: head-to-body ratio, eye style, nose style, set once and reused
- **Texture**: none, or one subtle grain/dot pattern used everywhere

## Step 2: Compose in layers

Every scene has at least four layers, drawn back to front:

1. **Background**: sky, wall, or ground color field, plus soft shapes at low opacity
2. **Midground**: furniture, buildings, plants, props
3. **Subject**: the characters or hero object, largest and highest contrast
4. **Foreground accents**: leaves, particles, overlapping edges that frame the subject

Rules:
- One focal point per scene. The subject gets the most contrast and detail
- Overlap shapes. Flat objects floating side by side read as clip art
- Use a ground shadow (soft ellipse) under every object so it sits in the scene
- Leave breathing room: subject fills about 60 percent of the frame, not 95

## Step 3: Add depth with SVG features

The previous storybook build used none of these. Use them.

- **Gradients**: `linearGradient` on large fills (sky, ground, bodies) with a subtle 2-tone shift
- **Shading shapes**: a darker copy of the shape, clipped to it with `clipPath`, offset to the shadow side
- **Highlights**: small light shapes (eye glints, rim highlights) in one consistent spot
- **Soft shadows**: blurred ellipse via `feGaussianBlur`, low opacity. Use sparingly for performance
- **Reuse**: define repeated parts (paws, leaves, stars) once in `<defs>` as `<symbol>` and place with `<use>`
- **Color via CSS variables**: `fill="var(--c-accent)"` so one illustration recolors per chapter or dark mode

## Step 4: Draw characters (pets, mascots)

- Start from 3 primitives: body (rounded blob), head (circle or rounded shape), limbs (rounded rectangles or paths)
- Build the face last: eyes with a glint, small nose, mouth curve. Faces carry the emotion
- Give each pet 2 or 3 identifying traits (ear shape, spot, tail curl)
- Poses show action: tilt the body, lift one paw, tuck the tail. Avoid stiff front-facing stands
- Keep each character in named groups: `<g id="dog-head">`, `<g id="dog-tail">` so they can be animated

## Step 5: Make it move (SVG animation)

Motion lives inside the scene, not only on scroll reveal. Aim for 3 to 6 small moving parts per scene:

- Tail wag, ear flick, blink (scale Y on eyes), breathing (scale 1 to 1.02)
- Floating particles: zzz, bubbles, sparkles, falling leaves
- Prop motion: swinging toy, steam from a bowl, bouncing ball
- Rules: animate only `transform` and `opacity`, set `transform-box: fill-box; transform-origin` on the group, use CSS keyframes, 2 to 6 second loops with `ease-in-out`, and disable under `prefers-reduced-motion`

## Step 6: Icon sets

- 24x24 or 32x32 viewBox, same stroke width and cap style across the entire set
- Draw on a pixel grid, align strokes to whole or half pixels
- `stroke="currentColor"` so icons inherit text color
- One distinctive custom detail per icon (a paw in the corner, a rounded notch). This is what makes it "custom-made" instead of a stock set
- Test at 24px. If it reads poorly, simplify

## Step 7: Illustrated maps and diagrams

- Top-down or isometric, pick one
- Zones are separate `<g>` groups with `tabindex="0"`, hover and focus states, labels, and a text alternative
- Use consistent landmarks (trees, paths, water) to tie zones together
- On mobile, collapse the map to a tappable list

## Step 8: Decorative shapes and dividers

- Blobs, waves, squiggles, stars, and paw prints from the same corner language as the characters
- Wavy dividers: `preserveAspectRatio="none"`, fill matches the next section
- Scatter at low opacity (0.08 to 0.15), vary size and rotation, keep out of text areas

## Step 9: Accessibility and performance

- Meaningful illustrations: `role="img"` plus `<title>` and `<desc>`. Decorative ones: `aria-hidden="true"`
- Text never baked into SVG paths for content that matters
- Keep each scene under about 15 KB. Remove unused groups, round coordinates to 1 decimal, avoid hundreds of tiny paths
- Never use filters on large animated areas

## Quality checklist (run before presenting)

- [ ] Style sheet written and followed by every illustration
- [ ] Each scene has 4 or more layers and one clear focal point
- [ ] No object floats: shadows or overlaps ground everything
- [ ] Gradients or shading present, not flat fills only
- [ ] 3 or more moving parts per hero scene, reduced-motion handled
- [ ] Characters have faces with life (eye glints, expression) and named groups
- [ ] Palette limited to 5 to 7 colors plus ink
- [ ] Squint test: shapes still read when blurred
- [ ] Cover-the-logo test: scene could only belong to this client's concept
- [ ] Icons identical in stroke, cap, and corner language
- [ ] Accessibility attributes set, file size within budget
- [ ] Viewed in a real browser at 390px and 1440px, not just read as code

## Common failures to fix

- **Loose shapes stacked**: add overlap, shadow, and a shared light direction
- **Everything the same size**: scale up the subject, shrink props
- **Rainbow palette**: cut to the style sheet palette
- **Static scene**: add the small loops from Step 5
- **Stiff characters**: tilt, offset, and add a secondary action

## No emojis

Never use emojis anywhere in a built page. Standard UI icons use Font Awesome 6.5.1. Branded, decorative, or concept-specific icons use custom inline SVG from this skill. Scan the output for emoji characters before presenting.

