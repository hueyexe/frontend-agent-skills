---
name: forms-inputs-checkout
description: "Use when designing, critiquing, or implementing forms, inputs, validation, checkout, registration, payment, or any data-entry flow."
---

# Forms, Inputs, and Checkout

## Purpose

Help an agent design, critique, and implement clear, accessible, high-conversion forms, inputs, validation, and checkout flows.

Treat every form as a barrier between a person and a goal. The agent's job is to reduce that barrier without collecting bad data, hiding meaningful choices, or weakening accessibility, privacy, legal, or business requirements.

## When to use this skill

Use this skill for:

- Checkout, cart, payment, shipping, billing, promo-code, account, registration, sign-in, onboarding, subscription, lead-capture, support, survey, settings, profile, upload, and data-entry forms.
- Critiquing screenshots, wireframes, Figma descriptions, HTML/CSS/React components, design-system components, or product flows involving forms.
- Choosing labels, input controls, grouping, progress indicators, defaults, validation, error messages, help text, submit states, and success states.
- Making frontend guidance for semantic HTML forms, accessible names, focus, keyboard flow, validation, and responsive behavior.

## When not to use this skill

Do not use this skill for:

- General page layout, landing pages, navigation, marketing content, or visual brand work unless the page contains a form or checkout decision.
- Backend data modeling, fraud detection, tax, legal, PCI/security implementation, or payment processor integration details beyond UX/frontend implications.
- General conversion-copy work outside form context.
- Native platform-specific form controls when the user explicitly asks for a platform guideline not covered by the source material. In that case, ask or use the appropriate platform skill/source.

## Core principles

1. **Start outside-in.** Begin with the user's goal and the moment in their journey, not with the database fields the organization wants.
2. **Remove, defer, infer, or default before designing another field.** Every question creates effort and the possibility of error.
3. **Make the path to completion visually obvious.** A form should have a clear scan line from title to first question to final action.
4. **Use controls that match the question.** Prefer native, semantic form controls and visible options when the number of options is small.
5. **Use labels as durable context.** Do not rely on placeholder-only labels for anything longer than a trivial, familiar, one-field interaction.
6. **Validate to help, not to scold.** Validate after a person has finished an answer, prevent avoidable errors, and provide remedies in context.
7. **Design for mistakes.** People will omit steps, choose the wrong action, mistype, misunderstand labels, and miss information under stress.
8. **Do not use color alone.** Errors, success, required/optional status, disabled states, and payment/security cues need text and/or shape in addition to color.
9. **Keep checkout focused.** Remove distractions, avoid forced account creation, show costs and consequences clearly, and keep the primary action aligned with the buyer's goal.
10. **Make progress honest.** Use progress indicators only when the sequence and scope are stable enough that the indicator will not mislead.

## Default recommendations

Use these defaults unless the user provides a product-specific constraint or the skill's decision prompts indicate a question is needed.

### Form purpose and scope

Default: optimize for successful completion of the user's current goal with the minimum trustworthy data required.

Override when: regulatory, security, fraud, identity, eligibility, support, or fulfillment requirements demand additional data. Ask for the requirement and consequence.

### Question set

Default: remove nonessential questions; postpone optional or marketing questions until after the core submission; infer answers from known context when confidence is high.

Override when: optional answers are critical to personalization, eligibility, pricing, compliance, or operational routing.

### Structure

Default: use a single page for short forms with a few coherent topics; use multiple pages or one-thing-per-page for long forms, branching flows, mobile-first flows, or high-focus tasks.

Override when: users need to review many related answers together, compare choices, or complete a dense expert workflow.

### Labels

Default: use visible, concise, natural-language labels above fields. Top labels usually minimize completion time, handle localization better, and work well on mobile.

Override when: a dense desktop form has severe vertical constraints, or when a complex settings form needs label scanning more than speed.

### Required and optional fields

Default: avoid optional fields. When most fields are required, mark the few optional fields with text such as "Optional." When most fields are optional, mark the few required fields with text such as "Required." Do not mark every field required.

Override when: organizational standards require asterisks; still provide a legend and associate the indicator with the label.

