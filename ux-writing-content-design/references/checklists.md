# UX Writing & Content Design Checklists

## Discovery/context checklist

- The primary user task is known.
- The product outcome or business goal is known and does not conflict with user benefit.
- The audience and their likely vocabulary are known or safely defaulted to plain language.
- The platform/device context is known when wording depends on tap/click/voice/keyboard.
- The state of the UI is known: default, empty, loading, success, warning, error, disabled, offline, permission denied, destructive, or recovery.
- The surrounding UI is known, or the copy is clearly marked as draft pending in-context review.
- Sensitive data, legal/compliance, payment, identity, health, safety, or security implications are identified.
- Localization or multi-region needs are identified.
- Design-system and frontend constraints are identified when implementation is requested.
- Success metrics or validation approach are identified for high-impact flows.

## UX copy quality checklist

- Each string has a clear job: orient, instruct, motivate, confirm, warn, recover, explain, or invite action.
- The copy uses the user’s language rather than internal system language.
- The title or heading tells users where they are or what they can do.
- Labels are specific enough to stand on their own.
- Helper text explains only what the user needs at that moment.
- Button/link labels name the action outcome.
- Copy is concise without removing necessary meaning.
- Terms are consistent across screens and states.
- Voice is consistent, but tone adapts to the user’s emotional context.
- Brand personality never obscures comprehension or recovery.
- The copy does not manipulate users into actions unrelated to their task.
- The copy is readable when scanned quickly.
- The copy avoids idioms, puns, and metaphors in functional states unless tested.
- The copy can expand for localization without breaking the component.

## Button and action checklist

- The primary action is visually and verbally distinct from secondary actions.
- The label starts with a verb when an action is performed.
- The object or consequence is included when ambiguity or risk exists.
- Paid, destructive, sharing, sending, publishing, permission, or irreversible actions disclose consequence.
- Secondary actions are not shame-inducing or manipulative.
- “OK,” “Continue,” “Submit,” and “Save” are used only when context already makes the consequence unmistakable.
- Links navigate; buttons perform actions.
- The inverse action is clear: cancel, back, undo, remove, delete, dismiss, or close.

## Forms checklist

- Every input has a persistent visible label.
- Programmatic labels match visible labels.
- Helper text is connected to the field and appears before the user needs it.
- Placeholder text is not the only label.
- Format requirements are stated before submission when possible.
- Required/optional status is clear without relying only on asterisks.
- Sensitive questions explain why the information is needed.
- Inclusive options are provided for identity-related questions where feasible.
- Field-level errors appear near the relevant fields.
- Long forms include an error summary after failed submission.
- Validation timing does not interrupt typing unnecessarily.
- Disabled controls are explained accessibly, or an enabled path tells the user what to do.

## Error and stress-case checklist

- The experience first attempts to prevent the error.
- The error copy states what happened in user terms.
- The copy avoids blame and avoids technical codes unless support requires them.
- The user has a clear recovery action.
- The recovery action is technically possible.
- High-stress contexts use calm, plain, non-humorous tone.
- The error is announced to assistive technologies when appropriate.
- Focus moves to a helpful place after submission failure.
- The user can leave, cancel, retry, undo, or contact support when relevant.
- The system does not hide failure behind vague “Something went wrong” copy unless no better information is available.
- If no immediate fix exists, the copy explains what happens next.

## Empty, loading, and success-state checklist

- Empty state says what is empty.
- Empty state explains why it matters only if the reason is not obvious.
- Empty state provides the next useful action when available.
- Empty state does not become a generic marketing pitch.
- Loading state says what is happening when wait time is noticeable.
- Loading state sets time expectations when known.
- Progress messages do not mask serious uncertainty or risk with personality.
- Success message confirms what happened.
- Success message explains important consequences, such as visibility, delivery, payment, permission, or reversibility.
- Success message offers a next step only when it helps the task.

## Accessibility and inclusion checklist

- UI text is readable at expected zoom and font sizes.
- Text contrast and states meet accessibility requirements.
- Meaning is not conveyed by color, icon, location, or animation alone.
- Input labels, helper text, and errors are programmatically associated.
- Status changes use appropriate live-region behavior.
- Keyboard users can reach and operate all controls.
- Focus is visible and managed after modal, route, and error state changes.
- Copy is written in plain language with short sentences.
- Acronyms and domain terms are introduced or avoided.
- The copy avoids stereotyping, forced categories, or exclusionary defaults.
- Sensitive requests explain why the information is needed and how it will be used.
- Humor is avoided in errors and stressful moments.
- Copy remains understandable to people using screen readers, magnification, translation, or cognitive assistive strategies.

## Implementation feasibility checklist

- Copy is mapped to components and states.
- Strings are not concatenated in ways that break grammar or localization.
- Dynamic variables have examples and translator notes.
- Character limits are documented only as constraints, not as excuses for unclear copy.
- There are fallbacks for offline, timeout, permission denied, and unknown error states.
- Error codes are logged internally, not exposed as the primary user message.
- Content tokens/string IDs preserve context.
- Long labels have wrapping/truncation behavior.
- Design-system docs include copy guidance for the component.
- Tests cover key states and accessibility attributes.
- Product analytics, support logs, or usability testing can evaluate high-impact copy.

## Final response checklist for the agent

- The recommendation includes actual copy, not only advice.
- The recommendation explains why it helps the user.
- The recommendation calls out tradeoffs or assumptions.
- The recommendation identifies when user input or expert review is needed.
- The response avoids over-asking and applies safe defaults.
- The response includes accessibility and frontend notes when relevant.
- The response marks legal/compliance-sensitive text as needing review.
- The response separates required fixes from optional polish.
- The response does not include long copyrighted excerpts.
