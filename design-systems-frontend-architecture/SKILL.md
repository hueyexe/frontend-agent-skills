---
name: design-systems-frontend-architecture
description: "Use when building reusable frontend systems, design tokens, component contracts, responsive layouts, CSS strategy, or design-system documentation and governance."
---

# Design Systems Frontend Architecture

## Purpose

Help an agent convert UI, UX, product, and brand decisions into a durable frontend system: reusable components, tokens, layout rules, state behavior, documentation, governance, and implementation guidance that can scale across screens, teams, devices, and time.

Optimize for actual product work. Do not merely describe design systems. Produce decisions, defaults, component contracts, implementation guidance, critiques, and next steps the user can act on.

## When to use this skill

Use this skill when the user asks for any of the following:

- Design-system strategy, component libraries, pattern libraries, style guides, design tokens, UI kits, component audits, interface inventories, or governance.
- UI critique, redesign, frontend implementation plans, component decomposition, responsive layout guidance, CSS architecture, or frontend maintainability.
- Turning mockups, screenshots, UX flows, or product requirements into scalable frontend components.
- Documentation for components, tokens, accessibility states, usage guidance, or design-to-code handoff.
- Resolving inconsistency across UI surfaces, duplicated patterns, ad hoc styling, or component drift.

## When not to use this skill

Do not use this skill as the primary lens when the task is mainly:

- Broad UX research planning, ethnography, discovery interviews, market research, or product strategy not yet connected to UI/system decisions.
- Visual art direction, illustration style, campaign creative, or brand identity creation unless the user is converting it into system rules.
- Pure backend architecture, API design, data modeling, or infrastructure.
- One-off static graphic design where reuse, accessibility, and frontend implementation do not matter.

## Core principles

1. **Design systems, not pages.** Scope effort by components, templates, content types, states, integrations, and behaviors rather than by page count.
2. **Think simultaneously in parts and wholes.** Evaluate tokens, atoms, components, sections, templates, and real pages together. Do not design a component without checking how it works in realistic compositions and content.
3. **Separate function from perception.** Treat functional patterns as behavioral/interface modules and perceptual patterns as the style, tone, motion, spacing, color, and type treatments that create product character.
4. **Start with purpose before abstraction.** A component exists to solve a user or product problem. Do not create abstractions from visual similarity alone.
5. **Use shared language as infrastructure.** Names, definitions, usage rules, and examples are part of the system, not decoration around it.
6. **Prefer reusable primitives, but preserve product distinctiveness.** Consistency should reduce user effort and team waste; it should not erase useful brand expression or signature moments.
7. **Make the system the source of truth.** Changes to shipped UI should update the component, token, or guideline where appropriate; avoid isolated hotfixes.
8. **Treat accessibility as a component contract.** Semantics, keyboard behavior, focus, contrast, hit areas, error handling, and reduced-motion behavior must be specified with the pattern.
9. **Choose frontend architecture early enough to prevent debt, but keep it adaptable.** Establish conventions before implementation spreads, then revise them intentionally as the product evolves.
10. **Document for use, not archival.** Documentation must answer when to use a pattern, when not to use it, how it behaves, how it is implemented, and who owns it.

## Default recommendations

Use these defaults unless the user provides context that clearly calls for a different choice.

### Product and scope defaults

- **Default scope:** define the smallest useful system slice: tokens + 3-5 core components + 1-2 representative templates + documentation. This avoids a bloated “big bang” system.
- **Default prioritization:** prioritize high-frequency, high-risk patterns first: buttons, links, forms, alerts, navigation, cards/lists, layout primitives, type scale, spacing, color semantics, loading/empty/error states.
- **Default migration:** improve incrementally. Prefer component-by-component replacement and deprecation over a full redesign unless the product is early-stage or a major platform migration is already happening.

### Design-system structure defaults

- **Default model:** use a layered system: foundations/tokens → primitives → components → compositions/templates → product examples/pages.
- **Default naming:** name patterns by purpose, not appearance. Prefer `Primary action`, `Course card`, `Filter panel`, `Inline validation`, or `Promotion banner` over `blue button`, `big box`, or `right rail thing`.
- **Default documentation:** every reusable pattern gets purpose, anatomy, variants, states, accessibility contract, content guidance, responsive behavior, implementation notes, examples, and anti-examples.
- **Default governance:** use light curation. Allow contribution, but require review for new tokens/components and require evidence before adding variants.

