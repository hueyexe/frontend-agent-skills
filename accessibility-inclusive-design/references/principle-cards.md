# Principle Cards — accessibility-inclusive-design

These cards convert the source extraction into reusable rules for an AI agent. Use them when critiquing, generating, or implementing UI/UX/frontend work.

## Principle: Start with purpose before interface mechanics

Rule:
- Identify the user task and remove unnecessary interface complexity before choosing layout, components, or visual styling.

Why it matters:
- Clear purpose reduces cognitive load and makes accessibility, content, code, and visual decisions converge instead of compete.

Use when:
- Designing a new feature, critique, page, flow, navigation model, form, or design-system component.

Do not use when:
- The user asks for a narrowly scoped implementation detail and purpose is already obvious.

Default recommendation:
- Use the simplest pattern that lets the user complete the primary task with native controls and clear content.

Ask the user when:
- The primary task, audience, or business goal is genuinely unclear and materially changes the design.

Question prompt:
- `question({ question: "What is the primary task this interface must help users complete?", recommended_default: "Optimize for the most common successful completion path, because clear purpose improves accessibility and reduces unnecessary complexity.", options: ["Complete one primary transaction", "Find or compare information", "Configure/filter content", "Navigate between sections", "Other / custom"] })`

Agent behavior:
- Begin recommendations with task fit. Do not start by picking colors, layout chrome, or animations.

## Principle: Design for diversity without stereotyping

Rule:
- Assume users vary by ability, literacy, language, device, bandwidth, input method, environment, and preferences; do not design for a mythical average user or for one stereotyped disability profile.

Why it matters:
- A solution optimized for a narrow imagined user can exclude many real people, including the people it intended to help.

Use when:
- Audience assumptions influence typography, language, layout, media, device support, form fields, localization, or testing.

Do not use when:
- Making a universal best-practice recommendation that does not depend on audience specifics, such as using associated labels for inputs.

Default recommendation:
- Use broad inclusive defaults: semantic structure, readable text, keyboard support, flexible layout, clear language, and user-controlled alternatives.

Ask the user when:
- The product has a known specialized audience, assistive technology baseline, language/region, or regulated context.

Question prompt:
- `question({ question: "Do you have known audience, language, device, or assistive-technology requirements that should override broad inclusive defaults?", recommended_default: "Use broad web defaults that support keyboard users, screen reader users, low vision, cognitive load, mobile, zoom, and variable bandwidth.", options: ["Broad public audience", "Known enterprise/internal audience", "Known assistive technology requirements", "Known localization/RTL requirements", "Other / custom"] })`

Agent behavior:
- State which user groups benefit from a recommendation without claiming the recommendation is only for that group.

## Principle: Native HTML before ARIA or custom JavaScript

Rule:
- Use native elements that already provide semantics and behavior before recreating controls with `div`, `span`, JavaScript, and ARIA.

Why it matters:
- Native elements provide role, name, keyboard support, focus behavior, and platform accessibility with less code and fewer failure modes.

Use when:
- Designing buttons, links, forms, radio groups, checkboxes, select-like controls, disclosure controls, or navigation.

Do not use when:
- The required interaction has no native equivalent and a custom ARIA pattern is justified and fully implemented.

Default recommendation:
- Use `button` for actions, `a href` for navigation, `input`/`label`/`fieldset`/`legend` for forms, and native form submission as the baseline.

Ask the user when:
- They request a custom component that changes expected behavior or cannot be represented with native elements.

Question prompt:
- `question({ question: "Does this component need behavior that native HTML cannot provide?", recommended_default: "Use native HTML and style it, because it already includes reliable semantics and keyboard behavior.", options: ["Native HTML is sufficient", "Needs custom behavior", "Must match an existing design-system component", "Unsure / evaluate both", "Other / custom"] })`

Agent behavior:
- Flag custom controls as high risk. If custom is necessary, specify role, name, state, keyboard interactions, focus management, and tests.

## Principle: Progressive enhancement preserves access

Rule:
- Begin with meaningful content and working HTML; add CSS and JavaScript as enhancements that improve, not replace, the baseline.

Why it matters:
- Users may experience failed CSS, failed scripts, slow networks, blocked assets, old devices, assistive tech quirks, or disabled features.

Use when:
- Building pages, forms, filters, product lists, navigation, article content, media pages, and JavaScript-enhanced components.

Do not use when:
- The user is asking about a purely native platform component outside the web; still preserve equivalent fallback where possible.

Default recommendation:
- Ensure the main content and basic action work before JavaScript; scripts should preserve expected focus, URL, and keyboard behavior.

Ask the user when:
- The product is an app-like interface where server-rendered or no-JS fallback may have major architecture implications.

