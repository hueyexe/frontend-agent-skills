# Principle Cards

These cards convert lessons into reusable agent behavior.

## Principle: Solve the user’s goal before selecting a pattern

Rule:
- Start with the user’s goal, task, context, and skill level. A component is valid only if it helps users complete the job with less effort, confusion, or risk.

Why it matters:
- Users do not want forms, menus, dashboards, or modals for their own sake. They want outcomes such as finding, learning, buying, monitoring, creating, conversing, or controlling.

Use when:
- Any screen, flow, critique, redesign, or component recommendation is requested.

Do not use when:
- The task is purely visual styling and the user explicitly says interaction behavior is out of scope. Even then, preserve usability constraints.

Default recommendation:
- Infer the most likely user goal from the feature and recommend the simplest useful pattern.

Ask the user when:
- Multiple goals compete or the missing goal changes the pattern choice.

Question prompt:
```js
question({
  question: "What is the primary outcome users need from this screen or component?",
  recommended_default: "Optimize for the most frequent task and keep secondary tasks available but visually subordinate.",
  options: [
    "Find or browse information",
    "Compare and select items",
    "Create or edit something",
    "Monitor status or metrics",
    "Complete a transaction or setup flow",
    "Other / custom"
  ]
})
```

Agent behavior:
- Name the inferred user goal at the start of any critique or recommendation.
- Reject unnecessary UI steps when the goal can be achieved without them.

## Principle: Match guidance to user skill and frequency

Rule:
- Choose guided, explicit, low-memory interactions for occasional or novice users; choose denser, shortcut-friendly, configurable workspaces for frequent expert users.

Why it matters:
- One-time users need learnability and clear prompts. Frequent users tolerate more complexity but become frustrated by repeated friction.

Use when:
- Selecting wizards, dashboards, tables, shortcuts, contextual tools, hover behavior, dense controls, or expert features.

Do not use when:
- The user has already specified a homogeneous audience and workflow.

Default recommendation:
- Design for mixed expertise: obvious basics, efficient repeat paths, and progressive disclosure for advanced features.

Ask the user when:
- The product is likely expert-only, kiosk-like, regulated, or rarely used.

Question prompt:
```js
question({
  question: "How often will the target users perform this task, and how experienced are they?",
  recommended_default: "Assume mixed expertise: make the main path obvious, then add shortcuts or advanced controls for repeat users.",
  options: [
    "Mostly first-time or occasional users",
    "Mixed new and repeat users",
    "Frequent operational users",
    "Expert power users",
    "Other / custom"
  ]
})
```

Agent behavior:
- For mixed audiences, avoid forcing every user through the same slow tutorial or wizard.
- Provide visible primary actions and optional accelerators.

## Principle: Preserve context whenever possible

Rule:
- Prefer patterns that let users act on content without losing orientation: inline editing, split views, overlays for bounded tasks, preserved scroll/filter state, and direct feedback.

Why it matters:
- Navigation away from a task forces users to rebuild mental context.

Use when:
- Designing editing, selection, filtering, checkout, setup, side panels, overlays, or detail views.

Do not use when:
- A separate page is needed for deep content, sharing, bookmarking, accessibility, browser history, or complex comparison.

Default recommendation:
- Use same-page interaction for small bounded actions; use full pages for complex, linkable, or long-lived states.

Ask the user when:
- It is unclear whether users need deep links, browser history, collaboration, or comparison with the previous page.

Question prompt:
```js
question({
  question: "Does this interaction need to be linkable, shareable, or revisited as its own page?",
  recommended_default: "Use same-page interaction for small bounded tasks; use a full page when the state must be linkable or deeply editable.",
  options: [
    "Same-page interaction is enough",
    "It needs a shareable/deep link",
    "Users need to compare it with surrounding content",
    "Users need a long-form editing page",
    "Other / custom"
  ]
})
```

Agent behavior:
- Recommend split views, inlays, drawers, or overlays only when they preserve more context than they remove.
- Always specify close, cancel, back, escape, and focus restoration behavior.

