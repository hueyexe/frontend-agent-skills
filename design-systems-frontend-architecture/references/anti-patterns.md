# Anti-patterns

Prioritize these because AI agents commonly produce them when generating UI, CSS, design-system guidance, or frontend architecture plans.

## Anti-pattern: Page-count scoping

What it looks like:
- Estimating or designing by “five pages,” “one homepage,” or “a dashboard screen” without identifying components, content types, states, data dependencies, and interactions.

Why it fails:
- Pages are not uniform units of effort. A single page can contain many complex patterns, while thousands of pages may share only a few content types and templates.

Better approach:
- Scope by reusable components, templates, content types, states, integrations, and behaviors.

Ask the user when:
- The product goal, content types, or key interactions are unknown and materially affect scope.

## Anti-pattern: Component spray

What it looks like:
- A library filled with disconnected modules, screenshots, or components without purpose, hierarchy, examples, or usage rules.

Why it fails:
- Teams cannot reliably compose coherent products from an unstructured pile of parts.

Better approach:
- Use a layered model: foundations/tokens, primitives, components, organisms/compositions, templates, and real examples. Document how parts compose into wholes.

Ask the user when:
- The right system layer is unclear.

## Anti-pattern: Pattern library equals design system

What it looks like:
- Treating a style guide, UI kit, or component gallery as the entire design system.

Why it fails:
- A design system also includes shared language, principles, contribution practices, governance, documentation, and maintenance.

Better approach:
- Define the artifact and the operating model: patterns + practices + ownership + documentation + review + evolution.

Ask the user when:
- The user asks for “a design system” but only describes a library or visual kit.

## Anti-pattern: Naming by appearance

What it looks like:
- Names like `blue button`, `big card`, `right rail`, `gray text`, or `fancy banner`.

Why it fails:
- Appearance changes; purpose should remain stable. Visual names encourage one-off variants and make design/code language brittle.

Better approach:
- Name by role, purpose, or behavior: `Primary action`, `Course card`, `Filter panel`, `Promotional banner`, `Muted text`.

Ask the user when:
- Existing terminology conflicts across design, code, and documentation.

## Anti-pattern: Visual similarity as the only abstraction rule

What it looks like:
- Combining two cards because they look similar, or separating two patterns because they look different, without considering purpose, content, and behavior.

Why it fails:
- Reuse based only on appearance creates components with confused responsibilities and awkward variants.

Better approach:
- Group components by purpose, content model, actions, and behavior. Use visual treatment as a secondary signal.

Ask the user when:
- The user provides screenshots without user goals or content model.

## Anti-pattern: Token bucket of raw values

What it looks like:
- A token file that only stores raw values such as `blue-1`, `gray-500`, `spacing-12`, with no semantic usage rules.

Why it fails:
- Teams still need to guess which value to use. Values can change, but meaning should remain stable.

Better approach:
- Use primitive tokens for scales and semantic tokens for roles/states, such as `color.action.primary.bg`, `text.muted`, `border.focus`, `status.error.fg`.

Ask the user when:
- The system must support multi-brand, theming, dark mode, or cross-platform delivery.

## Anti-pattern: One-off styling for business urgency

What it looks like:
- Adding a special banner, color, badge, or motion style for a short-term request without checking brand/system fit.

Why it fails:
- Small exceptions multiply and can weaken the product’s perceived personality.

Better approach:
- Use an existing semantic variant, create a temporary documented experiment, or graduate a recurring need into a system pattern.

Ask the user when:
- The business need is real but recurrence, duration, or brand risk is unclear.

## Anti-pattern: Consistency at the expense of product character

What it looks like:
- Flattening all patterns into neutral sameness, removing distinctive details, signature interactions, or expressive moments because they are not universal.

Why it fails:
- A system can become generic and rigid; perceptual patterns create product differentiation and emotional fit.

Better approach:
- Keep core functional patterns consistent while documenting controlled signature moments and brand-specific perceptual patterns.

Ask the user when:
- Brand personality or campaign/product context materially changes the visual system.

## Anti-pattern: Unlimited variants

What it looks like:
- Every screen or team gets its own button, card, modal, or color variant.

Why it fails:
- The system becomes hard to learn, hard to maintain, and inconsistent for users.

Better approach:
- Require a purpose for each variant: role, hierarchy, behavior, state, or context. Deprecate redundant variants.

Ask the user when:
- Governance strictness or contribution model is unknown.

## Anti-pattern: Over-strict governance

What it looks like:
- A central team blocks all change, requires heavy approval for minor usage, or prevents product teams from experimenting.

Why it fails:
- Adoption slows, teams route around the system, and useful product learning is lost.

