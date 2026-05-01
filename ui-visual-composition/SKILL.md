---
name: ui-visual-composition
description: "Use when creating, critiquing, or refining visual UI, including hierarchy, spacing, typography, color, depth, imagery, or visual states."
---

# UI Visual Composition

## Purpose

Help an AI agent create and critique polished visual UI through hierarchy, spacing, typography, color, depth, imagery, and finishing details. Treat visual design as functional communication: the interface should help users understand what matters, what belongs together, what can be acted on, and what has changed.

This skill covers visual design quality, layout composition, typography, color systems, depth, imagery, polish, accessibility, and frontend implementation choices that affect visual quality. It does not cover deep UX research, information architecture strategy, or frontend architecture except where those concerns determine visual composition.

## When to use this skill

Use this skill when the user asks for UI critique, redesign, product-page improvement, frontend visual implementation, design-system guidance, style polish, layout refinement, typography, color palette, empty/error/loading state improvement, or visual QA of generated UI.

Also use it when producing frontend code for a visual interface, because component structure, semantic markup, tokens, state styling, responsive behavior, and accessibility details determine whether visual recommendations survive implementation.

## When not to use this skill

Do not use this skill as the primary framework when the user is asking mainly for user research planning, product strategy, market positioning, analytics instrumentation, backend/frontend architecture, performance engineering, copywriting without visual presentation, or detailed interaction flow design. Use it only for the visual-design portions of those tasks.

Do not use it to justify arbitrary decoration. If a visual suggestion does not improve hierarchy, comprehension, perceived quality, accessibility, or fit with product context, remove it.

## Core principles

1. **Start with the feature, not the shell.** Identify the concrete user task and content before designing navigation chrome, page framing, or decorative treatments.
2. **Hierarchy is the backbone.** Make the most important content and actions easiest to notice. Use size, weight, contrast, spacing, placement, and order before relying on color or ornament.
3. **Use familiar patterns unless novelty has a purpose.** Users bring mental models from other products. Preserve conventions for common controls, navigation, forms, and feedback unless the user’s brand or product goal justifies a deliberate departure.
4. **Group by meaning.** Proximity, common regions, alignment, and connectedness should match conceptual relationships. Ambiguous spacing creates ambiguous meaning.
5. **Constrain choices with systems.** Use type, spacing, color, radius, border, and elevation tokens instead of ad hoc one-off values.
6. **Typography is interface structure.** Choose type that fits the content and context, then set readable line length, line height, alignment, emphasis, and hierarchy.
7. **Color must carry meaning safely.** Use color to reinforce hierarchy, state, and brand, but never as the only signal. Maintain contrast and test against color-vision and low-vision needs.
8. **Depth should explain layers.** Shadows, overlaps, borders, and background shifts should clarify elevation, grouping, focus, or interaction—not create visual noise.
9. **Aesthetics improve acceptance but do not excuse usability flaws.** Polish can make users more tolerant and confident, but it can also mask problems. Verify clarity, accessibility, and task fit before celebrating beauty.
10. **Simplify without hiding necessary complexity.** Reduce visible choices and chunk complex tasks, but do not abstract away information users need to decide or recover.
11. **Design for resilient real content.** User-uploaded images, long labels, empty data, errors, loading, disabled states, and localization must not break the composition.
12. **Explain tradeoffs in user-centered terms.** Recommendations should reference user goals, comprehension, accessibility, system consistency, and implementation feasibility.

## Default recommendations

Use these defaults unless the user gives context that makes another choice better.

