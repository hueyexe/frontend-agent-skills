# Decision Prompts — accessibility-inclusive-design

Use these prompts only when product context genuinely changes the recommendation. Do not ask users to confirm routine accessibility best practices such as “Should inputs have labels?” or “Should focus be visible?” Apply those defaults automatically.

## How to use

- Ask at most one or two questions before producing a useful first pass.
- Always provide the recommended default and why.
- If no answer is available, proceed with the default and label assumptions.
- Do not ask questions that outsource accessibility expertise to the user.

---

### Decision: Accessibility target and compliance posture

When to ask:
- The user asks for compliance, audit, release readiness, procurement, regulated work, or a formal accessibility target.
- The user requests a statement such as “is this accessible?” or “does this meet standards?”

Do not ask when:
- The user asks for a normal design or implementation recommendation and no legal/conformance claim is needed.

Recommended default:
- Design to WCAG AA-level expectations and the product’s current standard; treat standards as the floor, not the full experience.

Reason:
- The sources identify WCAG/POUR and common AA targets while emphasizing that usability and inclusion go beyond legal minimums.

Question tool pattern:
```js
question({
  question: "What accessibility target should this work aim for?",
  recommended_default: "WCAG AA-level design and the product’s current standard, because it is a practical baseline while still requiring usability beyond checklist compliance.",
  options: [
    "WCAG AA-level design baseline",
    "Formal compliance audit target",
    "Internal design-system standard",
    "Exploratory accessibility critique only",
    "Other / custom"
  ]
})
```

---

### Decision: Primary user task

When to ask:
- The interface goal is unclear.
- The user provides a screen/component but not what users are trying to accomplish.
- Multiple competing tasks would change layout, labels, or interaction.

Do not ask when:
- The task is clear from the request, such as “signup form,” “filter products,” or “menu button.”

Recommended default:
- Optimize the shortest reliable path to the main user task.

Reason:
- Clear purpose reduces clutter, cognitive load, and inconsistent decisions.

Question tool pattern:
```js
question({
  question: "What primary task should this interface help users complete?",
  recommended_default: "Optimize the most common successful completion path, because clear purpose makes accessibility and usability decisions simpler.",
  options: [
    "Complete a transaction or submission",
    "Find information",
    "Compare or filter items",
    "Navigate between sections",
    "Other / custom"
  ]
})
```

---

### Decision: Audience and assistive technology assumptions

When to ask:
- The product serves a specialized group, internal workforce, education/health/public service users, older adults, international users, or known assistive technology profiles.
- The design decision depends on literacy, language, device, input method, or support environment.

Do not ask when:
- The product is a broad public web interface and inclusive defaults are sufficient.

Recommended default:
- Assume broad diversity: keyboard, screen reader, low vision, motor, cognitive, mobile, zoom, language, slow network, and situational constraints.

Reason:
- Designing for a fictional average user excludes real users.

Question tool pattern:
```js
question({
  question: "Do you have known audience, device, language, or assistive-technology requirements?",
  recommended_default: "Use broad inclusive web defaults unless you have specific user research, because people vary widely even within disability groups.",
  options: [
    "Broad public audience",
    "Known internal/enterprise audience",
    "Known assistive technology requirements",
    "Known language/localization requirements",
    "Other / custom"
  ]
})
```

---

### Decision: Web, native, or hybrid platform

When to ask:
- The implementation platform is unclear and affects semantics, keyboard behavior, native controls, or assistive technology APIs.
- The user asks for frontend implementation but does not specify web/native.

Do not ask when:
- The user explicitly asks for web, HTML/CSS/JS, React, or browser UI.

Recommended default:
- Assume standards-based web UI with semantic HTML.

Reason:
- The uploaded technical source is web-focused and native web semantics are the safest baseline for the target skill.

Question tool pattern:
```js
question({
  question: "What platform should this accessibility guidance target?",
  recommended_default: "Standards-based web UI, because semantic HTML and progressive enhancement provide the strongest default for browser-based accessibility.",
  options: [
    "Web / HTML / CSS / JavaScript",
    "React or other web component framework",
    "Native mobile",
    "Hybrid webview/app shell",
    "Other / custom"
  ]
})
```

---

### Decision: Native element vs custom component

When to ask:
- The requested design uses custom buttons, tabs, selects, menus, radio groups, sliders, comboboxes, date pickers, dialogs, or disclosure widgets.
- A design-system component may not use native HTML.

Do not ask when:
- A native element clearly satisfies the task.

