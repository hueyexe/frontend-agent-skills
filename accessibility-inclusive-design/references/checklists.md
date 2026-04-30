# Checklists — accessibility-inclusive-design

Use these checklists before finalizing critique, recommendations, component specs, or frontend implementation guidance.

## 1. Discovery/context checklist

- The primary user task is identified.
- The product context is known or an inclusive default is stated.
- The target platform is known: web, React/web component, native, hybrid, or unknown.
- The accessibility target is known when compliance is central.
- Known audience constraints are identified: age, literacy, language, geography, assistive technology, device, bandwidth, or environment.
- The agent did not ask the user to make routine best-practice decisions.
- Any unresolved assumption is explicit and paired with a recommended default.
- If brand voice is relevant, task-critical clarity remains the default.
- If legal compliance is requested, the response avoids legal advice and recommends appropriate expert validation.

## 2. Critique workflow checklist

- The critique starts with user goal/task fit, not visual polish.
- Issues are grouped by severity: blocker, major, moderate, minor.
- Each issue names who is affected, such as keyboard users, screen reader users, low-vision users, cognitive load, motor access, language/literacy, or low bandwidth.
- Each issue explains why it matters to use, not only which rule it violates.
- Each issue includes a concrete fix.
- Each issue includes a verification step.
- Pattern-level issues are separated from one-off content issues.
- Visual and code recommendations are aligned.
- The critique identifies missing information without over-asking.
- The final summary prioritizes the highest-impact fixes first.

## 3. Generation/design quality checklist

- The simplest useful pattern has been chosen.
- Native HTML or platform-native controls are preferred before custom widgets.
- The primary action is visually stronger than secondary and tertiary actions.
- Controls that look similar behave similarly.
- Controls that behave differently are visually and textually differentiated.
- The UI uses familiar affordances for buttons, links, fields, and navigation.
- The layout supports the primary task without distracting clutter.
- Content is organized into logical groups.
- The page or component has clear entry, progress, completion, error, loading, and empty states where relevant.
- The design includes edge cases: long labels, empty results, loading delays, errors, missing images, and variable data.
- The design tolerates zoom and text resizing.
- The design does not depend on hover alone.
- The design avoids unnecessary animation and preserves user control.

## 4. Semantic structure checklist

- The page has a meaningful title that identifies the current page or state.
- The page language is declared with `lang`.
- Direction `dir` is declared or planned when RTL content is in scope.
- There is one primary `main` region for unique page content.
- A skip link to `main` is provided for pages with repeated header/nav content.
- The page has one clear `h1`.
- Heading levels are not skipped for visual size.
- Headings describe the topic or purpose of the section.
- Source order matches logical reading order.
- Visual order does not contradict source/focus order.
- Lists are used for grouped navigation or grouped repeated content.
- Tables are used for tabular data, not layout.
- Decorative containers do not add unnecessary semantic noise.

## 5. Navigation and wayfinding checklist

- Primary navigation is in a `nav` landmark.
- Multiple navigation landmarks have unique accessible labels.
- Navigation uses familiar placement and recognizable link/button shapes.
- Current page or current section is identified with more than color.
- Current-location indicators are available to assistive technologies.
- Redundant current-page links do not reload the page unnecessarily.
- Long pages include an in-page table of contents when useful.
- In-page links preserve expected URL fragment behavior.
- Smooth scrolling does not strand keyboard focus.
- Breadcrumbs, if present, are labeled and show the current location.
- Drop-down or flyout menus are avoided unless genuinely needed and fully keyboard/touch/screen-reader tested.
- Search, sitemap, or alternate navigation is considered for large sites.

## 6. Keyboard and focus checklist

- Every actionable control can be reached with the keyboard.
- Every actionable control can be operated with expected keys.
- Every actionable control can be exited or dismissed with keyboard where relevant.
- Focus indicators are visible and meet contrast/visibility expectations.
- `outline: none` is not used unless replaced with a stronger focus style.
- No positive `tabindex` values are used to force tab order.
- `tabindex="-1"` is used only for programmatic focus targets.
- Disabled controls are handled intentionally and do not create dead ends.
- Hidden content is not focusable.
- Focus remains predictable after modals, menus, disclosures, validation, navigation, and dynamic loading.
- JavaScript that hijacks native behavior restores focus behavior and expected keyboard operation.
- Keyboard testing covers forward and backward tabbing, activation, dismissal, and error recovery.

## 7. Screen reader and accessibility tree checklist

- Each interactive element has an accessible name.
- Names are concise and describe the control’s purpose.
- Role and state match the visible control.
- Expanded/collapsed state is exposed for disclosures.
- Selected/current state is exposed for current navigation, toggles, tabs, filters, or options.
- Invalid state is exposed for invalid fields.
- Descriptions are attached with `aria-describedby` when instructions or errors are needed.
- Live regions are used only for meaningful asynchronous changes.
- Live-region politeness matches urgency.
- The agent has not used ARIA to replace a native element that would work better.
- ARIA attributes are not present without the required behavior.
- Screen-reader-only text is used only when it clarifies non-visual meaning and does not hide important visible content from sighted users.

## 8. Forms checklist

