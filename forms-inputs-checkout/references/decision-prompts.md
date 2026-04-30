# Decision Prompts for `forms-inputs-checkout`

Use these prompts only when the answer changes the design. Do not ask users to approve routine best practices such as readable labels, visible focus, or error messages.

## Decision: Primary form goal

When to ask:
- The user's request says "make a form" or "improve checkout" but does not identify the user goal, business goal, or submission outcome.

Do not ask when:
- The flow type and outcome are already clear, such as "shipping address step for checkout" or "newsletter sign-up."

Recommended default:
- Optimize for successful completion of the user's immediate task with the minimum trustworthy data needed.

Reason:
- Forms sit between users and goals; unclear goals cause inside-out field dumps and unnecessary friction.

Question tool pattern:
```js
question({
  question: "What is the primary thing this form must help users accomplish?",
  recommended_default: "Successful completion of the user's immediate task with the fewest necessary fields, because forms are barriers unless each question supports the goal.",
  options: [
    "Complete a purchase or checkout",
    "Create/sign in to an account",
    "Submit lead/support/application information",
    "Configure settings or preferences",
    "Other / custom"
  ]
})
```

## Decision: Required versus optional data

When to ask:
- The field list includes optional, marketing, profile, preference, analytics, or internal-only data and it is unclear which fields are truly required.

Do not ask when:
- The user provides a fixed required field list or a short obvious form where every field is needed to complete the task.

Recommended default:
- Remove or postpone optional fields; mark the minority case if optional/required status remains mixed.

Reason:
- Optional questions add effort, visual noise, and error risk; deferring them often preserves completion while still allowing later enrichment.

Question tool pattern:
```js
question({
  question: "Which fields are required to complete the user's task right now, and which can be removed or asked later?",
  recommended_default: "Keep only fields required for fulfillment, payment, eligibility, safety, or legal compliance; postpone profile, marketing, and preference fields.",
  options: [
    "Keep only fulfillment/compliance/payment fields",
    "Include optional personalization fields in the flow",
    "Ask optional fields after submission/purchase",
    "Other / custom"
  ]
})
```

## Decision: Checkout account requirement

When to ask:
- Designing checkout, purchase, booking, donation, subscription, or payment and account creation/sign-in appears before completion.

Do not ask when:
- The user explicitly says the product supports guest checkout or account creation is legally/operationally mandatory.

Recommended default:
- Offer guest checkout or account creation after purchase.

Reason:
- Forced account creation before checkout can block motivated buyers at the worst point in the journey; many account benefits can be offered after the transaction.

Question tool pattern:
```js
question({
  question: "Is an account truly required before purchase, or can users complete checkout as guests and create an account afterward?",
  recommended_default: "Guest checkout first, then optional account creation after purchase, because it reduces friction at the conversion point.",
  options: [
    "Guest checkout is allowed",
    "Account is required before purchase for fulfillment/security/compliance",
    "Account can be created after purchase",
    "Other / custom"
  ]
})
```

## Decision: Single page, multi-page, or one thing per page

When to ask:
- The form has many fields, multiple topics, branching logic, mobile-first usage, or a user asks whether to split it.

Do not ask when:
- The form is short and fits naturally on one page, or the user explicitly asks for a one-step flow.

Recommended default:
- Short coherent forms stay on one page; long or branching forms use meaningful steps; mobile/high-focus flows can use one thing per page.

Reason:
- Structure should match the conversation. Splitting can improve focus and branching, but can slow review or make scope unclear if overused.

Question tool pattern:
```js
question({
  question: "Should users see the whole form at once, or is this a long/branching flow where steps would reduce effort?",
  recommended_default: "Use one page for short coherent forms; use meaningful steps or one-question pages for long, branching, or mobile-first flows.",
  options: [
    "Single page with grouped sections",
    "Multi-step flow with clear sections",
    "One thing per page",
    "Other / custom"
  ]
})
```

## Decision: Progress indicator

When to ask:
- The form is multi-step and the number or order of steps may vary because of branching, eligibility, optional sections, or dynamic content.

Do not ask when:
- The form has a fixed, short, stable sequence and showing scope/position is clearly helpful.

Recommended default:
- Show progress only when it can honestly represent scope, position, and status. Omit or use general section status when steps are uncertain.

Reason:
- Misleading progress indicators damage trust and can make a dynamic form feel longer or broken.

Question tool pattern:
```js
question({
  question: "Is the number and order of steps fixed for almost every user?",
  recommended_default: "Use a progress indicator only for stable multi-step flows; otherwise use section labels or general progress cues.",
  options: [
    "Yes, fixed steps for nearly everyone",
    "No, steps vary based on answers",
    "Mostly fixed but with optional sections",
    "Other / custom"
  ]
})
```

## Decision: Label alignment

When to ask:
- The user asks about dense layout, localization, desktop-only admin tools, or a tradeoff between speed, vertical space, and label scanning.