### Input controls

Default: use native controls and semantic HTML. Use radio buttons for one choice among a small set, checkboxes for yes/no or multiple choices, text inputs for free-form answers, and select/combobox patterns only when they reduce effort for long option sets.

Override when: the design system has tested accessible custom controls that preserve keyboard, screen reader, focus, and error behavior.

### Select boxes

Default: use select boxes as a last resort. Prefer visible radio options for a short list, autocomplete/combobox for long searchable lists, or sensible defaults when the likely answer is known.

Override when: platform conventions or limited space make a select control the simplest accessible solution.

### Input width

Default: make field width communicate expected answer length when the answer has a known size, such as postal code or security code. Use consistent practical widths when length does not carry meaning.

Override when: responsive constraints, localization, or auto-formatting make exact width misleading.

### Help text

Default: provide short, adjacent help only for unfamiliar data, privacy/security concerns, unusual formats, sensitive questions, optional/required exceptions, or recommended answer formats.

Override when: expert, repeated-use, or complex workflows require a persistent contextual help panel.

### Validation

Default: validate after the user finishes a field, usually on blur or after selection, not while they are still typing. Use inline validation for fields with high error rates, strict formats, uniqueness checks, limits, or large valid answer sets.

Override when: a live counter or meter directly supports answer construction, such as character limits or password strength; make the feedback nonblocking while typing.

### Error messages

Default: provide a top-level error summary for long forms or multiple errors and inline field-level remedies for each problematic field. Mark error fields with text plus visual emphasis, not color alone.

Override when: a very short form has only one obvious error and the inline message is in view.

### Submit button and submission state

Default: keep the primary action visible and enabled; when clicked, clearly show processing and prevent duplicate submission. Avoid hiding or disabling the submit button before submission unless the reason is communicated and the next fix is obvious.

Override when: a destructive, irreversible, or legally sensitive action requires explicit prerequisites; explain what is missing and move focus to the first blocker.

### Checkout

Default: support guest checkout or account-after-purchase, keep order summary and total visible, minimize offramps, ask for delivery/payment information in a sensible order, and postpone account/profile questions.

Override when: the product cannot fulfill the transaction without an account, identity verification, eligibility, or saved relationship.

### Progress indicators

Default: omit progress bars for short, uncertain, or dynamically branching forms. Show scope, position, and save/status only for stable multi-step flows.

Override when: long forms need reassurance but steps are dynamic; use general progress language such as "Almost done" or section completion rather than precise step counts.

### Accessibility level

Default: design to WCAG-style expectations: semantic controls, visible labels, keyboard access, meaningful focus, sufficient contrast, text alternatives, no color-only cues, scalable text, and error messaging announced to assistive technology.

Override: do not lower accessibility. For high-risk domains, ask whether additional accessibility, testing, or legal conformance is required.

### Frontend implementation

Default: use semantic HTML first; style the native controls when possible; prefer design-system components that preserve native semantics; build form state around field value, touched/dirty status, validation status, submission status, and server error status.

Override when: a custom interaction is necessary; require keyboard, focus, screen reader, and mobile input behavior before recommending it.

## Required user questions

Ask a focused question only when the answer changes the recommended form design. Do not ask routine best-practice questions.

Ask when any of the following are unknown and materially affect the work:

- The form's business/user goal is ambiguous.
- The flow involves checkout, payment, identity, legal consent, healthcare, finance, government, minors, accessibility compliance, or irreversible consequences.
- The form has many fields and it is unclear which are required, optional, inferable, or deferrable.
- The audience, locale, language, device mix, or assistive technology needs are likely to change label length, input formats, keyboard behavior, or trust messaging.
- A tradeoff exists between one-page versus multi-page, speed versus careful review, visible options versus compact controls, or guest checkout versus account creation.
- Existing analytics/research are needed to diagnose drop-off, error rates, or conversion problems.

Use the prompts in `references/decision-prompts.md` for question-tool-ready patterns.

## Workflow for critiquing existing forms

Inspect in this order:

1. **Goal fit:** What is the user trying to accomplish, and does the form delay or block it unnecessarily?
2. **Question necessity:** Which fields can be removed, inferred, defaulted, made optional, or postponed?
3. **Flow and sequence:** Does the order match how people think about the task? Are sensitive or high-effort questions delayed until trust/context exists?
4. **Structure and grouping:** Are related questions grouped with the least visual noise necessary? Is branching handled without disorientation?
5. **Scan line and layout:** Can a person move steadily from label to input to action without zigzagging, jumping columns, or missing important information?
6. **Labels and controls:** Are labels visible, succinct, durable, and associated with the right semantic controls?
7. **Help and microcopy:** Is help contextual and minimal? Does it explain only what design cannot make obvious?
8. **Validation and errors:** Are errors prevented where possible, shown at the right time, and written as actionable remedies?
9. **Submission and success:** Is the primary action clear? Are loading, duplicate-submit prevention, success, and next steps handled?
10. **Accessibility and implementation:** Does the form work by keyboard, screen reader, touch, mobile keyboard, zoom, and without color-only cues?
11. **Measurement:** Recommend testing or analytics for completion rate, drop-off, error locations, time to complete, support contacts, and qualitative frustration.

When presenting critique, group findings by severity: blockers, high-friction issues, accessibility issues, conversion opportunities, polish.

## Workflow for creating or improving a form

1. **Clarify the task.** Identify the user's goal, business goal, required output, audience, device mix, and constraints.
2. **Define the minimum successful submission.** List fields as required, optional, inferable, defaultable, and deferrable.
3. **Choose the flow shape.** Single page, multi-step, one-question-per-page, progressive disclosure, or gradual engagement.
4. **Order the questions.** Start with low-friction/context-setting questions; delay account, sensitive, legal, or high-effort questions until they are justified.
5. **Group fields by user topic.** Use headings, whitespace, fieldsets, and legends; avoid decorative dividers that add visual noise.
6. **Select controls and labels.** Choose the simplest native control that matches the question; use visible labels and expected input attributes.
7. **Add defaults and help.** Default only when likely correct; keep help adjacent, brief, and specific.
8. **Design validation and errors.** Prevent errors, validate at humane timing, summarize when needed, and provide field-level remedies.
9. **Design submission states.** Make primary, secondary, loading, duplicate-submit prevention, success, and next steps explicit.
10. **Check accessibility and frontend feasibility.** Verify semantic HTML, focus, keyboard order, ARIA where needed, responsive behavior, and design-system fit.
11. **Explain tradeoffs.** State the chosen default, why it is appropriate, and what would change under different constraints.

## Decision framework

Use this order of preference before adding complexity:

1. **Remove** the question.
2. **Infer** the answer from known context or system data.
3. **Default** the answer when the default aligns with most users' goals and is easy to change.
4. **Defer** the question until after the core task or until the answer becomes relevant.
5. **Ask** the question in the simplest possible way.
6. **Explain** why the question is needed when people may wonder, worry, or lack context.
7. **Validate** at the least disruptive time.
8. **Recover** gracefully when the answer is missing, wrong, or rejected by the server.

## Practical rules

### Structure and flow

- Name the form with a title that matches the user's expected task, not the internal database object.
- For checkout, avoid sign-in walls. Let people proceed as guests or create an account after purchase whenever feasible.
- Break long forms into meaningful topics; do not split a short form into many pages just to simulate engagement.
- Use one thing per page when focus, branching, mobile ergonomics, or comprehension matter more than visible overview.
- Use progress indicators only when they honestly communicate scope, current position, and status.
- Provide save/resume for long, high-effort forms.

### Labels and questions

- Write labels as short, concrete questions or noun phrases in the user's language.
- Use consistent capitalization. Avoid all caps except for narrow warning contexts.
- Keep labels visible after the user types. Placeholder text can supplement, not replace, labels.
- Do not mix label alignments within the same form.
- Prefer top-aligned labels for familiar data and mobile-first work.
- Prefer left-aligned labels only when scanning unfamiliar or many optional fields matters more than speed.

### Grouping and visual hierarchy

