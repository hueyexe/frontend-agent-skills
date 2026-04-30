# Checklists

Use these before finalizing critique, redesign, pattern selection, or frontend guidance.

## Discovery and context checklist

- The primary user task is stated in one sentence.
- The user’s success outcome is clear.
- The target audience skill level and task frequency are known or reasonably inferred.
- The platform and input mode are known or defaulted responsively.
- The data shape is known: item type, attributes, scale, volatility, and visual richness.
- The action risk is known: reversible, destructive, costly, private, legal, or cross-user.
- The navigation depth is known: flat, hierarchy, process, workspace, or hub.
- The design-system/frontend constraints are known when implementation guidance is requested.
- Any domain-specific accessibility, compliance, privacy, or safety requirements are known.
- The agent asked no more than one focused context question unless multiple unknowns genuinely block the recommendation.

## Pattern selection checklist

- The recommended pattern directly serves the user task.
- A simpler pattern was considered before recommending a complex one.
- The screen has one dominant organizing purpose: overview, focus, make, do, dashboard, flow, or workspace.
- The navigation model fits the information architecture.
- The component choice fits the data shape and scale.
- The recommendation explains why likely alternatives are weaker.
- The chosen pattern preserves context where possible.
- The pattern includes an escape, back, cancel, or undo path.
- The pattern supports both first-time comprehension and repeat-use efficiency where relevant.
- The pattern does not rely on hidden interactions for critical tasks.

## UI/UX quality checklist

- The primary object or content area is visually obvious.
- The primary action is visually stronger than secondary and tertiary actions.
- Secondary actions are accessible but not competing with the primary action.
- Related controls and content are grouped by proximity and headings.
- Labels use the user’s vocabulary rather than implementation terms.
- The screen does not ask users to remember information from a previous step unnecessarily.
- The UI preserves safe state after navigation, filtering, or detail inspection.
- The interface clearly shows what changed after an action.
- The user can recover from mistakes.
- Empty states explain what is missing and what to do next.
- Loading states preserve layout and prioritize useful content.
- Error states explain the problem, location, and recovery action.
- Disabled states explain why the action is unavailable when the reason is not obvious.
- The layout still works with long labels, missing data, and unusually long content.
- Critical controls do not move unexpectedly after the task begins.
- The interface avoids unnecessary page transitions and refreshes.

## Navigation and wayfinding checklist

- The current location is visible.
- The user can identify available next destinations.
- The user can return to a parent, previous, or safe starting point.
- Deep pages can be linked or bookmarked when needed.
- Multistep flows show progress when users need orientation.
- Modal or overlay contexts have a clear close/cancel behavior.
- Focus returns to the triggering element after a modal closes.
- Breadcrumbs are used for hierarchy, not as the only navigation.
- Mobile navigation does not consume top-screen real estate unnecessarily.
- Long pages provide section cues, anchors, or scroll-position support when needed.

## Lists, tables, and cards checklist

- The item representation matches the user’s scanning behavior.
- Tables are used when users need attribute comparison, sorting, filtering, or bulk actions.
- Cards are used when each item is a self-contained object with rich content or imagery.
- Thumbnail grids are used when image recognition matters more than text comparison.
- Carousels do not contain essential choices users must discover.
- Lists show enough metadata for users to identify each item.
- Bulk selection has clear selected/unselected states.
- Selection across pages or filters is explicitly represented.
- Sorting and filtering controls show current state.
- Pagination or infinite loading preserves user position.
- Empty results distinguish “no data yet” from “no results match filters.”
- Row/card actions make their scope clear.

## Dashboard and data display checklist

- Every metric supports a decision, triage step, or monitoring need.
- The dashboard distinguishes normal status from exceptions.
- Users can inspect exact values when needed.
- Users can filter, sort, drill down, or segment data where relevant.
- Charts use visual encodings appropriate to the data.
- Multiple scales or axes are avoided unless necessary and clearly labeled.
- Small multiples are considered for comparing related series.
- Stale data, refresh time, and loading status are visible when relevant.
- The dashboard includes an action path for important findings.
- Decorative metrics and vanity charts are removed or deprioritized.

## Forms and input checklist

- The form’s purpose and user benefit are clear.
- Only fields needed now are required.
- Optional fields are marked or separated consistently.
- Labels remain visible after input.
- Placeholder text is not the only label.
- Field hints are adjacent to the relevant field.
- Input type matches expected data.
- Field width gives a useful cue about expected input length when possible.
- Defaults and prefills are likely correct and easy to change.
- Autocomplete suggestions are relevant and do not trap keyboard users.
- Validation is timely but does not punish users while they are still typing.
- Error messages identify the field, problem, and correction.
- Multi-section forms are grouped with meaningful headings.
- Long forms preserve progress and support safe return.
- Sensitive or destructive submissions include appropriate review, confirmation, or recovery.

## Microinteraction and feedback checklist

- Every interactive control has visible feedback.
- The system acknowledges input immediately.
- Long-running actions show progress or background status.
- Users can cancel long-running operations when feasible.
- Success messages confirm meaningful completion, not obvious clicks.
- Notifications are timely, relevant, and actionable.
- Notification frequency is capped or user-configurable when appropriate.
- Nudges serve a user-valued goal, not only product engagement.
- Quantitative status is visualized when comparison or progress matters.
- Motion clarifies cause, change, or continuity.
- Reduced-motion alternatives are supported.

## Accessibility checklist

- Interactive elements use semantic controls.
- All controls have accessible names.
- Inputs have associated labels.
- Errors are programmatically associated with fields.
- Focus order follows visual and task order.
- Focus states are visible.
- All functionality is available by keyboard.
- Menus, dialogs, tabs, accordions, comboboxes, and grids follow expected keyboard patterns.
- Modal dialogs trap focus only while open and restore focus on close.
- No critical interaction depends on hover alone.
- No meaning depends on color alone.
- Text and controls meet contrast expectations.
- Touch targets are large enough for mobile/touch use.
- Dynamic status updates are announced when they affect task completion.
- Reduced-motion preferences are respected.
- Screen-reader users can understand loading, empty, error, and success states.
- Disabled controls are not the only explanation of unavailable actions.
- Drag-and-drop has an accessible alternative.

## Frontend implementation feasibility checklist

- The component can be built from existing design-system primitives where possible.
- Component anatomy is specified.
- Variants are behaviorally meaningful, not cosmetic one-offs.
- All required states are specified.
- Responsive behavior is specified for small, medium, and large screens.
- Keyboard behavior is specified.
- ARIA roles/properties are used only when native semantics are insufficient.
- Loading and asynchronous states are implementable without layout shift.
- Data fetching and pagination/virtualization do not break accessibility.
- State persistence rules are defined.
- Error and retry logic are defined.
- Content limits, truncation, wrapping, and overflow behavior are defined.
- Design tokens are used for spacing, typography, color, elevation, radius, and motion.
- The component API does not expose unnecessary complexity to product teams.
- Performance risks are identified for large lists, dashboards, charts, or media grids.

## Final response checklist

- The recommendation is framed around user task and outcome.
- The best default is clearly stated.
- Tradeoffs and context-dependent alternatives are included.
- The user is not asked unnecessary best-practice questions.
- Accessibility is treated as a baseline, not an optional add-on.
- Frontend guidance is included when relevant.
- The response is actionable enough for design or implementation work.
