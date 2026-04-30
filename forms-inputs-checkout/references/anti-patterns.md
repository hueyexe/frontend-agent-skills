# Anti-patterns for `forms-inputs-checkout`

Prioritize these because an AI agent may accidentally produce them when generating forms, checkout flows, or frontend components.

## Anti-pattern: Database dump form

What it looks like:
- The form mirrors backend fields, department requests, or CRM columns instead of the user's task.
- Users are asked for profile, marketing, or administrative data before receiving value.

Why it fails:
- It treats the form as an internal record-creation tool rather than a conversation that helps a person accomplish a goal.

Better approach:
- Start from the user's goal, remove nonessential fields, infer or default safe answers, and defer enrichment until after completion.

Ask the user when:
- It is unclear which fields are legally, operationally, or technically required.

## Anti-pattern: Forced account creation before checkout

What it looks like:
- Users must sign in, create a password, or register before they can pay.
- Checkout asks "new or returning?" before collecting information needed for purchase.

Why it fails:
- It interrupts the purchase at the point of highest intent and makes a business goal compete with the user's goal.

Better approach:
- Support guest checkout or ask for account creation after purchase using data already provided during checkout.

Ask the user when:
- The product may legally or operationally require an account before purchase.

## Anti-pattern: Asking questions that could be asked later

What it looks like:
- Optional preferences, promo/student code, marketing consent, profile details, or account questions appear before the core task can proceed.

Why it fails:
- It increases effort, distracts from the main path, and creates opportunities for abandonment.

Better approach:
- Ask the minimum needed now. Move optional or enrichment questions after submission or to a contextual later step.

Ask the user when:
- A field may affect pricing, eligibility, fulfillment, support routing, or legal compliance.

## Anti-pattern: Placeholder-only labels

What it looks like:
- The label disappears once the user types.
- Review, editing, validation, and autofill become ambiguous because context is gone.

Why it fails:
- Labels provide the durable question. Removing them makes medium/long forms harder to review and inaccessible if not implemented carefully.

Better approach:
- Use visible labels. Use placeholder/help text only for examples or recommended formats.

Ask the user when:
- Extreme space constraints exist and the form is only one or two familiar fields.

## Anti-pattern: Select boxes for everything

What it looks like:
- Small sets of options are hidden behind dropdowns.
- Users must open a menu before seeing choices.

Why it fails:
- Hidden choices increase effort, impair comparison, and can be awkward on mobile or assistive technology.

Better approach:
- Use radio buttons for small mutually exclusive sets, checkboxes for independent choices, and autocomplete/combobox for long searchable lists.

Ask the user when:
- The number of options, single/multiple selection rules, or search need is unknown.

## Anti-pattern: Fake controls for form decisions

What it looks like:
- Tabs, cards, buttons, icons, or text links behave like choices but lack form semantics.
- Keyboard and screen reader behavior is not equivalent to radio/checkbox/select controls.

Why it fails:
- It weakens accessibility, state management, validation, and user expectations.

Better approach:
- Use real form controls or fully accessible design-system equivalents. Make both label and control clickable.

Ask the user when:
- A custom design-system component is required.

## Anti-pattern: Premature or misleading progress bar

What it looks like:
- A progress bar appears on a short form, a dynamic/branching flow, or before the product knows the real number of steps.

Why it fails:
- Misstated progress damages trust and can make the flow feel longer or less predictable.

Better approach:
- Omit progress for short/uncertain flows. For long stable flows, show scope, position, and save/status.

Ask the user when:
- The step count varies by user answers or eligibility.

## Anti-pattern: Splitting every field into its own page without purpose

What it looks like:
- A short form becomes many screens with no branching, learning, or focus benefit.

Why it fails:
- It adds navigation overhead and can reduce efficiency without increasing understanding or engagement.

Better approach:
- Use one thing per page only when it supports focus, mobile ergonomics, branching, or comprehension. Keep short coherent forms on one page.

Ask the user when:
- The user asks for multi-step/one-question-per-page but the form is short or review-heavy.

## Anti-pattern: Wrong question order

What it looks like:
- Payment appears before delivery constraints are known; promo code is primary; sensitive fields come before trust is established.

Why it fails:
- People expect a natural conversational order. Wrong order forces backtracking or creates suspicion.

Better approach:
- Ask in a sequence that matches the task: contact, location/delivery, options, payment, review/confirm for typical checkout.

Ask the user when:
- Domain constraints require a nonstandard sequence.

## Anti-pattern: Excessive help text

What it looks like:
- Long instruction blocks, multiple help links for a single choice, or paragraphs before the form.

Why it fails:
- Many users skip instructions and jump to the first field. Excess help often signals that the field, label, or flow is wrong.

Better approach:
- Improve labels/controls first. Add concise help only for unfamiliar, sensitive, format-specific, optional/required, or privacy/security questions.

Ask the user when:
- The form contains complex expert data or repeated-use workflows that may need contextual help panels.

## Anti-pattern: Optional-field clutter

