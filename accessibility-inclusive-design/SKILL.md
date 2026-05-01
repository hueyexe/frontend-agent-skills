---
name: accessibility-inclusive-design
description: "Use when designing, critiquing, implementing, or revising UI/UX/frontend work for accessibility and inclusion."
---

# Accessibility Inclusive Design

## Purpose

Help an agent design and critique interfaces that are accessible, inclusive, keyboard-friendly, screen-reader-aware, and usable by diverse people.

Use this skill to turn accessibility into normal design practice. Treat accessibility as part of product quality, not as a late QA task or legal checkbox.

## When to use this skill

Use this skill when the user asks for help with:

- UI, UX, frontend implementation, product design, or design-system work.
- Accessibility critique, audit, remediation, redesign, or conformance planning.
- Forms, navigation, menus, filters, product lists, media, tables of contents, dynamic loading, or interactive widgets.
- Keyboard interaction, focus management, screen reader behavior, semantic HTML, ARIA, color contrast, typography, responsive behavior, or inclusive content.
- Design defaults for users with visual, auditory, motor, cognitive, language, device, bandwidth, or situational constraints.

## When not to use this skill

Do not use this skill as the primary skill for:

- Broad UX research planning unrelated to inclusion or accessibility.
- Brand-only visual exploration where no interface behavior, content, or user task is being designed.
- Backend-only architecture with no user-facing accessibility impact.
- Legal advice. You may identify accessibility risk and recommend standards-aligned review, but do not make legal determinations.

## Core principles

1. **Design for real diversity, not an average user.** People differ in ability, technology, language, attention, literacy, device, bandwidth, and environment. Avoid solutions that only work for the designer’s setup.
2. **Start with purpose and user task.** Clear purpose reduces complexity, cognitive load, and implementation waste.
3. **Prefer native semantics and standard web behavior.** Use HTML elements that already include roles, states, keyboard behavior, and platform integration before recreating behavior with JavaScript and ARIA.
4. **Make structure machine-readable.** Headings, landmarks, lists, labels, form controls, alt text, captions, and document metadata are part of the interface.
5. **Progressively enhance.** Begin with meaningful content and working HTML. Add CSS and JavaScript only when they improve the experience without destroying the baseline.
6. **Give users control.** Do not block zoom, trap focus, autoplay media, force motion, impose infinite scroll, or decide display preferences when user choice is feasible.
7. **Use convention as an accessibility feature.** Familiar navigation, link styling, button affordance, form patterns, and predictable placement reduce cognitive effort.
8. **Make hidden state explicit.** If something expands, loads, errors, becomes selected, or changes dynamically, communicate the state visually and programmatically.
9. **Content is part of design.** Clear headings, descriptive links, plain language, usable labels, and helpful errors are accessibility features.
10. **Test beyond automation.** Automated checks help, but keyboard walkthroughs, screen reader checks, device/browser testing, and disabled participant feedback uncover issues automation misses.

## Default recommendations

Use these defaults unless the user provides stronger product context or constraints.

