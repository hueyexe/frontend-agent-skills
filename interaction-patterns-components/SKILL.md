---
name: interaction-patterns-components
description: "Use when choosing, critiquing, or designing UI interaction patterns and reusable components for web, mobile, SaaS, dashboards, or design systems."
---

# Interaction Patterns Components

## Purpose

Help an agent choose, critique, and design effective UI interaction patterns and reusable product components.

The skill covers navigation patterns, menus, cards, tables, dashboards, modals, flows, states, and component behavior. It treats visual polish only where it affects interaction clarity, hierarchy, accessibility, or component usability.

## When to use this skill

Use this skill when the user asks for any of the following:

- Critique, redesign, or UX review of an app screen, website, product flow, wireframe, component, or frontend implementation.
- Selection of UI patterns such as navigation, menus, breadcrumbs, dashboards, cards, tables, forms, modals, wizards, split panes, tabs, accordions, toolbars, hover tools, lists, grids, or feedback states.
- Design of reusable components or design-system behavior.
- Frontend guidance for interaction behavior, accessibility, responsive behavior, component APIs, or UI state handling.
- Creation of product UX recommendations where the best answer depends on tasks, user skill, device context, data complexity, or risk.

## When not to use this skill

Do not use this skill as the main framework when the user primarily needs:

- Brand identity, illustration, mood boards, or visual polish not tied to interaction clarity.
- Deep copywriting, messaging strategy, or content design beyond labels, help text, errors, and microcopy.
- Pure graphic design, logo design, or marketing creative.
- Native voice, AR/VR, spatial, or non-screen interaction design unless the task also includes screen-based controls or companion UI.
- Backend architecture, database design, or API design except where implementation constraints affect component behavior.

## Core principles

### 1. Start with people, goals, and context

Identify what the user is trying to accomplish before choosing a component. A form, menu, table, modal, or dashboard is only a means to a user goal. Ask “why” until the job, risk, and success criteria are clear enough to design the simplest useful interface.

Default: infer the user goal from the feature and proceed. Ask only when the missing context changes the pattern choice, such as expert vs novice users, mobile vs desktop, or high-risk vs low-risk actions.

### 2. Treat interaction as a conversation

Every UI should respond as if it is a considerate partner: it listens, acknowledges input, shows progress, prevents confusion, and makes the next step clear. Encode this into components through visible states, feedback, labels, focus behavior, and recovery paths.

Default: every interactive component must define at least default, hover/pressed where applicable, focus, loading, disabled, success, empty, and error states.

### 3. Choose the simplest pattern that preserves context

Prefer patterns that keep the user oriented and reduce unnecessary navigation. Keep tools close to the object they affect, but do not hide critical actions behind hover-only affordances or ambiguous icons.

Default: use in-place editing, contextual tools, inline validation, and same-page previews when they reduce context switching and remain discoverable.

### 4. Preserve wayfinding

Users need to know where they are, where they can go, what changed, and how to recover. Navigation is not just chrome; it includes signposts, hierarchy, breadcrumbs, progress indicators, deep links, escape hatches, and stable screen regions.

Default: provide a stable primary navigation model, a clear page title, visible current location, and a reversible route back to the previous or parent context.

### 5. Let information structure drive layout

Layout should reflect task structure, not decoration. Use grouping, proximity, alignment, visual hierarchy, progressive disclosure, and screen regions to show relationships and priorities.

Default: use a single clear primary action per task area; group related controls; make the most important content or object the center of attention.

### 6. Match the pattern to the data and task

A table, card grid, list, dashboard, feed, wizard, or detail page is correct only when it fits what users compare, scan, select, create, monitor, or edit.

Default: for structured, comparable, sortable data, use a table or dense list. For heterogeneous, visually recognizable items, use cards or thumbnails. For stepwise unfamiliar tasks, use a wizard. For expert repeated work, use a denser workspace with shortcuts and visible tools.

### 7. Make actions safe

Support safe exploration through preview, undo, cancel, clear labels, confirmation only for consequential actions, and strong recovery. Avoid blocking confirmations for routine reversible actions.

Default: prefer undo over confirmation when the action is reversible. Use a confirmation or buffer step only for destructive, costly, irreversible, privacy-sensitive, financial, or broadly propagating actions.

### 8. Design for interruption, re-entry, and repetition