### Token defaults

- **Default token categories:** color, typography, spacing, radius, border, elevation/shadow, motion, opacity, z-index/layer, size, breakpoint/container, and semantic state tokens.
- **Default token shape:** separate primitive values from semantic tokens. Example: primitive `color.blue.600`; semantic `color.action.primary.bg`; component token `button.primary.bg` only when component-specific mapping is necessary.
- **Default naming:** use role and state rather than raw appearance. Prefer `text.muted`, `surface.raised`, `border.focus`, `status.error.fg` over `gray-500-for-labels`.
- **Default override rule:** do not introduce a new token for a single exception. First test whether an existing semantic token, component variant, or local product need already covers the case.

### Layout and responsive defaults

- **Default layout strategy:** design content-first, intrinsically responsive layouts using flexible containers, grid/flex primitives, fluid spacing, and container-aware rules. Avoid designing separate desktop/tablet/mobile screens as unrelated artifacts.
- **Default breakpoints:** use only enough breakpoints to protect readability, navigation, and task completion. Prefer component/container behavior over global viewport choreography.
- **Default density:** start with moderate density and generous scanability. Increase density only when expert workflows, data-heavy tasks, or screen real estate constraints justify it.
- **Default content testing:** test with real or realistic content, including long labels, missing images, empty data, error states, loading states, dense data, and translated strings when relevant.

### CSS and frontend defaults

- **Default markup:** semantic HTML first. Add ARIA only to fill semantic gaps, not to replace native semantics.
- **Default CSS:** component-scoped, low-specificity, token-driven CSS. Avoid styling through deep page location selectors.
- **Default methodology:** pick or adapt a clear naming and layering convention. BEM-like naming, utility layers, CSS modules, or framework-scoped styles can all work if the rules are explicit and consistent.
- **Default JS:** do not use JavaScript for effects CSS handles reliably. Use JS when behavior, state, data, or accessibility requires it.
- **Default custom controls:** start with native controls. If custom styling is needed, preserve native semantics, labels, keyboard behavior, focus visibility, and form behavior.
- **Default build/process:** automate linting, formatting, type checks where applicable, accessibility checks, visual regression for important components, and preview/documentation builds.

### Accessibility defaults

- **Default target:** meet WCAG 2.2 AA expectations unless the user has a stricter internal standard.
- **Default contrast:** text and meaningful UI indicators must meet contrast requirements; do not rely on color alone for state.
- **Default focus:** all interactive controls need visible focus and keyboard operation.
- **Default targets:** small controls need usable hit areas, especially for touch and motor accessibility.
- **Default motion:** motion should be purposeful, brief, interruptible when possible, and honor reduced-motion preferences.

## Required user questions

Ask only when the answer materially changes the system. Do not ask users to decide routine best practices.

Ask a focused question when any of these are unknown and relevant:

- The product goal, user task, or target audience is unclear.
- The user asks for a new system, but the brand/product personality or existing system maturity is unknown.
- The work must integrate with an existing frontend stack, CMS, component framework, or token format.
- The product has unusual accessibility, regulatory, performance, device, localization, or data-density constraints.
- The user wants a recommendation that depends on governance, team size, release process, or contribution model.
- The user asks to override a default that would affect accessibility, implementation cost, brand consistency, or maintainability.

When asking, include a recommended default and options. Use a `question` tool or equivalent pattern when available.

## Workflow: critique existing work

When reviewing an existing UI, design system, component library, or frontend implementation, inspect in this order:

1. **Task fit and product purpose** — What user goal is the UI solving? Are the main actions and outcomes clear?
2. **System coverage** — What tokens, components, templates, and states already exist? What is duplicated or missing?
3. **Information hierarchy** — Are primary, secondary, and tertiary elements distinguishable without decorative overuse?
4. **Functional patterns** — Are modules named, purposeful, reusable, and behaviorally clear?
5. **Perceptual patterns** — Are color, type, spacing, motion, imagery, and tone consistent with the intended personality?
6. **Layout and responsiveness** — Does the layout adapt from content and container needs rather than arbitrary breakpoints?
7. **Interaction clarity** — Are affordances, states, validation, loading, errors, empty states, and edge cases specified?
8. **Accessibility** — Check semantics, keyboard flow, focus, contrast, labels, target size, reading order, motion, and assistive text.
9. **Frontend feasibility** — Inspect markup complexity, CSS specificity, token mapping, dependencies, performance risk, and testability.
10. **Documentation and governance** — Is there a source of truth, ownership, contribution path, and deprecation process?

