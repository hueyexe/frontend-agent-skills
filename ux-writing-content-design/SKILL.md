---
name: ux-writing-content-design
description: "Use when writing, critiquing, or implementing product UX copy, microcopy, labels, CTAs, empty states, onboarding, errors, or notifications."
---

# UX Writing & Content Design

## Purpose

Help an AI agent write and evaluate product copy that helps people understand an interface, take action, recover from problems, and trust the product. Treat words as part of the design system and interaction model, not as decoration added after the interface is finished.

This skill covers product UX copy: microcopy, button labels, links, labels, hints, descriptions, empty states, onboarding, validation, errors, success messages, loading/progress states, notifications, terminology, voice, tone, and content strategy. It does not cover long-form marketing copy except when that copy directly affects product comprehension, action, trust, onboarding, or conversion inside a product experience.

## When to use this skill

Use this skill when the user asks you to:

- Write, rewrite, or critique UI text, product copy, UX copy, microcopy, form copy, navigation labels, CTAs, onboarding, empty states, errors, confirmations, loading states, notifications, help text, or design-system content guidance.
- Review a UI, mockup, screenshot, frontend component, flow, prototype, or design system for clarity, tone, usability, trust, recovery, or accessibility.
- Design or implement frontend states where copy affects user understanding or behavior.
- Create content rules, voice and tone guidance, terminology, content patterns, or a UX writing checklist.

## When not to use this skill

Do not use this skill as the primary skill for:

- Long-form marketing pages, ads, brand campaigns, PR, SEO articles, or sales copy unless they affect an in-product UX flow.
- Pure visual styling, layout, illustration, or animation tasks where no interface text, state, or comprehension issue is involved.
- Legal, medical, financial, or compliance wording that requires a licensed professional. You may improve clarity, but flag the need for expert review.
- Translation/localization itself. Use this skill to make source copy localizable and context-safe, then use translation/localization expertise separately.

## Core principles

1. **Words are design material.** Do not merely choose “nice words.” Use words to solve user problems and shape interaction behavior.
2. **Start with the user task and product purpose.** Copy is effective only when it supports what the user is trying to do and what the product legitimately needs.
3. **Prefer useful over clever.** Personality and delight are secondary to comprehension, action, trust, and recovery.
4. **Design the conversation, not isolated strings.** Inspect the entry point, action, system response, next step, inverse action, and failure path.
5. **Use the right pattern for the state.** A label, hint, tooltip, inline error, banner, empty state, notification, or confirmation each has a different job.
6. **Write in context.** Draft and evaluate text where it appears, with surrounding UI, component constraints, state, platform, and device.
7. **Make actions consequence-revealing.** Buttons and links should say what happens, not describe the input method.
8. **Errors are stress cases.** Avoid the error when possible, explain clearly when it happens, and help the user resolve it.
9. **Respect people on the margins.** Sensitive questions, forced choices, default suggestions, and “harmless” quick replies can exclude or hurt people.
10. **Be concise, not cryptic.** Short copy is valuable only when users can still understand it immediately.
11. **Measure when the stakes justify it.** Use usability testing, behavioral metrics, support data, and A/B tests when copy changes affect activation, conversion, retention, recovery, or trust.
12. **Make copy implementable.** Content should work with semantic HTML, accessibility APIs, localization, design tokens, component states, and design-system patterns.

## Default recommendations

Use these defaults unless the user provides stronger product-specific context.

