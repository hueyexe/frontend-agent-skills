# Principle Cards for `forms-inputs-checkout`

These cards convert the source extraction into reusable rules an agent can apply when designing, critiquing, or implementing forms and checkout flows.

## Principle: Start outside-in

Rule:
- Begin with what the user is trying to accomplish, not with the database record, department request, or component inventory.

Why it matters:
- Forms are usually barriers between users and desired outcomes. Inside-out forms ask for too much too early and cause abandonment.

Use when:
- Any new form, redesign, checkout, registration, onboarding, or data-entry flow.

Do not use when:
- Never ignore this principle. Even compliance-heavy forms should be explained from the user's task and consequence.

Default recommendation:
- Define the user's goal, the business goal, and the minimum successful submission before choosing fields or layout.

Ask the user when:
- The purpose or outcome of the form is ambiguous.

Question prompt:
```js
question({
  question: "What is the primary user goal this form must complete?",
  recommended_default: "Optimize for the user's immediate task and collect only data needed to complete it.",
  options: ["Purchase/checkout", "Register/sign in", "Submit a request/application", "Configure/manage data", "Other / custom"]
})
```

Agent behavior:
- State the inferred goal before critiquing. If unclear, ask one focused question. Map each field to the goal or mark it remove/defer/infer/default.

## Principle: Remove, infer, default, or defer before asking

Rule:
- Do not design a field until you have tested whether the question can be removed, inferred, safely defaulted, or asked later.

Why it matters:
- Every field adds effort, visual weight, cognitive load, and opportunities for error.

Use when:
- Reviewing field lists, checkout flows, profile forms, signup flows, and long forms.

Do not use when:
- The field is legally, operationally, or technically required now; still explain why it is needed.

Default recommendation:
- Keep only fields required for the current task; postpone optional and enrichment data.

Ask the user when:
- A field's necessity is unclear or might be required by legal/fulfillment/security constraints.

Question prompt:
```js
question({
  question: "Which of these fields are required to complete the task right now, and which can be removed or asked later?",
  recommended_default: "Keep only fields needed for fulfillment, payment, eligibility, safety, or compliance; defer optional enrichment.",
  options: ["Only required fields", "Include some optional personalization", "Ask optional fields after submission", "Other / custom"]
})
```

Agent behavior:
- Produce a field audit with columns: keep now, remove, infer, default, defer, needs user decision.

## Principle: Organize the form as a conversation

Rule:
- Order questions the way a helpful person would ask them, using natural topic breaks.

Why it matters:
- A sensible sequence reduces backtracking, suspicion, and mental reordering.

Use when:
- Structuring checkout, onboarding, applications, support forms, and settings.

Do not use when:
- A technical dependency or compliance sequence requires a different order; explain that constraint.

Default recommendation:
- Start with low-friction context, ask dependent questions only after their prerequisites, and delay sensitive/payment/account questions until justified.

Ask the user when:
- Product constraints may force a nonstandard order.

Question prompt:
```js
question({
  question: "Are there technical, legal, or operational dependencies that force a specific question order?",
  recommended_default: "Use a natural task order unless a dependency requires otherwise.",
  options: ["No special dependency", "Payment/identity must happen early", "Eligibility determines the rest", "Other / custom"]
})
```

Agent behavior:
- Reorder fields and explain each group by user topic, not internal team ownership.

## Principle: Use a clear path to completion

Rule:
- Create a visually continuous path from title to fields to primary action, with minimal distractions.

Why it matters:
- People scan screens based on expectations and miss items that interrupt their path or sit at the edges.

Use when:
- Critiquing form layout, checkout pages, modal forms, and multi-column forms.

Do not use when:
- Dense expert tools may need compact arrangements, but they still need predictable focus and scan order.

Default recommendation:
- Use a single-column path for most forms; align the primary action with the input column.

Ask the user when:
- Desktop density is a hard constraint.

