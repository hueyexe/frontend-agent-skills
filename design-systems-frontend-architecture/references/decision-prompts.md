# Decision Prompts

Use these prompts only when the answer changes the recommendation. Do not ask routine best-practice questions such as whether text should be readable, buttons should be accessible, or CSS should be maintainable. Apply those defaults automatically.

## Prompt format

Use a `question` tool or equivalent pattern:

```js
question({
  question: "Clear user-facing question",
  recommended_default: "Recommended default with reason",
  options: ["Option 1", "Option 2", "Option 3", "Other / custom"]
})
```

---

### Decision: Product goal and primary task

When to ask:
- The user asks for a UI, component, token system, critique, or redesign without stating what the product or feature is trying to help users accomplish.
- The recommendation could differ depending on conversion, productivity, learning, trust, safety, exploration, or content consumption goals.

Do not ask when:
- The user supplied a clear task, flow, product goal, or screenshot with enough context to infer the immediate purpose.

Recommended default:
- Optimize for clear task completion and comprehension, because most interfaces fail first at purpose and hierarchy before visual polish.

Reason:
- Source lessons emphasize purpose-directed systems and component scoping rather than isolated pages or decoration.

Question tool pattern:
```js
question({
  question: "What is the primary user task this UI or component must support?",
  recommended_default: "Optimize for clear task completion and comprehension unless this is explicitly a marketing/brand-expression surface.",
  options: [
    "Complete a task or workflow",
    "Compare or scan content",
    "Learn or consume information",
    "Convert/sign up/purchase",
    "Express brand or campaign identity",
    "Other / custom"
  ]
})
```

---

### Decision: Existing system vs new system

When to ask:
- The user asks for components, tokens, redesign, critique, or implementation guidance but does not say whether an existing design system must be followed.

Do not ask when:
- The user has clearly asked for a greenfield system, or has provided existing tokens/components/docs/screenshots to follow.

Recommended default:
- Assume there is at least some existing UI language and preserve it until evidence shows it should be replaced.

Reason:
- Design systems evolve gradually; unnecessary resets create inconsistency and relearning cost.

Question tool pattern:
```js
question({
  question: "Should this work extend an existing design system or define a new one?",
  recommended_default: "Extend the existing system first, because reuse and continuity usually reduce user confusion and implementation debt.",
  options: [
    "Extend an existing design system",
    "Create a new system from scratch",
    "Audit existing UI and decide what to keep",
    "Prototype outside the system first",
    "Other / custom"
  ]
})
```

---

### Decision: System maturity

When to ask:
- Governance, documentation, token strategy, or rollout recommendations depend on whether the system is new, emerging, mature, fragmented, or undergoing migration.

Do not ask when:
- The user only needs a small component-level recommendation that can use strong defaults.

Recommended default:
- Treat the system as emerging and recommend a small, high-value slice with light governance.

Reason:
- A manageable start prevents both under-systemization and big-bang design-system projects.

Question tool pattern:
```js
question({
  question: "How mature is the current design system?",
  recommended_default: "Assume it is emerging and start with a small, high-value slice unless you already have mature tokens, components, documentation, and contribution processes.",
  options: [
    "No shared system yet",
    "Emerging: some tokens/components, limited docs",
    "Mature: documented, implemented, governed",
    "Fragmented: multiple competing systems",
    "Migrating or redesigning",
    "Other / custom"
  ]
})
```

---

### Decision: Target platform and implementation surface

When to ask:
- Component structure, responsive behavior, tokens, and interaction guidance depend on platform or framework.

Do not ask when:
- The user clearly says web, React, native mobile, email, design-only, or another target.

Recommended default:
- Web-first responsive implementation using semantic HTML, CSS, and progressively enhanced JavaScript.

Reason:
- The source material is primarily web/frontend oriented, and semantic web defaults are the safest baseline for accessibility and maintainability.

Question tool pattern:
```js
question({
  question: "What platform or implementation surface should this system target?",
  recommended_default: "Responsive web with semantic HTML/CSS and progressive enhancement, because it gives the most accessible and reusable baseline for frontend systems.",
  options: [
    "Responsive web",
    "Web app component framework",
    "Native iOS/Android",
    "Cross-platform design tokens only",
    "Email or constrained HTML",
    "Other / custom"
  ]
})
```

---

### Decision: Frontend stack and constraints

When to ask:
- The user asks for implementation guidance and framework/tooling choices are not specified.
- The recommendation depends on React/Vue/Svelte, CSS Modules, utility CSS, Sass, design-token pipeline, CMS, build tooling, or package distribution.

Do not ask when:
- The user asks for conceptual critique or design guidance only.

Recommended default:
- Provide framework-agnostic guidance first; then map to the known stack if supplied.

Reason:
- Design-system architecture should define reusable contracts before locking into tool-specific syntax.

Question tool pattern:
```js
question({
  question: "What frontend stack or constraints should the implementation guidance fit?",
  recommended_default: "Start framework-agnostic and specify semantic markup, tokens, states, and CSS architecture before translating into a framework.",
  options: [
    "React / component library",
    "Vue / component library",
    "Svelte / component library",
    "Static HTML/CSS/JS",
    "CMS-rendered templates",
    "Design-only guidance for now",
    "Other / custom"
  ]
})
```

