# Decision Prompts for `ui-visual-composition`

Use these prompts only when the decision materially changes the design. Do not ask users to confirm routine best practices such as readable text, sufficient contrast, visible focus, or clear hierarchy.

## How to use these prompts

- Ask at most one or two questions before producing useful work.
- Include the recommended default so the user can accept, override, or ignore it.
- If the user does not answer, continue with the default and state the assumption.
- Prefer context-specific questions over broad design interviews.

### Decision: Primary task and success criterion

When to ask:
- The user asks for a new UI, redesign, or critique but does not identify the primary user task or screen goal.

Do not ask when:
- The task is obvious from the artifact or prompt, or the user asks only for visual polish of a known screen.

Recommended default:
- Optimize for the most frequent or business-critical task.

Reason:
- Visual hierarchy, grouping, and action styling depend on what the interface must help users do first.

Question tool pattern:
```js
question({
  question: "What is the primary task this screen must help users complete?",
  recommended_default: "Optimize for the most frequent or business-critical task first, because visual hierarchy and layout should follow the task.",
  options: [
    "Complete a transaction or submission",
    "Find or compare information",
    "Monitor status or data",
    "Configure settings",
    "Other / custom"
  ]
})
```

### Decision: Brand personality

When to ask:
- The visual tone could significantly change typography, spacing, color, imagery, depth, or ornament.

Do not ask when:
- The user wants a neutral product interface, the brand is evident from supplied material, or the task is a quick critique.

Recommended default:
- Professional, warm, restrained, and content-first.

Reason:
- This default suits most SaaS, productivity, admin, ecommerce, and dashboard interfaces without distracting from task completion.

Question tool pattern:
```js
question({
  question: "What personality should this product communicate?",
  recommended_default: "Professional but warm, because it works well for most productivity and SaaS interfaces unless the brand has a stronger established voice.",
  options: [
    "Professional/warm",
    "Premium/editorial",
    "Playful/friendly",
    "Technical/precise",
    "Other / custom"
  ]
})
```

### Decision: Visual density

When to ask:
- The interface could be spacious or dense, and the context suggests dashboards, professional tools, monitoring, tables, or frequent use.

Do not ask when:
- The product is a simple marketing page, onboarding flow, standard form, or consumer task where comfortable spacing is appropriate.

Recommended default:
- Comfortable spacing first; reduce density only deliberately.

Reason:
- Generous spacing improves grouping and perceived clarity; dense UIs are valuable only when users need more simultaneous information.

Question tool pattern:
```js
question({
  question: "How much information should users be able to see at once?",
  recommended_default: "Use comfortable spacing unless expert users need high information density, because cramped layouts are harder to scan and easier to misread.",
  options: [
    "Comfortable/clear",
    "Balanced",
    "Dense for expert users",
    "Very spacious/presentation-like",
    "Other / custom"
  ]
})
```

### Decision: Platform and input modality

When to ask:
- Target platform, viewport, touch/mouse/keyboard context, or environmental conditions affect layout, target size, density, or focus behavior.

Do not ask when:
- The artifact clearly targets web desktop/mobile or the user already specified platform.

Recommended default:
- Responsive web with keyboard, pointer, and touch-aware controls.

Reason:
- Many interfaces are used across viewport sizes and input types; Fitts’s Law and accessibility require comfortable target acquisition.

Question tool pattern:
```js
question({
  question: "What platform and input context should this UI prioritize?",
  recommended_default: "Responsive web with keyboard, pointer, and touch-aware controls, because it is the safest default for most product UI.",
  options: [
    "Desktop web",
    "Mobile web/app",
    "Responsive web",
    "Kiosk/TV/spatial/other special context",
    "Other / custom"
  ]
})
```

### Decision: Existing design system

When to ask:
- The user asks for code, component redesign, or system-compatible recommendations and no design-system constraints are provided.

Do not ask when:
- The task is conceptual, exploratory, or the user explicitly wants a standalone proposal.