Question prompt:
```js
question({
  question: "Is desktop density more important than a simple single-column completion path?",
  recommended_default: "Use a single-column path unless density is a hard requirement.",
  options: ["Prioritize single-column clarity", "Prioritize dense desktop layout", "Need both responsive variants", "Other / custom"]
})
```

Agent behavior:
- In critique, call out zigzags, offramps, extra boxes/lines, and tab-order jumps before visual polish.

## Principle: Make progress honest

Rule:
- Use progress indicators only when they accurately communicate scope, position, and status.

Why it matters:
- Progress can motivate, but inaccurate progress creates distrust and confusion.

Use when:
- Multi-step forms, checkout, applications, onboarding, and high-effort forms.

Do not use when:
- The form is short, step count is unknown, or branching changes the sequence.

Default recommendation:
- Start without a progress bar; add one only for stable multi-step flows.

Ask the user when:
- Branching or optional sections may change the number of steps.

Question prompt:
```js
question({
  question: "Is the number and order of steps fixed for nearly every user?",
  recommended_default: "Show progress only when the sequence is stable; otherwise use section labels or save/status cues.",
  options: ["Fixed sequence", "Branching sequence", "Optional sections", "Other / custom"]
})
```

Agent behavior:
- Replace misleading step bars with section headings, save status, or general progress language.

## Principle: Default to visible top labels

Rule:
- Use visible, durable labels. Default to top-aligned labels for most consumer, checkout, mobile, and familiar-data forms.

Why it matters:
- Top labels keep question and answer close, simplify mobile layouts, and preserve context while users type.

Use when:
- Checkout, signup, address, payment, contact, lead forms, and mobile-responsive UI.

Do not use when:
- Dense expert settings or unfamiliar-data forms require scanning labels more than fast completion.

Default recommendation:
- Visible top-aligned labels.

Ask the user when:
- Vertical space, localization, or scanning many labels is a primary constraint.

Question prompt:
```js
question({
  question: "What matters most here: fast completion, compact vertical space, or scanning unfamiliar labels?",
  recommended_default: "Top-aligned visible labels for most forms because they are fast, mobile-friendly, and localization-friendly.",
  options: ["Fast/mobile completion", "Compact desktop density", "Scan many unfamiliar labels", "Other / custom"]
})
```

Agent behavior:
- Reject placeholder-only labels unless the form is a tiny familiar interaction and accessibility is preserved.

## Principle: Use native controls that match the question

Rule:
- Choose controls based on the decision type: one choice, many choices, free entry, known list, or long searchable list.

Why it matters:
- Wrong controls hide options, confuse state, and create accessibility and implementation problems.

Use when:
- Selecting input components, design-system controls, or writing frontend code.

Do not use when:
- A custom control is required and has already been accessibility-tested; preserve equivalent behavior.

Default recommendation:
- Native semantic controls first; accessible design-system wrappers second.

Ask the user when:
- The number of options or single/multiple selection rule is unclear.

Question prompt:
```js
question({
  question: "How many options are there, and can users choose one or many?",
  recommended_default: "Use radios for small single-choice sets, checkboxes for independent/multiple choices, and autocomplete for long searchable lists.",
  options: ["2-5 choose one", "Choose many", "Long searchable list", "Other / custom"]
})
```

Agent behavior:
- Specify semantic HTML/control behavior in design recommendations, not just visual appearance.

## Principle: Treat select boxes as a last resort

Rule:
- Do not hide small option sets in dropdowns; make important choices visible.

Why it matters:
- Visible choices reduce memory and comparison effort. Select boxes add clicks/taps and hide the decision space.

Use when:
- Country, state, delivery method, account status, product option, and preference fields.

Do not use when:
- The option list is long, predictable, and compact display is valuable; use search/autocomplete when appropriate.

Default recommendation:
- Radios for small sets; autocomplete/combobox for long searchable sets.

Ask the user when:
- Option count and search need are unknown.