- Use proximity and whitespace before lines, panels, or alternating backgrounds.
- Use fieldsets and legends for groups of radio buttons, checkboxes, and related controls.
- Give the primary action a clear visual relationship to the fields it submits.
- Avoid two-column layouts unless tab order, responsive collapse, and scanning remain obvious.

### Controls

- Use radio buttons when one option among a small set must be selected and all options should be visible.
- Use checkboxes for independent choices or a single yes/no consent/option.
- Avoid select boxes for small option sets; they hide choices and add interaction cost.
- For long lists, consider autocomplete/combobox with accessible keyboard behavior and clear valid suggestions.
- Make option labels clickable; ensure the input and its label share the same activation target.
- Use mobile-appropriate input types and attributes: `email`, `tel`, `url`, `number` only when numeric behavior is truly appropriate, `autocomplete`, `inputmode`, `autocapitalize`, `spellcheck`, and `aria-describedby` as needed.

### Required, optional, and deferrable inputs

- Remove optional fields unless they serve a clear user or business purpose.
- Mark the minority case: optional when most are required, required when most are optional.
- Use text over symbols for clarity. If using an asterisk, provide a legend and accessible label.
- Ask for promo codes, account creation, marketing preferences, and profile enrichment only when contextually useful; otherwise defer.

### Defaults and personalization

- Use defaults to reduce work only when the default is likely correct, reversible, and aligned with user interests.
- Do not default to hidden costs, marketing opt-ins, premium plans, or risky permissions.
- Personalize defaults for returning users when the information is likely stable and easy to change.
- Be careful with country, delivery, and payment defaults: wrong defaults can cause costly errors.

### Help text

- Use help for unfamiliar terms, sensitive data, privacy/security reassurance, unusual formatting, answer limits, or why a field is needed.
- Place help adjacent to the relevant label/input or in a consistent help area for complex repeated-use forms.
- Avoid long instruction blocks before the form; people often jump directly into fields.
- Do not use help text to compensate for bad labels, wrong controls, arbitrary formats, or unnecessary questions.

### Validation, errors, and success

- Accept flexible human input where possible, such as varied phone/credit card spacing, then normalize after entry.
- Validate uniqueness, availability, strict formats, and limits at the point they are useful.
- Do not show errors while the user is still typing a normal answer.
- Explain the problem, the location, and the remedy.
- On long forms, provide an error summary and link/focus to each field error.
- Use text, icon/shape, and styling for errors; reserve red/warning icons for errors so they retain meaning.
- After successful submission, confirm what happened and provide the next logical action. Avoid dead-end success screens.

### Checkout-specific rules

- Keep checkout visually calmer than browsing. Remove unrelated navigation, offers, and links that lead away from completion.
- Preserve cart context: item count, editable order summary, shipping/billing/payment totals, taxes/fees when known, and delivery expectations.
- Ask questions in a sequence people expect: contact/email, delivery/location, delivery method, payment, review/confirm. Adjust when the product context requires another order.
- Defer account creation, password, preferences, and marketing until after purchase whenever possible.
- Make payment/security reassurance specific and verifiable, not generic decoration.
- Keep promo-code entry available but visually secondary unless discounts are central to the business model.
- Ensure the final action communicates consequence: place order, pay, subscribe, submit application, save changes.

## Accessibility and inclusion requirements

Always check:

- Every field has an accessible name, preferably a visible `<label>` associated with `for`/`id` or a wrapping label.
- Related controls use semantic grouping: `<fieldset>` and `<legend>` for radio/checkbox groups.
- Error and help text are programmatically associated with fields via `aria-describedby` or equivalent.
- Error summaries are focusable, announced, and provide links to invalid fields.
- Focus order follows visual/task order; no keyboard traps; all controls and help triggers work without a mouse.
- Focus states are visible and not removed by CSS.
- The form works at zoom and with larger text; mobile layouts do not hide labels or error messages.
- Color is never the only signal. Add text, icon/shape, and programmatic state.
- Motion, flashing, and automatic changes are minimized; dynamic validation is polite and not disruptive.
- Timeouts provide warning, extension, and no loss of work when possible.
- Copy avoids references that depend only on physical location, color, or visual shape, such as "the green button on the right."
- Test with intended users, including users with disabilities, when the flow is critical.