| Area | Default | Why it is usually best | Override only when |
|---|---|---|---|
| Accessibility target | Design to WCAG AA-level expectations and current product/platform standard; treat legal conformance as a floor, not the goal. | Uploaded sources repeatedly frame accessibility as built-in quality and identify AA as a common conformance target. | The user has a regulated context, internal standard, or specific conformance target. |
| Product goal | Clarify the primary user task before layout or styling. | Clear purpose simplifies decisions and reduces barriers. | The user is only asking for a narrow component fix. |
| Semantics | Use native HTML first: `button`, `a`, `label`, `input`, `fieldset`, `legend`, `nav`, `main`, headings, lists. | Native elements include expected keyboard and assistive-technology behavior. | The needed interaction has no suitable native pattern. |
| ARIA | Use ARIA only to add missing names, relationships, live updates, and states to otherwise sound markup. | ARIA changes semantics but does not automatically add behavior. | A custom component truly needs ARIA roles/states and matching keyboard behavior. |
| Layout | Use flexible, content-driven, responsive layouts; avoid fixed widths/heights. | Content, device sizes, zoom, and text settings vary. | A fixed dimension is intrinsic to media or a constrained platform surface. |
| Breakpoints | Add breakpoints where content breaks, not for named devices. | Device-specific breakpoints cannot cover all setups. | A native app or embedded surface has fixed known constraints. |
| Typography | Use readable type, relative units, generous line height, comfortable measure, and real content. | Readability supports low vision, dyslexia, cognitive load, language learners, and everyone else. | Brand type is constrained; then test and tune size, spacing, weight, and contrast. |
| Contrast | Ensure sufficient contrast and never use color alone; avoid unnecessary low contrast and avoid extreme glare as the only option. | Low contrast excludes many users; excessive glare can harm some readers. | A brand palette is fixed; then adapt tokens to meet contrast and comfort. |
| Links | Keep inline links visually identifiable, usually underlined, and make link text meaningful out of context. | Screen readers list links independently; color-only links fail many users. | Button-like CTAs may use button affordance, but still need clear text. |
| Navigation | Use landmarked, list-based navigation with familiar placement and clear current-location cues. | It works visually, without CSS, and in assistive technologies. | A very small flow genuinely needs no navigation. |
| Menus | Do not hide a short menu. For disclosure menus, use a real button, visible label, `aria-expanded`, adjacent menu, and robust hidden state. | Hidden navigation adds an action cost and state complexity. | Screen space is severely constrained or the menu is large. |
| Forms | Use persistent labels, grouped controls when useful, clear required indicators, forgiving validation, and error recovery. | Forms are high-risk for cognitive, motor, and screen reader barriers. | Extremely short forms may not need grouping; labels still remain required. |
| Validation | Validate on submit first; after errors exist, give supportive inline feedback while the user corrects. | Premature live validation can be noisy and stressful. | The field is high-cost or security-sensitive and immediate feedback is clearly helpful. |
| Passwords | Prefer a show-password control over forcing duplicate password entry. | It reduces cognitive and motor burden while preserving user control. | Security policy prohibits reveal controls. |
| Dynamic loading | Prefer explicit “Load more” or user-triggered updates over infinite scroll. Announce loading and move focus after new content appears. | Infinite scroll undermines keyboard navigation, control, and orientation. | Research proves auto-loading is expected and an accessible fallback is provided. |
| Media | Provide captions, transcripts, and meaningful image alternatives. | Different users need different sensory channels and contexts. | Decorative images should use empty alt text rather than a description. |
| Motion | Keep motion optional, purposeful, and controllable. | Motion can distract, disorient, or trigger symptoms. | Motion conveys essential state; still provide reduced-motion handling. |
| Testing | Run at least keyboard-only, focus, semantic/DOM, contrast, responsive/zoom, and screen reader smoke checks. | Automation cannot validate real interaction quality. | The task is conceptual only; still mention testing needed before launch. |

## Required user questions

Do not ask users to approve routine best practices. Apply the default and explain it.

Ask one focused question only when the answer affects a material recommendation. Use a `question` tool or equivalent when available.

Ask when:

1. **Regulatory or organizational target is unknown and compliance is central.**
   - Default: WCAG AA-level design and current product standard.
2. **Audience, assistive technologies, language, geography, or platform materially changes the design.**
   - Default: broad web audience, keyboard and screen reader support, responsive browser behavior.
3. **A component may need a custom interaction pattern rather than native HTML.**
   - Default: native HTML or simpler pattern.
4. **Brand voice conflicts with clear labels, plain language, or recognizable affordances.**
   - Default: clear task language with brand personality secondary.
5. **A dynamic behavior could change user control, focus, or orientation.**
   - Default: explicit user-triggered action with visible and programmatic feedback.