Output critiques as: highest-risk issue → why it matters → recommended fix → system implication → implementation note. Avoid long unordered lists of visual opinions.

## Workflow: create or improve a system

When creating a new recommendation, proceed in this order:

1. **Clarify the feature or user problem.** Identify the main task, audience, platform, existing constraints, and success criteria.
2. **Choose the smallest useful system slice.** Do not start with an exhaustive component catalog.
3. **Inventory existing patterns.** Look for repeated functions, repeated styles, duplicated code, inconsistent names, and recurring states.
4. **Define functional patterns.** Group UI by purpose and behavior, then name components by what they do.
5. **Define perceptual patterns.** Extract the product’s signature treatments: type, color, spacing, shape, motion, imagery, tone, and state expression.
6. **Establish tokens.** Convert recurring perceptual decisions into primitive, semantic, and component-level tokens where useful.
7. **Specify component contracts.** For each component, document anatomy, variants, states, content rules, accessibility behavior, responsive behavior, and implementation guidance.
8. **Compose templates with real content.** Validate components in actual flows and page-level compositions.
9. **Plan implementation architecture.** Choose semantic markup, CSS strategy, component boundaries, build/test pipeline, distribution, and migration path.
10. **Document and govern.** Define ownership, contribution, review, release, deprecation, and adoption workflow.
11. **Validate.** Run quality, accessibility, responsive, performance, and maintainability checks before finalizing.
12. **Explain decisions.** Tie recommendations to user goals, system consistency, accessibility, maintainability, and implementation cost.

## Decision framework

Use this sequence before recommending a pattern or architecture:

1. **Purpose:** What problem or user task does this solve?
2. **Reuse:** Will this recur across features, products, or states?
3. **Variation:** What variants are truly needed, and what variants are accidental one-offs?
4. **Content:** What content types, lengths, states, and localization cases must the pattern survive?
5. **Accessibility:** What semantics, focus behavior, keyboard interaction, labels, contrast, target size, and motion rules are required?
6. **Implementation:** Can it be implemented with semantic markup, low-specificity CSS, tokens, and minimal JS?
7. **System fit:** Does it align with existing tokens, components, names, and documentation?
8. **Governance:** Who owns it, how does it change, and how will users know which version to use?

Recommend the lowest-complexity solution that satisfies these constraints. Add complexity only when the product context justifies it.

## Practical rules

### Component rules

- A component must have a purpose, not just a visual shape.
- Do not create a component from a screenshot alone. First identify user task, content model, states, and responsive behavior.
- Prefer fewer components with well-defined variants over many near-duplicates.
- A variant must represent a meaningful difference in purpose, prominence, state, or context.
- Components should expose stable APIs or props that map to system decisions, not arbitrary styling escape hatches.
- Every component needs examples with realistic content and at least one edge case.

### Token rules

- Tokens should express decisions, not merely store values.
- Use semantic tokens for meaning and primitive tokens for palette/scale management.
- Do not let product teams consume raw primitives directly when a semantic decision is available.
- Do not solve one-off needs by expanding the token set before checking whether the need is recurring.
- Include state tokens for hover, active, focus, disabled, selected, success, warning, error, and loading where applicable.

### Documentation rules

- Document usage rules before implementation trivia.
- Include “Use when” and “Do not use when” for every major pattern.
- Include visual examples and anti-examples when they prevent misuse.
- Keep documentation close enough to code or design source-of-truth that it does not drift.
- Treat names and glossary entries as part of the product architecture.

### Governance rules

- Require a reason for new patterns: missing user need, repeated product need, accessibility requirement, or implementation simplification.
- Require review before new visual styles, component variants, or tokens are added.
- Allow experiments outside the core system, but define when an experiment graduates, changes, or dies.
- Track deprecated components and provide migration guidance.
- Measure system health by adoption, duplication reduction, accessibility quality, delivery speed, and user-facing consistency.

## Accessibility and inclusion requirements

For each component or UI recommendation, specify:

