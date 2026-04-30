# Principle Cards for `ux-writing-content-design`

## Principle: Words are design material

Rule:
- Treat product words as part of the interaction design, not as a final editing pass.

Why it matters:
- A label, button, or error can change what users understand, attempt, trust, and recover from.

Use when:
- Any UI copy or component state affects user action or comprehension.

Do not use when:
- The task is purely visual polish with no text or state implications.

Default recommendation:
- Inspect the task, flow, state, and system behavior before drafting copy.

Ask the user when:
- The UI may need redesign but the user has only requested wording.

Question prompt:
```js
question({
  question: "Can we change the UI or component behavior, or can we only change the words?",
  recommended_default: "Improve the interaction first when possible, then use the smallest necessary copy to guide the user.",
  options: ["Can change UI and copy", "Can change copy only", "Can change validation/state behavior", "Other / custom"]
})
```

Agent behavior:
- Suggest UI or state changes when copy would otherwise become a bandage.

## Principle: Align user and organization goals

Rule:
- Write copy that helps the user succeed while supporting legitimate product goals.

Why it matters:
- Trust breaks when copy hides friction, forces opt-ins, or prioritizes business goals over the user’s task.

Use when:
- Activation, onboarding, conversion, subscription, retention, signup, or notification copy is requested.

Do not use when:
- The flow is a neutral operational state with no goal tension.

Default recommendation:
- Frame benefits transparently and keep the user’s primary path available.

Ask the user when:
- Business and user goals appear to conflict.

Question prompt:
```js
question({
  question: "What user benefit should this business goal support?",
  recommended_default: "Frame the copy around a benefit the user can understand and choose, rather than forcing the business goal into the flow.",
  options: ["Complete current task", "Explain optional benefit", "Reduce risk/support", "Optimize conversion with guardrail", "Other / custom"]
})
```

Agent behavior:
- Refuse manipulative phrasing and provide a user-benefit alternative.

## Principle: Design the conversation

Rule:
- Evaluate copy as a sequence: entry point, prompt, action, system response, next step, inverse action, and failure path.

Why it matters:
- Isolated string choices miss what users know before and after they encounter the text.

Use when:
- Drafting CTAs, onboarding, forms, dialogs, errors, or flow-level content.

Do not use when:
- The user asks for a standalone term or design-system naming convention with known context.

Default recommendation:
- Map the user’s next action and system response before choosing words.

Ask the user when:
- The action after a button or link is unknown.

Question prompt:
```js
question({
  question: "What exactly happens after the user activates this action?",
  recommended_default: "Use a specific verb-led label that names the outcome.",
  options: ["Creates/saves", "Publishes/shares/sends", "Pays/subscribes", "Deletes/cancels", "Other / custom"]
})
```

Agent behavior:
- Provide copy by state and by step, not just a single “best” phrase.

## Principle: Choose the right content pattern

Rule:
- Match the copy to the user need and UI state: title, label, hint, CTA, empty state, confirmation, notification, loading, or error.

Why it matters:
- The same words can help or fail depending on placement and component behavior.

Use when:
- Creating or critiquing UI text patterns.

Do not use when:
- The user explicitly requests only a wording variation for a fixed component.

Default recommendation:
- Prefer the lightest pattern that gives the user enough context.

Ask the user when:
- The available component/state is constrained.

Question prompt:
```js
question({
  question: "What component or state will this copy appear in?",
  recommended_default: "Use the lightest pattern that gives enough context: label first, helper text when needed, modal only for blocking decisions.",
  options: ["Label/field", "Button/link", "Toast/banner", "Modal/dialog", "Other / custom"]
})
```

Agent behavior:
- Recommend changing the component if the current pattern is too weak or too intrusive.

## Principle: Make actions consequence-revealing

Rule:
- Button and link labels should tell users what will happen.

Why it matters:
- Actions are decision points; vague labels increase hesitation and errors.