6. **The user requests a legal/conformance claim.**
   - Default: provide design/implementation recommendations and recommend expert/legal validation.

## Workflow

### A. Critique existing UI, screenshots, code, or flows

Inspect in this order:

1. **Task and purpose**
   - What is the user trying to do?
   - Is the primary path obvious and unnecessary complexity removed?
2. **Structure and semantics**
   - Are document title, language, headings, landmarks, lists, controls, labels, and relationships meaningful?
   - Does source order match reading and focus order?
3. **Keyboard and focus**
   - Can every interactive element be reached, seen, operated, and exited by keyboard?
   - Are focus states visible and not removed?
   - Is focus managed after disclosures, in-page links, validation, and dynamic loading?
4. **Interaction behavior**
   - Are controls recognizable?
   - Are states and changes communicated visually and programmatically?
   - Does the interface preserve user control?
5. **Content and labels**
   - Are headings, links, form labels, button names, instructions, and errors clear out of context?
   - Is brand language secondary to task clarity?
6. **Visual presentation**
   - Are contrast, text size, line height, measure, spacing, and grouping readable?
   - Is information conveyed by more than color, position, or sound alone?
7. **Forms and errors**
   - Are labels persistent and associated?
   - Are required fields clear?
   - Are errors announced, located near the user’s work, and actionable?
8. **Media and alternatives**
   - Are images, icons, video, audio, and non-text cues available through appropriate alternatives?
9. **Responsive and environmental resilience**
   - Does it work with zoom, text resizing, narrow/wide viewports, slow networks, disabled CSS/JS, and user font/color preferences?
10. **Testing and maintainability**
   - Are accessibility checks embedded in the component/design-system workflow?

Output critique as:
- Severity: blocker, major, moderate, minor.
- Who is affected: keyboard users, screen reader users, low-vision users, cognitive load, motor access, language/literacy, low bandwidth, etc.
- Why it matters.
- Recommended fix.
- Implementation note.
- Test to verify.

### B. Create or improve a design

Proceed in this order:

1. **Clarify the feature and user task.**
   - If missing, ask one focused question and propose the default.
2. **Choose the simplest useful pattern.**
   - Prefer native controls and familiar conventions.
3. **Establish structure.**
   - Define headings, regions, reading order, navigation, form groups, and content relationships before styling.
4. **Write labels and content.**
   - Use direct, descriptive, context-independent copy.
5. **Define interaction and state.**
   - Specify keyboard behavior, focus order, visible focus, state announcements, loading, errors, and recovery.
6. **Apply visual design.**
   - Tune typography, contrast, spacing, grouping, affordance, and responsive behavior.
7. **Add progressive enhancement.**
   - Add JavaScript only after the HTML baseline works.
8. **Validate edge cases.**
   - Test zoom, long content, localization, RTL if relevant, slow network, disabled CSS/JS, and alternative input.
9. **Explain decisions.**
   - Tie recommendations to user impact, not just standards.

## Decision framework

When choosing a pattern, prefer the first option that satisfies the user task:

1. **No interaction needed:** Use semantic static content.
2. **Native interaction exists:** Use the native element.
3. **Native interaction can be styled:** Keep native behavior and style labels/containers rather than replacing controls.
4. **Progressive enhancement is enough:** Keep the baseline form/link behavior and enhance with JS.
5. **Custom interaction is unavoidable:** Implement the full pattern: role, name, state, keyboard behavior, focus management, visible affordance, instructions, and tests.
6. **The pattern hides content or takes control:** Reconsider. Ask whether the product context truly requires it.
7. **The pattern depends on user preferences:** Provide choice or respect browser/OS settings.

## Practical rules

### Document and page structure