What it looks like:
- Many fields are labeled optional and shown in the main path.

Why it fails:
- Optional fields still create effort, scanning cost, and uncertainty.

Better approach:
- Remove optional fields, postpone them, or reveal them only when the user chooses to provide more.

Ask the user when:
- Optional data affects fulfillment, personalization, or compliance.

## Anti-pattern: Arbitrary field widths

What it looks like:
- Every field has the same width even when expected answers are short, or fields vary randomly for aesthetic reasons.

Why it fails:
- Width is an affordance. Random or misleading widths make people wonder whether their answer length is wrong.

Better approach:
- Match width to expected value for known-length answers; otherwise use consistent practical widths.

Ask the user when:
- Internationalization or flexible formats make fixed length misleading.

## Anti-pattern: Hidden or disabled submit button before submission

What it looks like:
- The button disappears or stays disabled until all fields are valid, without clear explanation.

Why it fails:
- Users cannot discover what remains to fix; keyboard/screen reader users may not know the path forward.

Better approach:
- Keep the primary action visible. Let submit reveal actionable errors, or clearly explain blockers next to the button and focus the first issue.

Ask the user when:
- The action is destructive, irreversible, or legally gated by explicit prerequisites.

## Anti-pattern: Validating while the user is still typing

What it looks like:
- The form shows an error after the first character of an email, phone, password, or name.

Why it fails:
- It punishes valid in-progress input and interrupts the user's flow.

Better approach:
- Validate after the user finishes a field. Use live counters/meters only when they guide construction without scolding.

Ask the user when:
- Server-side availability, payment, address, or identity validation is required.

## Anti-pattern: Color-only error or status

What it looks like:
- Errors are indicated only by red text, green borders, colored rows, or color-changing buttons.

Why it fails:
- Color perception varies; users with color blindness or assistive technology may miss the state.

Better approach:
- Use text, icons/shapes, programmatic state, and visible placement in addition to color.

Ask the user when:
- Brand colors conflict with conventional error/success colors.

## Anti-pattern: Red text used for normal labels or help

What it looks like:
- Labels, hints, or normal text are red.

Why it fails:
- Red loses its error meaning, and actual errors become harder to notice.

Better approach:
- Reserve red and warning icons for errors/urgent warnings.

Ask the user when:
- Existing brand styles use red as a primary color and the error system needs a distinct accessible treatment.

## Anti-pattern: Equal-weight secondary actions

What it looks like:
- Reset, cancel, clear, back, or delete appears next to submit with equal or greater emphasis.

Why it fails:
- It increases wrong-action errors and undermines the single path to completion.

Better approach:
- Remove secondary actions when possible. If required, visually demote them, separate destructive actions, and provide undo.

Ask the user when:
- A secondary action is legally or operationally required.

## Anti-pattern: Decorative grouping noise

What it looks like:
- Alternating backgrounds, boxes, lines, and panels surround every label/input pair.

Why it fails:
- Extra visual elements interrupt scanning and compete with labels and fields.

Better approach:
- Use the minimum visual information needed: headings, whitespace, proximity, and thin separators only for meaningful sections.

Ask the user when:
- Dense enterprise forms need stronger grouping for scanning.

## Anti-pattern: Exposing all dependent fields

What it looks like:
- Every possible branch or follow-up field is visible, with irrelevant sections disabled or grayed out.

Why it fails:
- Users must process content that does not apply to them. Disabled sections can still overwhelm and obscure the active path.

Better approach:
- Hide irrelevant branches until needed; use page-level selection for large branches or inline reveal for 1-3 associated follow-up fields.

Ask the user when:
- Users need to compare branches before choosing.

## Anti-pattern: Success dead end

What it looks like:
- After submission, the screen only says success or redirects without explaining what happened or what to do next.

Why it fails:
- Users need confirmation, closure, and next steps, especially after payment or important submissions.

Better approach:
- Confirm what happened, show useful details, and provide contextually relevant next actions.

Ask the user when:
- The next best action depends on business workflow or user segment.

## Anti-pattern: Two-column keyboard maze

What it looks like:
- Fields are visually arranged in columns but tab order jumps unpredictably, moves offscreen, or breaks reading order.

Why it fails:
- Many users navigate fields with the keyboard. Jumps damage orientation and accessibility.

Better approach:
- Keep DOM order aligned with the visual/task order; prefer a single column unless the grouped fields are simple and the responsive/tab path is obvious.

Ask the user when:
- Desktop density is a hard constraint.

## Anti-pattern: Unsupported custom checkout widgets

What it looks like:
- Custom date pickers, payment inputs, comboboxes, or overlays lack focus management, keyboard support, error association, or mobile behavior.

Why it fails:
- Forms are already high-friction; broken custom controls add accessibility and implementation risk.

Better approach:
- Use native controls when possible. When custom controls are necessary, specify keyboard interaction, focus, roles, names, states, and fallback behavior.

Ask the user when:
- A design system mandates a custom control.
