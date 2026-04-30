# Decision Prompts

Use these prompts only when the missing information materially changes the recommendation. Do not ask users to approve routine best practices.

## How to use these prompts

- First recommend the most likely default.
- Ask one focused question when the user-specific answer changes the pattern, risk model, or implementation.
- Prefer a single decision prompt over a long questionnaire.
- When the user has already provided context, do not ask again.

### Decision: Primary task and screen type

When to ask:
- The screen could reasonably be an overview, focus page, creation workspace, dashboard, or step-by-step task flow.

Do not ask when:
- The user clearly names the screen purpose, such as “checkout form,” “admin table,” or “profile settings.”

Recommended default:
- Optimize for the most frequent user task and choose one dominant screen type.

Reason:
- Screens become confusing when they try to be overview, editor, dashboard, and settings page at once.

Question tool pattern:
```js
question({
  question: "What is the primary task users must complete on this screen?",
  recommended_default: "Optimize for the most frequent task and make secondary actions available but less prominent.",
  options: [
    "Find or browse items",
    "Compare and select items",
    "Create or edit something",
    "Monitor status or metrics",
    "Complete a step-by-step process",
    "Other / custom"
  ]
})
```

### Decision: Audience skill and task frequency

When to ask:
- The choice depends on guided wizard vs dense workspace, explicit labels vs expert shortcuts, or simplified vs configurable UI.

Do not ask when:
- The product context makes frequency obvious, such as a kiosk, public checkout, or internal expert tool.

Recommended default:
- Support mixed expertise with an obvious main path and optional accelerators.

Reason:
- Most real products need to welcome new users without slowing repeat users.