Question prompt:
- `question({ question: "What baseline experience must work if JavaScript, CSS, or network assets fail?", recommended_default: "Main content, navigation, and form submission should remain available wherever feasible, because failures and constrained environments are part of real use.", options: ["Content and navigation only", "Content, navigation, and form submission", "Full app requires JavaScript", "Internal tool with controlled environment", "Other / custom"] })`

Agent behavior:
- In code/spec output, describe the baseline first and the enhancement second.

## Principle: Structure is navigation

Rule:
- Use headings, landmarks, lists, labels, page titles, and source order to create a navigable information map.

Why it matters:
- Screen reader users, keyboard users, search engines, feed readers, browser tools, and users with cognitive load all depend on structure.

Use when:
- Reviewing pages, long-form content, dashboards, navigation, menus, articles, product lists, and forms.

Do not use when:
- The content is a tiny isolated component with no document context; still specify component name/role.

Default recommendation:
- One meaningful page title, one main region, a clear h1, logical heading levels, labeled navigation landmarks, and source order matching reading order.

Ask the user when:
- Multiple navigation systems, nested app regions, or long pages require a custom information architecture.

Question prompt:
- `question({ question: "Which navigation regions or page sections are essential for this experience?", recommended_default: "Use one primary site navigation and one main content region; add labeled secondary navigation only when it helps orientation.", options: ["Primary navigation only", "Primary + in-page table of contents", "Primary + secondary/product navigation", "App shell with multiple regions", "Other / custom"] })`

Agent behavior:
- In critiques, list structural issues before color or polish issues.

## Principle: Visible and programmatic states must match

Rule:
- If a state is visible, it must also be represented programmatically; if a state is programmatic, it must be visible or otherwise perceivable when relevant.

Why it matters:
- Selected, current, expanded, collapsed, invalid, loading, and disabled states are essential for orientation and operation.

Use when:
- Designing tabs/toggles, menus, accordions, filters, current navigation, form errors, loading indicators, or validation.

Do not use when:
- The state is purely decorative and communicates no user-relevant information.

Default recommendation:
- Tie styling to semantic state attributes where possible, such as `[aria-expanded]`, `[aria-invalid]`, `[aria-pressed]`, or native checked/current states.

Ask the user when:
- A visible state has product-specific meaning that is not obvious.

Question prompt:
- `question({ question: "What does this state mean to the user, and what action should it enable next?", recommended_default: "Expose the state visibly and programmatically, because assistive technologies need the same operational information sighted users receive.", options: ["Current location", "Selected filter/view", "Expanded/collapsed content", "Validation/error state", "Other / custom"] })`

Agent behavior:
- Do not accept color-only or image-only state. Specify text/icon/shape plus semantic state.

## Principle: Keyboard access is a first-class interaction mode

Rule:
- Every interactive element must be reachable, operable, visible when focused, and escapable using the keyboard.

Why it matters:
- Keyboard access supports blind users, motor-impaired users, power users, temporary constraints, switch devices, voice systems, and broken pointer scenarios.

Use when:
- Any interaction exists.

Do not use when:
- The artifact is non-interactive content only; still ensure structural navigation.

Default recommendation:
- Source order determines tab order; visible focus is required; use `tabindex="-1"` only for scripted focus targets; avoid positive `tabindex`.

Ask the user when:
- A custom interaction requires non-standard key bindings or a focus trap.

Question prompt:
- `question({ question: "Does this custom interaction require a non-standard keyboard model or focus trap?", recommended_default: "Avoid traps and use expected native keyboard behavior unless the component is a modal/dialog or composite widget that requires it.", options: ["No custom keyboard model", "Modal/dialog needs contained focus", "Composite widget needs arrow-key model", "Unsure / use simpler native pattern", "Other / custom"] })`

Agent behavior:
- Always include keyboard test steps for interactive recommendations.

## Principle: Persistent labels beat placeholder hints

Rule:
- Every form input must have a persistent, associated label; placeholder text may only supplement the label.

Why it matters:
- Placeholders disappear on focus or autofill, may have poor contrast, and may not be announced consistently by assistive technologies.

Use when:
- Designing forms, search fields, login/signup, filters, checkout, settings, or onboarding.

Do not use when:
- The control’s accessible name is provided by another standard visible mechanism, such as button text.

Default recommendation:
- Use visible `<label for>` text for each input and reserve placeholders for examples or format hints.

Ask the user when:
- Space constraints are severe and the user requests label-free designs.