Users change direction, pause, resume, repeat actions, and rely on memory. Keep state stable, avoid rearranging controls unexpectedly, remember safe progress, and bring forward recent/repeated actions when helpful.

Default: preserve unsaved work where possible, retain filters and scroll position after detail views, and do not move controls after users begin a task.

### 9. Make forms short, purposeful, and forgiving

Ask only for information needed now. Use labels, hints, appropriate input types, smart defaults, validation, examples, and error recovery. Do not rely on placeholder text as the only label or instruction.

Default: use visible labels, one-column flow for most forms, inline errors tied to fields, forgiving formats where possible, and smart prefills only when confidence is high and users can edit them.

### 10. Build patterns as reusable systems

Do not create one-off components unless the context demands it. Define component responsibilities, variants, states, accessibility behavior, responsive behavior, content rules, and escape hatches.

Default: start from the existing design system or common UI framework, then extend intentionally. Treat libraries as a floor, not a ceiling.

## Default recommendations

Use these defaults unless the user’s context justifies an override.

| Area | Default recommendation | Why it is usually best | Override when |
|---|---|---|---|
| Product goal | Optimize for the user’s task completion, not feature exposure. | Users use UI as a means to an end. | The screen is primarily exploratory, educational, or promotional. |
| Audience | Design for capable but busy users with mixed expertise. | Most products serve beginners and repeat users simultaneously. | The product is explicitly expert-only, kiosk-like, or one-time use. |
| Platform | Start responsive/mobile-aware, then enhance for larger screens. | Small screens force prioritization and reusable content units. | The tool is a dense desktop-only professional workspace. |
| Navigation | Use stable global navigation plus local signposts. | Predictability lowers cognitive load. | The product is a single-task flow or immersive canvas. |
| Information density | Use moderate density with progressive disclosure. | It supports scanning without overwhelming. | Expert workflows require dense data and keyboard efficiency. |
| Screen structure | Choose one dominant screen type: overview, focus, make, or do. | Clear organizing principles make screens learnable. | A dashboard/workbench genuinely requires multiple regions. |
| Lists | Use a list/table for comparison; cards for rich or visual items. | Pattern follows the user’s scanning task. | Items have unusual content or selection behavior. |
| Primary action | One visually dominant primary action per task region. | Prevents split attention and supports next-step clarity. | Multiple actions are truly equal and frequent. |
| Modals | Avoid modals for complex workflows; use them for focused, interruptive, bounded tasks. | Modals interrupt context and complicate navigation/focus. | A lightweight overlay preserves context better than page navigation. |
| Wizards | Use only for unfamiliar, ordered, multi-step tasks. | They reduce cognitive burden for sequential setup. | Expert users need nonlinear editing or comparison. |
| Dashboards | Show actionable monitoring, not decorative metrics. | Dashboards should support decisions and triage. | The dashboard is explicitly for ambient awareness. |
| Forms | Minimize fields, label everything, group sections, validate inline. | Reduces effort and prevents errors. | Legal, compliance, or operational requirements force extra fields. |
| Defaults | Prefill only when likely correct and easy to change. | Smart defaults reduce effort without removing control. | Incorrect defaults would be costly or misleading. |
| Error handling | Prevent errors first, then explain and recover. | Error recovery is part of the interaction. | Real-time prevention would interrupt expert flow. |
| Motion | Use transitions to preserve orientation, not to decorate. | Motion can show cause, continuity, and change. | User has reduced-motion preference or motion adds delay. |
| Accessibility | Treat keyboard, focus, labels, contrast, and screen-reader semantics as baseline. | Accessibility is interaction quality. | Never override; only adapt implementation. |
| Design system | Reuse existing components and document variants/states. | Reduces inconsistency and UX debt. | Existing components are inaccessible or do not fit the task. |

## Required user questions

Ask a focused question only when the answer changes the pattern choice or risk model. Do not ask routine best-practice questions.

Ask when any of these are unknown and materially relevant:

1. **Primary task and success outcome**: when multiple goals compete.
2. **Audience skill level and frequency**: when choosing between guided flow and expert workspace.
3. **Platform/device context**: when mobile, touch, desktop density, keyboard use, or responsive behavior matters.
4. **Data shape and scale**: when choosing list, table, card grid, dashboard, feed, filter, pagination, or visualization.
5. **Action risk/reversibility**: when choosing undo, confirmation, preview, or buffer step.
6. **Navigation depth and information architecture**: when choosing flat, hub-and-spoke, tree, pyramid, wizard, or workspace model.
7. **Design-system/frontend constraints**: when the user needs implementation-ready guidance.
8. **Accessibility or compliance constraints**: when domain-specific requirements may exceed baseline accessibility.

