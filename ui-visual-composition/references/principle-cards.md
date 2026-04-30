# Principle Cards for `ui-visual-composition`

These cards convert the uploaded source lessons into reusable agent behavior. Page references use the visible/book page numbers where available; PDF page counts may differ.

## Principle: Start with the feature, not the frame

Rule:
- Begin with the concrete user task, required content, and primary action before designing navigation, page chrome, decoration, or global layout.

Why it matters:
- Visual decisions about shells and containers are premature until the agent knows what the screen must help users accomplish.

Use when:
- Creating a new UI, redesigning a screen, or critiquing a vague “make this app look better” request.

Do not use when:
- The user is explicitly asking for global navigation, app shell architecture, or a design-system frame.

Default recommendation:
- Design one core feature/screen first and let the shell emerge from repeated feature needs.

Ask the user when:
- The core user task, audience, or success criterion is unknown.

Question prompt:
- `question({ question: "What is the primary task this screen must help users complete?", recommended_default: "Design around the most frequent or business-critical task first, because visual hierarchy and layout should follow the task.", options: ["Complete a transaction or submission", "Find or compare information", "Monitor status or data", "Configure settings", "Other / custom"] })`

Agent behavior:
- Identify required elements, rank them, and produce a low-fidelity structure before applying color, imagery, or polish.

## Principle: Familiarity beats novelty for common interactions

Rule:
- Use familiar patterns for common controls and flows unless novelty meaningfully improves comprehension, brand, or task performance.

Why it matters:
- Users should spend effort on their goal, not on learning a custom interface model.

Use when:
- Designing forms, nav, search, filters, tables, menus, cards, modals, controls, onboarding, or product conventions.

Do not use when:
- The product intentionally teaches a new paradigm and has time/space for onboarding, feedback, and migration.

Default recommendation:
- Use platform- and category-standard UI patterns, then differentiate through visual quality, content, and brand details.

Ask the user when:
- They request a novel interaction that conflicts with expected patterns.

Question prompt:
- `question({ question: "Should this interface prioritize convention or distinctive brand expression?", recommended_default: "Prioritize convention for core tasks, then add brand expression around the edges, because users complete tasks faster when common patterns behave predictably.", options: ["Convention-first", "Balanced", "Distinctive/experimental", "Other / custom"] })`

Agent behavior:
- Preserve conventional affordances and labels for core actions; move experimentation to low-risk surfaces such as illustrations, background treatments, or optional advanced views.

## Principle: Hierarchy first, decoration second

Rule:
- Rank content/actions and assign visual weight according to importance before adding color, illustrations, shadows, or effects.

Why it matters:
- A polished UI that does not show users where to start still fails.

Use when:
- Creating or critiquing any screen with multiple content blocks, actions, or states.

Do not use when:
- A screen is intentionally ambient or decorative and has no task priority, though accessibility and readability still apply.

Default recommendation:
- Make one primary action/content region visually dominant; secondary items should support without competing.

Ask the user when:
- Business priority and user priority conflict.

Question prompt:
- `question({ question: "Which outcome should the visual hierarchy optimize for first?", recommended_default: "Optimize for the user's primary task unless the business goal is explicitly different, because task clarity usually improves conversion and satisfaction.", options: ["User task completion", "Business conversion", "Learning/exploration", "Risk reduction/compliance", "Other / custom"] })`

Agent behavior:
- Provide a hierarchy map: primary, secondary, tertiary, ambient. Then translate it into type, spacing, contrast, action styles, and state emphasis.

## Principle: Group by meaning, not by available space

Rule:
- The distance, alignment, and containment between elements should match their conceptual relationships.

Why it matters:
- Users infer structure from spacing. Ambiguous spacing makes unrelated items look connected and related items look separate.

Use when:
- Designing cards, forms, toolbars, dashboards, lists, tables, nav, settings, or detail pages.

Do not use when:
- A deliberately chaotic editorial or campaign layout is the goal, and comprehension is still preserved.

Default recommendation:
- Use generous spacing between groups and tighter spacing within groups; use common regions or dividers only when spacing alone is insufficient.

Ask the user when:
- Density requirements are unclear or the product is for expert/high-frequency work.

Question prompt:
- `question({ question: "How dense should this interface be for its users?", recommended_default: "Comfortable density, because it improves comprehension for most users; reduce spacing only when expert users need more information visible at once.", options: ["Comfortable", "Balanced", "Dense/expert", "Presentation/marketing spacious", "Other / custom"] })`