Question tool pattern:
```js
question({
  question: "How often will users perform this task, and how experienced are they?",
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

### Decision: Platform and interaction mode

When to ask:
- Touch, mobile, desktop density, keyboard workflow, responsive behavior, or small-screen constraints materially affect the pattern.

Do not ask when:
- The user already specified web/mobile/desktop/native or provided a screenshot with clear platform.

Recommended default:
- Use responsive, mobile-aware structure with progressive enhancement for larger screens.

Reason:
- Small screens force prioritization and help components scale.

Question tool pattern:
```js
question({
  question: "Where will users primarily use this interface?",
  recommended_default: "Design mobile-aware responsive behavior first, then enhance larger screens with denser layouts or shortcuts.",
  options: [
    "Mobile touch",
    "Desktop web",
    "Tablet",
    "Responsive across devices",
    "Keyboard-heavy desktop workflow",
    "Other / custom"
  ]
})
```

### Decision: Navigation model

When to ask:
- The product has multiple destinations, hierarchy, modules, workspaces, or process steps and the navigation model is not obvious.

Do not ask when:
- The task is a single component or simple screen with no navigation depth.

Recommended default:
- Use stable primary navigation for product areas and local signposts for current context.

Reason:
- Stable navigation lowers cognitive load and supports wayfinding.

Question tool pattern:
```js
question({
  question: "What navigation structure best matches the product?",
  recommended_default: "Use stable primary navigation plus local signposts; add breadcrumbs or progress only when hierarchy or steps require them.",
  options: [
    "Flat set of peer sections",
    "Hub-and-spoke from a central home",
    "Deep hierarchy",
    "Step-by-step process",
    "Multiple expert workspaces",
    "Other / custom"
  ]
})
```

### Decision: List, table, card, or grid

When to ask:
- The user wants to display repeated items but the item shape, comparison need, or selection behavior is unclear.

Do not ask when:
- The item type and task clearly imply a pattern, such as spreadsheet-like data or visual gallery.

Recommended default:
- Use list/table for comparison and card/grid for rich visual browsing.

Reason:
- Tables support attribute comparison; cards support self-contained browsing and responsive reuse.

Question tool pattern:
```js
question({
  question: "What do users most need to do with these items?",
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

### Decision: Data scale and loading

When to ask:
- Pagination, infinite scroll, virtualized table, filters, search, or loading behavior depends on item count or backend performance.

Do not ask when:
- The dataset is small or fixed.

Recommended default:
- Provide search/filter/sort for medium or large sets; use pagination for finite task-oriented sets and infinite loading for exploratory feeds.

Reason:
- Users need control and position recovery for large sets.

Question tool pattern:
```js
question({
  question: "Roughly how many items or rows can users encounter?",
  recommended_default: "For large sets, provide search/filter/sort and avoid endless scrolling unless the task is feed-like exploration.",
  options: [
    "Fewer than 50",
    "Hundreds",
    "Thousands or more",
    "Unbounded feed",
    "Unknown / design for growth",
    "Other / custom"
  ]
})
```

### Decision: Action risk and recovery

When to ask:
- The action might be destructive, costly, irreversible, privacy-sensitive, or system-propagating.

Do not ask when:
- The action is harmless and reversible.

Recommended default:
- Use undo for reversible actions; use confirmation or buffer steps only for high-risk actions.

Reason:
- Confirmations slow routine work and are often ignored; recovery is usually better for reversible mistakes.

Question tool pattern:
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

### Decision: Modal, drawer, page, or inline editing

When to ask:
- The interaction could be handled inline, in a side panel/drawer, in a modal, or on a separate page.

Do not ask when:
- The task is clearly tiny and bounded, or clearly deep and linkable.

Recommended default:
- Use inline or side-panel interactions for small context-preserving tasks; use pages for complex, shareable, long-lived work; use modals sparingly.

Reason:
- Modals interrupt focus and complicate accessibility; separate pages can break context but are better for deep work.

Question tool pattern:
```js
question({
  question: "Does this interaction need to be deep, shareable, or compared with the surrounding page?",
  recommended_default: "Use inline or side-panel UI for small context-preserving tasks; use a full page for deep or shareable work.",
  options: [
    "Small edit or quick action",
    "Needs comparison with surrounding content",
    "Needs a shareable/deep link",
    "Long-form or complex editing",
    "Must interrupt before continuing",
    "Other / custom"
  ]
})
```

### Decision: Form requirements and validation

When to ask:
- The agent cannot determine which fields are required, can be inferred, or have special validation/compliance requirements.

Do not ask when:
- The form is a simple known pattern and fields are provided.

Recommended default:
- Ask only for information needed now, infer safe values, and validate inline with field-specific messages.

Reason:
- Forms are user work; every field must earn its place.

Question tool pattern:
```js
question({
  question: "Which information is truly required to complete the immediate task?",
  recommended_default: "Ask only for information needed now; infer, prefill, or defer the rest when safe.",
  options: [
    "Only the minimum fields needed now",
    "Some optional profile/configuration fields",
    "Compliance requires all fields",
    "User must review imported/prefilled data",
    "Other / custom"
  ]
})
```

### Decision: Dashboard purpose

When to ask:
- The user asks for a dashboard but the decision, monitoring task, or target audience is unclear.

Do not ask when:
- The dashboard’s operational purpose and metrics are already specified.

Recommended default:
- Design for triage and action: overview status, priority exceptions, drilldown, and next steps.

Reason:
- Dashboards should help users decide what needs attention, not merely decorate numbers.

Question tool pattern:
```js
question({
  question: "What should users decide or do after looking at this dashboard?",
  recommended_default: "Prioritize metrics that trigger decisions, triage, or drilldown actions.",
  options: [
    "Monitor status or health",
    "Find exceptions/anomalies",
    "Compare performance",
    "Report high-level progress",
    "Manage operational work queue",
    "Other / custom"
  ]
})
```

### Decision: Notifications and nudges

When to ask:
- The interface may send notifications, reminders, alerts, badges, or off-screen status updates.

Do not ask when:
- The notification is purely current-screen feedback; use inline status instead.

Recommended default:
- Use the least interruptive channel that still lets the user act in time.

Reason:
- Notifications should protect user attention and remain useful.

Question tool pattern:
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

### Decision: Information density

When to ask:
- The agent must choose between spacious progressive disclosure and dense expert UI.

Do not ask when:
- The user's screenshot or product type makes density obvious.

Recommended default:
- Use moderate density with progressive disclosure.

Reason:
- It supports scanning while keeping advanced details available.

Question tool pattern:
```js
question({
  question: "How much information do users need visible at once?",
  recommended_default: "Use moderate density with progressive disclosure, unless expert comparison requires a dense workspace.",
  options: [
    "Minimal; one clear task",
    "Moderate; scan and act",
    "High; compare many attributes",
    "Expert dense workspace",
    "Other / custom"
  ]
})
```

### Decision: Design-system and frontend constraints

When to ask:
- The output needs implementation guidance and the component library, frontend stack, or design tokens may constrain the solution.

Do not ask when:
- The user asks for framework-agnostic UX advice only.

Recommended default:
- Reuse existing components and document variants/states; stay framework-agnostic if the stack is unknown.

Reason:
- Component reuse prevents inconsistency and UX debt.

Question tool pattern:
```js
question({
  question: "What frontend or design-system constraints should this fit?",
  recommended_default: "Reuse the existing component library and document any new variants, states, and accessibility behavior.",
  options: [
    "Existing design system / component library",
    "React or similar component implementation",
    "Native mobile components",
    "Prototype only",
    "Unknown / framework-agnostic guidance",
    "Other / custom"
  ]
})
```

### Decision: Persistence, memory, and re-entry

When to ask:
- The UI contains filters, drafts, progress, long flows, recent actions, or sensitive data.

Do not ask when:
- State is temporary and harmless, or security requirements are obvious.

Recommended default:
- Remember non-sensitive progress, filters, and recent context so users can resume.

Reason:
- Users pause, resume, and rely on stable state.

Question tool pattern:
```js
question({
  question: "Should the interface remember progress, filters, or recent actions across sessions?",
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