- Include a valid doctype.
- Declare the page language with `lang`; declare `dir` for right-to-left languages.
- Use one meaningful document `<title>` that names the current page or result state.
- Use one primary `<main>` region for the unique page content.
- Provide a skip link to main content for sighted keyboard users.
- Use headings for structure, not visual size. Do not skip heading levels just to achieve a style.
- Use lists for grouped navigation and grouped content.
- Ensure source order makes sense when read top-to-bottom.

### Navigation and wayfinding

- Put primary navigation in a `nav` landmark.
- Label multiple navigation landmarks uniquely, such as “site” and “contents”.
- Keep familiar placement and recognizable shapes.
- Indicate the current page/section with more than color.
- For current-page links, avoid redundant reload behavior; use a same-page link to main content when appropriate, or a clear described current state.
- Use tables of contents for long pages instead of complex dropdown submenus when the goal is section navigation.

### Buttons, links, and controls

- Use `button` for actions and `a href` for navigation.
- Do not use a clickable `div` or `span` when a native element fits.
- Do not remove button or link affordance without replacing it with an equally clear affordance.
- Icon-only controls need an accessible name. Prefer visible text when space allows.
- Keep touch targets generous and separated; use full-row vertical navigation on narrow touch viewports.
- Invisible elements must not be focusable.

### Keyboard and focus

- Every actionable control must be reachable by keyboard.
- Every focused control must have a visible focus indicator.
- Do not set `outline: none` unless you provide a stronger replacement.
- Do not use positive `tabindex` to rearrange navigation. Fix the source order instead.
- Use `tabindex="-1"` only for programmatic focus targets such as in-page headings after smooth scroll or newly loaded content.
- When JavaScript hijacks native behavior, restore focus movement, URL updates, and expected keyboard behavior.

### Forms

- Every input has a persistent, associated label.
- Placeholder text is only a hint; never use it as the only label.
- Use `fieldset` and `legend` when they clarify multiple related controls; avoid them when they add noise without benefit.
- Ask only for information needed to complete the task.
- Mark required fields visibly and programmatically.
- Put errors near the user’s current work, not only at the top of the page.
- Separate “there are errors” from “how to fix this field.”
- Use `aria-invalid` and `aria-describedby` for invalid fields and remediation text when appropriate.
- Use live regions for asynchronous form or loading feedback, but do not over-announce every keystroke.
- Debounce live validation and avoid noisy, aggressive validation.
- Prefer “show password” to duplicate password fields unless policy prevents it.

### Dynamic content

- Prefer explicit actions such as “Apply filters” and “Load more” when changes are consequential.
- Announce loading and completion to screen readers.
- Prevent duplicate loading actions while requests are pending.
- After new content loads, move focus to the first meaningful new item when the trigger is displaced.
- Avoid infinite scroll by default.
- If using live regions, choose polite/assertive behavior based on urgency and avoid interrupting routine reading unless necessary.

### Visual design and readability

- Use real content early. Do not design only with idealized placeholder text.
- Choose typefaces for legibility, character distinction, language support, and required weights/styles.
- Use relative units for text, spacing, and layout.
- Keep line length comfortable; avoid overly wide or narrow text blocks.
- Use unitless line-height, typically around 1.5 for body text unless typography testing supports another value.
- Avoid justified text for web body copy unless hyphenation and language support are reliable and tested.
- Use enough contrast for text and UI states, but avoid unnecessary harshness as the only reading mode.
- Convey state with shape, text, icon, placement, or pattern, not color alone.
- Use whitespace and proximity to clarify grouping.

### Media and non-text content

- Decorative images use empty alt text.
- Informative images get concise alt text that communicates purpose or content.
- Linked images describe the link destination or action, not merely the image.
- Complex images, infographics, and charts need surrounding explanation or structured text alternatives.
- Video with speech needs captions and a transcript.
- Captions should identify speaker changes and important non-speech audio.
- Media players must be keyboard operable, visibly focusable, and screen-reader labeled.

### Internationalization and environmental resilience

