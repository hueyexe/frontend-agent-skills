# Principle Cards

## Principle: Scope components, not pages

Rule:
- Scope UI and frontend work by reusable components, content types, templates, states, behaviors, and integrations rather than page count.

Why it matters:
- Page count hides complexity. A single page may contain many interactive systems; many pages may share one template.

Use when:
- Estimating, planning, critiquing, redesigning, or implementing product UI.

Do not use when:
- The user asks for a one-off static artifact with no intended reuse or implementation.

Default recommendation:
- Translate every “page/screen” request into components, states, content, and system layers.

Ask the user when:
- The product goal, main content types, or interaction complexity is unknown.

Question prompt:
- What is the primary user task and what reusable parts, states, or content types must this screen support? Recommended default: identify components and states first, because page count is not a reliable measure of effort.

Agent behavior:
- Before proposing visuals or implementation, list the likely components and states. Explain that this creates a more maintainable system.

## Principle: Work across system layers

Rule:
- Treat tokens, primitives, components, compositions, templates, and pages as connected layers.

Why it matters:
- Components designed in isolation can fail in real product contexts; pages designed without components become hard to maintain.

Use when:
- Decomposing UI, defining a component library, or reviewing a pattern library.

Do not use when:
- The task is purely about a single atomic style value and the user has no need for system context.

Default recommendation:
- Define the component layer and validate it with at least one realistic template/page example.

Ask the user when:
- It is unclear whether the user needs tokens, components, templates, or a full example.

Question prompt:
- Which layer should we focus on first: tokens, primitives, components, templates, or full page examples? Recommended default: start with reusable components and validate them in real compositions.

Agent behavior:
- Identify the layer being addressed and note adjacent layers that must also be updated.

## Principle: Separate functional and perceptual patterns

Rule:
- Distinguish what a component does from how the product feels.

Why it matters:
- Functional reuse and brand expression are different kinds of system decisions. Mixing them causes confused components and arbitrary styling.

Use when:
- Naming components, defining tokens, auditing UI, or creating documentation.

Do not use when:
- The user asks only for a narrow implementation fix and the functional/perceptual distinction would add unnecessary overhead.

Default recommendation:
- Name functional modules by purpose and express perceptual choices through tokens, style rules, motion, tone, and signature patterns.

Ask the user when:
- The desired product personality is unknown and styling direction will materially differ.

Question prompt:
- What personality should the interface communicate? Recommended default: professional, clear, and warm, because it supports most product interfaces unless the brand has a stronger established voice.

Agent behavior:
- In critiques, separate “this component has unclear behavior” from “this perceptual treatment weakens the brand.”

## Principle: Abstract by purpose before appearance

Rule:
- Create or merge components only after comparing purpose, content structure, actions, states, and behavior.

Why it matters:
- Visual similarity can be misleading. Two similar cards may need different components; two different-looking items may share one underlying pattern.

Use when:
- Extracting components from screenshots, audits, or legacy UI.

Do not use when:
- The user provides an already-defined component model and only asks for implementation details.

Default recommendation:
- Run a purpose-directed mini-inventory before componentizing.

Ask the user when:
- The user has not provided user goals or content models.

Question prompt:
- What job does this pattern perform for the user, and what content/actions does it always need? Recommended default: classify by purpose and structure before deciding whether visuals should vary.

Agent behavior:
- Produce a component candidate table with purpose, anatomy, variants, states, and source examples.

## Principle: Treat tokens as decisions

Rule:
- Tokens should encode reusable design decisions, not just raw CSS values.

Why it matters:
- Semantic tokens let teams change values without changing meaning and reduce guesswork in implementation.

Use when:
- Creating or critiquing color, typography, spacing, radius, border, elevation, motion, and state systems.

Do not use when:
- A value is genuinely local and temporary and does not deserve system status.

Default recommendation:
- Use primitive tokens for scales and semantic tokens for product meaning; add component tokens only when necessary.

Ask the user when:
- The system requires theming, dark mode, multi-brand, or cross-platform delivery.

Question prompt:
- Should tokens support a single brand, themes/dark mode, multiple brands, or cross-platform output? Recommended default: primitive + semantic tokens for a single responsive web system, adding more layers only when needed.

Agent behavior:
- Map raw values to semantic roles and flag one-off values for consolidation or removal.

## Principle: Shared language is system infrastructure

Rule:
- Maintain consistent names, definitions, and examples across design files, code, documentation, and team conversations.

Why it matters:
- Teams can use the same word while meaning different things. Shared language reduces coordination cost and design drift.

Use when:
- Documenting components, naming patterns, aligning design and code, or diagnosing inconsistency.

Do not use when:
- A one-off answer does not need persistent naming.

Default recommendation:
- Create or update a glossary for high-frequency components, tokens, states, and product terms.

Ask the user when:
- Existing naming conflicts are likely but not visible.

Question prompt:
- Are there existing names in design files or code that this recommendation must preserve? Recommended default: align naming across design, code, and documentation to avoid duplicate mental models.

Agent behavior:
- Suggest canonical names and aliases when needed, and call out ambiguous terms.

## Principle: Consistency needs controlled flexibility

Rule:
- Make repeated functional patterns consistent, but allow controlled experiments and signature moments for product/brand expression.

Why it matters:
- Too little consistency fragments UX; too much can erase product character and discourage useful exploration.

Use when:
- Defining governance, component variants, brand expression, or design-system contribution rules.

Do not use when:
- Strict compliance or safety-critical contexts require near-total standardization.

Default recommendation:
- Use light curation: shared defaults and review for new patterns, with documented experimental space.

Ask the user when:
- Team size, brand risk, or governance model is unknown.

Question prompt:
- How strict should system rules be? Recommended default: lightly strict, because it balances coherence with product learning.