Question prompt:
- `question({ question: "Is there a strict space constraint preventing persistent visible labels?", recommended_default: "Keep persistent labels, because disappearing placeholder labels create cognitive and assistive-technology barriers.", options: ["No, keep visible labels", "Yes, use compact persistent labels", "Use floating labels with testing", "Icon-only field with explicit accessible name", "Other / custom"] })`

Agent behavior:
- Refuse placeholder-only form designs as an accessibility failure; offer compact alternatives.

## Principle: Error recovery is part of form design

Rule:
- Design validation to help users recover, not to punish or disorient them.

Why it matters:
- Error feedback can create cognitive stress, screen reader noise, focus loss, and task abandonment.

Use when:
- Any user input is validated.

Do not use when:
- Input is not user-editable; then errors should be system status messages instead.

Default recommendation:
- Validate on submit first; show a clear error notice near the submit action; mark invalid fields; attach specific repair instructions; debounce live updates after the user begins fixing.

Ask the user when:
- Validation timing affects security, cost, or data integrity.

Question prompt:
- `question({ question: "When should this form validate user input?", recommended_default: "Validate on submit first, then provide supportive inline feedback while users correct errors, because this avoids noisy premature errors.", options: ["On submit first", "On blur for each field", "After debounced typing", "Immediate validation for high-risk fields", "Other / custom"] })`

Agent behavior:
- Specify both global error feedback and field-level repair text.

## Principle: User control over dynamic content

Rule:
- Interfaces that change content, play media, load more results, animate, or reorganize layout should preserve user control and orientation.

Why it matters:
- Automatic changes can interrupt screen readers, displace focus, confuse keyboard users, trigger motion sensitivity, or make content unreachable.

Use when:
- Filters, sorting, infinite scroll, async loading, carousels, alerts, media, menu disclosures, or live validation are involved.

Do not use when:
- Changes are purely local and expected, such as selecting a native radio button.

Default recommendation:
- Prefer explicit actions such as “Apply” and “Load more”; announce loading and completion; move focus to new content when the trigger is displaced.

Ask the user when:
- The product wants auto-updating content, infinite scroll, autoplay, or animation.

Question prompt:
- `question({ question: "Should content update automatically, or should users explicitly trigger the update?", recommended_default: "Use an explicit user-triggered action with loading feedback, because it preserves control and orientation for keyboard and screen reader users.", options: ["Explicit Apply/Load more action", "Auto-update after selection", "Auto-update only for pointer users", "Continuous auto-update with accessible controls", "Other / custom"] })`

Agent behavior:
- Treat infinite scroll and autoplay as high-risk patterns requiring justification and accessible alternatives.

## Principle: Readability is an accessibility requirement

Rule:
- Text, typography, spacing, contrast, headings, and labels must support comprehension before brand expression.

Why it matters:
- Readability affects low vision, dyslexia, cognitive load, language learners, older users, distracted users, and everyone reading under stress.

Use when:
- Writing UI copy, form labels, headings, error messages, article content, navigation labels, or choosing type/design tokens.

Do not use when:
- A purely decorative brand asset has no informational role; still avoid interference with task content.

Default recommendation:
- Use short direct language, descriptive headings/links, comfortable line length, relative units, unitless line-height, sufficient contrast, and non-color-only link/state cues.

Ask the user when:
- Brand voice or specialized terminology may conflict with clarity.

Question prompt:
- `question({ question: "How much brand personality should task-critical labels and messages carry?", recommended_default: "Professional, direct, and warm, with brand personality secondary to clarity, because users need to understand actions and errors quickly.", options: ["Plain and direct", "Professional but warm", "Playful but clear", "Use established brand voice", "Other / custom"] })`

Agent behavior:
- Rewrite vague headings, links, buttons, and error text into context-independent alternatives.

## Principle: Media needs equivalent channels

Rule:
- Do not make meaning available through only one sensory channel.

Why it matters:
- Images, color, sound, video, diagrams, and icons may be unavailable to users due to disability, device, bandwidth, context, or preference.

Use when:
- Any image, icon, chart, audio, video, animation, infographic, product image, or media player appears.

Do not use when:
- The asset is purely decorative; then hide it from assistive technology with empty alt or equivalent.

Default recommendation:
- Provide purposeful alt text for informative images, empty alt for decorative images, captions and transcripts for video/audio, and redundant cues beyond color or sound.

Ask the user when:
- The meaning of an image/media asset depends on product context or intent.

Question prompt:
- `question({ question: "What is the purpose of this image or media in the user task?", recommended_default: "Describe the information or action it supports; if it is decorative, hide it from assistive technology.", options: ["Decorative only", "Illustrates content", "Conveys data/instructions", "Acts as a link/control", "Other / custom"] })`