Do not ask when:
- The form is mobile-first, familiar-data, checkout, registration, or a standard consumer flow.

Recommended default:
- Top-aligned visible labels.

Reason:
- Top labels keep label and field close, support mobile and localization, and usually create a fast downward path through familiar fields.

Question tool pattern:
```js
question({
  question: "What matters most for this form: fast completion, dense vertical space, or scanning many labels?",
  recommended_default: "Top-aligned labels for most consumer and mobile forms because they reduce completion effort and handle localization well.",
  options: [
    "Fast completion and mobile support",
    "Very dense desktop layout",
    "Users scan many unfamiliar labels before editing",
    "Other / custom"
  ]
})
```

## Decision: Control type for choices

When to ask:
- The user gives a field with multiple options but does not indicate number of options, whether users can select one or many, or whether options must be visible/searchable.

Do not ask when:
- The choice type is obvious, such as a yes/no checkbox or country list.

Recommended default:
- Radios for small mutually exclusive sets; checkboxes for independent/multiple choices; autocomplete/combobox for long searchable sets; select boxes only when they truly reduce complexity.

Reason:
- Hidden options and wrong controls increase cognitive load and errors.

Question tool pattern:
```js
question({
  question: "How many options are there, and can users choose one or many?",
  recommended_default: "Use visible radio buttons for a small single-choice set; use autocomplete for long searchable lists.",
  options: [
    "2-5 options, choose one",
    "Several options, choose multiple",
    "Long searchable list",
    "Other / custom"
  ]
})
```

## Decision: Defaults and prefilled values

When to ask:
- The agent is considering a default for country, plan, delivery method, billing same as shipping, marketing opt-in, saved payment, or personalized data.

Do not ask when:
- The default is purely mechanical and reversible, such as today's date in a date field where the task is always today.

Recommended default:
- Default only when the likely answer is correct for most users, reversible, and aligned with user interests.

Reason:
- Defaults reduce work but people often leave them unchanged, so biased or risky defaults can create harm and mistrust.

Question tool pattern:
```js
question({
  question: "Is this default likely to be correct for most users and easy to change if wrong?",
  recommended_default: "Use defaults only when they are likely correct, reversible, and in the user's interest.",
  options: [
    "Yes, likely correct and low-risk",
    "No, user should actively choose",
    "Use personalized saved value for returning users",
    "Other / custom"
  ]
})
```

## Decision: Sensitive or trust-heavy fields

When to ask:
- The form asks for date of birth, government ID, health/financial data, phone number, location, payment, password, SSN/tax ID, or other sensitive data.

Do not ask when:
- The user already provides a clear compliance or transactional reason and asks only for microcopy/implementation.

Recommended default:
- Explain why the data is needed, how it will be used, and what protects it; place help near the field.

Reason:
- Sensitive questions raise trust and privacy concerns that can cause abandonment or false answers.

Question tool pattern:
```js
question({
  question: "Why is this sensitive information required, and what reassurance can we truthfully provide?",
  recommended_default: "Ask only if necessary; add concise, adjacent help explaining purpose, use, and protection.",
  options: [
    "Required for payment/fulfillment/security",
    "Required for legal/compliance/eligibility",
    "Optional but useful for personalization/support",
    "Other / custom"
  ]
})
```

## Decision: Validation timing and server checks

When to ask:
- The field needs uniqueness checks, server validation, strict formatting, high error-rate validation, or expensive validation.

Do not ask when:
- Basic client-side validation after field completion is sufficient.

Recommended default:
- Validate after the user finishes the answer; use inline validation only where it helps them avoid likely errors.

Reason:
- Immediate errors during typing interrupt people and can make valid in-progress answers look wrong.

Question tool pattern:
```js
question({
  question: "Which fields need real-time or server-side validation before submission?",
  recommended_default: "Validate after field completion for high-risk or high-error fields; avoid interrupting while users type.",
  options: [
    "Email/username/password availability or strength",
    "Payment/address/identity validation",
    "Only validate on submit",
    "Other / custom"
  ]
})
```

## Decision: Error severity and recovery

When to ask:
- Errors can cause payment failure, legal submission rejection, irreversible action, data loss, or safety risk.

Do not ask when:
- Errors are low-risk and can be corrected with standard inline messages.

Recommended default:
- Prevent high-cost errors before submission, require review when consequences are irreversible, and support undo where possible.

Reason:
- People make predictable mistakes, especially under stress; high-cost errors need stronger safeguards.

Question tool pattern:
```js
question({
  question: "What is the consequence if a user submits incorrect information here?",
  recommended_default: "Use stronger prevention and review for irreversible, financial, legal, or safety-critical errors; use standard correction for low-risk errors.",
  options: [
    "Low risk; user can edit later",
    "Financial or fulfillment risk",
    "Legal/compliance/safety risk",
    "Other / custom"
  ]
})
```

