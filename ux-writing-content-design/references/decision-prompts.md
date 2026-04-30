# Decision Prompts for `ux-writing-content-design`

Use these prompts only when the answer changes the copy, pattern, tone, accessibility behavior, or implementation. Do not ask routine best-practice questions.

## Decision: Primary user task

When to ask:
- The user asks for copy but does not explain what the user is trying to accomplish.
- The same UI could support multiple tasks with different wording.

Do not ask when:
- The task is obvious from the provided UI, route, or component name.

Recommended default:
- Optimize for the immediate visible task and make the next action obvious.

Reason:
- Product copy should help people move through the current experience, not become standalone prose.

Question tool pattern:
```js
question({
  question: "What is the primary user task this copy needs to support?",
  recommended_default: "Assume the user wants to complete the immediate visible action with as little uncertainty as possible.",
  options: [
    "Complete a task",
    "Learn how something works",
    "Recover from a problem",
    "Make a high-stakes decision",
    "Other / custom"
  ]
})
```

## Decision: Product and user goal alignment

When to ask:
- The requested copy appears to push a business goal that may conflict with the user’s stated goal.
- The user asks for conversion optimization, retention prompts, upsells, forced signups, opt-ins, or notification copy.

Do not ask when:
- The product goal and user benefit are clearly aligned.

Recommended default:
- Serve the user’s immediate goal while making legitimate product benefits clear.

Reason:
- Copy that forces, hides, or manipulates damages trust and can make the experience less useful.

Question tool pattern:
```js
question({
  question: "What user benefit should this business goal support?",
  recommended_default: "Frame the copy around a benefit the user can understand and choose, rather than forcing the business goal into the flow.",
  options: [
    "Help the user complete the current task",
    "Explain an optional benefit",
    "Reduce risk or support burden",
    "Increase activation/conversion with a user-benefit guardrail",
    "Other / custom"
  ]
})
```

## Decision: Audience and vocabulary

When to ask:
- The audience may have specialized domain knowledge, low familiarity, high stress, or mixed language/literacy levels.
- The copy involves technical, legal, medical, financial, developer, or internal terminology.

Do not ask when:
- The product is general-purpose and no specialized language is necessary.

Recommended default:
- Use plain language and explain necessary terms in context.

Reason:
- Familiar terms reduce cognitive load and support accessibility.

Question tool pattern:
```js
question({
  question: "How familiar is the target audience with this topic or terminology?",
  recommended_default: "Use plain language for a broad mixed-ability audience, and introduce domain terms only when users expect them.",
  options: [
    "General consumer audience",
    "Business/professional audience",
    "Expert/domain audience",
    "Mixed audience",
    "Other / custom"
  ]
})
```

## Decision: Brand voice

When to ask:
- The user asks for voice/tone, brand personality, delight, humor, or copy that should match an existing product.
- Multiple tone directions would be plausible.

Do not ask when:
- The user asks only for functional default copy in a common product context.

Recommended default:
- Professional, warm, direct, and human.

Reason:
- This tone supports comprehension and trust without over-branding.

Question tool pattern:
```js
question({
  question: "What personality should this product communicate in UI copy?",
  recommended_default: "Professional, warm, direct, and human, because it works for most productivity, SaaS, commerce, and service interfaces unless a stronger brand voice is documented.",
  options: [
    "Professional and warm",
    "Plain and utilitarian",
    "Playful and energetic",
    "Premium and polished",
    "Other / custom"
  ]
})
```

## Decision: Tone for emotional stakes

When to ask:
- The copy appears in an error, rejection, denial, payment issue, identity flow, legal consent, health, safety, security, account lockout, or sensitive user moment.
- The user asks for humor or delight in a potentially stressful state.

Do not ask when:
- The state is clearly low-stress and reversible.

Recommended default:
- Calm, direct, supportive, and non-humorous.

Reason:
- Stress cases require respect and recovery, not personality performance.