## Principle: Make wayfinding explicit

Rule:
- Users should always know where they are, what they can do next, how far they are in a flow, and how to leave or recover.

Why it matters:
- Poor wayfinding turns simple tasks into exploration and increases cognitive load.

Use when:
- Designing navigation, flows, modals, multistep processes, dashboards, information architecture, or deep content.

Do not use when:
- The interface is a single-screen tool with no depth; still provide state and exit clarity.

Default recommendation:
- Provide stable navigation, page title, current-location indication, and an escape path.

Ask the user when:
- The product’s information architecture, depth, or platform navigation conventions are unknown.

Question prompt:
```js
question({
  question: "How deep is the product’s navigation or content hierarchy?",
  recommended_default: "Use stable primary navigation and add breadcrumbs/progress only when depth or process steps require them.",
  options: [
    "One level / mostly flat",
    "Two to three levels",
    "Deep hierarchy",
    "Step-by-step process",
    "Multiple workspaces or modules",
    "Other / custom"
  ]
})
```

Agent behavior:
- Do not recommend breadcrumbs as a substitute for primary navigation.
- Include deep links and escape hatches for modal or nested contexts when appropriate.

## Principle: Use layout to communicate priority and relationship

Rule:
- Use size, position, grouping, alignment, contrast, labels, and progressive disclosure to make the task structure visible.

Why it matters:
- Users scan before reading. Layout silently tells them what matters, what belongs together, and what happens next.

Use when:
- Critiquing or designing any screen, especially dashboards, forms, settings, dense tools, and mobile pages.

Do not use when:
- The user explicitly asks only for backend or non-visual architecture.

Default recommendation:
- Establish one clear center of gravity, group related controls, and hide advanced or optional material behind understandable disclosure.

Ask the user when:
- Information density or expert workflow needs may justify a denser layout.

Question prompt:
```js
question({
  question: "How much information do users need to see at once to complete the task?",
  recommended_default: "Use moderate density with progressive disclosure, so the main path remains clear while details stay accessible.",
  options: [
    "Very little; focus on one task",
    "Moderate; scan and act",
    "High; compare many values",
    "Expert workspace; dense controls are expected",
    "Other / custom"
  ]
})
```

Agent behavior:
- In critique, identify mismatches between visual weight and task importance.
- In design, state the hierarchy from primary object to secondary actions.

## Principle: Choose the list pattern by comparison, recognition, and scale

Rule:
- Use the representation that best supports how users scan, compare, select, and act on items.

Why it matters:
- Cards, tables, feeds, grids, and carousels optimize for different tasks. Choosing the wrong one hides needed comparisons or overwhelms users.

Use when:
- Designing search results, product listings, inboxes, data tables, media galleries, resource libraries, dashboards, or item selection.

Do not use when:
- The screen does not contain repeated objects or selectable items.

Default recommendation:
- Use tables/lists for comparison and triage; cards/grids for rich visual browsing; split views for list-plus-detail work.

Ask the user when:
- Data scale, item attributes, selection behavior, or comparison requirements are unknown.

Question prompt:
```js
question({
  question: "What do users most need to do with the items?",
  recommended_default: "Use a list or table when comparison matters; use cards or thumbnails when visual recognition matters.",
  options: [
    "Compare attributes across items",
    "Browse visually rich items",
    "Select one item and inspect details",
    "Bulk select and act on many items",
    "Consume a continuous feed",
    "Other / custom"
  ]
})
```

Agent behavior:
- State why the chosen representation fits the item shape.
- Define selection, sorting, filtering, loading, empty, and bulk-action behavior.

## Principle: Keep actions close, clear, and safe

Rule:
- Put actions near the object they affect, make their result clear, and provide recovery for mistakes.

Why it matters:
- Users need to understand what will be affected before acting. Ambiguous action placement causes errors.

Use when:
- Designing toolbars, menus, bulk actions, hover tools, row actions, cards, destructive actions, and editing commands.