| Area | Default recommendation | Why it is usually best | Override when | Ask before overriding |
|---|---|---|---|---|
| Product goal | Help the user complete the immediate task with minimal uncertainty. | Most product copy is functional and users are not there to read. | The flow intentionally teaches, warns, or changes a high-stakes decision. | Ask what outcome matters most: comprehension, conversion, completion, retention, safety, or support reduction. |
| Audience | Write for a broad, busy, mixed-ability audience using plain language. | It reduces cognitive load and improves accessibility/localization. | The product serves a specialized expert audience with necessary domain terms. | Ask whether the audience expects domain-specific terminology. |
| Voice | Professional, warm, direct, and human. | Works for most SaaS, productivity, commerce, and public-service products. | A documented brand voice or regulated tone exists. | Ask for the brand personality or voice chart. |
| Tone | Calm and helpful. Match emotional stakes. | Users often encounter copy during uncertainty or interruption. | Success/delight states can support more warmth; severe or sensitive states require restraint. | Ask how stressful or sensitive the moment is. |
| CTA labels | Verb-led, specific, 1–3 words where possible; include object or consequence when needed. | Users make decisions at buttons and links. | Legal, destructive, paid, or irreversible actions need more specificity. | Ask what exactly happens after the action. |
| Form labels | Persistent visible labels above or beside fields; hints only for extra guidance. | Labels remain available after entry and support accessibility. | Very constrained UI already has a tested accessible pattern. | Ask about platform/component constraints. |
| Placeholder text | Use only for examples or formatting, never as the only label. | Placeholders disappear, can be low contrast, and are weak accessibility support. | A design system provides accessible floating labels. | Ask whether the component has accessible labels and error associations. |
| Help/instruction copy | Put guidance near the action only when the label alone is insufficient. | Extra text can help, but unnecessary instruction creates reading burden. | The task is unfamiliar, high-risk, or constrained by policy/format. | Ask what users commonly misunderstand. |
| Sensitive data requests | Explain why the data is needed and how it will be used. | Context improves trust and reduces harm for users who do not fit simple categories. | The reason is obvious and the data is not sensitive. | Ask why the product needs the information and whether users can skip it. |
| Error handling | Avoid first, explain second, resolve third. | Prevention reduces friction; recovery copy must still help when prevention fails. | A backend or legal constraint prevents prevention. | Ask what recovery actions are technically available. |
| Disabled controls | Do not rely on disabled UI as the only instruction. | Disabled controls can be inaccessible and leave users stuck. | Progressive activation is supplemented with accessible status/help. | Ask whether the disabled control has an accessible explanation. |
| Empty states | State what is empty, why it matters, and the next useful action. | Empty states are onboarding and recovery opportunities. | The absence is self-evident and no action is available. | Ask what the user can do next. |
| Success messages | Confirm what happened and, when useful, the next step or consequence. | Users need closure and sometimes need to know visibility, delivery, or reversibility. | The UI state itself clearly shows completion. | Ask whether success changes visibility, billing, permissions, or data. |
| Loading/progress | Say what is happening and set expectation if delay is noticeable. | Feedback reduces anxiety during wait states. | The delay is imperceptible. | Ask whether duration is known or variable. |
| Notifications | Send only timely, relevant, actionable messages. | Notifications interrupt; value must exceed interruption cost. | Compliance or operational needs require non-actionable notice. | Ask what user action or decision the notification supports. |
| Delight | Add personality only after the copy is functional, useful, and emotionally appropriate. | Humor can help in success or low-stress moments and harm in error/stress moments. | Brand voice is intentionally playful and the state is safe. | Ask whether the moment is stressful, sensitive, or irreversible. |
| Metrics | Use task success and comprehension first; use conversion only when aligned with user benefit. | Copy should not manipulate users away from their goals. | The business goal is the explicit optimization target. | Ask which metric and guardrail metric matter. |
| Accessibility level | Meet WCAG-aligned product basics: labels, programmatic errors, focus, keyboard, screen-reader states, readable text. | Accessibility is usability and exclusion is a design choice. | Higher conformance is required by policy. | Ask about required accessibility standard if compliance matters. |
| Localization | Avoid idioms, culture-specific jokes, compact strings that cannot expand, and ambiguous variables. | Product copy often becomes UI strings; localization can break layout and meaning. | Product is single-locale and will remain so. | Ask whether the product will be translated. |

## Required user questions

Do not ask routine best-practice questions such as whether text should be clear, concise, or accessible. Apply the defaults.

Ask only when the answer materially changes the copy, pattern, tone, or implementation. Ask one focused question at a time unless the user explicitly asks for a full discovery pass.

Ask when any of these are missing and necessary:

- The **primary user task** or feature outcome is unclear.
- The **audience** is specialized, vulnerable, multilingual, very young/old, regulated, or otherwise context-dependent.
- The flow asks for **sensitive personal data**, legal consent, payment, health, identity, security, or irreversible action.
- The requested tone conflicts with user stress, inclusion, accessibility, or trust.
- The copy depends on a **technical constraint**, backend validation, recovery path, design-system pattern, or localization requirement.
- The user asks to optimize for a metric, but the metric or guardrail is unclear.
- A decision requires legal/compliance approval.