- Every input has a persistent visible label or an equally clear persistent labeling mechanism.
- Labels are programmatically associated with inputs.
- Placeholder text is not the only label.
- Placeholder text, if used, is only a hint or example.
- Required fields are marked visibly and programmatically.
- Optional fields are identified when that reduces ambiguity.
- Fields are grouped with `fieldset` and `legend` only when grouping aids comprehension.
- Field instructions appear before or near the relevant field.
- Inputs use appropriate types and autocomplete hints where relevant.
- The form asks only for task-critical information.
- Users can review and change inputs before final submission when consequences are significant.
- Password fields include a show-password option unless security policy prevents it.
- Error messages are specific and actionable.
- Error messages do not rely on color alone.
- Error messages are associated with fields.
- A form-level error notice is provided for multi-error submissions.
- Validation is not noisy or premature.
- Validation feedback is debounced if it responds to typing.
- Submission failure does not erase user input.
- The submit button label clearly states the action.

## 9. Content and plain-language checklist

- Headings describe the topic or purpose of the following content.
- Link text makes sense when read out of context.
- Button text describes the action.
- Labels use familiar terms or explain necessary specialist terms.
- Sentences are direct and avoid unnecessary passive voice.
- Paragraphs are short enough to scan.
- Critical instructions are not hidden in dense prose.
- Error text tells users what happened and how to fix it.
- Brand voice does not obscure task-critical meaning.
- Complex content has summaries or progressive disclosure where useful.
- Content is tested or reviewed with real audience needs where possible.
- The response avoids “click here,” “read more,” and other generic labels unless the surrounding accessible name resolves the purpose.

## 10. Typography, color, and visual presentation checklist

- Body text is legible at default size.
- Text uses relative units where implementation is discussed.
- Line-height is generous and proportional.
- Text blocks avoid overly long or short measure.
- Body text is not justified by default.
- Text has sufficient contrast against its background.
- UI states have sufficient contrast.
- Color is not the only way to convey meaning.
- Focus, error, selected, disabled, and current states use text, shape, icon, border, position, or pattern as well as color.
- Spacing and proximity clarify relationships between elements.
- Visual grouping matches semantic grouping.
- The design supports browser zoom and text resizing.
- The design avoids overly stark contrast as the only reading option when a more comfortable accessible palette is possible.
- The design avoids clutter that competes with the primary task.

## 11. Media and non-text content checklist

- Decorative images have empty alt text or are hidden from assistive technology.
- Informative images have purpose-based alt text.
- Images that act as links describe the link destination or action.
- Icons used with visible text do not create duplicate screen reader output.
- Icon-only controls have accessible names.
- Charts and diagrams have text explanations or structured data summaries.
- Video with speech has captions.
- Video/audio with meaningful content has a transcript.
- Captions identify speaker changes when needed.
- Captions include important non-speech sounds.
- Media players are keyboard operable.
- Media players expose meaningful control names and states.
- Autoplay is avoided or user-controllable.
- Audio is not the only way to receive important information.
- Visual cues such as “the red area on the right” have non-visual equivalents.

## 12. Dynamic content checklist

- The user initiates consequential updates unless auto-update is clearly expected and tested.
- Loading state is visible.
- Loading state is announced to assistive technologies when needed.
- Completion state is announced when it changes what the user can do next.
- Users cannot trigger duplicate async actions accidentally.
- Focus remains on the trigger or moves intentionally to new content.
- New content insertion does not trap keyboard users.
- Infinite scroll is avoided by default.
- “Load more” or pagination is provided for long result sets.
- Filters and sorting have a no-JavaScript fallback when feasible.
- Result counts are communicated after filtering.
- Empty results provide next steps.
- Error states for failed loading provide retry or recovery.
- Motion caused by updates respects reduced-motion preferences.

## 13. Responsive and environmental resilience checklist

- Breakpoints are based on content failure points, not named devices.
- Layout works across narrow, medium, wide, and zoomed viewports.
- Fixed heights/widths do not clip text or controls.
- Touch targets are large enough and not crowded.
- Navigation on narrow viewports uses enough vertical padding and spacing.
- Browser zoom is not disabled.
- Text resizing does not break layout.
- User fonts or font loading failures do not hide content.
- Web fonts do not cause invisible text while loading.
- CSS failure leaves content readable and navigable.
- JavaScript failure leaves core content and basic actions available where feasible.
- Slow network conditions do not block primary content behind decorative assets.
- High contrast or forced colors do not erase essential icons or states.
- Long translated text and variable content are tested.
- RTL layout is supported when relevant.

## 14. Implementation feasibility checklist

- The proposed markup is valid enough for assistive technology parsing.
- Component behavior can be implemented with available platform APIs.
- State is stored in one source of truth where possible.
- Visual styling is tied to semantic state where appropriate.
- Design tokens include focus, error, selected, disabled, contrast, spacing, and motion states.
- Component docs specify required markup and forbidden misuse.
- Component docs specify keyboard behavior.
- Component docs specify focus management.
- Component docs specify ARIA roles/states only when required.
- Component docs specify content requirements such as label format and alt text.
- Automated tests cover accessible names, roles, state attributes, and relationships.
- Manual tests cover keyboard, screen reader smoke check, zoom, and responsive behavior.
- Pattern-level fixes are preferred when multiple screens share the issue.
- The implementation avoids framework constraints that prevent semantic output.

## 15. Final response checklist

- The answer is actionable, not a generic accessibility lecture.
- The answer gives a default recommendation before asking for context.
- The answer asks only necessary questions.
- The answer identifies tradeoffs and when to override the default.
- The answer includes user impact.
- The answer includes implementation details when relevant.
- The answer includes testing steps.
- The answer does not make unsupported legal compliance claims.
- The answer is concise enough for the user to act on.