Agent behavior:
- Diagnose spacing with relationship labels: item-to-label, field-to-field, group-to-group, section-to-section, page margins.

## Principle: Systems create polish

Rule:
- Use a constrained set of reusable values for type, spacing, color, radius, borders, and elevation.

Why it matters:
- Random values create subtle inconsistency that users perceive as unprofessional even if they cannot name it.

Use when:
- Producing design-system advice, code, Tailwind classes, CSS variables, component variants, or visual QA.

Do not use when:
- The artifact is an exploratory sketch intentionally meant to be disposable.

Default recommendation:
- Define tokens first enough to guide the screen: type scale, spacing scale, neutral scale, accent scale, semantic colors, radius, elevation.

Ask the user when:
- Existing design-system constraints may override defaults.

Question prompt:
- `question({ question: "Should I follow an existing design system or define a lightweight local system?", recommended_default: "Follow the existing design system when available; otherwise define a compact local token set so the UI remains consistent.", options: ["Use existing design system", "Create lightweight local tokens", "Match a provided screenshot/style", "Other / custom"] })`

Agent behavior:
- In code, express the system through tokens/classes and avoid one-off pixel/color values unless necessary.

## Principle: Typography is content architecture

Rule:
- Select and set type to make content readable, scannable, and appropriately voiced.

Why it matters:
- Text is the dominant material of most UIs. Poor type harms hierarchy, credibility, and task completion.

Use when:
- A UI contains labels, body text, tables, cards, forms, headings, metrics, captions, or dense information.

Do not use when:
- The screen is primarily image/video/canvas and text is minimal; still check labels and controls.

Default recommendation:
- Use a high-quality UI font, small type scale, readable line length, proportional line-height, restrained emphasis, and consistent hierarchy cues.

Ask the user when:
- Typeface choice is a brand decision or licensing/platform constraints are unknown.

Question prompt:
- `question({ question: "What typographic personality should the product communicate?", recommended_default: "Use a neutral, highly legible UI typeface unless the brand needs a stronger editorial or expressive voice.", options: ["Neutral/productive", "Friendly/rounded", "Editorial/premium", "Technical/precise", "Other / custom"] })`

Agent behavior:
- Include concrete type recommendations: roles, scale, line-height behavior, alignment, emphasis rules, and long-content handling.

## Principle: Color reinforces meaning; it should not carry meaning alone

Rule:
- Use color for hierarchy, brand, state, and attention, but pair it with non-color cues and sufficient contrast.

Why it matters:
- Color improves scanability and personality, but color perception varies and contrast failures exclude users.

Use when:
- Designing palettes, buttons, alerts, charts, status indicators, links, focus rings, badges, or dark mode.

Do not use when:
- A visual cue must be universally understood without supporting text or iconography.

Default recommendation:
- Build a neutral scale, one primary accent scale, semantic state colors, and focus treatment; validate contrast.

Ask the user when:
- Brand colors are fixed, contrast standard is strict, or semantic colors have domain meanings.

Question prompt:
- `question({ question: "Are there fixed brand or accessibility requirements for color?", recommended_default: "Use the provided brand color as an accent and tune accessible shades around it, because raw brand colors often need adaptation for UI states.", options: ["Fixed brand palette", "Flexible palette around a brand color", "No palette yet", "Strict accessibility/compliance requirements", "Other / custom"] })`

Agent behavior:
- Specify semantic color roles and fallback/non-color cues, not just attractive swatches.

## Principle: Depth should explain layers

Rule:
- Use shadows, highlights, overlap, and surface changes to clarify z-order, focus, and grouping.

Why it matters:
- Depth can focus attention and make layers understandable, but inconsistent shadows and gratuitous effects create noise.

Use when:
- Designing cards, modals, popovers, drawers, dropdowns, inputs, buttons, sticky bars, overlays, or layered hero sections.

Do not use when:
- A flat brand system deliberately avoids shadows and can still express hierarchy with surface and spacing.

Default recommendation:
- Use a small elevation scale with consistent light direction and reserved high elevation for blocking/foreground elements.

Ask the user when:
- Brand style is strongly flat, skeuomorphic, brutalist, or immersive.

Question prompt:
- `question({ question: "What depth style should this UI use?", recommended_default: "Subtle functional depth, because it clarifies layers without making the interface feel heavy.", options: ["Flat/minimal", "Subtle functional depth", "Soft/tactile", "Highly dimensional", "Other / custom"] })`