---

### Decision: CMS and markup control

When to ask:
- The user asks for frontend architecture, component implementation, or migration and content will be produced by a CMS, design tool, or server templates.

Do not ask when:
- The UI is fully controlled by the frontend app code or the user provides a fixed stack.

Recommended default:
- Use modular markup with controlled templates and automated content insertion.

Reason:
- Modular markup balances automation and frontend control, avoiding both CMS-generated div soup and manually maintained static pages.

Question tool pattern:
```js
question({
  question: "How much control will the frontend team have over the rendered markup?",
  recommended_default: "Aim for modular templates where content is automated but HTML structure/classes remain controlled by the frontend system.",
  options: [
    "Full control in frontend components",
    "Shared control with CMS/templates",
    "Limited control over CMS output",
    "Static pages maintained manually",
    "Unknown",
    "Other / custom"
  ]
})
```

---

### Decision: Brand personality / perceptual pattern direction

When to ask:
- The user asks for tokens, visual system, component styling, or redesign and brand personality is not obvious.
- Multiple valid perceptual directions would produce different type, color, spacing, motion, or imagery rules.

Do not ask when:
- The user supplies brand guidelines, existing UI samples, or asks specifically for neutral/productivity defaults.

Recommended default:
- Professional, clear, and warm with restrained distinctiveness.

Reason:
- This default works for many SaaS/productivity surfaces while leaving room for signature moments.

Question tool pattern:
```js
question({
  question: "What personality should the interface communicate?",
  recommended_default: "Professional, clear, and warm, because it supports trust and usability for most product interfaces unless the brand has a stronger established voice.",
  options: [
    "Professional and calm",
    "Warm and friendly",
    "Bold and expressive",
    "Playful and energetic",
    "Editorial/content-led",
    "Utility-first and neutral",
    "Other / custom"
  ]
})
```

---

### Decision: Information density

When to ask:
- Layout, typography, spacing, and component variants depend on whether the product is casual, expert, data-heavy, or high-frequency.

Do not ask when:
- The artifact is a simple marketing page, small form, or the user provided a screenshot with obvious density.

Recommended default:
- Moderate density with strong scanability.

Reason:
- It balances readability and efficiency for most product UI, and can be safely adjusted after content testing.

Question tool pattern:
```js
question({
  question: "How dense should the interface be for its users and tasks?",
  recommended_default: "Moderate density with clear grouping and scanability, because it works well until expert/data-heavy usage is confirmed.",
  options: [
    "Low density / spacious",
    "Moderate density / balanced",
    "High density / expert workflow",
    "Data-table or dashboard-heavy",
    "Unknown; recommend a default",
    "Other / custom"
  ]
})
```

---

### Decision: Component abstraction level

When to ask:
- The user asks to turn screens into components and it is unclear whether to define primitives, reusable components, templates, or page-level examples.

Do not ask when:
- The user requested a specific layer, such as tokens, button component, card system, or page template.

Recommended default:
- Define components at the smallest level that has a stable purpose and reusable behavior, then show them in one or two template/page contexts.

Reason:
- Atomic/layered thinking avoids both atom soup and monolithic page components.

Question tool pattern:
```js
question({
  question: "At what system layer should I focus the recommendation?",
  recommended_default: "Start with reusable components that have stable purpose and behavior, then validate them inside templates with realistic content.",
  options: [
    "Foundations/tokens",
    "Primitives/atoms",
    "Reusable components",
    "Compositions/templates",
    "Full page examples",
    "Audit and choose the right layer",
    "Other / custom"
  ]
})
```

---

### Decision: Strictness of system rules

When to ask:
- The recommendation concerns governance, component variants, token expansion, brand control, or contribution model.

Do not ask when:
- The user only needs a small component critique or implementation default.

Recommended default:
- Lightly strict: clear defaults, review for new patterns, but room for documented experiments.

Reason:
- It reduces fragmentation without freezing useful product learning.

Question tool pattern:
```js
question({
  question: "How strict should the design-system rules be?",
  recommended_default: "Lightly strict: use clear defaults and review new patterns, while allowing documented experiments outside the core system.",
  options: [
    "Strict: few variants, central approval",
    "Lightly strict: curated contribution",
    "Loose: teams can adapt patterns freely",
    "Experimental: prototype first, systemize later",
    "Other / custom"
  ]
})
```

---

### Decision: Contribution and ownership model

When to ask:
- The user asks how to maintain, govern, or roll out a system.

Do not ask when:
- The request is a one-off component recommendation with no governance implications.

Recommended default:
- Federated contribution with central curation.

Reason:
- It spreads knowledge while preventing uncontrolled drift.

Question tool pattern:
```js
question({
  question: "Who will own and contribute to the system?",
  recommended_default: "Federated contribution with central curation, because product teams should contribute but shared patterns need review and ownership.",
  options: [
    "Central design-system team owns it",
    "Product teams contribute with central review",
    "Fully distributed ownership",
    "Single small team maintains it",
    "Ownership unknown",
    "Other / custom"
  ]
})
```