Use this pattern:

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

## Workflow

### A. Critiquing existing UI

Inspect in this order:

1. **User goal and task fit**  
   Identify what the screen is trying to help users accomplish. Flag controls, copy, or screens that serve the product before the user.

2. **Information architecture and screen type**  
   Determine whether the screen is an overview, focus, make, do, dashboard, flow, or workspace. Check whether the pattern matches the task.

3. **Wayfinding and navigation**  
   Check location cues, entry points, exit paths, breadcrumbs, progress indicators, deep links, and whether the user can recover from dead ends.

4. **Hierarchy, grouping, and layout**  
   Check whether the main object/action is obvious; related elements are grouped; visual weight matches priority; and progressive disclosure is used appropriately.

5. **Interaction clarity and component behavior**  
   Inspect affordances, labels, action placement, feedback, state changes, hover/touch behavior, keyboard behavior, loading, empty, and error states.

6. **Safety and recovery**  
   Check undo, cancel, preview, confirmation, error prevention, and resilience to interrupted workflows.

7. **Forms and input behavior**  
   Check labels, required/optional indicators, input types, hints, defaults, validation, and error wording.

8. **Data display and scanning**  
   Check whether tables, cards, dashboards, filters, sorting, datatips, and visualizations support comparison and decision-making.

9. **Accessibility and inclusion**  
   Check keyboard use, focus order, semantics, labels, contrast, reduced motion, target size, non-color cues, and screen-reader behavior.

10. **Frontend feasibility and design-system fit**  
   Check component reuse, responsive layout, tokenization, state complexity, performance, and maintainability.

Return critique in this format:

```markdown
## Overall diagnosis
[1-3 sentence summary]

## Highest-impact fixes
1. [Fix] — [why it matters] — [pattern/component recommendation]
2. ...

## Component-level notes
- [Component]: [issue] → [recommended behavior]

## Accessibility and implementation notes
- [Specific requirement or constraint]

## Tradeoffs
- [When another pattern might be better]
```

### B. Creating or improving a design

Proceed in this order:

1. Clarify the user problem and success outcome.
2. Identify audience skill, platform, data scale, and action risk only if needed.
3. Choose the screen type: overview, focus, make, do, dashboard, flow, or workspace.
4. Choose the navigation model and wayfinding cues.
5. Establish layout hierarchy and grouping.
6. Select components and define their responsibilities.
7. Define behavior: interactions, feedback, states, validation, transitions, keyboard/focus, and recovery.
8. Define responsive behavior and design-system variants.
9. Run the quality checklist.
10. Explain recommendations as user-task benefits, not as style preferences.

Return new recommendations in this format:

```markdown
## Recommended pattern
[Pattern and why it fits]

## Structure
[Regions, navigation, hierarchy]

## Component behavior
[States, actions, feedback, validation]

## Accessibility and frontend notes
[Semantics, keyboard, responsive, state management]

## Alternatives considered
[Why not the likely alternatives]
```

## Decision framework

Use these pattern choices as starting points:

### Screen and flow patterns

- **Overview screen**: Use for lists, grids, search results, feeds, dashboards, or collections where users choose what to inspect next.
- **Focus screen**: Use when one object, media item, record, canvas, or map is the center of attention.
- **Make workspace**: Use when users create or manipulate content; use toolbars, palettes, inspectors, and direct manipulation carefully.
- **Do screen**: Use for one bounded task such as payment, booking, import, export, setup, or confirmation.
- **Wizard**: Use for unfamiliar, ordered steps with dependencies. Avoid for expert repeated tasks.
- **Dashboard**: Use for monitoring, triage, and decision-making. Avoid as a decorative metric collage.
- **Modal/overlay**: Use for bounded tasks that must interrupt or preserve the underlying page context. Avoid for deep flows, large forms, or content users need to compare with the page behind it.
- **Many workspaces / split view**: Use for expert or high-context tasks that require comparing and editing multiple objects.
- **Settings editor**: Use for persistent preferences and configuration; group by mental model, not implementation model.

### Navigation patterns

