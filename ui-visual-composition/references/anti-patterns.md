# Anti-patterns for `ui-visual-composition`

Prioritize the anti-patterns an AI agent is most likely to produce accidentally: decoration before structure, arbitrary values, inaccessible color, generic cards, and happy-path-only polish.

## Anti-pattern: Designing the shell before the feature

What it looks like:
- The agent starts with nav bars, sidebars, logos, containers, or page chrome before defining the screen’s actual task and content.

Why it fails:
- Shell decisions depend on the features the product must support. Starting with chrome creates premature constraints and distracts from user goals.

Better approach:
- Design one concrete feature first. List the fields, content, actions, states, and success criterion; then choose the necessary frame.

Ask the user when:
- The primary task is unknown.

## Anti-pattern: Decoration before hierarchy

What it looks like:
- Gradients, shadows, icons, illustrations, animated effects, and brand colors are added while the primary content/action remains unclear.

Why it fails:
- Decoration cannot compensate for weak information hierarchy. It often adds noise and makes everything compete.

Better approach:
- Build a grayscale layout first using size, weight, contrast, spacing, and placement. Add color and effects only after hierarchy works.

Ask the user when:
- Brand expressiveness could conflict with task clarity.

## Anti-pattern: Making everything important

What it looks like:
- Multiple filled buttons, large headings, badges, alerts, saturated colors, bold labels, and heavy borders all appear on the same screen.

Why it fails:
- Users cannot distinguish priority. Emphasis works only when most elements are quieter.

Better approach:
- Rank elements as primary, secondary, tertiary, and ambient. Make one thing clearly dominant and de-emphasize the rest.

Ask the user when:
- User priority and business priority conflict.

## Anti-pattern: Ambiguous spacing

What it looks like:
- Spacing between a label and value is similar to spacing between unrelated groups; cards, form fields, or controls float without clear relationships.

Why it fails:
- Users infer meaning from proximity. Ambiguous spacing creates ambiguous structure.

Better approach:
- Make within-group spacing clearly smaller than between-group spacing. Use common regions or dividers only where spacing alone cannot clarify relationships.

Ask the user when:
- The UI must be unusually dense.

## Anti-pattern: Arbitrary pixel nudging

What it looks like:
- The UI contains one-off values like 13px, 17px, 23px, 29px, or subtly different gaps that have no design-system role.

Why it fails:
- It slows design work and creates inconsistency that feels unpolished.

Better approach:
- Use a constrained spacing and sizing scale with visibly meaningful steps; define tokens for recurring values.

Ask the user when:
- Existing design-system tokens may already exist.

## Anti-pattern: Rigid grid worship

What it looks like:
- The agent forces every element into a strict grid even when content relationships, line lengths, or responsive behavior suffer.

Why it fails:
- A grid is a flexible structural tool, not a substitute for judgment. Overly rigid grids can make content harder to scan.

Better approach:
- Use grids to align and relate content, but allow content, hierarchy, and responsiveness to override the grid when needed.

Ask the user when:
- The output is editorial, data-heavy, or has strict design-system grid rules.

## Anti-pattern: Full-width text by default

What it looks like:
- Body copy, descriptions, settings text, and forms stretch edge to edge across large screens.

Why it fails:
- Long line lengths slow reading and make groups feel disconnected.

Better approach:
- Use max-width containers for prose and forms; reserve full width for canvases, maps, tables, timelines, or media that need it.

Ask the user when:
- The content type may require wide data comparison.

## Anti-pattern: Type confetti

What it looks like:
- Too many fonts, weights, sizes, colors, all-caps treatments, italics, underlines, and letter-spacing rules appear in one interface.

Why it fails:
- Typography stops expressing structure and becomes noise.

Better approach:
- Use a small type scale and no more than a few consistent cues per hierarchy level. Use one emphasis cue for inline emphasis in most cases.

Ask the user when:
- Brand typography requires expressive variation.

## Anti-pattern: Distorted or fake type styles

What it looks like:
- Text is horizontally stretched, vertically squashed, fake-bolded, or pseudo-italicized.

Why it fails:
- Distortion damages the typeface’s proportions and makes UI look amateurish.

Better approach:
- Choose a typeface family with the needed weight, width, optical size, italic, small caps, and numeral support.

Ask the user when:
- Font licensing or brand fonts constrain available styles.

## Anti-pattern: Labels as visual crutches

What it looks like:
- Every value has a loud label even when the value and context already communicate meaning.

Why it fails:
- Excess labels add noise and reduce scanability.