Question prompt:
```js
question({
  question: "How many choices will users choose from, and do they need search?",
  recommended_default: "Show small choice sets as radios; use searchable autocomplete for long lists.",
  options: ["Small list", "Long searchable list", "Long but rarely changed", "Other / custom"]
})
```

Agent behavior:
- Flag unnecessary dropdowns in critique and propose visible alternatives.

## Principle: Field width is an affordance

Rule:
- Use field width to suggest expected answer length when length is meaningful; otherwise use consistent widths.

Why it matters:
- Users infer meaning from size. Random widths make them wonder whether their answer is too short/long.

Use when:
- Postal code, CVV, phone, date, code, quantity, short IDs, and multi-line text areas.

Do not use when:
- International formats vary so much that fixed width becomes misleading.

Default recommendation:
- Match known-length fields; use flexible/consistent width for variable data.

Ask the user when:
- Locale/international support is unclear.

Question prompt:
```js
question({
  question: "Is this field's answer length predictable across the target locales?",
  recommended_default: "Use length-matched fields only when the expected value length is stable; otherwise use flexible width.",
  options: ["Stable length", "Varies by locale", "Unknown", "Other / custom"]
})
```

Agent behavior:
- Include field width and example formatting in component specs.

## Principle: Mark the minority required/optional state

Rule:
- Mark whichever state is rare: optional when most fields are required, required when most fields are optional.

Why it matters:
- Marking every field adds noise; ambiguous symbols force users to decode a convention.

Use when:
- Mixed required/optional forms.

Do not use when:
- All fields are required or all fields are optional; no marker is usually needed beyond context.

Default recommendation:
- Avoid optional fields; if present, mark the few optional fields with text.

Ask the user when:
- It is unclear which fields are truly optional.

Question prompt:
```js
question({
  question: "Which fields are truly optional in the current submission?",
  recommended_default: "Remove optional fields where possible; otherwise mark only the few optional fields with text.",
  options: ["Most fields required", "Most fields optional", "All required", "Other / custom"]
})
```

Agent behavior:
- Do not generate asterisks without a legend and accessible text.

## Principle: Help belongs at the question

Rule:
- Provide help only where it reduces uncertainty about a specific question.

Why it matters:
- People often skip instructions. Excess help can make simple tasks seem complex.

Use when:
- Unfamiliar terms, sensitive data, privacy/security concerns, unusual formats, optional/required exceptions, or complex expert data.

Do not use when:
- Better labels, controls, or defaults can remove the need for help.

Default recommendation:
- Short adjacent help beneath or beside the field.

Ask the user when:
- A complex repeated-use form may need automatic, user-activated, or persistent section help.

Question prompt:
```js
question({
  question: "Will users need brief field-specific help, or a persistent help area for complex repeated use?",
  recommended_default: "Use concise adjacent help for most fields; reserve persistent help for complex repeated workflows.",
  options: ["Brief adjacent help", "Automatic contextual help", "User-activated help panel", "Other / custom"]
})
```

Agent behavior:
- Convert long pre-form instructions into field-level help or remove them.

## Principle: Validate after completion, not during typing

Rule:
- Trigger validation when the user has finished a field, except for constructive live feedback like counters.

Why it matters:
- Premature errors interrupt, stress users, and mark valid in-progress answers as wrong.

Use when:
- Email, username, password, payment, address, strict format, uniqueness, and character-limit fields.

Do not use when:
- A live counter or strength/quality indicator helps the user construct the answer without showing a blocking error.

Default recommendation:
- Validate on blur, after selection, or after submit; use inline validation selectively.

Ask the user when:
- Server checks, uniqueness, or expensive validation are involved.

Question prompt:
```js
question({
  question: "Which fields need server-side or inline validation before final submit?",
  recommended_default: "Validate after field completion for high-error or strict fields; avoid interrupting while typing.",
  options: ["Availability/uniqueness", "Payment/address/identity", "Only on submit", "Other / custom"]
})
```

Agent behavior:
- Specify validation trigger, loading state, success state, and error state for each high-risk field.