- **Flat navigation**: Use for a small set of peer destinations.
- **Hub-and-spoke**: Use when users return to a central place between tasks.
- **Tree / multilevel**: Use for large hierarchical information spaces.
- **Pyramid**: Use when top-level exploration leads to more specific pages while retaining routes across branches.
- **Step-by-step**: Use for ordered flows.
- **Fat menu / menu page**: Use when users need overview and direct access to many destinations.
- **Breadcrumbs**: Use for deep hierarchy, not as the only primary navigation.
- **Progress indicator**: Use when users need orientation in a multistep process.
- **Escape hatch**: Always provide a safe exit from modal, wizard, or deep navigation contexts.

### List and content patterns

- **Table**: Use for structured data where users compare rows by attributes, sort, filter, scan exact values, or perform bulk actions.
- **Dense list**: Use for text-heavy items or inbox-like triage.
- **Cards**: Use for items with image/title/summary/actions where each item is a self-contained object.
- **Thumbnail grid**: Use for visually recognizable items where scanning by image matters.
- **Carousel**: Use sparingly for small, optional, visually rich sets; do not hide essential choices in a carousel.
- **Pagination**: Use when position, finite sets, SEO, or performance matter.
- **Infinite list**: Use for feeds/exploration where exact position is less important; preserve loading and return position.
- **Two-panel selector / split view**: Use when users browse a list and inspect details without losing list context.
- **List inlay**: Use to show detail without full navigation when detail is short and related.

### Actions and commands

- Put frequent actions close to the object they affect.
- Keep destructive and high-risk actions visually and spatially distinct from routine actions.
- Use button groups for small related action sets; avoid mixing unrelated priorities.
- Use smart menu labels that name the affected object or operation.
- Provide preview for changes with uncertain outcomes.
- Provide cancelability for long-running operations.
- Provide undo/history for reversible actions and exploration.
- Use macros or saved actions only for repeated expert tasks.

### Forms and controls

- Prefer the input method that matches the data: select/radio for finite choices, checkbox for multiple choices, slider for approximate ranges, stepper for small numeric increments, text field for open text, autocomplete for large known sets.
- Use forgiving formats for known structured strings when the system can parse them safely.
- Use structured formats when precision, error prevention, or compliance is more important than flexibility.
- Provide hints adjacent to the relevant field.
- Keep placeholders supplemental; visible labels must remain.
- Use dynamic validation without punishing users mid-typing.
- Use smart defaults and prefills when likely correct, visible, and editable.

### Feedback and microinteractions

- Show the result of direct manipulation immediately.
- Show progress for operations that take noticeable time.
- Use notifications only when they are timely, relevant, and actionable.
- Visualize quantitative status when it helps compare, predict, or act.
- Keep notification actions minimal and direct.
- Use transitions to show continuity, not to slow the task.
- Respect reduced-motion settings.

## Practical rules

1. Never recommend a component without stating what user task it serves.
2. Prefer removing a step over making the step prettier.
3. Do not hide the primary action in a menu, hover-only control, or ambiguous icon.
4. Do not use a modal when the user must compare, reference, or navigate behind it.
5. Do not use a wizard when users need nonlinear editing or expert speed.
6. Do not use cards for data that users need to sort, compare, or bulk-edit by multiple attributes.
7. Do not use a table for visually rich browsing when image recognition is the primary behavior.
8. Do not rely on color alone to communicate status or selection.
9. Do not rearrange controls after the user has learned their location unless the benefit is large and tested.
10. Do not use placeholder text as a substitute for labels.
11. Do not block reversible actions with confirmations; provide undo.
12. Do not auto-advance, auto-submit, or auto-delete without clear feedback and recovery.
13. Do not expose every possible action at once; reveal advanced actions where context makes them relevant.
14. Do not make keyboard shortcuts the only way to complete a task.
15. Do not treat a component library as a complete UX solution; define task-specific behavior and states.

## Accessibility and inclusion requirements

Baseline requirements for every recommendation:

- Use semantic HTML or platform-native semantics first.
- Provide visible labels for inputs and accessible names for controls.
- Ensure keyboard access to all interactive elements.
- Define logical focus order and visible focus states.
- Trap focus only inside true modals; restore focus to the trigger after closing.
- Use appropriate ARIA only when native semantics are insufficient.
- Make error messages programmatically associated with fields.
- Do not rely on hover-only interactions; provide click/tap/keyboard alternatives.
- Do not rely on color alone; pair color with text, icon, shape, or position.
- Respect reduced-motion preferences.
- Use target sizes appropriate for touch when designing mobile or touch interfaces.
- Ensure loading, empty, success, and error states are announced where necessary.
- Make disabled controls understandable; when possible, explain why an action is unavailable.
- Avoid interaction patterns that require advanced desktop conventions unless the target audience is known to use them.