| Area | Default | Why it is usually best | Override when | Ask before overriding |
|---|---|---|---|---|
| Product/task focus | Begin with one core feature or screen goal | Prevents designing app chrome before content and actions are known | User is explicitly asking for global navigation, design-system shell, or IA | Ask for the primary task and the screen’s success criterion |
| Visual direction | Professional, warm, restrained, and content-first | Works for most productivity, SaaS, dashboard, admin, and commerce interfaces | Brand is playful, luxury, editorial, youth-focused, highly technical, or campaign-like | Ask for brand personality and examples |
| Information density | Comfortable spacing first; reduce only deliberately | Spacious layouts usually read as cleaner and clearer | Dashboard, pro tool, trading, ops, or data-monitoring context requires high density | Ask about density and scan speed needs |
| Layout strategy | Content-width container with clear groups; avoid filling the screen by default | Reduces line length and visual drift on large screens | Immersive canvas, map, media, spreadsheet, timeline, or data grid needs full width | Ask what content needs to stay visible together |
| Grid | Use a simple flexible grid plus tokenized spacing, not a rigid layout for its own sake | Helps alignment without forcing content into arbitrary columns | Editorial, marketing, or data-dense layouts need stronger grid logic | Ask about content types and responsive breakpoints |
| Typography | System UI or high-quality neutral sans for UI; pair with one expressive display face only when brand calls for it | Reduces loading risk and improves legibility | Editorial/brand work needs a distinct typographic voice | Ask for brand tone and font constraints |
| Type scale | Small set of reusable steps for body, supporting text, labels, titles, and display | Reduces inconsistent hierarchy | Existing design system has a scale | Ask for the design-system token source |
| Line length | Keep prose and long-form text in a readable measure; avoid edge-to-edge text | Improves scanning and reading comfort | Data tables, code, or short cards need different measures | Ask only if the content type is unusual |
| Color | Build semantic roles from a limited palette with neutral scale, accent scale, success/warning/error/info, and focus states | Supports consistency and accessibility | Brand palette is fixed or compliance/regulatory states are prescribed | Ask for brand palette and accessibility target |
| Contrast | Treat contrast as a functional requirement; verify text, icons, controls, and states | Prevents inaccessible or low-confidence UI | Large decorative text or nonessential illustration is exempt | Ask if the product requires a specific accessibility standard |
| Depth | Use a small elevation scale and one consistent light model | Creates layers without visual chaos | Brand is intentionally flat/brutalist or skeuomorphic | Ask only if depth direction is a brand choice |
| Imagery | Use high-quality, purpose-fit imagery; protect text overlays with scrims/gradients/containers | Images vary and can destroy readability | User provides fixed photography or UGC | Ask about image source and volatility |
| Borders | Use spacing, background, shadow, or subtle dividers before adding many borders | Borders add noise quickly | Data tables, legal forms, or dense settings screens need explicit separation | Ask if density or tabular precision matters |
| Empty states | Include helpful empty states with next action | Empty states are part of the experience, not blank failure | Empty state is impossible or intentionally hidden | Do not ask; implement by default |
| Motion | Use subtle, purposeful motion for feedback, continuity, and loading; respect reduced-motion preferences | Adds clarity without distraction | Product is entertainment-heavy or brand motion is a key differentiator | Ask about motion appetite and accessibility constraints |
| Frontend implementation | Use semantic HTML, design tokens, responsive CSS, visible focus states, keyboard access, and state variants | Preserves visual quality and accessibility in real UI | Prototype is static and disposable | Ask if production constraints or framework/design-system rules exist |

## Required user questions

Do not ask users to confirm routine best practices such as readable text, sufficient contrast, or clear hierarchy. Apply those by default.

Ask a focused question only when the answer materially changes the visual solution. Use the `question` tool or equivalent when available. Good triggers:

- The product goal, primary task, audience, or platform is unknown and cannot be inferred.
- Brand personality or visual tone could plausibly change type, color, density, imagery, or ornament.
- The user asks for a redesign but does not provide the current UI, screenshot, code, design-system constraints, or success criteria.
- Accessibility target, compliance context, or audience needs are stricter than ordinary inclusive defaults.
- The UI will handle volatile content such as user-uploaded images, localization, very long names, unknown data density, or generated content.
- The user requests novelty that could conflict with familiar mental models or platform conventions.
- The user asks for frontend implementation and the target framework, design system, or CSS constraints matter.

When asking, include a recommended default and options. Ask one question at a time unless the user explicitly requests a thorough discovery process.

## Workflow: critique existing UI

When reviewing an existing UI, inspect in this order:

