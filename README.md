# Frontend Agent Skills

You know the look. The AI-generated landing page with the gradient blob hero, the perfectly symmetrical 3-column grid, the "Get Started" button that floats in space with no visual weight. It's technically correct and completely forgettable.

These skills exist because AI agents are fast but tasteless. They'll scaffold a full page in seconds and make every decision with the confidence of someone who has never used the thing they're building. The result is interfaces that feel like they were assembled from a template, because they were.

This is a collection of 9 agent skills that inject real design thinking into your AI workflow. They cover the stuff that separates "it works" from "it works and people actually want to use it": visual hierarchy that guides the eye, forms that don't make people want to close the tab, navigation that makes sense on the first try, copy that sounds like a human wrote it.

Each skill gives your agent structured decision-making for a specific design domain. Instead of generating generic best-practice soup, the agent gets opinionated guidance, anti-patterns to avoid, checklists to verify against, and decision prompts that force it to think about context before reaching for defaults.

## Install

```bash
npx skills@latest add hueyexe/frontend-agent-skills
```

## The Skills

### [accessibility-inclusive-design](./accessibility-inclusive-design)
Keyboard-friendly, screen-reader-aware, semantically structured interfaces. Not the "add alt text and call it done" version. Covers resilient layouts, inclusive defaults, readable content, and the kind of accessibility that works across devices and abilities without feeling like an afterthought.

### [design-systems-frontend-architecture](./design-systems-frontend-architecture)
Turns isolated screens into reusable systems. Design tokens, component contracts, responsive layouts, semantic markup, CSS strategy, documentation, and governance. For when you need the agent to think in systems instead of one-off pages.

### [forms-inputs-checkout](./forms-inputs-checkout)
Forms are where users go to suffer. This skill reduces that suffering. Validation, error states, field grouping, progressive disclosure, checkout flows, registration, payment, and onboarding. Covers the details that make people actually finish filling things out.

### [information-architecture-navigation](./information-architecture-navigation)
Navigation, labels, taxonomy, hierarchy, search, metadata, content grouping, and wayfinding. For products where users need to find, compare, and act on structured information without getting lost.

### [interaction-patterns-components](./interaction-patterns-components)
Pattern selection, component behavior, flow design, and state management for web, mobile, SaaS, dashboards, and design systems. Helps the agent pick the right pattern for the job instead of defaulting to a modal for everything.

### [ui-visual-composition](./ui-visual-composition)
Hierarchy, spacing, typography, color, depth, imagery, and visual states. The difference between a layout that looks "fine" and one that actually communicates. Covers the visual decisions that make interfaces clear and attractive without over-designing.

### [ux-research-discovery-testing](./ux-research-discovery-testing)
Lightweight research planning, discovery interviews, usability tests, synthesis, and evidence-backed recommendations. For when you want the agent to help you learn something about your users instead of just assuming.

### [ux-usability-foundations](./ux-usability-foundations)
The fundamentals: affordances, feedback, constraints, error prevention, recognition over recall, navigation clarity, and task flow. Covers the baseline usability that every interface needs before you start worrying about whether the border radius is 8px or 12px.

### [ux-writing-content-design](./ux-writing-content-design)
Microcopy, labels, CTAs, empty states, onboarding, errors, success messages, notifications, voice, and tone. Makes product interfaces clearer, more trustworthy, and easier to recover from. Because "Something went wrong" is not a helpful error message.

## What's in each skill

Every skill directory contains:

- **SKILL.md** - The main skill file with structured guidance, decision frameworks, and operational rules
- **references/anti-patterns.md** - Common mistakes and how to detect/fix them
- **references/checklists.md** - Verification checklists for quality gates
- **references/decision-prompts.md** - Context-gathering questions the agent should ask before making choices
- **references/principle-cards.md** - Core design principles converted into reusable agent behavior

## License

MIT