Agent behavior:
- Recommend elevation levels and when each applies; avoid one-off shadow tweaking.

## Principle: Aesthetic polish increases trust, but cannot replace clarity

Rule:
- Add polish after structure, hierarchy, and accessibility are working.

Why it matters:
- A pleasant interface can increase perceived ease and tolerance, but can also hide real usability defects.

Use when:
- Finalizing screens, improving generated UI, preparing a demo, or critiquing perceived quality.

Do not use when:
- The product’s core task flow, accessibility, or content hierarchy is unresolved.

Default recommendation:
- Polish with improved defaults, empty states, accent borders, subtle backgrounds, fewer borders, and tighter state details.

Ask the user when:
- The amount of expressiveness should match brand/campaign goals.

Question prompt:
- `question({ question: "How expressive should the finishing details be?", recommended_default: "Restrained polish, because it improves perceived quality without distracting from task completion.", options: ["Minimal/productive", "Restrained polished", "Bold/brand-forward", "Playful/campaign-like", "Other / custom"] })`

Agent behavior:
- Separate critical usability fixes from polish recommendations so the user can prioritize.

## Principle: Simplify, but do not hide irreducible complexity

Rule:
- Chunk content, reduce choices, and highlight recommendations, but keep necessary information available where users need it.

Why it matters:
- Users are overwhelmed by excess, yet harmed when complexity is hidden so aggressively that they cannot understand consequences or recover.

Use when:
- Designing onboarding, forms, settings, plan selection, filters, dashboards, checkout, or AI-generated outputs.

Do not use when:
- A professional/expert audience needs simultaneous comparison and high data visibility.

Default recommendation:
- Show the most relevant options first; progressively disclose advanced or rare options.

Ask the user when:
- Expert users may value density and control more than simplicity.

Question prompt:
- `question({ question: "Should this screen optimize for simplicity or expert control?", recommended_default: "Simplicity first with progressive disclosure, because it supports most users while preserving access to advanced options.", options: ["Simplicity first", "Balanced", "Expert control/dense", "Other / custom"] })`

Agent behavior:
- Explain what is hidden, what remains visible, and how users recover or access advanced detail.

## Principle: Accessibility is visual composition

Rule:
- Every visual recommendation must preserve perceivability, operability, simplicity, and forgiveness.

Why it matters:
- Visual design determines whether users can see, understand, reach, operate, and recover from the interface.

Use when:
- Any UI includes text, controls, states, motion, validation, media, keyboard navigation, or touch targets.

Do not use when:
- Never. Accessibility may be scoped, but not ignored.

Default recommendation:
- Default to inclusive contrast, redundant state cues, visible focus, comfortable targets, keyboard behavior, clear feedback, and error recovery.

Ask the user when:
- Compliance standard, audience needs, or risk level is unclear and material.

Question prompt:
- `question({ question: "What accessibility target should this UI meet?", recommended_default: "Use WCAG AA-equivalent production defaults unless the product requires stricter compliance, because it covers most mainstream digital interfaces.", options: ["WCAG AA-equivalent default", "Stricter/compliance-critical", "Internal prototype only", "Audience-specific needs", "Other / custom"] })`

Agent behavior:
- Include accessibility checks in the main design rationale, not as a separate afterthought.

## Principle: Design for real content and states

Rule:
- Design the non-happy paths and volatile content conditions as part of the visual system.

Why it matters:
- Static mockups often look good only because content is perfect. Real products contain empty states, errors, slow loading, long text, broken media, and unpredictable user content.

Use when:
- Creating production UI, component libraries, dashboards, forms, feeds, profiles, cards, ecommerce, or AI-generated content surfaces.

Do not use when:
- A disposable concept sketch is explicitly requested.

Default recommendation:
- Include empty, loading, error, long-content, missing-image, selected, focus, disabled, and success states.

Ask the user when:
- Content source, moderation, image volatility, or localization scope is unknown and impacts layout.

Question prompt:
- `question({ question: "Will this UI need to handle unpredictable user-generated or localized content?", recommended_default: "Assume yes for production interfaces, because long labels, missing images, and variable media can break otherwise polished layouts.", options: ["Yes, user-generated content", "Yes, localization/long text", "Mostly controlled content", "Static/demo only", "Other / custom"] })`

Agent behavior:
- Add resilience rules: truncation, wrapping, fallback media, aspect ratios, skeletons, inline errors, and state variants.