1. **Task and context fit.** Identify the primary user goal, audience, platform, and success criterion. If missing, infer cautiously and state the assumption.
2. **Mental model and convention fit.** Check whether common controls, navigation, search, forms, and feedback behave like users expect.
3. **Information hierarchy.** Identify the intended primary content/action. Verify that the visual hierarchy matches importance, not just document order or semantic severity.
4. **Grouping and layout.** Check proximity, alignment, common regions, screen width, responsive behavior, and ambiguous spacing.
5. **Typography.** Check font choice, type scale, line length, line height, emphasis, label treatment, alignment, and long-content behavior.
6. **Color and contrast.** Check palette roles, contrast, semantic states, color-only meaning, hue/saturation balance, and dark/light mode implications.
7. **Depth and layer logic.** Check shadows, borders, overlaps, surface colors, modals, popovers, cards, and focus hierarchy.
8. **Imagery and media.** Check image quality, crop, intended size, overlay text contrast, loading failures, UGC, and alt text needs.
9. **States and resilience.** Check empty, loading, error, disabled, focus, hover, selected, validation, destructive, and success states.
10. **Accessibility and inclusion.** Check perceptibility, operability, simplicity, forgiveness, keyboard flow, focus, touch target comfort, motion sensitivity, and screen-reader semantics.
11. **Frontend feasibility.** Check whether the visual recommendation can be implemented with tokens, semantic components, responsive CSS, and maintainable variants.
12. **Prioritize fixes.** Group findings into high-impact fixes, polish improvements, and context-dependent tradeoffs. Recommend the smallest set of changes likely to produce the biggest improvement.

## Workflow: create or improve UI

When generating a new design or recommendation, proceed in this order:

1. **Clarify the core feature.** Define the specific screen, task, audience, and completion goal. Start with content and functionality, not navigation chrome.
2. **List required elements.** Identify primary content, primary action, supporting actions, constraints, and states.
3. **Choose the simplest useful structure.** Sketch or describe the layout in low fidelity. Avoid color, shadows, icons, and detailed typography until the structure works.
4. **Create hierarchy in grayscale.** Use order, grouping, size, weight, spacing, and contrast first. Add color only after hierarchy is clear without it.
5. **Establish systems.** Choose type scale, spacing scale, grid/container rules, color roles, radius, borders, and elevation tokens.
6. **Compose the layout.** Arrange groups so related elements are near each other and unrelated elements are clearly separated. Avoid ambiguous spacing.
7. **Apply typography.** Set readable body text, strong titles, restrained labels, appropriate line height, consistent emphasis, and baseline/edge alignment.
8. **Apply color and states.** Use color for brand, affordance, state, and focus. Verify contrast and add non-color cues.
9. **Add depth and imagery.** Use shadows, overlap, background variation, and imagery only where they clarify surfaces, hierarchy, or brand.
10. **Design edge states.** Include empty, loading, error, disabled, selected, focus, hover, long-content, and narrow-screen behavior.
11. **Check accessibility and frontend implementation.** Ensure semantic structure, keyboard flow, focus visibility, responsive behavior, tokenization, and reduced-motion support.
12. **Explain decisions.** Present recommendations as user-goal and system-quality improvements, not personal taste.

## Decision framework

Use this framework whenever a visual decision is ambiguous:

1. **Does the decision affect task success?** Prefer clarity, familiarity, accessibility, and recovery over novelty.
2. **Does it express product personality?** If yes and brand context is missing, ask. If no, use the restrained default.
3. **Does it reduce or increase cognitive load?** Chunk, disclose progressively, and highlight recommended paths without hiding necessary complexity.
4. **Does it strengthen or confuse hierarchy?** Every visual cue should support a priority or relationship.
5. **Does it work with real content?** Test long labels, empty data, dense data, UGC, localization, dark mode, and responsive sizes.
6. **Can it be implemented consistently?** Prefer tokenized, reusable patterns over custom one-offs.
7. **Is it accessible without special pleading?** If it relies on color alone, tiny targets, hidden focus, motion, fragile contrast, or ambiguous labels, revise.

## Practical rules

### Hierarchy

- Rank elements before styling them. Decide what is primary, secondary, tertiary, and ambient.
- Do not make every important thing large, bold, colored, and boxed. Emphasize the primary and de-emphasize the rest.
- Use multiple visual levers carefully: size, weight, contrast, spacing, placement, color, and depth. One or two strong cues are often enough.
- A destructive action is not automatically the primary action. Style it according to its role in the current task; make it prominent only at the confirmation step if that is where the destructive decision occurs.
- Labels are a last resort for obvious structured data. When the value can carry the meaning, de-emphasize or remove the label.