Default question pattern:

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

## Workflow

### A. Critique existing UI copy

Inspect in this order:

1. **Task fit:** What is the user trying to do? Does the copy help that task or distract from it?
2. **User/business alignment:** Does the copy serve a legitimate product goal without forcing, hiding, or manipulating?
3. **Conversation flow:** Entry point → instruction → action → feedback → next step → inverse action → failure path.
4. **Pattern choice:** Is each string using the right component/state: label, hint, CTA, tooltip, inline validation, banner, modal, empty state, confirmation, notification?
5. **Action clarity:** Do buttons and links name the outcome?
6. **Comprehension:** Is the copy plain, specific, scannable, and free of unnecessary jargon?
7. **Stress and recovery:** Do errors avoid blame, explain the issue, and offer a realistic next step?
8. **Trust and inclusion:** Are sensitive asks explained? Are choices inclusive? Are defaults and suggestions safe?
9. **Voice and consistency:** Does wording follow product principles, terminology, grammar, capitalization, and tone?
10. **Accessibility and frontend feasibility:** Are labels, descriptions, errors, status updates, focus behavior, and localization implementable?
11. **Measurement:** If stakes are high, identify how to test or measure whether the copy works.

When reporting a critique, group findings by severity:

- **Blocking:** prevents comprehension, action, accessibility, trust, or recovery.
- **Important:** increases cognitive load, uncertainty, or inconsistency.
- **Polish:** improves tone, flow, or delight after core usability is fixed.

For each issue, provide: current problem, better copy or pattern, reason, and any implementation note.

### B. Create or improve new UX copy

Proceed in this order:

1. **Clarify the product moment.** Identify user, task, state, platform, constraints, and success criteria. Ask only if missing context changes the recommendation.
2. **Map the conversation.** What does the user know now? What do they need to know? What action can they take? What does the system do next?
3. **Select the pattern.** Decide whether the copy belongs in a title, label, hint, body text, CTA, inline validation, banner, modal, empty state, toast, notification, loading message, or help entry.
4. **Draft useful copy first.** Make the copy accurate, task-focused, and outcome-specific before making it shorter or more branded.
5. **Edit in four passes.**
   - Purposeful: Does it serve the user and product goal?
   - Concise: Can anything be removed without losing meaning?
   - Conversational: Does it sound like a human interaction, not a system log?
   - Clear: Would the intended user understand it immediately?
6. **Handle edge and stress states.** Include empty, loading, success, validation, failure, permission, offline, destructive, and undo/retry states as relevant.
7. **Make it implementable.** Provide component/state mapping, semantic labels, error associations, ARIA live-region guidance where needed, string tokens if useful, and localization notes.
8. **Test or validate.** Recommend usability test prompts, comprehension checks, support-data review, or A/B tests when stakes justify it.
9. **Explain decisions.** Tie recommendations to task completion, comprehension, trust, recovery, accessibility, and product goals.

## Decision framework

Use this framework to choose the content pattern:

| User need | Prefer this pattern | Default content structure |
|---|---|---|
| Know where they are | Page title / section heading | Object or task name; avoid generic “Details” when specificity matters. |
| Know what a field is | Visible label | Noun phrase: “Work email,” “Deposit amount.” |
| Know format or constraint | Hint / helper text | Constraint or example: “Use 8–64 characters.” |
| Decide what happens | Button / link | Verb + object/consequence: “Create post,” “Pay $24,” “Download report.” |
| Understand a sensitive ask | Contextual explanation | Why needed + how used + whether optional. |
| Know something is happening | Loading/progress | Current operation + duration/expectation if known. |
| Know action succeeded | Confirmation/toast | What happened + important consequence + next step if useful. |
| Know nothing is here yet | Empty state | What is empty + why/when + next action. |
| Recover from a problem | Inline error or error page | What happened + why if useful + how to fix/retry/escape. |
| Learn without blocking | Inline help / documentation link | Short in-context guidance + link to deeper help. |
| Respond to timely change | Notification | Timely reason + user benefit + clear action or dismissal. |
| Prevent harm | Confirmation dialog / interstitial | Consequence + irreversible scope + safe cancel + specific confirm action. |

