# Anti-patterns

Prioritize these because AI agents commonly produce them when designing UI quickly.

## Anti-pattern: Component-first design

What it looks like:
- Recommending a modal, card, table, carousel, or dashboard before identifying the user task.

Why it fails:
- Components are means to goals. A visually plausible component can still force unnecessary work or hide needed information.

Better approach:
- Start by naming the user goal, data shape, action risk, and platform. Then choose the simplest pattern that serves the task.

Ask the user when:
- Multiple user goals compete or the task is unclear.

## Anti-pattern: Dashboard as metric collage

What it looks like:
- A dashboard full of charts, cards, and KPIs with no prioritization, thresholds, drilldown, or action path.

Why it fails:
- It decorates data instead of helping users monitor, triage, or decide.

Better approach:
- Identify the decisions the dashboard supports. Show status, exceptions, trends, exact values, and next actions.

Ask the user when:
- The dashboard purpose or target user is unclear.

## Anti-pattern: Modal maze

What it looks like:
- Multi-step editing, settings, comparison, or forms trapped inside stacked modals.

Why it fails:
- Modals interrupt context, complicate focus management, and make deep work hard to share, resume, or navigate.

Better approach:
- Use inline editing, a side panel, split view, or full page depending on task depth and linkability. Reserve modals for bounded interruptions.

Ask the user when:
- It is unclear whether the task needs a shareable page, comparison, or a small context-preserving overlay.

## Anti-pattern: Hover-only critical actions

What it looks like:
- Edit, delete, save, or primary row actions appear only on hover.

Why it fails:
- Hover is undiscoverable, unavailable on touch, and inaccessible for many keyboard and assistive technology users.

Better approach:
- Keep critical actions visible or provide a visible menu/trigger with keyboard and touch support. Use hover reveal only for secondary conveniences.

Ask the user when:
- Screen density is extremely constrained and action priority is unclear.

## Anti-pattern: Every button is primary

What it looks like:
- Multiple same-weight buttons compete in a card, form, hero, toolbar, or dashboard.

Why it fails:
- Users cannot infer the next step and may choose the wrong action.

Better approach:
- Pick one primary action per task region. Make secondary actions visible but visually quieter.

Ask the user when:
- The business wants multiple competing calls to action and priority is unresolved.

## Anti-pattern: Cards for comparison-heavy data

What it looks like:
- Enterprise records, prices, statuses, dates, owners, and numeric attributes shown as large cards.

Why it fails:
- Cards obscure row-by-row comparison, sorting, scanning, and bulk action.

Better approach:
- Use a table or dense list for comparable structured data. Use cards only when the object benefits from rich content or imagery.

Ask the user when:
- The item attributes and comparison needs are unknown.

## Anti-pattern: Table for visual browsing

What it looks like:
- Media, homes, products, articles, or images forced into a dense table when users recognize them visually.

Why it fails:
- The representation hides the cues users use to choose.

Better approach:
- Use cards or thumbnail grids when imagery and self-contained summaries support scanning.

Ask the user when:
- The content type has both strong attributes and strong visual cues.

## Anti-pattern: Essential carousel

What it looks like:
- Critical choices, onboarding content, pricing plans, or navigation hidden in a carousel.

Why it fails:
- Users may never see off-screen items; comparison is difficult.

Better approach:
- Show essential options as visible cards, tabs, sections, or a list. Use carousels only for optional browsing.

Ask the user when:
- Space constraints or content priority are unclear.

## Anti-pattern: Wizard for expert repeat work

What it looks like:
- A linear step-by-step flow for users who frequently edit, compare, or change earlier inputs.

Why it fails:
- It slows repeat users and blocks nonlinear work.

Better approach:
- Use a single-page form, settings editor, split view, or workspace with visible sections. Use a wizard for unfamiliar ordered setup only.

Ask the user when:
- User frequency and skill level are unknown.

## Anti-pattern: Confirmation spam

