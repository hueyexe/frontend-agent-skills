# UX Writing & Content Design Anti-patterns

## Anti-pattern: Wordsmithing after the design is finished

What it looks like:
- The UI is already decided, and the agent only swaps synonyms or “makes it friendlier.”

Why it fails:
- The wrong pattern, missing recovery path, or manipulative flow cannot be fixed by nicer wording alone.

Better approach:
- Inspect the user task, interaction flow, component state, and system behavior before drafting copy.

Ask the user when:
- It is unclear whether the UI can change or copy is the only allowed intervention.

## Anti-pattern: “Click here” / method-as-label

What it looks like:
- Buttons or links say “Click here,” “Tap here,” “Learn more” without context, or “Submit” when the outcome matters.

Why it fails:
- The label names the input method or generic action, not the outcome the user is choosing.

Better approach:
- Use verb + object/consequence, such as “View pricing,” “Create post,” or “Download report.”

Ask the user when:
- The action consequence is unclear or risky.

## Anti-pattern: Vague “Save” for a specific creation or publication action

What it looks like:
- A button says “Save” when it actually creates a post, publishes content, sends a message, starts a paid subscription, or changes visibility.

Why it fails:
- Users cannot predict the result or risk of the action.

Better approach:
- Name the specific outcome: “Create post,” “Publish profile,” “Send invite,” “Pay $24.”

Ask the user when:
- The action changes visibility, payment, data, permissions, or account state.

## Anti-pattern: Placeholder as the only label

What it looks like:
- The field only has faint placeholder text inside it.

Why it fails:
- Placeholder text disappears, may have low contrast, and is not a reliable accessible label.

Better approach:
- Use a persistent visible label, with placeholder only for examples or formatting.

Ask the user when:
- A design-system component uses floating labels or another custom accessible pattern.

## Anti-pattern: Error code as user message

What it looks like:
- “Error authenticating,” “Invalid request,” “ERR_403,” stack traces, or backend field names.

Why it fails:
- Users do not know what went wrong or how to recover.

Better approach:
- Explain the problem in user terms and give a specific next step.

Ask the user when:
- The system can return several causes or recovery paths.

## Anti-pattern: Blaming the user

What it looks like:
- “You entered the wrong password,” “You failed to complete the form,” “Invalid user input.”

Why it fails:
- Blame increases stress and does not improve recovery.

Better approach:
- Use neutral phrasing: what happened + how to fix it.

Ask the user when:
- The error may be caused by security, permissions, fraud, or policy and needs careful wording.

## Anti-pattern: Humorous error in a stressful moment

What it looks like:
- Jokes, puns, emojis, or playful blame in payment failure, identity, account lockout, medical, legal, or destructive states.

Why it fails:
- Humor can make users feel mocked or abandoned when they need help.

Better approach:
- Use calm, plain, supportive error copy; save delight for safe success or onboarding moments.

Ask the user when:
- The brand is strongly playful but the user moment may be high-stress.

## Anti-pattern: Disabled control as the only instruction

What it looks like:
- A “Next” button stays disabled until all requirements are met, but no text explains what is missing.

Why it fails:
- Users may not understand what to do; disabled controls can create accessibility problems.

Better approach:
- Pair progressive activation with accessible helper text or validation that states what is required.

Ask the user when:
- The component behavior or accessibility implementation is unknown.

## Anti-pattern: Forced opt-in disguised as UX copy

What it looks like:
- Friendly copy pushes a loyalty program, newsletter, or account creation when the user is trying to book, buy, or complete another task.

Why it fails:
- It serves the organization at the expense of the user and damages trust.

Better approach:
- Make optional benefits clear and skippable; keep the user’s primary task available.

Ask the user when:
- The business goal and user task appear to conflict.

## Anti-pattern: Sensitive question with no reason

What it looks like:
- The UI asks for gender, birthdate, identity, location, health, finance, or legal information without explaining why.

Why it fails:
- Users may not fit the available categories, may feel unsafe, or may provide lower-quality data.

Better approach:
- Explain why the information is needed, how it will be used, and whether it is optional; provide inclusive choices.

Ask the user when:
- The reason for collecting sensitive information is unclear.

## Anti-pattern: Over-branding functional copy

What it looks like:
- Navigation, forms, errors, legal text, or instructions are packed with jokes, slogans, or brand personality.

Why it fails:
- Brand voice can obscure the task and make the interface inconsistent or tiring.

Better approach:
- Express voice through controlled vocabulary, tone, and patterns; prioritize clarity in functional and stressful states.

Ask the user when:
- The user asks for “more personality” in a high-stakes or core task flow.

## Anti-pattern: Empty state as a dead end

What it looks like:
- “No results” or “Nothing here” with no explanation, action, or route forward.

Why it fails:
- The user is stranded and cannot continue.

Better approach:
- State what is empty and offer the next useful action, such as create, upload, adjust filters, or request access.

Ask the user when:
- The next useful action is unknown.

## Anti-pattern: Success message with no consequence

What it looks like:
- “Done” or “Success” after publishing, sending, paying, or changing permissions.

Why it fails:
- The user may need to know what changed, who can see it, whether it is reversible, or what happens next.

Better approach:
- Confirm the completed action and any important consequence.

Ask the user when:
- Success changes visibility, payment, delivery, permissions, or data.

## Anti-pattern: Too concise to understand

What it looks like:
- Short labels like “Go,” “Set,” “Apply,” “Manage,” “Fix,” or “More” without enough context.

Why it fails:
- Brevity increases cognitive load when users cannot infer the object or result.

Better approach:
- Add the object or consequence even if the label is slightly longer.

Ask the user when:
- Component width is severely constrained.

## Anti-pattern: Notification without user value

What it looks like:
- Pushes, banners, badges, or toasts that exist mainly to drive engagement rather than support timely user action.

Why it fails:
- Interruptions reduce trust unless they are relevant and actionable.

Better approach:
- Notify only when the user can use the information now; otherwise surface it in context.

Ask the user when:
- The action or urgency behind the notification is unclear.

## Anti-pattern: Inconsistent terminology

What it looks like:
- The same object is called “project,” “file,” “workspace,” and “item” across related states.

Why it fails:
- Inconsistency makes the product feel patched together and increases comprehension burden.

Better approach:
- Create preferred terms, avoid-list terms, and string patterns in the design system.

Ask the user when:
- Existing terminology or brand vocabulary is unknown.