## Practical rules

### Buttons and links

- Use the action outcome, not the interaction method. Prefer “Download report,” “Create post,” or “View pricing” over “Click here,” “Submit,” or vague “Save” when the object/action matters.
- Put the most important consequence in the label for payment, deletion, sending, publishing, sharing, permissions, and irreversible actions.
- Make primary and secondary actions meaningfully different. Avoid pairs like “OK / Cancel” when users need consequence clarity.
- Use “Back,” “Cancel,” “Undo,” “Remove,” and “Delete” carefully; they imply different reversibility.

### Forms

- Use persistent labels for every input. Do not rely on placeholders as labels.
- Use helper text for unusual constraints, examples, privacy concerns, or why the information is needed.
- Put errors near the field and summarize at the top only when the form is long or submission failed.
- Use examples that match required formatting, but avoid examples that look like actual saved data.
- Prefer progressive disclosure over long instructions, but do not hide information required to complete the task.

### Sensitive questions and personal data

- Before asking for identity, demographics, health, finance, location, contacts, or legal information, explain the reason in plain language.
- Do not force binary, overly narrow, or culturally specific categories unless legally required.
- Offer “Prefer not to say,” “Self-describe,” “Not listed,” or skip options when appropriate and feasible.
- Never use playful tone to soften surveillance, coercion, or a data grab.

### Errors and validation

Use **Avoid → Explain → Resolve**.

1. **Avoid:** Prevent errors through clear labels, constraints, input masks, examples, progressive validation, and better interaction design.
2. **Explain:** State what went wrong in human language. Avoid raw error codes, stack traces, or blame.
3. **Resolve:** Tell the user what to do next: fix, retry, undo, contact support, use an alternative path, or wait.

Error message structure:

```text
[Problem in user terms]. [Specific fix or next step].
```

Examples of structures, not fixed copy:

- “Enter a valid email address.”
- “Your file is too large. Upload a file under 10 MB.”
- “We couldn’t save your changes. Check your connection and try again.”

For high-stress, legal, financial, medical, identity, security, or destructive states, use calm, explicit, non-humorous copy.

### Empty states

Use empty states to orient and move the user forward.

Default structure:

```text
Title: No [objects] yet
Description: [What will appear here or why it matters]
Action: [Next useful action]
```

Do not turn every empty state into a marketing pitch. If there is no useful next action, explain the state and provide a path back.

### Loading and progress states

- If a wait is noticeable, tell users what is happening.
- If duration is predictable, set expectation.
- If the process may fail, prepare recovery paths.
- Use brand personality sparingly; never let playful loading copy hide risk, cost, or uncertainty.

### Success and confirmation

- Confirm the completed action in specific terms.
- Include important consequences: publication, visibility, payment, delivery, permissions, data changes, or email sent.
- Add next steps only when they help the current task.
- Avoid celebratory tone for sensitive successes.

### Notifications

- Send fewer, better notifications.
- Make them timely, relevant, and actionable.
- Avoid vague engagement bait.
- Use the user’s language and current context.
- Provide controls for frequency and opt-out when appropriate.

### Voice and tone

Build voice from product principles, not from adjectives alone.

Define:

- **Concepts:** what the product should consistently emphasize.
- **Vocabulary:** preferred and avoided terms.
- **Verbosity:** how much explanation is appropriate by state.
- **Grammar:** sentence structure, point of view, contractions, tense.
- **Punctuation and capitalization:** consistent mechanics.
- **Tone shifts:** how the voice changes in success, error, legal, privacy, onboarding, and high-stress moments.

When no voice is supplied, use a professional, warm, direct voice.

### Editing

Use the four-pass edit:

1. Purposeful
2. Concise
3. Conversational
4. Clear

Do not start by shortening. First confirm that the copy solves the right problem. Then shorten without removing necessary meaning.

## Accessibility and inclusion requirements