Recommended default:
- Use native HTML and style it.

Reason:
- Native controls provide role, state, keyboard behavior, focus behavior, and platform integration with fewer failure modes.

Question tool pattern:
```js
question({
  question: "Does this interaction require custom behavior that native HTML cannot provide?",
  recommended_default: "Use native HTML and style it, because it already includes reliable semantics and keyboard behavior.",
  options: [
    "Native HTML is sufficient",
    "Custom behavior is required",
    "Must use existing design-system component",
    "Unsure / compare native and custom options",
    "Other / custom"
  ]
})
```

---

### Decision: Navigation depth and wayfinding model

When to ask:
- The interface involves multiple pages, long pages, hierarchical navigation, breadcrumbs, table of contents, menus, or app shell navigation.
- Navigation structure is ambiguous.

Do not ask when:
- The requested component has no navigation or a very obvious single nav.

Recommended default:
- Use one primary navigation landmark and add in-page table of contents only for long or dense pages.

Reason:
- Familiar navigation and clear orientation reduce cognitive work and help assistive technology users.

Question tool pattern:
```js
question({
  question: "What navigation depth does this experience need?",
  recommended_default: "Use simple primary navigation; add in-page navigation only when content length or density requires it.",
  options: [
    "No global navigation needed",
    "Simple primary navigation",
    "Primary navigation + breadcrumbs",
    "Primary navigation + in-page table of contents",
    "Other / custom"
  ]
})
```

---

### Decision: Hidden menu or always-visible navigation

When to ask:
- The user requests a hamburger/menu button or hidden navigation.
- Navigation has few items and could be visible.
- Screen size or information architecture constraints are unclear.

Do not ask when:
- The layout is a narrow mobile viewport and there are many navigation items; proceed with an accessible menu button pattern.

Recommended default:
- Keep short menus visible. Hide navigation only when space or item count requires it.

Reason:
- Hiding functionality adds a user action and state complexity; if fewer than about five items, hiding is often unnecessary.

Question tool pattern:
```js
question({
  question: "Should this navigation be hidden behind a menu button, or kept visible?",
  recommended_default: "Keep short navigation visible; use a menu button only when space or item count requires hiding it.",
  options: [
    "Keep navigation visible",
    "Use menu button on narrow viewports only",
    "Use menu button across all viewports",
    "Use in-page table of contents instead",
    "Other / custom"
  ]
})
```

---

### Decision: Form data and required fields

When to ask:
- The user asks to design or critique a form but required fields, business rules, or data necessity are unknown.
- The form asks for sensitive or optional information.

Do not ask when:
- The form fields are provided and the task is to improve accessibility.

Recommended default:
- Ask only for information required to complete the user’s task.

Reason:
- Simpler forms reduce cognitive load, errors, privacy risk, and motor effort.

Question tool pattern:
```js
question({
  question: "Which fields are truly required for users to complete this task?",
  recommended_default: "Keep only task-critical fields required, because unnecessary inputs increase errors and abandonment.",
  options: [
    "Only account/contact essentials",
    "Task-critical fields plus optional profile details",
    "All listed fields are required by policy",
    "Unknown / audit fields for necessity",
    "Other / custom"
  ]
})
```

---

### Decision: Validation timing

When to ask:
- The user requests form validation behavior.
- A field has complex, security-sensitive, or high-cost validation.
- There is a tradeoff between immediate feedback and reduced interruption.

Do not ask when:
- Basic validation is obvious and can follow the default.

Recommended default:
- Validate on submit first; after errors exist, provide debounced supportive feedback while users correct.

Reason:
- Premature validation can be noisy, stressful, and confusing, especially with screen readers.

Question tool pattern:
```js
question({
  question: "When should this form validate user input?",
  recommended_default: "Validate on submit first, then provide supportive inline feedback while users correct errors, because this avoids noisy premature errors.",
  options: [
    "On submit first",
    "On blur for each field",
    "After debounced typing",
    "Immediate validation for high-risk fields",
    "Other / custom"
  ]
})
```

---

### Decision: Error summary and focus behavior

When to ask:
- The form is long or errors may occur outside the current viewport.
- The user asks whether to move focus to the first error.
- The product has existing error-handling conventions.

Do not ask when:
- A short form has a simple inline error pattern; apply default.

Recommended default:
- Announce error presence near the submit action, mark fields inline, and do not unexpectedly move focus unless there is a strong reason.

Reason:
- Unexpected focus movement can disorient users; separate “something is wrong” from “what to fix.”