## Frontend implementation guidance

Use semantic HTML before adding JavaScript complexity.

```html
<form novalidate>
  <fieldset>
    <legend>Delivery method</legend>
    <label><input type="radio" name="delivery" value="ship"> Ship to address</label>
    <label><input type="radio" name="delivery" value="pickup"> Pick up in store</label>
  </fieldset>

  <label for="email">Email address</label>
  <input id="email" name="email" type="email" autocomplete="email" autocapitalize="none" spellcheck="false" aria-describedby="email-help email-error">
  <p id="email-help">We will send your receipt and delivery updates here.</p>
  <p id="email-error" role="alert" hidden>Enter an email address, like name@example.com.</p>

  <button type="submit">Continue to payment</button>
</form>
```

Implementation rules:

- Do not replace native controls with custom controls unless the custom version preserves keyboard and assistive technology behavior.
- Keep DOM order aligned with the visual order, especially in multi-column layouts.
- Avoid positive `tabindex`; fix DOM order instead. Use `tabindex="-1"` only to programmatically focus summaries or headings.
- Model form state explicitly: value, dirty/touched, client validity, server validity, loading/submitting, success, and recoverable failure.
- For server validation, preserve user-entered values and return field-level errors keyed to stable field names.
- Disable or guard against duplicate submission after click; communicate processing state and keep the label/consequence understandable.
- Do not hide the only submit path because a validation condition is unmet unless the UI also explains the blocker and how to fix it.
- Use `autocomplete` tokens for common checkout fields: name, email, tel, street-address, address-line1, address-level2, postal-code, country, cc-name, cc-number, cc-exp, cc-csc where appropriate.
- Use `inputmode` for numeric-looking text values that should not be number inputs, such as postal codes, phone numbers, and card numbers.
- Format after input when possible rather than rejecting common human formats.
- Component APIs should accept visible label, help text, error text, required/optional text, described-by IDs, and design tokens for spacing/state.

## Quality checklist

Before finalizing a recommendation, verify:

- The form has a clear user goal and a clear primary action.
- Every field has a reason to exist now.
- Optional fields are removed, deferred, or marked as the minority case.
- The question order matches the user's mental model of the task.
- The layout provides a single readable path to completion.
- The controls match the data type and decision type.
- Labels remain visible and are programmatically associated.
- Help is contextual, concise, and not compensating for poor design.
- Validation timing is humane and field errors are actionable.
- Error and success states are designed, not left to defaults.
- Checkout avoids account walls and unnecessary offramps unless required.
- Keyboard, focus, screen reader, color contrast, zoom, and mobile keyboards are covered.
- The implementation is feasible within the design system and frontend stack.

## Common mistakes to avoid

- Designing from database fields instead of the user's task.
- Asking optional/profile/marketing/account questions before the core task.
- Using placeholders as labels.
- Using select boxes for short lists.
- Marking every field required.
- Using red text for normal labels or help, weakening error meaning.
- Validating while the user is still typing.
- Hiding or disabling submit without an obvious remedy.
- Using progress bars for dynamic or unknown steps.
- Making secondary/destructive actions visually equal to the primary action.
- Adding decorative grouping that interrupts scanning.
- Showing all dependent fields at once and overwhelming the user.
- Ending with a success page that offers no confirmation or next step.

## How to explain recommendations to the user

Explain in terms of completion, confidence, error prevention, and trust.

Use this pattern:

1. **State the recommendation.** "Use visible top-aligned labels and keep help text under the field."
2. **Tie it to the user's goal.** "This keeps the checkout path easy to scan on mobile and reduces the chance of people losing context while typing."
3. **Mention the tradeoff.** "It uses more vertical space, but the form is short enough that clarity is more valuable than density."
4. **Name the exception.** "For dense expert settings screens, left-aligned labels may be better because users scan labels before editing."
5. **Give implementation detail only when useful.** "Use a real `<label>` and associate help/error text with `aria-describedby`."