Recommended default:
- Follow an existing design system when available; otherwise define a compact local token set.

Reason:
- Systems reduce visual inconsistency and make implementation maintainable.

Question tool pattern:
```js
question({
  question: "Should I follow an existing design system or define a lightweight local system?",
  recommended_default: "Follow the existing design system when available; otherwise define compact local tokens for type, spacing, color, radius, and elevation.",
  options: [
    "Use existing design system",
    "Create lightweight local tokens",
    "Match a provided screenshot/style",
    "No system constraints",
    "Other / custom"
  ]
})
```

### Decision: Accessibility target

When to ask:
- Product risk, regulation, public-sector use, healthcare/finance/education context, or audience needs may require stricter accessibility targets.

Do not ask when:
- The user asks for a quick concept, but still apply inclusive defaults.

Recommended default:
- WCAG AA-equivalent production defaults.

Reason:
- It is a broadly appropriate baseline for contrast, focus visibility, input accessibility, and non-color cues.

Question tool pattern:
```js
question({
  question: "What accessibility target should this UI meet?",
  recommended_default: "Use WCAG AA-equivalent production defaults unless the product requires stricter compliance, because it covers most mainstream digital interfaces.",
  options: [
    "WCAG AA-equivalent default",
    "Stricter/compliance-critical",
    "Internal prototype only",
    "Audience-specific needs",
    "Other / custom"
  ]
})
```

### Decision: Convention vs novelty

When to ask:
- The user asks for a distinctive or unconventional UI pattern that could conflict with mental models for forms, navigation, filters, tables, menus, or controls.

Do not ask when:
- Novelty is only decorative and does not affect the core task.

Recommended default:
- Convention-first for core tasks, expressive around the edges.

Reason:
- Familiar patterns reduce cognitive load and errors; brand expression can still live in typography, color, illustration, and layout rhythm.

Question tool pattern:
```js
question({
  question: "Should the core interaction prioritize convention or distinctive expression?",
  recommended_default: "Use familiar patterns for core tasks and add distinctive expression in lower-risk visual details, because users complete tasks faster when common interactions behave predictably.",
  options: [
    "Convention-first",
    "Balanced",
    "Distinctive/experimental",
    "I have a specific pattern in mind",
    "Other / custom"
  ]
})
```

### Decision: Information complexity and progressive disclosure

When to ask:
- The interface includes complex settings, long forms, many filters, dense plan comparisons, technical data, or advanced controls.

Do not ask when:
- The content is already simple or the user explicitly wants a compact expert UI.

Recommended default:
- Simplicity first with progressive disclosure.

Reason:
- Chunking and fewer visible choices reduce cognitive load, while disclosure preserves necessary power and information.

Question tool pattern:
```js
question({
  question: "Should this screen optimize for simplicity or expert control?",
  recommended_default: "Simplicity first with progressive disclosure, because it supports most users while preserving access to advanced options.",
  options: [
    "Simplicity first",
    "Balanced",
    "Expert control/dense",
    "Show everything for comparison",
    "Other / custom"
  ]
})
```

### Decision: Color constraints

When to ask:
- Palette, brand color, semantic state colors, dark mode, or accessibility requirements materially affect the design.

Do not ask when:
- The user supplied a palette or asks for neutral wireframe-level layout.

Recommended default:
- Use a neutral system with one primary accent and semantic state colors tuned for contrast.

Reason:
- Raw brand colors often fail in UI states; tuned shade scales produce reliable hover, active, border, surface, and text roles.

Question tool pattern:
```js
question({
  question: "Are there fixed brand or accessibility requirements for color?",
  recommended_default: "Use the provided brand color as an accent and tune accessible shades around it, because raw brand colors often need adaptation for UI states.",
  options: [
    "Fixed brand palette",
    "Flexible palette around a brand color",
    "No palette yet",
    "Strict accessibility/compliance requirements",
    "Other / custom"
  ]
})
```