What it looks like:
- Asking “Are you sure?” for routine, reversible actions.

Why it fails:
- Users habituate to confirmations and click through them, so they add friction without safety.

Better approach:
- Use undo for reversible actions. Use confirmation or buffer steps for destructive, costly, irreversible, or propagating actions.

Ask the user when:
- Reversibility or consequence is unclear.

## Anti-pattern: No escape hatch

What it looks like:
- Users enter a modal, wizard, deep page, filter state, or empty result with no clear way out.

Why it fails:
- Users lose confidence and cannot recover from exploration.

Better approach:
- Provide cancel, close, back, reset filters, clear selection, undo, or return-to-parent behavior.

Ask the user when:
- The flow’s safe exit behavior may affect data loss.

## Anti-pattern: Placeholder-only form labels

What it looks like:
- Text fields show placeholder instructions, but labels disappear once users type.

Why it fails:
- Users lose context, screen readers may not receive proper labels, and placeholders can look like completed input.

Better approach:
- Use persistent visible labels, adjacent hints, and examples. Keep placeholders supplemental.

Ask the user when:
- Space constraints are severe and field meaning is still ambiguous.

## Anti-pattern: Punitive live validation

What it looks like:
- A form shows errors before the user has finished typing or blocks partial input unnecessarily.

Why it fails:
- It interrupts input and makes users feel wrong before they have completed the field.

Better approach:
- Validate at natural pauses, on blur, or after enough input exists. Use hints before errors when possible.

Ask the user when:
- Validation rules are strict and timing affects data quality or compliance.

## Anti-pattern: Smart defaults with no visibility or control

What it looks like:
- The system preselects, categorizes, fills, or submits values without showing what it did or letting users change it.

Why it fails:
- Incorrect defaults create hidden errors and reduce trust.

Better approach:
- Use defaults only when likely correct, visible, and editable. Explain unusual defaults.

Ask the user when:
- Incorrect defaults have high cost or sensitive implications.

## Anti-pattern: Spinner with no useful state

What it looks like:
- A blank page or spinner appears with no explanation, progress, skeleton, cancellation, or retry.

Why it fails:
- Users do not know whether the system is working, how long to wait, or what to do if it fails.

Better approach:
- Show immediate feedback, stable skeleton layout, progress when meaningful, and retry/cancel options for long operations.

Ask the user when:
- Latency and failure modes are unknown.

## Anti-pattern: Notification for everything

What it looks like:
- Push notifications, badges, or alerts are used for routine, non-urgent, or non-actionable events.

Why it fails:
- Users learn to ignore the product and may disable notifications entirely.

Better approach:
- Use in-product status for current-screen events; reserve notifications for timely, relevant, actionable off-screen updates.

Ask the user when:
- Urgency, channel, frequency, or user control is unclear.

## Anti-pattern: Motion as decoration

What it looks like:
- Transitions are added because they feel modern, not because they explain continuity or change.

Why it fails:
- Motion can slow tasks, distract, or harm users with motion sensitivity.

Better approach:
- Use motion to clarify cause, direction, hierarchy, or state change. Respect reduced-motion preferences.

Ask the user when:
- Motion is central to the brand or product experience and accessibility tradeoffs need review.

## Anti-pattern: Hidden selection scope

What it looks like:
- Users select items across pages, filters, or search results but cannot tell what is selected or what bulk actions affect.

Why it fails:
- Ambiguous scope leads to accidental deletion, modification, or confusion.

Better approach:
- Show selected count, selected item area, clear all, selection persistence rules, and whether actions apply to visible or all matching items.

Ask the user when:
- Selection across pages or filters is needed.

## Anti-pattern: One-off component drift

What it looks like:
- Each screen creates its own slightly different card, input, modal, table, or button.

Why it fails:
- Inconsistency creates UX debt and makes frontend maintenance harder.

Better approach:
- Reuse design-system components and create documented variants only when behavior or semantics differ.

Ask the user when:
- Existing design-system constraints are unknown.