## Principle: Errors must explain location, problem, and remedy

Rule:
- Error states must make the blocker obvious and tell users exactly how to fix it.

Why it matters:
- Users make predictable mistakes and may be stressed; vague errors create dead ends.

Use when:
- Any form submission or validation state.

Do not use when:
- Never omit remedies for blocking errors. Short forms can omit a top summary only if the field error is visible and obvious.

Default recommendation:
- Top error summary for long/multiple-error forms plus inline field messages.

Ask the user when:
- Error consequence is high-risk and may need review, confirmation, or undo.

Question prompt:
```js
question({
  question: "What happens if this error is not caught before submission?",
  recommended_default: "Use stronger prevention and review for payment, legal, safety, or irreversible errors.",
  options: ["Low risk/editable", "Financial/fulfillment risk", "Legal/safety risk", "Other / custom"]
})
```

Agent behavior:
- Write actual error copy, not just "show error." Include focus/ARIA behavior if implementation is in scope.

## Principle: Confirm success and offer next steps

Rule:
- After submission, confirm what happened and what the user can do next.

Why it matters:
- Success is part of the form experience. Dead ends create uncertainty after effort or payment.

Use when:
- Purchases, applications, account creation, support tickets, saves, uploads, and invitations.

Do not use when:
- Inline autosave may only need subtle confirmation, but critical changes still need perceivable status.

Default recommendation:
- Contextual success message plus relevant next actions.

Ask the user when:
- The correct next step depends on business workflow.

Question prompt:
```js
question({
  question: "After successful submission, what should users be able to do next?",
  recommended_default: "Confirm what happened and provide the most relevant next action.",
  options: ["View receipt/status", "Continue editing/adding", "Create account/share/save", "Other / custom"]
})
```

Agent behavior:
- Include success, empty/error/retry, and post-submit state in flow specs.

## Principle: Keep the submit path visible

Rule:
- Keep the primary action visible and understandable; do not hide or disable it as the only way to discover missing work.

Why it matters:
- A hidden/disabled action gives users no clear path forward. But duplicate submissions after click must still be prevented.

Use when:
- Submit, continue, pay, place order, save, register, and destructive actions.

Do not use when:
- An irreversible/legal action requires explicit prerequisites; still explain blockers.

Default recommendation:
- Visible enabled action; on click, show actionable validation. During processing, show loading and prevent duplicates.

Ask the user when:
- The action is legally or safely gated.

Question prompt:
```js
question({
  question: "Is there a legal, safety, or irreversible-action reason the primary action must be disabled until prerequisites are met?",
  recommended_default: "Keep the action visible; explain blockers instead of hiding the path.",
  options: ["No gating needed", "Legal/safety gating required", "Destructive action gating required", "Other / custom"]
})
```

Agent behavior:
- Specify pre-submit, validation-failed, submitting, submitted, and retry states.

## Principle: Checkout must minimize offramps

Rule:
- Once users enter checkout, remove unrelated navigation and questions that do not help them buy.

Why it matters:
- Checkout occurs after intent is established; offramps and account walls reduce completion.

Use when:
- Ecommerce, booking, donation, subscription, payment, and order forms.

Do not use when:
- Regulations, identity, eligibility, or fulfillment require extra steps; explain them.

Default recommendation:
- Guest checkout or account after purchase, order summary, contact/delivery/payment/review sequence, and focused primary action.

Ask the user when:
- Account, identity, or legal requirements may be mandatory before purchase.

Question prompt:
```js
question({
  question: "Can users complete checkout without creating an account first?",
  recommended_default: "Allow guest checkout or account creation after purchase unless account is required for fulfillment/security/compliance.",
  options: ["Guest checkout", "Account after purchase", "Account required before purchase", "Other / custom"]
})
```

Agent behavior:
- In checkout critiques, prioritize account walls, offramps, order summary, hidden costs, payment trust, and final-action clarity.

## Principle: Hide irrelevant dependent fields, but preserve association

