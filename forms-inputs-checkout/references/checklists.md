# Checklists for `forms-inputs-checkout`

Use these checklists before delivering a critique, redesign, implementation plan, or code for forms and checkout flows.

## Discovery/context checklist

- The user goal is stated in plain language.
- The business goal is stated separately from the user goal.
- The form's submission outcome is known: purchase, save, apply, subscribe, create account, send request, etc.
- The audience is known or defaulted to general consumer users.
- Device context is known or defaulted to responsive/mobile-friendly.
- Locale and language requirements are known for names, addresses, phone, dates, currency, and legal copy.
- Legal, payment, security, privacy, accessibility, or compliance constraints are identified.
- The required data fields are separated from optional, inferable, defaultable, and deferrable fields.
- Existing design-system or frontend constraints are known.
- Existing evidence is noted if available: analytics, error logs, support tickets, usability findings, user research.
- If evidence is missing, the recommendation is framed as expert heuristic guidance, not proven performance improvement.

## Field necessity checklist

- Every field has a current user or business reason.
- Optional fields have been removed, postponed, or justified.
- Fields needed only for account creation are deferred until after checkout unless an account is required.
- Marketing opt-ins are separate from required consent and not defaulted in a user-hostile way.
- Promo-code, voucher, referral, and gift-card fields are visible enough for users who need them but do not dominate checkout.
- Sensitive fields explain why they are needed and how the data will be used/protected.
- Data that can be inferred reliably is not re-asked.
- Defaults are likely correct, reversible, and aligned with user interests.
- Returning-user defaults are easy to inspect and change.

## Flow and structure checklist

- The form title matches the user's task.
- The first question is low-friction and contextually sensible.
- Questions appear in the order users naturally think about the task.
- Related fields are grouped into meaningful topics.
- Groups are separated primarily with headings, whitespace, and proximity.
- Decorative dividers, boxes, alternating backgrounds, or extra lines are minimized.
- The flow does not ask high-friction or sensitive questions before trust/context exists.
- Branching paths reveal only relevant fields.
- Dynamic fields remain visually associated with their trigger.
- Revealing fields does not create disorienting page jumps.
- Multi-step flows show progress only when the step sequence is stable.
- Long forms provide save/resume or preserve entered values after errors.
- Review steps are included for payment, legal, booking, application, or irreversible submissions.

## Layout and scan-line checklist

- There is a clear path from label to input to primary action.
- The primary action aligns with the form's main scan line.
- Labels and fields do not force zigzagging eye movement.
- Two-column layouts do not break keyboard order, zoom behavior, or responsive collapse.
- Spacing between questions is consistent and generous enough to avoid missed fields.
- Important content is not placed at screen edges where users are likely to miss it.
- Dense forms still preserve clear grouping and focus order.
- Visual hierarchy makes fields, errors, help, and actions distinguishable.
- The primary action is visually stronger than secondary actions.
- Destructive secondary actions are separated, lower emphasis, and recoverable.

## Labels and microcopy checklist

- Every field has a visible, durable label.
- Label text is short, natural, and uses the user's language.
- Labels remain visible after typing.
- Placeholder text is used only as supplementary example/help, not as the only label.
- Capitalization is consistent and not all-caps except for rare warnings.
- Required/optional markers are text-based or explained with an accessible legend.
- Help text explains only what is not obvious from label/control/format.
- Help text is adjacent to the relevant field or placed in a consistent help area.
- Long instruction blocks before the form are removed or shortened.
- Copy does not rely on color, direction, or visual position alone.
- Error copy states what happened and how to fix it.
- Success copy states what happened and what the user can do next.

## Control selection checklist

- Radio buttons are used for small mutually exclusive option sets.
- Checkboxes are used for independent selections or a single optional yes/no choice.
- Select boxes are avoided for short option sets.
- Long lists use accessible search/autocomplete/combobox behavior when appropriate.
- Text input is used only when free-form entry is truly needed.
- Field width provides an affordance when answer length is known.
- Arbitrary varying field widths are avoided.
- Input examples and masks do not make easy answers harder.
- Users can click/tap both the control and its label to select an option.
- Mobile keyboard type supports the expected answer.
- Flexible formatting is accepted for common human-entered values such as phone, card, dates, and postal codes when possible.

## Validation and error checklist