Question tool pattern:
```js
question({
  question: "How should this form bring errors to the user’s attention?",
  recommended_default: "Show and announce a concise error notice near the submit action, then provide field-level repair instructions without unexpectedly moving focus.",
  options: [
    "Inline errors only",
    "Error notice + inline field errors",
    "Move focus to error summary",
    "Move focus to first invalid field",
    "Other / custom"
  ]
})
```

---

### Decision: Dynamic update trigger

When to ask:
- Filters, sorting, live search, dashboards, or settings change content dynamically.
- The user wants auto-update behavior.
- Keyboard or screen reader orientation may be affected.

Do not ask when:
- The update is minor, local, and expected from a native control.

Recommended default:
- Use explicit “Apply” or equivalent for consequential changes; use live regions and focus management for async updates.

Reason:
- Explicit actions preserve user control and avoid surprise, especially for keyboard and screen reader users.

Question tool pattern:
```js
question({
  question: "Should changes apply automatically or only after the user confirms?",
  recommended_default: "Use an explicit Apply action for consequential content changes, because it preserves user control and reduces unexpected updates.",
  options: [
    "Explicit Apply action",
    "Auto-update after selection",
    "Auto-update after debounced input",
    "Auto-update only for low-risk preview changes",
    "Other / custom"
  ]
})
```

---

### Decision: Infinite scroll vs pagination/load more

When to ask:
- The user asks for infinite scroll or endless content.
- A list may contain many items and loading strategy affects orientation.

Do not ask when:
- A short list has no incremental loading requirement.

Recommended default:
- Use explicit “Load more” or pagination, not infinite scroll.

Reason:
- Infinite scroll can make keyboard navigation endless, displace scroll position, and reduce user control.

Question tool pattern:
```js
question({
  question: "How should long result sets load?",
  recommended_default: "Use an explicit Load more button or pagination, because it preserves user control and keyboard orientation better than infinite scroll.",
  options: [
    "Load more button",
    "Pagination",
    "Hybrid pagination + load more",
    "Infinite scroll with accessible fallback",
    "Other / custom"
  ]
})
```

---

### Decision: Display density and list/grid choice

When to ask:
- Users may need to compare many items or read details comfortably.
- A product/content list could be presented as a list or grid.
- Information density affects cognitive load.

Do not ask when:
- The display type is obvious from the task.

Recommended default:
- Provide a readable list by default; offer grid as a user choice when overview is valuable.

Reason:
- A list is simpler and easier to scan sequentially; a grid can help comparison but increases density.

Question tool pattern:
```js
question({
  question: "What display density should the content use?",
  recommended_default: "Use a readable list by default and offer grid view when comparison or visual overview matters.",
  options: [
    "Readable list",
    "Compact list",
    "Grid/cards",
    "User can switch list/grid",
    "Other / custom"
  ]
})
```

---

### Decision: Media alternative level

When to ask:
- The interface includes images, diagrams, charts, audio, video, animation, or icon-only content.
- The purpose of the media is unclear.

Do not ask when:
- The media is clearly decorative or clearly informational from context.

Recommended default:
- Provide text alternatives for meaningful media; use empty alt for decorative images; captions and transcripts for video/audio with speech.

Reason:
- Media should not make meaning available through only one sensory channel.

Question tool pattern:
```js
question({
  question: "What purpose does this image or media serve in the user task?",
  recommended_default: "Describe meaningful content or action; hide purely decorative media from assistive technology.",
  options: [
    "Decorative only",
    "Informative image or illustration",
    "Chart/diagram/data visualization",
    "Audio/video with speech",
    "Other / custom"
  ]
})
```

---

### Decision: Motion and animation

When to ask:
- The user requests animation, motion transitions, parallax, autoplay, carousels, or auto-advancing content.
- Motion conveys state or feedback.

Do not ask when:
- No motion is involved.

Recommended default:
- Use minimal purposeful motion, respect reduced-motion preferences, and provide user controls.

Reason:
- Motion can distract, disorient, or trigger vestibular symptoms; users should control pace.

Question tool pattern:
```js
question({
  question: "What role should motion play in this interface?",
  recommended_default: "Use minimal, purposeful motion and respect reduced-motion preferences, because motion can create barriers for some users.",
  options: [
    "No motion needed",
    "Subtle state transition only",
    "Instructional motion with pause/control",
    "Brand/expressive motion with reduced-motion alternative",
    "Other / custom"
  ]
})
```

---