Better approach:
- Let obvious values carry meaning. Use labels where ambiguity remains, and make labels quieter than the values.

Ask the user when:
- Compliance, accessibility, or unfamiliar data requires explicit labels.

## Anti-pattern: Color-only meaning

What it looks like:
- Errors, statuses, selected states, required fields, chart series, or links differ only by color.

Why it fails:
- Users with color-vision differences, low vision, poor displays, or bright environments may miss the meaning.

Better approach:
- Pair color with text, icons, shape, pattern, position, or interaction state.

Ask the user when:
- Domain-specific color meanings are regulated or culturally sensitive.

## Anti-pattern: Low-contrast gray on colored backgrounds

What it looks like:
- Muted gray text is placed on blue, purple, red, green, or gradient surfaces.

Why it fails:
- Gray may lose contrast and look dirty or disabled against saturated backgrounds.

Better approach:
- Choose foreground colors tuned to the background hue/lightness; verify contrast.

Ask the user when:
- Brand palette is fixed and contrast constraints are hard.

## Anti-pattern: Border overload

What it looks like:
- Cards, table cells, inputs, sections, sidebars, and headers all use heavy borders.

Why it fails:
- Borders increase visual noise and can make a UI feel boxed-in and brittle.

Better approach:
- Use spacing, background contrast, subtle dividers, shadows, or accent borders only where they clarify structure.

Ask the user when:
- Data tables or dense forms require explicit cell/field separation.

## Anti-pattern: Inconsistent shadows and fake physics

What it looks like:
- Shadows point in different directions, huge blurs appear on tiny controls, or everything floats at the same elevation.

Why it fails:
- Depth cues become decorative noise and no longer explain layers.

Better approach:
- Use a small elevation scale and a consistent light source. Reserve high elevation for modals and blocking layers.

Ask the user when:
- Brand style is intentionally flat or skeuomorphic.

## Anti-pattern: Fragile image overlays

What it looks like:
- White or black text is placed directly over photos without a protective overlay, assuming every image resembles the mockup.

Why it fails:
- Real images vary in brightness, contrast, crop, and subject; text becomes unreadable.

Better approach:
- Use gradients, scrims, solid panels, controlled crops, or separate text areas. Treat UGC as unpredictable.

Ask the user when:
- Image sources, moderation, or user uploads are unknown.

## Anti-pattern: Happy-path-only polish

What it looks like:
- The UI looks polished only with perfect content and no loading, errors, empty data, disabled controls, long labels, or narrow screens.

Why it fails:
- Real product experience includes edge states; neglected states make users lose confidence at critical moments.

Better approach:
- Design empty, loading, error, disabled, selected, focus, long-content, missing-media, and success states as part of the visual system.

Ask the user when:
- Production content volatility is unknown.

## Anti-pattern: Hiding all complexity

What it looks like:
- The UI removes controls, labels, details, or constraints until the screen looks simple but users cannot understand consequences or recover.

Why it fails:
- Some complexity is inherent and must be handled by the system or surfaced to the user at the right moment.

Better approach:
- Chunk and progressively disclose complexity. Keep consequences, constraints, and recovery paths visible when users need them.

Ask the user when:
- Expert users may need full control or comparison.

## Anti-pattern: Novel controls without affordance

What it looks like:
- Custom toggles, cards, menus, sliders, or gestures look unique but do not clearly indicate how to use them.

Why it fails:
- Users rely on mental models and visible affordances. Hidden or unfamiliar interactions increase errors and abandonment.

Better approach:
- Preserve standard affordances for core controls. If using a custom visual, keep semantics, labels, feedback, and keyboard behavior intact.

Ask the user when:
- The brand or product strategy intentionally requires a novel interaction.

## Anti-pattern: Kitchen-sink visibility

What it looks like:
- Every option, state, control, and explanation is visible at once in the name of clarity.

Why it fails:
- Too much visible information increases cognitive load and makes important options harder to find.

Better approach:
- Make current status, primary options, and likely next actions visible. Use progressive disclosure for advanced or rare options.

Ask the user when:
- Expert workflows require simultaneous access to many controls.

## Anti-pattern: Motion as the only signal

What it looks like:
- Motion is used to communicate state changes, errors, or attention without static text/icon/position alternatives.

Why it fails:
- Motion-sensitive users may disable motion or be harmed by it; users may miss brief animated cues.

Better approach:
- Use motion to reinforce feedback, not carry essential meaning alone. Respect reduced-motion preferences.

Ask the user when:
- Brand motion or entertainment value is a core requirement.