Do not use when:
- The action is global and intentionally affects the whole screen or workspace; then make the scope explicit.

Default recommendation:
- Use visible labeled buttons for primary and destructive actions; use contextual menus for secondary object-specific actions; provide undo for reversible actions.

Ask the user when:
- Action risk or reversibility is unclear.

Question prompt:
```js
question({
  question: "What happens if users trigger this action by mistake?",
  recommended_default: "Use undo for reversible actions and confirmation/buffer steps only for destructive or costly actions.",
  options: [
    "No serious consequence; reversible",
    "Reversible but disruptive",
    "Destructive or irreversible",
    "Financial/privacy/legal consequence",
    "Affects other users or systems",
    "Other / custom"
  ]
})
```

Agent behavior:
- For every consequential action, specify prevention, confirmation, undo, cancellation, or history.
- Avoid hiding critical actions behind hover-only UI.

## Principle: Use feedback to close the interaction loop

Rule:
- Every user input needs an appropriate response: acknowledgment, validation, progress, change, success, warning, or error.

Why it matters:
- Without feedback, users repeat actions, lose trust, or assume the product is broken.

Use when:
- Designing buttons, forms, uploads, saves, filters, search, drag-and-drop, asynchronous operations, or collaborative status.

Do not use when:
- Feedback would expose private or misleading information; still provide safe acknowledgment.

Default recommendation:
- Immediate local feedback first, then progressive status for longer operations.

Ask the user when:
- Backend latency, async job behavior, or system status is unknown.

Question prompt:
```js
question({
  question: "How long can this action take, and can it fail asynchronously?",
  recommended_default: "Show immediate local feedback, then progress or background status if the operation takes more than a moment.",
  options: [
    "Instant / local only",
    "A few seconds",
    "Long-running background job",
    "Can fail after submission",
    "Depends on network or external system",
    "Other / custom"
  ]
})
```

Agent behavior:
- Define loading, optimistic, success, error, retry, and cancellation behavior where relevant.
- Use motion only to clarify change, continuity, or attention.

## Principle: Design forms as error-prevention systems

Rule:
- A form should communicate purpose, ask for the least information, use the right input method, prevent avoidable errors, and make recovery easy.

Why it matters:
- Forms impose work on users. Every unnecessary field or unclear rule increases abandonment and error.

Use when:
- Designing registration, checkout, settings, search filters, creation flows, imports, onboarding, or data entry.

Do not use when:
- The system can infer, import, or delay asking for information without harming the user outcome.

Default recommendation:
- Use visible labels, adjacent hints, suitable input types, smart defaults, inline validation, and field-specific errors.

Ask the user when:
- Required fields, compliance needs, privacy concerns, or data validation rules are unknown.

Question prompt:
```js
question({
  question: "Which fields are truly required now, and which can be inferred or asked later?",
  recommended_default: "Ask only for information needed to complete the immediate task; infer or defer the rest.",
  options: [
    "Only the minimum fields needed now",
    "Some optional profile/configuration fields",
    "Compliance requires all fields",
    "User must review imported/prefilled data",
    "Other / custom"
  ]
})
```

Agent behavior:
- Remove or defer fields where possible.
- Do not recommend placeholder-only labels.
- Associate errors with specific fields and provide correction guidance.

## Principle: Make data displays explorable without losing exactness

Rule:
- Data UI should support overview, filtering, comparison, exploration, and exact values when users need them.

Why it matters:
- Attractive charts fail if users cannot answer the operational question or inspect the underlying values.

Use when:
- Designing dashboards, analytics, charts, maps, tables, filters, monitoring tools, or status visualizations.

Do not use when:
- The screen only needs a single known value or status; avoid chart decoration.

Default recommendation:
- Pair summary visualization with filters and exact values. Use small multiples instead of overloaded multi-axis charts when comparing related series.

Ask the user when:
- The user’s decision, metric definitions, granularity, or data volume is unclear.