Use when:
- Writing CTAs, links, menu items, destructive actions, payment actions, or publishing flows.

Do not use when:
- The object and consequence are obvious from immediate context and the label must be extremely short.

Default recommendation:
- Use verb + object/consequence.

Ask the user when:
- The consequence changes money, visibility, permissions, account status, or data.

Question prompt:
```js
question({
  question: "Does this action change money, visibility, permissions, account status, or data?",
  recommended_default: "Include the consequence in the label or nearby confirmation.",
  options: ["No, routine action", "Payment/subscription", "Publish/share/send", "Delete/cancel/irreversible", "Other / custom"]
})
```

Agent behavior:
- Rewrite vague actions and warn when a CTA hides risk.

## Principle: Make forms self-explanatory and accessible

Rule:
- Use visible labels, targeted hints, and contextual explanations for constraints or sensitive questions.

Why it matters:
- Forms are frequent failure points; placeholders and vague labels create avoidable errors.

Use when:
- Working with forms, onboarding inputs, validation, eligibility, or profile setup.

Do not use when:
- The field is purely decorative or non-interactive.

Default recommendation:
- Persistent label + hint only when needed + accessible error.

Ask the user when:
- The field asks for sensitive information or uses unusual categories.

Question prompt:
```js
question({
  question: "Why does the product need this information, and can the user skip or self-describe?",
  recommended_default: "Explain the reason in context and make the field optional when possible.",
  options: ["Required by law", "Required for service", "Optional personalization", "Not required", "Other / custom"]
})
```

Agent behavior:
- Add context for sensitive asks and avoid placeholder-only labels.

## Principle: Error states are stress cases

Rule:
- Handle errors by trying to avoid them, then explaining them, then resolving them.

Why it matters:
- Errors occur when user needs and system needs conflict; the copy must reduce stress and restore progress.

Use when:
- Creating validation, failed payment, account, upload, permission, offline, or eligibility messages.

Do not use when:
- The state is not actually an error and should be framed as neutral status.

Default recommendation:
- State the issue and the next step, calmly and specifically.

Ask the user when:
- Recovery options are unknown.

Question prompt:
```js
question({
  question: "What can the user actually do to recover from this error?",
  recommended_default: "Tell the user what went wrong and give the most direct available recovery step.",
  options: ["Fix input", "Retry later", "Use alternative path", "Contact support", "Other / custom"]
})
```

Agent behavior:
- Include prevention ideas, user-facing message, and implementation notes for accessible errors.

## Principle: Explain sensitive asks

Rule:
- When asking for personal, sensitive, or hard-to-categorize information, explain why it is needed and how it will be used.

Why it matters:
- Missing context can exclude users, reduce data quality, and damage trust.

Use when:
- Asking for gender, date of birth, health, identity, location, finances, contacts, or legal data.

Do not use when:
- The ask is ordinary, low-risk, and the reason is obvious.

Default recommendation:
- Put the explanation next to the ask and offer inclusive/optional choices when feasible.

Ask the user when:
- The business/legal reason or optionality is unclear.

Question prompt:
```js
question({
  question: "What will this data be used for, and is it required?",
  recommended_default: "Explain the use in plain language and give users a safe option when possible.",
  options: ["Required for compliance", "Required for service", "Optional", "Unknown", "Other / custom"]
})
```

Agent behavior:
- Flag unexplained sensitive asks as blocking issues.

## Principle: Useful states move the user forward

Rule:
- Empty, loading, success, and notification states should orient the user and support a next step.

Why it matters:
- Transitional states are not filler; they teach, reassure, and recover.

Use when:
- Writing empty states, confirmations, progress, status, toasts, banners, notifications, or onboarding.

Do not use when:
- A state is momentary and the UI itself clearly communicates status.

Default recommendation:
- What happened/what is missing + why it matters + next action when useful.

Ask the user when:
- The next action or consequence is unknown.