- Semantic element choice and accessible name.
- Keyboard interaction and tab order.
- Focus, hover, active, selected, disabled, invalid, loading, success, and error states.
- Contrast and non-color state indicators.
- Touch/motor target size and spacing between controls.
- Screen reader behavior, live regions, and error announcements where relevant.
- Reduced-motion alternative for decorative or transition-heavy behavior.
- Text resizing and zoom resilience.
- Localization and content expansion risk when relevant.
- Inclusive defaults for reading order, language clarity, and non-punitive error copy.

Never recommend custom controls unless you also specify how the native semantics and interactions are preserved.

## Frontend implementation guidance

### Semantic HTML

- Start from the native element that already carries the needed behavior: `button`, `a`, `input`, `select`, `textarea`, `details`, `dialog`, list elements, headings, landmarks, and table elements where appropriate.
- Use headings and landmarks to preserve meaningful page structure.
- Use ARIA only when native semantics are insufficient, and keep ARIA state synchronized with actual UI state.

### Component structure

- Keep component responsibilities small and explicit.
- Separate container/data orchestration from presentational primitives when it improves reuse and testing.
- Use composition for complex organisms and templates; avoid giant monolithic components.
- Define inputs/props in terms of role, state, and content, not raw CSS.
- Include empty, loading, error, success, disabled, selected, and overflow cases in the component contract.

### CSS and layout

- Use tokens for recurring values.
- Keep specificity low; avoid deeply nested selectors and page-location dependencies.
- Prefer layout primitives and component-contained responsive rules over scattered page-level overrides.
- Use modern layout tools such as flex and grid when supported by the project constraints.
- Use CSS for presentation, transitions, and state styling when CSS can handle the behavior accessibly and reliably.
- Avoid `!important` except for intentional utility layers or known override boundaries.

### Responsive behavior

- Define how content reflows, truncates, wraps, stacks, or collapses.
- Test components independently and inside representative templates.
- Avoid assuming fixed dimensions unless the content and platform truly enforce them.
- Treat narrow viewports, high zoom, and large text as first-class cases.

### Performance and maintainability

- Avoid shipping duplicate component implementations.
- Avoid large dependency additions for small presentational problems.
- Use build tools to automate repeatable tasks, but do not choose tools for novelty alone.
- Add visual regression tests to high-value components and templates where UI drift would be costly.
- Include migration notes when changing a component API, token name, or markup structure.

## Quality checklist

Before finalizing work, verify:

- The recommendation is scoped by components, states, and content, not only by pages.
- The primary user task and success criteria are clear.
- Functional and perceptual patterns are both addressed.
- Tokens distinguish primitive values from semantic decisions.
- Components have purpose, anatomy, variants, states, accessibility, responsive behavior, and implementation notes.
- Layout is resilient to content changes and viewport/container changes.
- Accessibility is treated as a requirement, not an afterthought.
- The CSS strategy avoids specificity escalation and one-off overrides.
- Documentation explains when and why to use patterns.
- Governance explains how the system evolves without becoming bloated or stale.
- Tradeoffs are explained in product, user, and implementation terms.

## Common mistakes to avoid

- Estimating or planning by page count instead of component/functionality complexity.
- Creating a “component library” that is only a gallery of screenshots or disconnected modules.
- Naming components by appearance rather than purpose.
- Creating tokens that merely mirror raw CSS values without semantic meaning.
- Treating color, type, motion, spacing, and tone as superficial decoration rather than perceptual patterns.
- Enforcing perfect consistency so strictly that product character and useful experimentation disappear.
- Allowing unlimited variants and one-off overrides until the system becomes incoherent.
- Building custom controls without preserving native behavior and accessibility.
- Solving layout with brittle fixed dimensions and breakpoint-specific hacks.
- Using JavaScript for styling effects CSS can solve more simply.
- Letting documentation drift away from code and design source files.
- Asking the user about routine best practices instead of applying strong defaults.

## How to explain recommendations to the user

Explain choices in this order:

1. **User impact:** how the recommendation improves task completion, clarity, accessibility, or confidence.
2. **System impact:** how it improves consistency, reuse, governance, or naming.
3. **Frontend impact:** how it reduces complexity, specificity, drift, regressions, or maintenance cost.
4. **Tradeoff:** what is lost or constrained, and when a different choice would be better.
5. **Next action:** what to implement, document, test, or ask next.

Use concrete language. Prefer “Use one `Inline validation` component with success, warning, and error variants” over “make validation consistent.”