Rule:
- Show follow-up fields only when relevant, and keep them visually/programmatically tied to the triggering choice.

Why it matters:
- Exposing every branch overwhelms users; detached dynamic fields make users lose context.

Use when:
- Delivery method, account type, payment type, shipping/pickup, business/personal, eligibility, and conditional settings.

Do not use when:
- Users must compare all branches before choosing; then provide an explicit comparison pattern.

Default recommendation:
- Inline reveal for 1-3 follow-up fields; separate step/page for large branches.

Ask the user when:
- Number of follow-ups per choice is unclear.

Question prompt:
```js
question({
  question: "How many follow-up fields appear for each choice?",
  recommended_default: "Reveal 1-3 fields inline near the trigger; use a separate step for larger branches.",
  options: ["1-3 follow-ups", "Many follow-ups", "Need comparison before choosing", "Other / custom"]
})
```

Agent behavior:
- Specify state transitions, focus behavior, and associations for revealed fields.

## Principle: Accessibility is form usability

Rule:
- Design forms so they work with keyboard, screen readers, zoom, color blindness, and cognitive load constraints.

Why it matters:
- Accessible form practices also improve speed, clarity, recovery, and reliability for everyone.

Use when:
- All form and checkout design or implementation.

Do not use when:
- Never treat accessibility as optional polish. For high-risk forms, raise the standard.

Default recommendation:
- Semantic HTML, visible labels, fieldsets/legends, described-by help/errors, focus order, no color-only cues, scalable text, and tested keyboard behavior.

Ask the user when:
- Compliance level, high-risk domain, or assistive technology requirements may be stricter than baseline.

Question prompt:
```js
question({
  question: "Does this form need to meet a specific accessibility or compliance standard?",
  recommended_default: "Design to WCAG-style expectations by default; raise rigor for regulated or high-risk contexts.",
  options: ["Standard accessible web form", "WCAG/Section 508 compliance required", "High-risk regulated workflow", "Other / custom"]
})
```

Agent behavior:
- Include accessibility requirements in every implementation-oriented answer.

## Principle: Design for predictable mistakes

Rule:
- Assume users will omit steps, type wrong values, choose wrong actions, miss warnings, and need recovery.

Why it matters:
- There is no fail-safe product. The design must prevent, detect, and repair errors.

Use when:
- Any validation, payment, account, destructive action, or high-effort form.

Do not use when:
- Never skip error design. Low-risk flows can use lighter recovery.

Default recommendation:
- Prevent errors through constraints and flexible inputs, then provide clear inline remedies and undo/retry where possible.

Ask the user when:
- The cost of an error changes the strength of safeguards.

Question prompt:
```js
question({
  question: "What is the cost of a wrong or incomplete submission?",
  recommended_default: "Use stronger prevention and review when consequences are financial, legal, safety-related, or hard to undo.",
  options: ["Low cost", "Medium operational cost", "High financial/legal/safety cost", "Other / custom"]
})
```

Agent behavior:
- Add prevention, review, confirmation, undo, and support paths proportional to error consequence.

## Principle: Make review available for consequential answers

Rule:
- Let users check critical answers before final submission.

Why it matters:
- Memory is limited and users make omissions/wrong-action errors. Review catches mistakes before they become costly.

Use when:
- Payment, booking, shipping, legal, applications, healthcare/finance/government, irreversible submissions.

Do not use when:
- Low-risk saves are immediately editable and adding review would slow the core task.

Default recommendation:
- Add concise review step for high-consequence flows.

Ask the user when:
- Consequence or editability is unclear.

Question prompt:
```js
question({
  question: "Can users easily edit this submission after sending, or should they review it first?",
  recommended_default: "Add review when the submission is hard to undo, legally meaningful, or tied to payment/fulfillment.",
  options: ["Easy to edit later", "Hard to edit later", "Payment/legal/booking", "Other / custom"]
})
```

Agent behavior:
- Include review summaries with edit links for critical fields and final totals.