Question prompt:
```js
question({
  question: "What should users do next from this state?",
  recommended_default: "Provide the most useful next action; if none exists, explain the state and give a path back.",
  options: ["Create/add", "Retry/fix", "Wait/check later", "Learn more/contact support", "Other / custom"]
})
```

Agent behavior:
- Never leave an empty or failure state as a dead end.

## Principle: Voice follows product principles

Rule:
- Define voice through product principles, vocabulary, verbosity, grammar, punctuation, and tone shifts.

Why it matters:
- Voice helps consistency only when it guides decisions; otherwise it becomes subjective style debate.

Use when:
- Creating brand voice, design-system content guidance, or copy across multiple screens.

Do not use when:
- One-off functional copy has no brand context and default warm/direct tone is sufficient.

Default recommendation:
- Professional, warm, direct, and human.

Ask the user when:
- Existing brand voice or audience expectations should override the default.

Question prompt:
```js
question({
  question: "What personality should this product communicate in UI copy?",
  recommended_default: "Professional, warm, direct, and human.",
  options: ["Professional and warm", "Plain and utilitarian", "Playful and energetic", "Premium and polished", "Other / custom"]
})
```

Agent behavior:
- Create reusable rules and examples rather than subjective tone adjectives only.

## Principle: Clarity beats cleverness

Rule:
- Edit for purpose, concision, conversational flow, and clarity; do not sacrifice meaning for shortness or personality.

Why it matters:
- Users scan interface text and need immediate recognition.

Use when:
- Rewriting any UX copy.

Do not use when:
- Brand campaigns or long-form creative copy are the actual task.

Default recommendation:
- Clear/default version first; warmer or shorter variants second.

Ask the user when:
- A strict character limit would change meaning.

Question prompt:
```js
question({
  question: "Is there a hard character limit or layout constraint for this copy?",
  recommended_default: "Prioritize clarity, then shorten; allow wrapping or component changes if meaning would be lost.",
  options: ["No hard limit", "Small button/nav limit", "Mobile constrained", "Strict system limit", "Other / custom"]
})
```

Agent behavior:
- Provide multiple variants only after giving a recommended default.

## Principle: Test and measure high-impact copy

Rule:
- Validate copy that affects activation, conversion, recovery, trust, comprehension, accessibility, or support volume.

Why it matters:
- Teams often debate wording subjectively; testing reveals whether users understand and act.

Use when:
- The copy is high-traffic, high-risk, or tied to measurable product behavior.

Do not use when:
- The change is small, low-risk, and follows established patterns.

Default recommendation:
- Use comprehension/task testing first; use A/B testing for measurable behavior when traffic and ethics allow.

Ask the user when:
- Success metric or guardrail is unclear.

Question prompt:
```js
question({
  question: "What success metric and guardrail should this copy optimize for?",
  recommended_default: "Use task completion and comprehension first, with conversion as secondary only when aligned with user benefit.",
  options: ["Task completion", "Comprehension", "Error recovery/support reduction", "Conversion with guardrail", "Other / custom"]
})
```

Agent behavior:
- Recommend a test plan and guardrails for important copy changes.

## Principle: Make copy system-ready

Rule:
- Deliver copy with states, components, accessibility behavior, terminology, and localization context.

Why it matters:
- Good wording can fail when implemented without labels, live regions, truncation behavior, or translation support.

Use when:
- The user asks for frontend, design-system, component, or implementation work.

Do not use when:
- The user only needs exploratory copy ideas.

Default recommendation:
- Provide component/state mapping and accessibility notes.

Ask the user when:
- Existing component constraints are unknown.

Question prompt:
```js
question({
  question: "What frontend or design-system constraints should the copy fit?",
  recommended_default: "Provide copy by component state, with visible labels, error associations, status behavior, and localization notes.",
  options: ["Existing design-system component", "Custom component", "Mobile native UI", "No known constraints", "Other / custom"]
})
```

Agent behavior:
- Include implementation guidance whenever copy affects accessibility or component behavior.