Question prompt:
```js
question({
  question: "What decision should the data display help users make?",
  recommended_default: "Show an overview first, then let users filter, sort, and inspect exact values.",
  options: [
    "Monitor status or thresholds",
    "Compare categories or items",
    "Find trends over time",
    "Diagnose outliers or anomalies",
    "Report exact values",
    "Other / custom"
  ]
})
```

Agent behavior:
- Define sorting, filtering, tooltip/datatip, drilldown, empty-data, stale-data, and loading behavior.
- Avoid decorative dashboards with no action path.

## Principle: Use notifications and nudges sparingly and functionally

Rule:
- Notifications should be timely, relevant, understandable, and actionable. They should reduce user effort, not merely seek attention.

Why it matters:
- Poor notifications interrupt users and train them to ignore the product.

Use when:
- Events happen outside the current screen, a user needs timely status, or a reminder genuinely helps complete a user-valued task.

Do not use when:
- The product only wants engagement, the information is not time-sensitive, or the user cannot act.

Default recommendation:
- Use in-product feedback for current-screen events; use notifications for off-screen, time-sensitive, or user-requested updates.

Ask the user when:
- Notification urgency, frequency, channel, or user control is unclear.

Question prompt:
```js
question({
  question: "How urgent and actionable is this notification?",
  recommended_default: "Use the least interruptive channel that still lets the user act in time.",
  options: [
    "Low urgency; in-app status is enough",
    "Medium urgency; notification center or badge",
    "High urgency; push/email/alert",
    "User-configurable reminder",
    "Compliance or safety alert",
    "Other / custom"
  ]
})
```

Agent behavior:
- Specify notification trigger, frequency cap, action, dismissal, settings, and fallback.
- Do not recommend engagement nudges without user benefit.

## Principle: Build components as reusable, accessible systems

Rule:
- Design components with responsibilities, variants, states, semantics, keyboard behavior, responsive behavior, and design-system integration.

Why it matters:
- Reusable components prevent inconsistency, reduce UX debt, and improve implementation speed only when their behavior is well specified.

Use when:
- Creating design-system components, frontend implementation guidance, reusable UI patterns, or component critiques.

Do not use when:
- A one-off experiment is intentionally disposable; still preserve accessibility basics.

Default recommendation:
- Start from the existing design system or a mature framework, then adapt intentionally for the user task.

Ask the user when:
- The frontend stack, component library, design tokens, or accessibility standard affects the recommendation.

Question prompt:
```js
question({
  question: "What frontend or design-system constraints should this fit?",
  recommended_default: "Reuse the existing component library and document any new variants, states, and accessibility behavior.",
  options: [
    "Existing design system / component library",
    "Common framework components",
    "Custom implementation",
    "Prototype only",
    "Unknown / recommend framework-agnostic guidance",
    "Other / custom"
  ]
})
```

Agent behavior:
- Provide component anatomy and states.
- Avoid one-off styling that changes meaning or bypasses accessibility.

## Principle: Respect interruption, re-entry, and memory

Rule:
- Preserve work, position, filters, and learned control locations. Reduce what users must remember.

Why it matters:
- Real users pause, resume, change direction, and rely on spatial and prospective memory.

Use when:
- Designing long flows, filters, dashboards, lists, workspaces, forms, and mobile sessions.

Do not use when:
- Security or privacy requires clearing state; then explain and provide safe recovery.

Default recommendation:
- Preserve safe state and restore users where they left off.

Ask the user when:
- Persistence has privacy, security, or collaboration implications.

Question prompt:
```js
question({
  question: "Should the interface remember user progress, filters, or recent actions across sessions?",
  recommended_default: "Remember non-sensitive progress and recent context so users can resume without rebuilding their state.",
  options: [
    "Remember within the current session only",
    "Remember across sessions",
    "Remember recent actions/preferences",
    "Do not remember for privacy/security",
    "Other / custom"
  ]
})
```

Agent behavior:
- Specify state persistence and reset behavior.
- Avoid rearranging controls dynamically unless the benefit clearly outweighs memory disruption.