- Use visible labels and programmatic labels for inputs.
- Associate helper text and errors with fields using accessible descriptions.
- Do not rely on color, icon, position, or animation alone to communicate status.
- Ensure error, success, and loading updates are announced appropriately for assistive technologies.
- Preserve focus and keyboard access through dialogs, errors, and state changes.
- Avoid disabled controls as the only instruction. If a control is disabled, explain why and how to enable it in accessible text.
- Use readable plain language, short sentences, and familiar terms.
- Avoid idioms, jokes, metaphors, and culture-specific references in functional copy unless tested for the audience.
- Provide inclusive options for identity-related questions and explain why the information is needed.
- Consider emotional context: people may be stressed, grieving, sick, locked out, financially worried, or under time pressure.
- Support localization with string expansion, variables that can move, pluralization, and context notes for translators.

## Frontend implementation guidance

When giving frontend recommendations, include copy as part of component behavior.

### Semantic HTML and ARIA

- Use real `<label>` elements connected to inputs.
- Use `<button>` for actions and `<a>` for navigation.
- Use headings that reflect information hierarchy.
- Use `aria-describedby` to connect helper and error text to fields.
- Use `aria-invalid="true"` when validation fails.
- Use `role="alert"` or an appropriate live region for urgent validation/status updates, but avoid excessive announcements.
- Manage focus after modal opens, form submission fails, route changes, and destructive confirmations.
- Do not remove focus outlines.

### Component/state structure

Document copy for each relevant state:

- default
- hover/focus where text changes, if any
- loading
- empty
- partial
- success
- warning
- error
- offline
- permission denied
- disabled
- destructive confirmation
- undo/retry

### Design-system integration

- Name reusable content patterns, not only individual strings.
- Store preferred terms and forbidden terms.
- Provide examples for labels, CTA labels, helper text, errors, empty states, loading, confirmations, and notifications.
- Use content tokens or string IDs when implementation requires reuse, but avoid abstract IDs that hide context.
- Keep source strings localizable. Avoid concatenating sentence fragments in code.

### Responsive and localization considerations

- Expect copy expansion in translation.
- Avoid layouts that only work for very short English strings.
- Do not encode meaning solely in line breaks.
- Test truncation behavior for CTAs, tabs, nav, toasts, and table headers.
- Provide translator comments for variables, tone, and context.

## Quality checklist

Before finalizing UX copy, verify:

- The user’s primary task is clear.
- Each string has a job: orient, instruct, motivate, confirm, warn, recover, or explain.
- The copy does not compensate for a broken interaction that should be redesigned.
- Buttons and links describe outcomes.
- Forms have visible labels and helpful constraints.
- Sensitive asks explain why the data is needed.
- Errors state the problem and the next step without blame.
- Empty states include a useful next action when one exists.
- Success states confirm important consequences.
- Tone matches emotional stakes.
- Voice and terminology are consistent.
- Copy is concise but not cryptic.
- Accessibility states are implementable.
- Localization will not break the UI.
- High-impact copy has a validation or measurement plan.
- Recommendations include frontend notes when implementation matters.

## Common mistakes to avoid

- Treating UX writing as wordsmithing after the UI is done.
- Asking users “Should I make it clear?” instead of applying clarity by default.
- Using “Submit,” “Continue,” “OK,” or “Save” when the action consequence matters.
- Replacing visible labels with placeholder text.
- Explaining a broken UI instead of fixing the UI.
- Hiding manipulative business goals in friendly language.
- Using humor in errors, denial, payment failure, identity, legal, security, medical, or financial states.
- Asking sensitive demographic or personal questions without explaining why.
- Using technical error codes or backend terms in user-facing copy.
- Over-branding navigation, forms, instructions, and errors.
- Creating empty states that are dead ends.
- Sending notifications that do not help the user act.
- Writing strings that cannot be localized or announced by assistive technology.
- Delivering copy without states, constraints, or implementation context.

## How to explain recommendations to the user

Explain recommendations in terms of user impact, not personal taste.

Use this structure:

```text
I recommend [copy/pattern] because [user goal or risk]. It improves [comprehension/action/trust/recovery/accessibility]. Use [alternative] only if [context/constraint].
```

When giving multiple options, label them by purpose:

- **Clear/default**
- **Warmer**
- **More formal**
- **Higher-trust**
- **Shorter for constrained UI**
- **Accessible/error-safe**
- **Legal/compliance-safe pending review**

Avoid saying “this sounds better” without explaining the task, state, or user need.