Agent behavior:
- Identify which decisions belong in the core system and which can remain local experiments.

## Principle: Documentation must enable use

Rule:
- Document purpose, usage, variants, states, accessibility, responsive behavior, implementation, examples, and ownership.

Why it matters:
- A pattern library that does not answer “when and how do I use this?” becomes stale and ignored.

Use when:
- Creating design-system documentation, handoff, or implementation guidance.

Do not use when:
- The user asks for a quick exploratory sketch with no need for reuse.

Default recommendation:
- Use a living documentation format close to code/design source-of-truth.

Ask the user when:
- Tooling, workflow, or ownership constraints are unknown.

Question prompt:
- Where should this documentation live so designers and developers will actually maintain it? Recommended default: keep docs close to the component source and design source-of-truth.

Agent behavior:
- Always include documentation sections for reusable components and tokens.

## Principle: Accessibility is part of the component contract

Rule:
- Specify semantic markup, accessible names, keyboard behavior, focus, contrast, hit areas, motion, and state announcements with the component.

Why it matters:
- Visual solutions can work for mouse users but fail keyboard, assistive technology, touch, or motor-impaired users.

Use when:
- Designing or implementing any interactive component.

Do not use when:
- Never; accessibility requirements should not be optional. Only the depth of compliance detail varies.

Default recommendation:
- Meet WCAG 2.2 AA-aligned behavior and preserve native controls where possible.

Ask the user when:
- The product has stricter legal/compliance requirements or unusual user needs.

Question prompt:
- Does this product need a specific accessibility standard beyond WCAG 2.2 AA? Recommended default: use WCAG 2.2 AA-aligned behavior for semantics, keyboard, focus, contrast, and state communication.

Agent behavior:
- Reject or revise custom controls that lack native semantics and keyboard behavior.

## Principle: Use semantic, modular markup

Rule:
- Markup should express content structure and component boundaries while giving CSS and JS stable hooks.

Why it matters:
- Bad markup leads to accessibility gaps, CSS specificity escalation, and brittle reuse.

Use when:
- Creating implementation guidance or evaluating frontend architecture.

Do not use when:
- The work is design-only and implementation details are out of scope; still mention semantic implications where relevant.

Default recommendation:
- Use semantic HTML, controlled templates, and component classes; avoid deep nesting and location-dependent selectors.

Ask the user when:
- CMS/template control is unknown.

Question prompt:
- How much control will the frontend team have over rendered markup? Recommended default: modular templates where content is automated but structure and classes are controlled by the frontend system.

Agent behavior:
- Include markup guidance and warn against div soup or over-specific selectors.

## Principle: Prefer intrinsic responsive layout

Rule:
- Build layouts that respond to content and container constraints before adding viewport-specific overrides.

Why it matters:
- Multi-device environments and variable content make fixed layouts brittle.

Use when:
- Recommending layout, CSS, responsive behavior, or component design.

Do not use when:
- A constrained platform has fixed dimensions and no responsive behavior.

Default recommendation:
- Use flexible grid/flex/layout primitives, content limits, and minimal breakpoints.

Ask the user when:
- The interface is data-dense, embedded, or has unusual device targets.

Question prompt:
- What responsive constraints matter most: mobile-first, desktop data density, embedded containers, or fixed device targets? Recommended default: content-first components with minimal breakpoints.

Agent behavior:
- Specify wrapping, stacking, overflow, truncation, and content edge cases.

## Principle: CSS should reduce assets, duplication, and brittleness

Rule:
- Use standards-based CSS techniques when they improve maintainability, but avoid cleverness that obscures intent.

Why it matters:
- CSS can replace extra images, markup, or JavaScript, but overly clever CSS becomes a maintenance risk.

Use when:
- Advising on visual effects, layout, typography, motion, and interaction details.

Do not use when:
- Browser constraints, accessibility, or team maintainability make a simpler implementation better.

Default recommendation:
- Prefer readable, tokenized, low-specificity CSS with minimal dependencies.

Ask the user when:
- Browser/support constraints are unknown and the technique depends on newer CSS.

Question prompt:
- Are there browser or platform support constraints I should respect? Recommended default: use modern standards-based CSS with graceful fallback for non-critical enhancements.

Agent behavior:
- Provide CSS architecture guidance rather than isolated tricks unless the user asks for code.

## Principle: Testing protects system integrity

Rule:
- Add automated checks and visual regression where UI drift would be costly.

Why it matters:
- Component systems can regress through unrelated changes, stale docs, or local overrides.

Use when:
- Planning implementation, release, migration, or governance.

Do not use when:
- The task is purely conceptual and no implementation plan is requested.

Default recommendation:
- Start with linting, accessibility checks, and visual regression for high-value components/templates.

Ask the user when:
- The team’s release pipeline, risk tolerance, or testing maturity is unknown.

Question prompt:
- How much automated testing should the workflow include? Recommended default: linting/accessibility checks plus visual regression on high-value components and templates.

Agent behavior:
- Include a practical testing plan tied to component risk and adoption.

## Principle: Architecture is iterative, not finished

Rule:
- Treat the design system and frontend architecture as products that evolve with product needs.

Why it matters:
- Systems become obsolete when documentation, code, tokens, and product UI drift apart.

Use when:
- Planning maintenance, governance, migration, or rollout.

Do not use when:
- The user explicitly needs a temporary prototype and no system adoption.

Default recommendation:
- Include ownership, contribution, deprecation, and review cadence.

Ask the user when:
- Ownership or maintenance capacity is unknown.

Question prompt:
- Who will maintain this pattern or system after the initial work? Recommended default: assign ownership and a lightweight review process before adoption.

Agent behavior:
- Never present a reusable system as “done” without explaining maintenance.