Better approach:
- Use curated contribution with clear rules: allow experiments, review additions, and graduate recurring patterns intentionally.

Ask the user when:
- Team size, product risk, brand strictness, or ownership model is unknown.

## Anti-pattern: Div soup

What it looks like:
- Deeply nested non-semantic markup generated by CMS templates or layout wrappers, with weak class semantics and difficult CSS targeting.

Why it fails:
- It damages accessibility, increases CSS specificity, and makes components hard to reuse.

Better approach:
- Use semantic, modular markup with controlled templates/classes and automated content insertion.

Ask the user when:
- CMS or markup control is unknown.

## Anti-pattern: Specificity war

What it looks like:
- CSS relies on long descendant selectors, page classes, repeated overrides, or `!important` escalation.

Why it fails:
- Styles become location-dependent and hard to modify without regressions.

Better approach:
- Use low-specificity component classes, explicit CSS layers/naming conventions, tokenized values, and documented override boundaries.

Ask the user when:
- The implementation must fit a legacy codebase with unknown CSS conventions.

## Anti-pattern: Breakpoint choreography

What it looks like:
- Designing separate desktop/tablet/mobile layouts with many viewport-specific overrides and no component-level reflow rules.

Why it fails:
- It is brittle across real devices, zoom levels, containers, and content changes.

Better approach:
- Use content-first, intrinsically responsive layout with component/container behavior and minimal breakpoints.

Ask the user when:
- The UI has unusual device targets or data-density constraints.

## Anti-pattern: Custom controls without native behavior

What it looks like:
- Custom checkbox, slider, dropdown, toggle, or image comparison control that works visually but lacks keyboard access, labels, focus, or native form behavior.

Why it fails:
- It excludes keyboard, assistive technology, and motor-impaired users; it also increases implementation risk.

Better approach:
- Start with native controls. If custom UI is necessary, preserve semantics, labels, keyboard behavior, focus, and state synchronization.

Ask the user when:
- The user requests a custom control for brand or interaction reasons and accessibility requirements are not stated.

## Anti-pattern: Tiny visible controls with tiny hit areas

What it looks like:
- Icons, close buttons, checkboxes, handles, or small links with only the visible pixels clickable/tappable.

Why it fails:
- Small targets are harder to acquire, especially on touch devices or for users with motor impairments.

Better approach:
- Extend the hit area while preserving visual size and spacing. Ensure focus styles match the operable area where possible.

Ask the user when:
- Dense expert UI may require smaller visual controls.

## Anti-pattern: Motion as decoration only

What it looks like:
- Bouncy, blinking, parallax, or animated effects added without a state, feedback, or brand purpose.

Why it fails:
- Motion can distract, slow users, and create accessibility issues.

Better approach:
- Use motion to clarify state, hierarchy, continuity, or a documented signature moment. Provide reduced-motion alternatives.

Ask the user when:
- The desired personality or motion level is unclear.

## Anti-pattern: Documentation graveyard

What it looks like:
- A static PDF, wiki, or website that is not connected to code/design sources and stops matching production.

Why it fails:
- Teams lose trust and return to ad hoc decisions.

Better approach:
- Keep docs close to source-of-truth, include ownership, examples, usage rules, contribution process, and review cadence.

Ask the user when:
- The team’s tools, workflow, or ownership model is unknown.

## Anti-pattern: Missing real-content states

What it looks like:
- Components shown only with ideal sample text, no loading/empty/error states, no long content, no missing images, and no disabled/selected/focus states.

Why it fails:
- Components fail in production and require one-off fixes.

Better approach:
- Document and test realistic content, edge cases, and states in isolation and in templates/pages.

Ask the user when:
- Data shape, content limits, or localization needs are unknown and materially change the component.

## Anti-pattern: Tool-first architecture

What it looks like:
- Choosing a framework, library, task runner, or documentation tool before defining component contracts, system rules, or workflow needs.

Why it fails:
- The tool becomes the architecture, and the system may not fit the product or team.

Better approach:
- Define purpose, patterns, tokens, component contracts, workflow, and governance first; choose tools that support them.

Ask the user when:
- The user asks “what tool should we use?” without constraints or goals.

## Anti-pattern: Over-asking the user

What it looks like:
- Asking the user to decide best practices such as “should this be accessible?”, “should text be readable?”, or “should components be reusable?”

Why it fails:
- It slows the work and shifts expert responsibility to the user.

Better approach:
- Apply strong defaults and ask only when product context changes the recommendation.

Ask the user when:
- The unknown affects product goal, platform, brand personality, density, governance, stack, or compliance.