Agent behavior:
- Generate alt/caption guidance based on purpose, not visual detail alone.

## Principle: Familiar wayfinding reduces cognitive work

Rule:
- Use recognizable navigation, current-location cues, and consistent labels/placement.

Why it matters:
- Familiar patterns let users rely on learned expectations; unconventional patterns impose extra cognitive work and increase errors.

Use when:
- Designing navigation bars, breadcrumbs, tables of contents, menu buttons, search/filter navigation, or page layout.

Do not use when:
- A highly specialized tool has trained expert users and documented shortcuts; still provide clear orientation.

Default recommendation:
- Use list-based nav in a labeled landmark, familiar placement, clear page title/h1, current-location cue beyond color, and table of contents for long pages.

Ask the user when:
- Navigation depth or IA is unclear.

Question prompt:
- `question({ question: "What navigation depth does this product need?", recommended_default: "Use a simple primary navigation and add in-page navigation only for long or dense content.", options: ["Single page / no global nav", "Simple primary nav", "Primary nav + breadcrumbs", "Primary nav + in-page table of contents", "Other / custom"] })`

Agent behavior:
- Prefer simpler navigation structures over fragile dropdowns when both can solve the problem.

## Principle: Inclusive layout tolerates real content

Rule:
- Layout must tolerate zoom, text resizing, long labels, localization, different reading directions, slow assets, dynamic content, and missing CSS/JS.

Why it matters:
- Static mockups with ideal content hide failures that appear when real people, content, devices, and settings meet the interface.

Use when:
- Designing responsive pages, grids, cards, product lists, forms, dashboards, navigation, or design-system components.

Do not use when:
- The deliverable is a static conceptual sketch; still note required later validation.

Default recommendation:
- Use flexible containers, content breakpoints, relative units, wrapping, realistic content, and edge-case test strings.

Ask the user when:
- Localization, RTL, data variability, or platform constraints are known but unspecified.

Question prompt:
- `question({ question: "What content variability should this layout tolerate?", recommended_default: "Test long labels, translated text, variable item counts, zoom, and narrow/wide viewports, because idealized content hides accessibility failures.", options: ["Standard English-only content", "Long/variable user-generated content", "Localization/translation expected", "RTL language support needed", "Other / custom"] })`

Agent behavior:
- In generation, include edge-case tests such as long names, long product titles, missing images, empty states, and zoom.

## Principle: Pattern-level accessibility scales better than one-off fixes

Rule:
- Fix accessibility at the reusable component/pattern level and document its required structure, behavior, and tests.

Why it matters:
- Design systems spread both good and bad accessibility. Pattern-level fixes prevent repeated defects.

Use when:
- Auditing product UIs, design systems, component libraries, templates, or repeated flows.

Do not use when:
- A one-off content page has no reusable component; still fix the page.

Default recommendation:
- Group issues by component pattern, then define acceptance criteria: markup, name/role/state, keyboard behavior, focus management, content rules, visual states, and tests.

Ask the user when:
- The agent needs to know whether to recommend one-off patching or design-system remediation.

Question prompt:
- `question({ question: "Should this be fixed as a one-off screen issue or as a reusable design-system pattern?", recommended_default: "Fix the reusable pattern when it appears in multiple places, because that prevents repeated accessibility defects.", options: ["One-off screen fix", "Reusable component fix", "Template-level fix", "Design-system governance change", "Other / custom"] })`

Agent behavior:
- In audits, classify each issue as instance-level, component-level, template-level, or process-level.

## Principle: Testing must combine tools, people, and scenarios

Rule:
- Automated accessibility checks are necessary but insufficient; combine them with manual keyboard, screen reader, device/browser, zoom, content, and user testing.

Why it matters:
- Many failures are technically valid but practically confusing, unsupported, or disorienting.

Use when:
- Finalizing designs, code, design-system components, accessibility audits, release readiness, or remediation plans.

Do not use when:
- The user only asks for conceptual advice; still state validation required before launch.

Default recommendation:
- Run automated checks, keyboard-only walkthrough, screen reader smoke test, contrast check, zoom/reflow check, real-device/browser matrix, and targeted disabled-participant testing when possible.

Ask the user when:
- Time, budget, or compliance target determines the test plan.

Question prompt:
- `question({ question: "What level of accessibility validation do you need for this work?", recommended_default: "Use automated checks plus manual keyboard/screen reader/zoom testing for normal product work; add disabled-participant testing for high-impact or public releases.", options: ["Quick design review", "Implementation smoke test", "Pre-release accessibility QA", "Formal audit/remediation plan", "Other / custom"] })`

Agent behavior:
- Every substantial output should include concrete verification steps, not just recommendations.