---

### Decision: Token strategy scope

When to ask:
- The user asks for tokens, theming, multi-brand support, cross-platform support, or migration from hard-coded styles.

Do not ask when:
- The user only needs a quick UI critique or component description.

Recommended default:
- Use primitive + semantic tokens, with component tokens only where needed.

Reason:
- This preserves system meaning while avoiding token bloat.

Question tool pattern:
```js
question({
  question: "How broad should the token system be?",
  recommended_default: "Primitive + semantic tokens, adding component-specific tokens only when a component needs controlled local mappings.",
  options: [
    "Single-brand web tokens",
    "Multi-theme or dark mode tokens",
    "Multi-brand tokens",
    "Cross-platform web/native tokens",
    "Migration from hard-coded styles",
    "Other / custom"
  ]
})
```

---

### Decision: Responsive strategy

When to ask:
- The user asks for layout strategy and content, device, or container behavior is unclear.

Do not ask when:
- The user supplies concrete viewport targets, content constraints, or asks for a general best-practice default.

Recommended default:
- Content-first, intrinsically responsive components with minimal breakpoints.

Reason:
- This aligns with modular, multi-device design and reduces brittle breakpoint choreography.

Question tool pattern:
```js
question({
  question: "What responsive constraints matter most for this UI?",
  recommended_default: "Use content-first, intrinsically responsive components and add breakpoints only where readability or task completion breaks.",
  options: [
    "Mobile-first responsive web",
    "Desktop-first data-heavy app",
    "Container-based components embedded in many surfaces",
    "Known fixed device targets",
    "Unknown; recommend resilient defaults",
    "Other / custom"
  ]
})
```

---

### Decision: Accessibility or compliance level

When to ask:
- The product may be regulated, public-sector, enterprise, education, health, finance, or otherwise high-risk; or the user asks for compliance.

Do not ask when:
- Basic accessible defaults suffice and no special compliance standard is mentioned.

Recommended default:
- WCAG 2.2 AA-aligned component behavior.

Reason:
- It is a strong accessible baseline for most frontend systems.

Question tool pattern:
```js
question({
  question: "Does this product need to meet a specific accessibility or compliance standard?",
  recommended_default: "Use WCAG 2.2 AA-aligned behavior as the baseline, including semantics, keyboard support, focus, contrast, error handling, and reduced motion.",
  options: [
    "WCAG 2.2 AA baseline",
    "WCAG AAA or stricter internal standard",
    "Public-sector/legal compliance requirements",
    "Enterprise procurement accessibility requirements",
    "Not sure; use accessible defaults",
    "Other / custom"
  ]
})
```

---

### Decision: Motion and animation level

When to ask:
- The user asks for motion, interaction polish, transitions, or a brand personality that might use motion.

Do not ask when:
- The recommendation can simply specify reduced, purposeful motion.

Recommended default:
- Subtle, functional motion with reduced-motion support.

Reason:
- Motion can clarify state and create character, but it can distract or harm accessibility if overused.

Question tool pattern:
```js
question({
  question: "How expressive should motion be in this system?",
  recommended_default: "Subtle and functional, with reduced-motion alternatives, because motion should clarify state before it decorates the interface.",
  options: [
    "Minimal: only state clarity",
    "Subtle: polished but restrained",
    "Expressive: brand/signature moments",
    "Avoid motion where possible",
    "Other / custom"
  ]
})
```

---

### Decision: Testing and regression depth

When to ask:
- The user asks for implementation process, governance, release quality, or preventing UI drift.

Do not ask when:
- The deliverable is conceptual or low-risk.

Recommended default:
- Add automated checks for linting/accessibility plus visual regression for high-value components and templates.

Reason:
- Visual drift and state regressions are common design-system failure modes.

Question tool pattern:
```js
question({
  question: "How much automated testing should the design-system workflow include?",
  recommended_default: "Use linting/accessibility checks plus visual regression on high-value components and templates, because that catches drift without over-testing everything at first.",
  options: [
    "Basic linting and formatting only",
    "Add accessibility checks",
    "Add component/unit tests",
    "Add visual regression tests",
    "Full release pipeline with package/version governance",
    "Other / custom"
  ]
})
```

---

### Decision: Migration approach

When to ask:
- The user has an existing fragmented UI or legacy frontend and asks how to improve, redesign, or systemize it.

Do not ask when:
- The work is clearly greenfield.

Recommended default:
- Incremental migration by highest-value patterns, with deprecation guidance.

Reason:
- Full redesigns often disrupt users and create delivery risk; component migration compounds value over time.

Question tool pattern:
```js
question({
  question: "How should legacy UI be migrated into the system?",
  recommended_default: "Incrementally migrate the highest-value repeated patterns first, while documenting deprecations and replacement components.",
  options: [
    "Incremental component-by-component migration",
    "Route/template migration",
    "Full redesign/rebuild",
    "Wrapper/adaptor around legacy components",
    "Audit first, then choose",
    "Other / custom"
  ]
})
```