### Decision: Brand voice vs task clarity

When to ask:
- The user asks for playful, branded, whimsical, or metaphorical labels/microcopy.
- The copy appears in form labels, buttons, errors, headings, or navigation.

Do not ask when:
- Brand voice does not affect task-critical understanding.

Recommended default:
- Use clear, direct, professional-but-warm wording for task-critical copy; put brand personality in supporting copy.

Reason:
- Labels and headings must describe topic or purpose; clever wording can confuse users at the moment of action.

Question tool pattern:
```js
question({
  question: "How much brand personality should task-critical labels and messages carry?",
  recommended_default: "Professional, direct, and warm, with brand personality secondary to clarity, because users need to understand actions and errors quickly.",
  options: [
    "Plain and direct",
    "Professional but warm",
    "Playful but clear",
    "Use established brand voice",
    "Other / custom"
  ]
})
```

---

### Decision: Localization and right-to-left support

When to ask:
- The product may support multiple languages, non-Latin scripts, right-to-left languages, translated UI, international addresses/names, or locale-specific formats.
- The UI includes forms for names, addresses, dates, phone numbers, or currencies.

Do not ask when:
- The product is explicitly single-locale and localization is out of scope; still avoid unnecessarily rigid fields.

Recommended default:
- Use flexible content/data assumptions and test long translated strings; declare `lang`, and support `dir` when RTL is in scope.

Reason:
- International variation can break rigid forms, layouts, and assistive technology pronunciation.

Question tool pattern:
```js
question({
  question: "Does this interface need localization, non-Latin text, or right-to-left language support?",
  recommended_default: "Design flexible labels, fields, and layouts that can tolerate translation and longer strings; add RTL support if needed.",
  options: [
    "Single language only",
    "Multiple left-to-right languages",
    "Right-to-left language support",
    "International names/addresses/dates/currency",
    "Other / custom"
  ]
})
```

---

### Decision: User customization and browser settings

When to ask:
- The design could block zoom, user fonts, high contrast, text resizing, or theme preferences.
- The user requests pixel-perfect or fixed-size layouts.

Do not ask when:
- You can simply preserve browser/user settings by default.

Recommended default:
- Preserve zoom, text resizing, user font/color preferences, and responsive reflow.

Reason:
- Users configure browsers and OS settings to meet access needs; blocking them creates barriers.

Question tool pattern:
```js
question({
  question: "Are there constraints requiring fixed sizing or blocked user customization?",
  recommended_default: "Do not block zoom, text resizing, user fonts, or high-contrast preferences, because users rely on these settings for access.",
  options: [
    "No, preserve user customization",
    "Fixed embedded surface",
    "Brand-controlled kiosk/display",
    "Legacy constraint to document and mitigate",
    "Other / custom"
  ]
})
```

---

### Decision: Design-system remediation level

When to ask:
- The same accessibility issue appears in multiple screens/components.
- The user asks for audit findings, component redesign, or design-system guidance.

Do not ask when:
- The issue is truly one-off content.

Recommended default:
- Fix the reusable pattern/component and document acceptance criteria.

Reason:
- Pattern-level fixes prevent repeated defects and scale better than screen-by-screen patches.

Question tool pattern:
```js
question({
  question: "Should this be addressed as a one-off fix or as a reusable design-system pattern?",
  recommended_default: "Fix the reusable pattern when it appears in multiple places, because that prevents repeated accessibility defects.",
  options: [
    "One-off screen fix",
    "Reusable component fix",
    "Template-level fix",
    "Design-system governance change",
    "Other / custom"
  ]
})
```

---

### Decision: Testing depth

When to ask:
- The user wants release readiness, audit, implementation QA, design-system validation, or a test plan.
- Time/budget constraints affect the validation strategy.

Do not ask when:
- Providing a quick conceptual critique; still include minimal verification steps.

Recommended default:
- Automated checks plus manual keyboard, screen reader smoke test, zoom/reflow, contrast, and device/browser checks; add disabled-user testing for high-impact releases.

Reason:
- Automation misses structure, comprehension, focus, and real-use issues.

Question tool pattern:
```js
question({
  question: "What level of accessibility validation do you need?",
  recommended_default: "Use automated checks plus manual keyboard/screen reader/zoom testing for normal product work; add disabled-participant testing for high-impact or public releases.",
  options: [
    "Quick design review",
    "Implementation smoke test",
    "Pre-release accessibility QA",
    "Formal audit/remediation plan",
    "Other / custom"
  ]
})
```