Question tool pattern:
```js
question({
  question: "How stressful or sensitive is this moment for the user?",
  recommended_default: "Use a calm, direct, supportive tone and avoid humor unless the moment is clearly low-stress and reversible.",
  options: [
    "Low-stress and reversible",
    "Mild friction or confusion",
    "High-stress or time-sensitive",
    "Sensitive personal/legal/financial/health/security context",
    "Other / custom"
  ]
})
```

## Decision: Sensitive data request

When to ask:
- The interface asks for identity, demographics, gender, race/ethnicity, health, finances, location, contacts, legal status, payment, or other sensitive personal data.
- The requested categories may exclude some users.

Do not ask when:
- The data is clearly non-sensitive and the reason is obvious.

Recommended default:
- Explain why the information is needed, how it will be used, and whether it is optional.

Reason:
- Context reduces distrust and harm, and inclusive choices improve data quality.

Question tool pattern:
```js
question({
  question: "Why does the product need this information, and can the user skip or self-describe?",
  recommended_default: "Explain the reason in context, use inclusive options, and make the field optional when the product can still work without it.",
  options: [
    "Required for legal/compliance reasons",
    "Required to provide the service",
    "Optional personalization or research",
    "Not actually required",
    "Other / custom"
  ]
})
```

## Decision: CTA consequence

When to ask:
- A button/link label depends on what happens after click/tap.
- The action involves payment, publishing, sending, deleting, sharing, permissions, subscription, or irreversible changes.

Do not ask when:
- The consequence is already stated clearly in the UI and action is routine.

Recommended default:
- Use verb + object/consequence.

Reason:
- Buttons are decision points; users need to know what will happen.

Question tool pattern:
```js
question({
  question: "What exactly happens after the user activates this action?",
  recommended_default: "Use a specific verb-led label that names the outcome, such as “Create post,” “Pay $24,” or “Delete account.”",
  options: [
    "Creates or saves something",
    "Publishes/shares/sends something",
    "Pays/subscribes/purchases",
    "Deletes/removes/cancels",
    "Other / custom"
  ]
})
```

## Decision: Error recovery path

When to ask:
- The agent can explain an error but does not know what recovery actions are technically available.
- The error may be avoidable through design, validation, or backend behavior.

Do not ask when:
- The fix is standard and obvious, such as entering a valid email format.

Recommended default:
- Provide a specific next step and, when possible, a retry or alternative route.

Reason:
- Error copy that only explains can still leave the user stuck.

Question tool pattern:
```js
question({
  question: "What can the user actually do to recover from this error?",
  recommended_default: "Tell the user what went wrong and give the most direct available recovery step.",
  options: [
    "Fix input and retry",
    "Retry later or check connection",
    "Use an alternative path",
    "Contact support",
    "Other / custom"
  ]
})
```

## Decision: Prevention versus explanation

When to ask:
- The user asks for explanatory copy for a confusing UI that might be better fixed by layout, progressive disclosure, validation, or a direct link/action.

Do not ask when:
- The UI cannot be changed and copy is the only available intervention.

Recommended default:
- Fix the interaction or place the needed action in context before adding explanatory copy.

Reason:
- Microcopy should guide, not serve as a bandage for broken design.

Question tool pattern:
```js
question({
  question: "Can we change the UI or component behavior, or can we only change the words?",
  recommended_default: "Improve the interaction first when possible, then use the smallest necessary copy to guide the user.",
  options: [
    "Can change UI and copy",
    "Can change copy only",
    "Can change validation/state behavior",
    "Can add a help link or inline action",
    "Other / custom"
  ]
})
```

## Decision: Empty-state next action

When to ask:
- The user asks for empty-state copy but the next useful action is unclear.

Do not ask when:
- The next action is obvious from the feature, such as creating the first project.

Recommended default:
- Explain what is empty and offer the next useful action.

Reason:
- Empty states can guide onboarding and prevent dead ends.

Question tool pattern:
```js
question({
  question: "What should users do next from this empty state?",
  recommended_default: "State what’s missing and offer the most useful next action.",
  options: [
    "Create the first item",
    "Import or upload content",
    "Adjust filters/search",
    "Wait for data or permissions",
    "Other / custom"
  ]
})
```