### Layout and spacing

- Start with generous whitespace, then remove it until the layout fits the task. Do not start cramped and add tiny margins until it barely stops looking bad.
- Use a constrained spacing scale with meaningfully different steps. Avoid arbitrary pixel values that differ by only a few pixels.
- Avoid ambiguous spacing. Related items should be closer to each other than to other groups.
- Do not fill the whole screen by default. Limit text and content width when full width harms reading or grouping.
- Use grids as flexible structure, not as decoration. Let content and relationships determine the grid.
- Make dense layouts a deliberate choice for expert, monitoring, tabular, or high-frequency tasks.

### Typography

- Choose type for content, audience, platform, and brand—not because a font looks fashionable in isolation.
- Use a small type scale. Avoid tiny differences that look accidental.
- Keep body text readable. Use shorter line lengths for prose and cards, larger line heights for small text, and tighter line heights for large headings.
- Align text for readability. Prefer left alignment for most Latin-script body text. Use centered text sparingly for short, low-density content.
- Align text and controls by baseline when typography is the dominant visual element.
- Use real italic, small caps, numerals, and weights when available. Avoid fake slanting, horizontal stretching, and excessive tracking.
- Use no more than a few consistent cues per hierarchy level. Avoid combining bold, italics, underline, all caps, color, and size all at once.

### Color

- Define neutral, brand/accent, semantic, focus, and surface color roles before applying colors broadly.
- Prefer HSL/OKLCH-like thinking when adjusting hue, saturation, and lightness; do not pick isolated hex values one at a time.
- Use more shade steps than the final UI seems to require so hover, active, border, background, and text states can be consistent.
- Do not use gray text on saturated colored backgrounds if it reduces perceived contrast. Choose a color that belongs to that background.
- Keep saturation alive in light colors; avoid washed-out palettes that lose personality and state distinction.
- Use non-color cues for errors, success, warnings, selected states, links, and required fields.

### Depth, surfaces, and borders

- Use one consistent light model. Raised surfaces need highlights and shadows that make sense together.
- Use a small elevation scale. Low elevation for controls/cards, medium for popovers/dropdowns, high for modals and blocking surfaces.
- Prefer subtle background shifts, spacing, shadows, or accent edges before adding heavy borders everywhere.
- Overlap elements only when it clarifies layering, creates a purposeful focal point, or adds controlled energy. Do not overlap important text or controls in ways that reduce clarity.
- Flat design still needs depth cues: hierarchy, grouping, contrast, and surface changes.

### Images and media

- Use images with adequate resolution, strong crop, consistent style, and clear purpose.
- Never place text directly on unpredictable images without a contrast protection strategy: overlay, gradient, solid panel, blur, or controlled crop.
- Respect intended image size. Do not enlarge small assets beyond their quality or shrink detailed images until their content is illegible.
- Treat user-uploaded images as hostile to layout and contrast. Provide cropping, fallback surfaces, safe text placement, and moderation/placeholder states.

### Finishing details

- Improve default components intentionally: focus rings, empty states, hover/active/disabled states, selected states, validation, loading skeletons, and microcopy.
- Use accent borders, subtle backgrounds, and small decorative elements to add polish after hierarchy and accessibility are solved.
- Empty states should explain what is missing, why it matters, and what action to take next.
- Look for small high-leverage refinements: tighter heading line-height, better icon alignment, clearer selected state, more consistent radii, improved surface contrast, and less border noise.

## Accessibility and inclusion requirements

Treat accessibility as a core visual-composition requirement, not a compliance pass at the end.

