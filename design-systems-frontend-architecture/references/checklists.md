# Checklists

Use these checklists before finalizing design-system, UI critique, frontend implementation, or documentation work.

## Discovery and context checklist

- The product or feature goal is stated or a recommended default is declared.
- The primary user task is clear.
- The target audience and likely expertise level are identified.
- The target platform/surface is known or assumed explicitly.
- Existing system status is known: none, emerging, mature, fragmented, or migrating.
- Existing constraints are captured: stack, CMS, framework, browser/device support, accessibility standard, brand guidelines, and release process.
- The scope is framed by components, states, templates, content types, and behaviors rather than page count.
- Known success criteria are listed: speed, consistency, accessibility, conversion, task completion, maintainability, or adoption.
- Unknowns that materially change the recommendation are asked with a recommended default.
- Routine best-practice questions are not asked.

## Interface inventory checklist

- Repeated UI is grouped by purpose, not only by visual similarity.
- Repeated style treatments are grouped as perceptual patterns: color, type, spacing, shape, motion, imagery, tone.
- Component candidates include anatomy, content model, actions, states, variants, and responsive behavior.
- Visual duplicates with different purposes are separated.
- Visually different elements with the same purpose are evaluated for consolidation.
- One-off exceptions are flagged for removal, promotion to a variant, or documentation as an experiment.
- Existing names are collected from design files, code, documentation, and team language.
- Naming conflicts or ambiguous terms are listed for glossary cleanup.
- High-frequency and high-risk patterns are prioritized first.

## Design and UX quality checklist

- The primary action is visually stronger than secondary and tertiary actions.
- Labels describe user outcomes, not internal system terms.
- Related elements are grouped and separated from unrelated elements.
- Hierarchy works without relying on color alone.
- Components communicate status, available actions, and consequences.
- Empty states explain what happened and what the user can do next.
- Loading states preserve layout stability where possible.
- Error states identify the problem, location, and recovery path.
- Validation is timed appropriately for the task and does not interrupt prematurely.
- Content has been tested with long labels, missing data, dense data, and realistic examples.
- The design does not solve a local issue by creating a global inconsistency.
- The design includes states for hover, focus, active, disabled, selected, loading, success, warning, and error where applicable.

## Component contract checklist

- Component name is based on purpose or role, not appearance.
- Purpose and user problem are stated.
- Use cases and non-use cases are documented.
- Anatomy identifies required and optional parts.
- Variants are justified by role, emphasis, behavior, or context.
- Props/API map to meaningful decisions rather than arbitrary styling escape hatches.
- Content guidance covers length, truncation, empty values, icons, imagery, and localization risk.
- Responsive behavior is specified at the component level.
- Accessibility behavior is specified: semantics, labels, keyboard, focus, ARIA if needed.
- The component has examples in isolation and inside at least one realistic composition.
- The component has test guidance for important states and variants.
- Ownership and contribution path are identified.

## Token checklist

- Token categories include color, typography, spacing, radius, border, elevation, motion, opacity, layer/z-index, size, and state where relevant.
- Primitive tokens are separated from semantic tokens.
- Semantic tokens are named by role and state, not raw appearance.
- Component tokens exist only when semantic tokens are insufficient for controlled local mapping.
- The token set avoids single-use tokens unless a one-off is explicitly documented as temporary.
- Dark mode, theming, brand variants, and platform variants are represented only if needed.
- Tokens include accessibility-sensitive states such as focus, disabled, error, warning, success, and selected.
- Token names are stable enough to survive value changes.
- Token documentation explains usage, not just values.
- Deprecated tokens have replacements and migration notes.

## Layout and responsive checklist

- Layout is based on content needs and container behavior, not fixed page screenshots.
- Components work at narrow widths, wide widths, high zoom, and large text.
- Breakpoints are introduced only where readability, hierarchy, navigation, or task completion breaks.
- Flexible layout primitives are used before fixed positioning or fixed dimensions.
- Wrapping, stacking, truncation, and overflow behavior are specified.
- Tables or data-dense views have horizontal overflow, column priority, or alternative layout guidance.
- Sticky/fixed elements do not obscure content or focus targets.
- The reading order remains logical when layout changes.
- Images and media have aspect-ratio and fallback behavior.
- Layout has been tested with realistic and edge-case content.

## Accessibility checklist

- Semantic HTML/native controls are used where available.
- Interactive elements have accessible names.
- Keyboard users can reach and operate every interactive control.
- Focus order matches the visual/logical task order.
- Focus indicators are visible and meet contrast expectations.
- Text and meaningful UI indicators meet contrast requirements.
- State is not communicated by color alone.
- Error messages are associated with fields and announced where appropriate.
- Dynamic content changes use live regions only when needed.
- Touch/click targets are large enough or have extended hit areas.
- Disabled states remain understandable and do not trap users.
- Custom controls preserve native semantics, keyboard behavior, and form behavior.
- Motion is brief, purposeful, and honors reduced-motion preferences.
- Text remains readable under zoom, text resizing, and localization.

## CSS and frontend implementation checklist

- Markup is semantic and avoids unnecessary wrapper elements.
- CSS selectors are low-specificity and component-scoped where appropriate.
- Styling does not depend on deep page-location selectors.
- Tokens are used for recurring values.
- There is a clear CSS layering or naming convention.
- `!important` is not used except in intentional, documented override layers.
- Layout uses modern CSS primitives when supported by constraints.
- JavaScript is used for behavior/state, not for simple presentational effects CSS can handle.
- Dependencies are justified by repeated value, not one isolated effect.
- Components include loading, error, empty, disabled, selected, and overflow states.
- Build workflow includes formatting/linting and relevant tests.
- Visual regression is recommended for high-value components or templates.
- Package/version/distribution strategy is documented when components are shared.

## Documentation checklist

- Documentation states the pattern’s purpose.
- Documentation includes “Use when” and “Do not use when.”
- Anatomy, variants, states, content rules, accessibility, responsive behavior, and implementation notes are included.
- Examples use realistic content.
- Anti-examples show common misuse when helpful.
- Related tokens and components are linked or named.
- Design and code names match or are mapped clearly.
- Ownership, contribution, review, and deprecation processes are stated.
- Documentation is close enough to code/design source-of-truth to avoid drift.
- The glossary captures ambiguous or high-frequency terms.

## Governance checklist

- There is an explicit owner or review group.
- New patterns require evidence: repeated need, user problem, accessibility requirement, or implementation simplification.
- Variants require purpose, not stylistic preference alone.
- Experiments have a graduation, revision, or removal path.
- Deprecations include replacement guidance.
- Contribution process is clear for designers, developers, and product partners.
- Adoption is measured or observable.
- System health is reviewed periodically for drift, duplication, accessibility, and documentation staleness.

## Critique final response checklist

- The critique starts with the highest-impact issues, not minor polish.
- Each issue includes why it matters and how to fix it.
- Recommendations distinguish user-facing impact from implementation/system impact.
- The response notes what is unknown and uses defaults where appropriate.
- Accessibility concerns are integrated, not isolated at the end.
- Suggested changes are concrete and testable.
- The response avoids unsupported claims and avoids inventing product context.

## Generation final response checklist

- The response includes the system layer being defined: tokens, primitives, components, templates, pages, or governance.
- Defaults are explicit and opinionated.
- Context-dependent decisions are asked only when necessary.
- The implementation guidance includes semantics, CSS/layout strategy, states, accessibility, and maintainability.
- Documentation and governance are included when the work affects a reusable system.
- Tradeoffs and override conditions are explained.
- The next action is clear.