- Do not assume one language, address format, name format, date format, device, connection speed, pointer type, or viewport.
- Use flexible data structures and UI labels where international variation is likely.
- Test long labels, translated strings, names, product titles, and variable content lengths.
- Support RTL layout when targeting RTL languages; prefer layout systems that respond to `dir`.
- Do not block browser zoom, text resizing, user font choices, or high-contrast settings.
- Treat web fonts, icons, and scripts as enhancements, not requirements for reading or basic operation.

## Accessibility and inclusion requirements

Before finalizing, verify:

- The product can be used without a mouse.
- Focus order follows visual and logical order.
- Focus is visible at all times.
- Interactive elements have accessible names, roles, states, and values.
- Important content is not hidden in background images, pseudo-elements, color, audio, or layout position alone.
- Page structure can be navigated by headings and landmarks.
- Forms can be understood, completed, corrected, and submitted with assistive technology.
- Error, loading, expanded/collapsed, selected, and invalid states are communicated visually and programmatically.
- Text remains readable under zoom, text resizing, small screens, user font settings, and slow networks.
- Media alternatives are provided.
- Automated checks are complemented by manual keyboard and assistive-technology checks.

## Frontend implementation guidance

- Start with semantic HTML; then add CSS; then add JavaScript.
- Keep controls native where possible. Style labels or wrappers instead of replacing inputs.
- Use CSS attribute selectors tied to semantic state, such as `[aria-invalid="true"]`, `[aria-expanded="true"]`, or `[aria-pressed="true"]`, to reduce drift between state and styling.
- Do not create controls that require JavaScript for basic access when a working form/link fallback is possible.
- If a component hides content, ensure hidden content is removed from the focus order.
- If a component reveals content, place the revealed content near the trigger in source order unless there is a strong reason not to.
- If a component changes page content asynchronously, provide live-region feedback and deliberate focus management.
- Use design tokens for focus, contrast, spacing, disabled state, error state, and touch target sizing so accessibility is built into the system.
- Test components with long content, different languages, missing assets, disabled CSS, failed scripts, high contrast mode, zoom, and keyboard-only operation.
- For design systems, document expected markup, keyboard behavior, ARIA states, focus behavior, content rules, and anti-patterns for each component.

## Quality checklist

Use the detailed checklists in `references/checklists.md`. At minimum, before answering:

- The recommendation starts from the user task.
- Native semantics are preferred over custom controls.
- Keyboard and focus behavior are specified.
- Screen reader names, states, and relationships are specified where relevant.
- Color is never the only cue.
- Text and labels are clear out of context.
- Errors, loading, and empty states are included.
- Responsive, zoom, and variable-content behavior are addressed.
- The response explains user impact and gives test steps.

## Common mistakes to avoid

See `references/anti-patterns.md`. The highest-risk mistakes are:

- Clickable `div` controls.
- Placeholder-only labels.
- Removing focus styles.
- Disabling zoom.
- Hiding navigation unnecessarily.
- Icon-only controls without accessible names.
- Color-only states.
- Infinite scroll without an explicit alternative.
- JavaScript-dependent static content.
- Visual order that differs from source/focus order.
- ARIA used to patch a broken native pattern.
- Relying on automated tests alone.

## How to explain recommendations to the user

Use practical, user-impact language:

- “This is not just compliance; it prevents keyboard and screen reader users from getting stuck.”
- “The native element is simpler and more reliable because the browser already provides role, keyboard behavior, and platform integration.”
- “This label needs to make sense out of context because screen readers can list controls and links independently.”
- “The visual state also needs a programmatic state so assistive technology receives the same information.”
- “This pattern preserves user control; the alternative would make the interface act unexpectedly.”
- “The default is inclusive for more users, and it does not prevent brand expression.”

When recommending a tradeoff, state:
1. the default,
2. the user groups protected,
3. the cost or constraint,
4. the condition that would justify an override,
5. how to test the override.