### Decision: Typography constraints

When to ask:
- Font choice affects brand voice, licensing, performance, platform consistency, or existing design-system compliance.

Do not ask when:
- The user wants a practical UI and no brand font is available.

Recommended default:
- Use a high-quality system UI or neutral sans-serif for interface text.

Reason:
- It improves legibility, performance, and cross-platform reliability.

Question tool pattern:
```js
question({
  question: "Do you have typography or font constraints I should follow?",
  recommended_default: "Use a neutral, highly legible UI typeface unless the brand needs a stronger editorial or expressive voice.",
  options: [
    "Use system UI font",
    "Use existing brand fonts",
    "Recommend a font direction",
    "No font constraints",
    "Other / custom"
  ]
})
```

### Decision: Imagery source and volatility

When to ask:
- The UI uses photos, avatars, thumbnails, hero media, user uploads, product images, or AI-generated media.

Do not ask when:
- The screen has no imagery or uses fixed icons/illustrations.

Recommended default:
- Assume production imagery is variable and design protective fallbacks.

Reason:
- User-generated or inconsistent media can destroy contrast, crop, layout rhythm, and perceived quality.

Question tool pattern:
```js
question({
  question: "What kind of imagery will this UI use?",
  recommended_default: "Assume variable production imagery and include safe crops, overlays, and fallbacks, because real images often differ from perfect mockup assets.",
  options: [
    "Curated brand photography",
    "User-uploaded images",
    "Product thumbnails",
    "Illustrations/icons only",
    "Other / custom"
  ]
})
```

### Decision: Motion appetite

When to ask:
- The user asks for animation, loading behavior, transitions, attention cues, or brand motion.

Do not ask when:
- The UI needs only standard hover/focus/loading feedback.

Recommended default:
- Subtle purposeful motion with reduced-motion support.

Reason:
- Motion can clarify continuity and perceived performance, but excessive or essential motion can distract or exclude motion-sensitive users.

Question tool pattern:
```js
question({
  question: "How much motion should this interface use?",
  recommended_default: "Use subtle, purposeful motion with reduced-motion support, because it improves feedback without distracting from the task.",
  options: [
    "Minimal/no motion",
    "Subtle functional motion",
    "Brand-forward motion",
    "High-energy/entertainment",
    "Other / custom"
  ]
})
```

### Decision: Performance/perceived speed strategy

When to ask:
- The interface has loading, AI generation, server processing, file uploads, or slow network operations.

Do not ask when:
- The UI is static or operations are instant.

Recommended default:
- Provide visible feedback quickly and use skeletons/progress/optimistic UI when appropriate.

Reason:
- Fast feedback maintains attention and confidence even when the actual operation takes longer.

Question tool pattern:
```js
question({
  question: "What kind of waiting or processing should users expect?",
  recommended_default: "Show immediate feedback and use skeletons or progress indicators for longer operations, because users need to know the system is responding.",
  options: [
    "Brief loading under a second",
    "Several seconds of processing",
    "Long-running generation/upload",
    "Unpredictable background sync",
    "Other / custom"
  ]
})
```

### Decision: Destructive and high-risk actions

When to ask:
- A flow includes deletion, irreversible changes, financial/legal commitment, privacy exposure, or data loss.

Do not ask when:
- The action is reversible, low-risk, or clearly specified.

Recommended default:
- Keep destructive actions visually secondary until the confirmation step, then make the confirmed destructive action explicit and accessible.

Reason:
- Severity alone should not dominate the main screen; user intent and recovery should determine visual prominence.

Question tool pattern:
```js
question({
  question: "How reversible is this destructive or high-risk action?",
  recommended_default: "Use a secondary treatment on the main screen and a clear confirmation for irreversible actions, because severity should be handled at the decision point.",
  options: [
    "Fully reversible/undoable",
    "Recoverable with support",
    "Irreversible",
    "Regulated/high-risk",
    "Other / custom"
  ]
})
```