## Decision: Notification value and timing

When to ask:
- The user asks for notification, alert, email subject, push, toast, or reminder copy.
- The notification may interrupt the user.

Do not ask when:
- The notification is a required transactional confirmation.

Recommended default:
- Notify only when timely, relevant, and actionable.

Reason:
- Interruptions must earn attention.

Question tool pattern:
```js
question({
  question: "What user action or decision does this notification support right now?",
  recommended_default: "Send the notification only if it is timely, relevant, and actionable; otherwise surface it in-product.",
  options: [
    "Immediate action required",
    "Useful reminder",
    "Status change the user cares about",
    "FYI only",
    "Other / custom"
  ]
})
```

## Decision: Measurement goal

When to ask:
- The user asks to optimize, test, justify, or measure UX copy.
- Multiple success metrics are possible or a business metric could harm user trust.

Do not ask when:
- The task is a low-stakes copy improvement with no requested measurement.

Recommended default:
- Measure task success and comprehension; use conversion only with guardrails.

Reason:
- Copy should improve the experience, not only drive a number.

Question tool pattern:
```js
question({
  question: "What success metric and guardrail should this copy optimize for?",
  recommended_default: "Use task completion and comprehension as primary signals, with conversion or retention as secondary only when aligned with user benefit.",
  options: [
    "Task completion",
    "Comprehension or reduced confusion",
    "Error recovery or support reduction",
    "Conversion/activation with trust guardrail",
    "Other / custom"
  ]
})
```

## Decision: Localization requirement

When to ask:
- The UI will be translated, supports multiple regions, or has constrained components.
- The copy uses idioms, jokes, metaphors, variables, plurals, or very tight labels.

Do not ask when:
- The product is explicitly single-locale and no translation/localization is planned.

Recommended default:
- Write localizable source copy and avoid idioms, fragment concatenation, and layout assumptions.

Reason:
- Localized strings expand, reorder, and carry different cultural assumptions.

Question tool pattern:
```js
question({
  question: "Will this copy need to support localization or multiple regions?",
  recommended_default: "Write localizable source copy: plain language, flexible length, movable variables, and translator context.",
  options: [
    "No localization planned",
    "Likely future localization",
    "Actively localized now",
    "Region-specific legal/cultural variants",
    "Other / custom"
  ]
})
```

## Decision: Design-system and frontend constraints

When to ask:
- The copy must fit a component, token, string table, validation system, or existing design system.
- The user asks for implementation-ready UI copy.

Do not ask when:
- The deliverable is conceptual only.

Recommended default:
- Provide component/state copy and accessibility notes.

Reason:
- Good UX copy must survive implementation.

Question tool pattern:
```js
question({
  question: "What frontend or design-system constraints should the copy fit?",
  recommended_default: "Provide copy by component state, with visible labels, error associations, live-region guidance where needed, and localization notes.",
  options: [
    "Existing design-system component",
    "Custom frontend component",
    "Mobile native UI",
    "No known constraints",
    "Other / custom"
  ]
})
```

## Decision: Legal/compliance review

When to ask:
- The copy states legal obligations, consent, privacy, medical/financial claims, regulated eligibility, fees, warranties, cancellation, or user rights.

Do not ask when:
- The copy is plainly functional and not compliance-sensitive.

Recommended default:
- Use plain language and mark for legal/compliance review.

Reason:
- Clarity matters, but a UX agent should not invent regulated obligations.

Question tool pattern:
```js
question({
  question: "Does this copy need legal, compliance, privacy, medical, or financial review?",
  recommended_default: "Draft in plain language and flag the final wording for expert review if it affects rights, obligations, eligibility, consent, payment, or regulated claims.",
  options: [
    "No special review needed",
    "Legal/compliance review required",
    "Privacy/security review required",
    "Medical/financial/regulatory review required",
    "Other / custom"
  ]
})
```