## Decision: Dependent or branching fields

When to ask:
- A field reveals different follow-up inputs based on the user's answer.

Do not ask when:
- There are only one or two trivial follow-up fields and the trigger/association is obvious.

Recommended default:
- Hide irrelevant inputs until needed, keep dependent inputs near their trigger, and avoid page jumping.

Reason:
- Showing all possible follow-up fields overwhelms people; poorly associated dynamic fields cause disorientation.

Question tool pattern:
```js
question({
  question: "How many follow-up fields appear for each choice, and do users need to compare choices before choosing?",
  recommended_default: "Reveal only relevant follow-up fields near the trigger; use separate steps when each branch has many fields.",
  options: [
    "1-3 follow-up fields per choice",
    "Many follow-up fields per choice",
    "Users need to compare choices before selecting",
    "Other / custom"
  ]
})
```

## Decision: Review before submission

When to ask:
- The form involves payment, booking, application, irreversible submission, legal attestation, or multi-step checkout.

Do not ask when:
- The submission is low-risk and immediately editable.

Recommended default:
- Include a review step or concise answer summary before final submission for high-consequence flows.

Reason:
- Review helps users catch omissions and wrong-action errors before they matter.

Question tool pattern:
```js
question({
  question: "Do users need to review their answers before the final submission is committed?",
  recommended_default: "Add review for payment, legal, booking, or irreversible submissions; skip it for low-risk editable actions.",
  options: [
    "Yes, high consequence or irreversible",
    "No, low risk and editable",
    "Review only key fields and total/terms",
    "Other / custom"
  ]
})
```

## Decision: Legal consent and terms

When to ask:
- The flow includes terms, privacy, marketing consent, subscription renewal, payment authorization, or regulatory attestations.

Do not ask when:
- The user provides the required legal pattern and asks for implementation details.

Recommended default:
- Keep legal language near the relevant action; avoid extra questions when legal approval can be clearly tied to the primary action, but use explicit opt-in where legally required.

Reason:
- Legal requirements should be clear without adding unnecessary fields or weakening the primary action.

Question tool pattern:
```js
question({
  question: "Which consents must be explicit checkboxes, and which can be communicated as part of the primary action?",
  recommended_default: "Attach terms/payment consequence text to the primary action when allowed; use explicit unchecked consent boxes only where required.",
  options: [
    "Terms can be accepted via primary action text",
    "Explicit consent checkbox is legally required",
    "Marketing consent must be separate and optional",
    "Other / custom"
  ]
})
```

## Decision: Locale and input format

When to ask:
- The form includes addresses, names, phone numbers, dates, currency, tax IDs, country selection, or localization/internationalization.

Do not ask when:
- The product is clearly single-locale and the user specifies the locale.

Recommended default:
- Use flexible inputs, locale-aware labels/examples, and avoid overfitting to one country's format unless the audience is known.

Reason:
- Rigid formats cause errors and exclusion, especially for names, addresses, phone numbers, and dates.

Question tool pattern:
```js
question({
  question: "Which countries/locales and languages does this form need to support?",
  recommended_default: "Design flexible, locale-aware inputs unless the audience is definitely single-locale.",
  options: [
    "Single known locale",
    "Multiple countries/languages",
    "Unknown or expanding internationally",
    "Other / custom"
  ]
})
```

## Decision: Design-system and frontend constraints

When to ask:
- The recommendation involves custom controls, component APIs, validation framework, browser behavior, or existing design-system components.

Do not ask when:
- The user asks for general UX critique only.

Recommended default:
- Use semantic native controls wrapped in design-system components that expose label, help, error, status, and described-by props.

Reason:
- Maintainable implementation depends on preserving accessibility and state behavior across components.

Question tool pattern:
```js
question({
  question: "Are there existing form components or frontend constraints this design must use?",
  recommended_default: "Use semantic native controls through design-system components, preserving accessible labels, help, errors, focus, and keyboard behavior.",
  options: [
    "Use existing design-system components",
    "Build new components with semantic HTML",
    "Custom controls are required",
    "Other / custom"
  ]
})
```

## Decision: Measurement and evidence

When to ask:
- The user wants to optimize conversion, diagnose abandonment, or choose between two plausible form patterns.

Do not ask when:
- The issue is a clear accessibility or usability defect that should be fixed regardless of metrics.

Recommended default:
- Combine analytics, field error/drop-off data, support contacts, and small usability tests before and after redesign.

Reason:
- Form redesign can materially affect completion; different contexts may favor different choices.

Question tool pattern:
```js
question({
  question: "What evidence do we have about where users struggle in this form?",
  recommended_default: "Use completion rate, drop-off by step/field, error frequency, support tickets, and quick usability tests to prioritize fixes.",
  options: [
    "Analytics/drop-off data available",
    "Support/error logs available",
    "No evidence yet; use expert review first",
    "Other / custom"
  ]
})
```