- Validation is not shown while the user is still typing a normal in-progress answer.
- Inline validation is used for high-error, strict-format, unique, availability, limit, or suggestion fields.
- Character counters update live when limits matter.
- Autocorrection/normalization happens after entry, not mid-entry.
- Server validation preserves user-entered values.
- Long forms provide a top-level error summary.
- Error summary identifies the problem and links/focuses to invalid fields.
- Field-level errors are placed near the field and explain the remedy.
- Error fields use more than color: text, icon/shape, border, and programmatic invalid state.
- Red/warning icons are reserved for errors or urgent warnings.
- Focus moves predictably after submit errors.
- Users can recover without losing data.
- Duplicate submissions are prevented after clicking submit.
- Loading/processing state is visible and announced where needed.

## Checkout checklist

- Guest checkout or account-after-purchase is supported unless account is truly required.
- Checkout removes unrelated navigation, promotions, and offramps.
- Order summary remains available with item count, item details, total, fees/taxes when known, shipping, and editable cart link.
- Contact/email is requested before information needed for receipt/status.
- Country/delivery information appears before delivery options that depend on location.
- Delivery, billing, and payment fields appear in a sequence that matches the user's task.
- Billing same as shipping is defaulted only when likely and easy to change.
- Promo-code entry is available but secondary.
- Payment/security reassurance is specific and truthful.
- The final button label communicates the consequence: pay, place order, subscribe, submit application.
- The review step shows final total and critical terms before purchase.
- Post-purchase success confirms the order and provides receipt, tracking, account creation, or next actions.

## Accessibility checklist

- Each control has an accessible name.
- Labels are associated using native label semantics.
- Radio/checkbox groups use fieldset and legend or equivalent accessible grouping.
- Help and error text are associated with controls.
- Required/optional status is available to assistive technology.
- Invalid fields expose an invalid state programmatically.
- Error summary is focusable and announced.
- Keyboard order matches visual/task order.
- All actions, help triggers, overlays, and custom controls work without a mouse.
- Focus states are visible.
- Focus is managed after opening/closing overlays and after submission errors.
- Text and controls scale without overlap or clipping.
- Contrast is sufficient for text, borders, focus, and error states.
- Color is not the only cue.
- Motion and animation are nonessential, brief, and not flashing.
- Timeouts can be extended or avoided without data loss when possible.
- The form is testable with screen reader, keyboard, touch, and zoom.

## Frontend implementation feasibility checklist

- DOM order matches the intended reading and tab order.
- Native controls are used unless a custom control is justified.
- Custom controls implement keyboard interaction, roles, names, state, focus, and disabled/expanded/selected semantics.
- Form component APIs support label, hint/help, error, optional/required text, described-by, and status.
- `autocomplete` tokens are included for common personal, address, and payment fields.
- `type`, `inputmode`, `autocapitalize`, and `spellcheck` are chosen intentionally.
- Error IDs are stable and can be referenced by `aria-describedby`.
- Client validation and server validation share clear field keys.
- The implementation preserves values after validation failure.
- Async validation handles loading, success, failure, and stale responses.
- Submit handling prevents duplicates and supports retry on recoverable failure.
- Layout uses responsive CSS without changing semantic order.
- Browser differences in form controls are accepted or normalized through tested design-system styles.
- The implementation is maintainable with tokens for spacing, color, typography, border, focus, and state.

## Critique response checklist

- The critique names the likely user goal and any assumptions.
- Findings are ordered by impact, not by visual location alone.
- Each finding explains the user problem and practical fix.
- Accessibility defects are clearly labeled and not treated as optional polish.
- Conversion recommendations are framed as hypotheses when no data is provided.
- The critique avoids vague advice like "make it cleaner" without specifying the form behavior to change.
- The critique includes at least one quick win and one higher-impact structural recommendation when available.
- Tradeoffs and exceptions are stated.
- The response does not over-ask; it asks only for missing context that changes the recommendation.

## Final response checklist

- The recommended default is explicit.
- Exceptions are stated briefly.
- Any user questions are specific, necessary, and include a recommended default.
- The answer includes frontend/accessibility implications when implementation is in scope.
- The answer distinguishes facts from assumptions.
- No long copyrighted excerpts from source material are included.
- The response gives the user something actionable: a revised flow, field list, wireframe description, component spec, critique, code guidance, or test plan.