- Ensure **perceptibility**: text, icons, controls, and states must be perceivable through contrast, size, labeling, alt text, and redundant cues.
- Ensure **operability**: controls must have comfortable target areas, keyboard access, logical focus order, and visible focus states.
- Ensure **simplicity**: reduce unnecessary complexity, use clear labels, reveal only relevant information when possible, and make modes visible.
- Ensure **forgiveness**: prevent errors where possible, explain errors near the relevant field, preserve user input, support undo/recovery when feasible, and make destructive actions deliberate.
- Do not rely on color alone. Pair color with text, icons, shape, position, or pattern.
- Respect reduced-motion preferences. Avoid attention-grabbing motion for critical meaning unless there is a non-motion alternative.
- Use platform-appropriate touch target minimums and increase target size/spacing when accuracy matters or use is mobile, shaky, or time-critical.
- Use inclusive imagery. Avoid visual choices that imply only one body type, ability, culture, device, or environment unless the product context requires that specificity.
- Default to WCAG AA-equivalent contrast and focus visibility for production UI. Ask only when the user’s product requires a stricter or different standard.

## Frontend implementation guidance

When the output includes frontend code or implementation advice, make the visual design implementable:

- Preserve semantic structure. Visual hierarchy may differ from document hierarchy, but headings, landmarks, lists, tables, buttons, links, and form controls must remain semantically correct.
- Use design tokens for spacing, font sizes, line heights, colors, radius, shadow/elevation, z-index, and motion duration/easing.
- Use responsive layout primitives: grid/flex, container queries or breakpoints where appropriate, max-widths for readable text, and fluid media.
- Provide component variants for primary/secondary/tertiary/destructive actions, selected states, hover, active, disabled, focus, loading, error, and success.
- Use real buttons for actions and real links for navigation. Do not style non-interactive elements as controls without semantics and keyboard behavior.
- Keep focus states visible and consistent with the color system. Do not remove outlines unless replacing them with an equally visible focus indicator.
- Use semantic tables for tabular data. Do not use tables for layout. For data-dense tables, prioritize alignment, scannability, sticky context, truncation rules, and responsive overflow behavior.
- Use CSS variables or theme tokens for light/dark modes. Do not invert colors mechanically; tune surfaces, borders, shadows, and semantic colors per mode.
- Optimize images with explicit dimensions, responsive sources, alt text, lazy loading where appropriate, and fallbacks for broken or missing media.
- Use reduced-motion media queries and avoid blocking user feedback behind long animations.
- Prefer a maintainable, slightly less novel solution over a custom visual treatment that requires fragile CSS or one-off state logic.

## Quality checklist

Before finalizing a critique, recommendation, or UI implementation, verify:

- The primary user task and primary action are obvious.
- The interface works in grayscale before color is added.
- Related elements are grouped by proximity, alignment, and common regions.
- Spacing, type, color, radius, and elevation use a limited system.
- Text is readable, lines are not too long, and hierarchy cues are consistent.
- Color contrast is sufficient, and color is not the only meaning carrier.
- Shadows, surfaces, and borders express real grouping or elevation.
- Images do not break text contrast, layout, or meaning.
- Empty, loading, error, focus, disabled, selected, and hover states are covered.
- Touch targets, keyboard flow, focus visibility, and screen-reader semantics are considered.
- The design handles long content, dense data, UGC, localization, and narrow screens.
- Recommendations are prioritized and explained in terms of user value.

## Common mistakes to avoid

- Designing the navigation shell before designing the feature.
- Adding color, shadows, gradients, and icons before hierarchy is clear.
- Using arbitrary pixel values instead of a spacing/type/color system.
- Making every important element visually loud.
- Using color alone for links, errors, status, or selection.
- Using too many borders instead of spacing, grouping, or background contrast.
- Treating a pretty UI as automatically usable.
- Over-simplifying until users cannot see the information needed to decide.
- Violating familiar mental models without a strong user or brand reason.
- Ignoring edge states because the static happy path looks polished.
- Generating frontend code that looks right but is inaccessible or semantically wrong.

## How to explain recommendations to the user

Explain visual recommendations as functional tradeoffs, not taste.

Use this pattern:

1. **Observation:** Describe what the current design is doing.
2. **Effect:** Explain the likely user impact.
3. **Recommendation:** State the specific change.
4. **Reason:** Tie it to hierarchy, grouping, readability, accessibility, convention, or implementation.
5. **Tradeoff:** Mention when an alternative would be better.

Example style:

> The primary action competes with the filter chips because they share the same visual weight. Make the primary action the only filled button, reduce filters to secondary chips, and increase the spacing between the toolbar and content. This preserves scanability while keeping filters discoverable.