## Frontend implementation guidance

When the output includes implementation guidance, specify:

### Component anatomy

Define subparts: root, label, trigger, content, item, action, helper text, error text, icon, badge, overlay, backdrop, footer, and any slots.

### States

For each component, define:

- Default
- Hover, pressed, selected, expanded, collapsed where applicable
- Focus-visible
- Disabled and read-only
- Loading and skeleton
- Empty
- Success
- Warning
- Error
- Offline or stale data, if relevant
- Reduced-motion alternative

### Semantic structure

Prefer native elements:

- `button` for actions, not clickable `div`.
- `a` for navigation.
- `label` associated with inputs.
- `table`, `thead`, `tbody`, `th`, `td` for true tabular data.
- `dialog` or accessible modal pattern for true modals.
- Lists (`ul`, `ol`) for list structures.
- Landmarks (`nav`, `main`, `aside`, `header`, `footer`) for page regions.

### Keyboard behavior

Specify keyboard behavior for menus, dialogs, tabs, accordions, tables, grids, autocompletes, and draggable interactions. Provide a non-drag fallback for drag-and-drop actions.

### Responsive behavior

Define how the component adapts:

- Stack or collapse secondary regions.
- Preserve primary task and action.
- Avoid hiding required navigation with no discoverable substitute.
- Keep touch targets large enough.
- Preserve state across viewport changes.

### Design-system integration

- Reuse existing tokens for spacing, color, typography, elevation, radius, and motion.
- Create variants only for meaningful behavioral or semantic differences.
- Avoid one-off styling overrides that change component meaning.
- Document content limits, truncation, wrapping, and long/empty values.
- Document when a component should not be used.

### Performance and maintainability

- Use virtualization only when needed and when accessibility/position recovery are handled.
- Avoid infinite loading without a way to recover position or reach footer content.
- Avoid excessive animations and layout shifts.
- Keep expensive data visualizations and dashboards progressively loaded.
- Make loading states useful: show stable regions first and prioritize readable content.

## Quality checklist

Before finalizing a recommendation, verify:

- The user task is explicit.
- The recommended pattern fits the task, data shape, user skill, platform, and risk.
- The primary action is clear and not competing with equal-weight actions.
- Navigation and escape routes are visible.
- State changes have immediate, understandable feedback.
- Empty, loading, error, success, and disabled states are defined.
- Destructive or costly actions have appropriate prevention or recovery.
- Forms minimize input, show labels, provide hints, validate helpfully, and recover gracefully.
- Components are keyboard accessible and screen-reader understandable.
- Responsive behavior preserves the primary task.
- The recommendation can be implemented with reusable components and tokens.
- Tradeoffs and alternatives are explained.

## Common mistakes to avoid

- Designing from component preference instead of user task.
- Treating the home page or dashboard as a catch-all.
- Overusing modals for complex tasks.
- Hiding important actions behind hover-only tools.
- Making every action visually primary.
- Choosing cards when users need comparison.
- Choosing tables when users need visual browsing.
- Using a wizard for expert workflows.
- Using confirmation dialogs for routine reversible actions.
- Using clever icons without labels for unfamiliar actions.
- Using skeletons/spinners without preserving layout or showing progress.
- Forgetting keyboard and focus behavior.
- Creating one-off components that bypass the design system.
- Optimizing for novelty at the expense of familiar interaction.

## How to explain recommendations to the user

Explain in terms of:

1. **User task**: “Users need to compare rows by status and date, so a table is stronger than cards.”
2. **Cognitive load**: “This keeps the next step visible and avoids making users remember what they selected.”
3. **Context preservation**: “A split view keeps the list visible while details change.”
4. **Safety**: “Undo is better than a confirmation here because the action is reversible and frequent.”
5. **Accessibility**: “The action must be reachable by keyboard and not depend on hover.”
6. **Implementation**: “This can reuse the existing table component with added empty/error/loading states.”

Avoid saying “it looks better” unless the visual change directly improves hierarchy, readability, affordance, or accessibility.

