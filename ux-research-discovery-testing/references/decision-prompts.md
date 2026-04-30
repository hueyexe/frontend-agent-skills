# Decision Prompts

Use these prompts only when the missing context would materially change the research plan, critique, or recommendation. Do not ask the user to decide routine best practices.

## How to use

- Ask at most one or two questions before making progress.
- Always include a recommended default.
- If the user does not answer, proceed with the default and label it as an assumption.
- Prefer asking about decisions, outcomes, audience, constraints, and access—not methodology jargon.

### Decision: Product or design decision

When to ask:
- The request says “do research,” “critique this,” “improve UX,” or “test this” but does not identify what decision the work should inform.

Do not ask when:
- The user already names a concrete decision, such as choosing between two onboarding concepts or finding checkout usability issues.

Recommended default:
- Focus the work on the next product/design decision that could improve the primary user task and business outcome.

Reason:
- Research is only useful if it changes a decision.

Question tool pattern:
```js
question({
  question: "What decision should this research or UX critique help you make?",
  recommended_default: "Decide the next product/design change that best improves the user's primary task while supporting the business outcome.",
  options: [
    "Decide what problem or opportunity to pursue",
    "Decide which solution or concept to build",
    "Find usability issues in an existing UI/prototype",
    "Prioritize improvements for a shipped product",
    "Other / custom"
  ]
})
```

### Decision: Target outcome

When to ask:
- The user asks for product recommendations, prioritization, or design critique without naming the behavior or business result that matters.

Do not ask when:
- The outcome is implied by the artifact, such as checkout completion, account creation, task completion, or reduced support contact.

Recommended default:
- Use a user behavior metric that plausibly drives the business outcome.

Reason:
- Outcomes keep the agent from optimizing for outputs or taste.

Question tool pattern:
```js
question({
  question: "What user behavior or business result should improve if this work succeeds?",
  recommended_default: "Use one behavior metric tied to business value, such as task completion, activation, retention, conversion, successful self-service, or reduced support contact.",
  options: [
    "Complete a critical task with fewer errors",
    "Activate or onboard successfully",
    "Convert or purchase",
    "Retain or repeat use",
    "Reduce support/operations burden",
    "Other / custom"
  ]
})
```

### Decision: Research stage

When to ask:
- It is unclear whether the team needs discovery, concept evaluation, usability testing, or post-launch measurement.

Do not ask when:
- The user explicitly asks for interviews, a usability test, analytics interpretation, or a critique of an existing UI.

Recommended default:
- If no solution exists, use discovery. If a solution exists, use evaluative testing. If live behavior data exists, combine metrics with qualitative follow-up.

Reason:
- The research method should match the maturity of the product decision.

Question tool pattern:
```js
question({
  question: "What stage is the work in right now?",
  recommended_default: "Use discovery if the problem is unclear; use usability testing if a design exists; use analytics plus qualitative follow-up if the product is live.",
  options: [
    "Exploring a problem/opportunity",
    "Comparing concepts or solution directions",
    "Testing a prototype or existing UI",
    "Understanding live product behavior",
    "Other / custom"
  ]
})
```

### Decision: Primary participant group

When to ask:
- The user has not identified who the research should include.

Do not ask when:
- The artifact is clearly for a known user role already described in the prompt.

Recommended default:
- Recruit people who recently performed or attempted the target task.

Reason:
- Recent behavior provides richer, less speculative evidence.

Question tool pattern:
```js
question({
  question: "Who should we learn from first?",
  recommended_default: "Start with people who recently tried to complete the target task, then add one contrasting group if it may reveal hidden constraints.",
  options: [
    "Current users performing the target task",
    "Prospective users or non-users",
    "Competitor users / recent switchers",
    "Internal operators, admins, support, or sales",
    "Other / custom"
  ]
})
```

### Decision: Participant contrast

When to ask:
- The product affects multiple roles, has a marketplace/workflow ecosystem, or the user asks who to recruit.

Do not ask when:
- A quick usability test on one critical flow is sufficient.

Recommended default:
- Include the primary user plus one contrast group: non-user, competitor loyalist, expert, novice, affected stakeholder, or extreme user.

Reason:
- Contrast reveals assumptions and influencing factors that typical users alone may hide.

Question tool pattern:
```js
question({
  question: "Should we include a contrasting participant group to reveal hidden constraints?",
  recommended_default: "Include one contrast group when the product has multiple roles, strong competitors, or high uncertainty.",
  options: [
    "No, focus only on primary users",
    "Add non-users or prospective users",
    "Add competitor loyalists/recent switchers",
    "Add extreme/expert/novice users",
    "Add affected stakeholders such as admins/support/approvers",
    "Other / custom"
  ]
})
```

### Decision: Research access

When to ask:
- The user asks for a research plan but access to users, analytics, artifacts, or prototype is unknown.

Do not ask when:
- The task is to draft a generic guide/script using stated assumptions.

Recommended default:
- Use the strongest available evidence now, label confidence, and recommend the next smallest research loop.

Reason:
- Research plans must be realistic under access constraints.

Question tool pattern:
```js
question({
  question: "What access do we currently have to users, artifacts, analytics, or prototypes?",
  recommended_default: "Use the strongest available evidence now, flag confidence, and propose the smallest next research loop.",
  options: [
    "Direct access to users",
    "Prototype or live product available for testing",
    "Analytics/support tickets/session recordings available",
    "Only stakeholders/internal knowledge available",
    "Other / custom"
  ]
})
```

### Decision: Method depth and timeline

When to ask:
- The user asks for a plan but timeline, rigor, or budget may change method choice.

Do not ask when:
- The user asks for a lightweight plan or immediate critique.

Recommended default:
- Use a one-week lightweight loop: plan, recruit, 5 sessions, same-day synthesis, decision memo.

Reason:
- A fast loop is practical for product teams and prevents research from becoming a blocker.

Question tool pattern:
```js
question({
  question: "How much time and rigor should this research use?",
  recommended_default: "Run a lightweight one-week loop with 5 sessions, collaborative synthesis, and a decision memo.",
  options: [
    "Very fast: 1-2 days, directional",
    "Lightweight: about 1 week",
    "Moderate: 2-4 weeks with stronger recruiting/synthesis",
    "High rigor: formal study, larger sample, or statistics",
    "Other / custom"
  ]
})
```

### Decision: Artifact fidelity

When to ask:
- The user wants usability testing or critique but it is unclear what artifact exists.

Do not ask when:
- The user uploaded or described the artifact.

Recommended default:
- Test the lowest fidelity artifact that can reveal the target risk.

Reason:
- Early, cheap tests avoid expensive rework.

Question tool pattern:
```js
question({
  question: "What artifact should we evaluate?",
  recommended_default: "Test the lowest fidelity artifact that can reveal the key risk: sketch for concept, prototype for flow, live UI for real behavior.",
  options: [
    "Sketch/wireframe",
    "Clickable prototype",
    "Live UI",
    "Competitor or analogous product",
    "No artifact yet",
    "Other / custom"
  ]
})
```

### Decision: Critical tasks

When to ask:
- Usability testing is requested but critical tasks are not specified.

Do not ask when:
- The artifact has an obvious primary task and the user asked for quick critique.

Recommended default:
- Test the highest-risk task that must succeed for the product to deliver value.

Reason:
- Not all tasks are equal; high-impact failures should drive test design.

Question tool pattern:
```js
question({
  question: "Which task is most important to test first?",
  recommended_default: "Start with the task whose failure would block user value or business value.",
  options: [
    "Find/understand information",
    "Sign up/onboard/configure",
    "Complete a transaction/submission",
    "Recover from an error or edge case",
    "Use a repeated workflow",
    "Other / custom"
  ]
})
```

### Decision: Success criteria

When to ask:
- The user needs a usability test, benchmark, or post-launch measurement but has no success criteria.

Do not ask when:
- A qualitative directional test is enough and you can use task completion/errors/confidence by default.

Recommended default:
- Track task completion, major errors, time/effort, confidence, and qualitative cause of failure.

Reason:
- Metrics make findings actionable and comparable without pretending small samples are statistically representative.

Question tool pattern:
```js
question({
  question: "What should count as success for the test or recommendation?",
  recommended_default: "Track task completion, severe errors, time/effort, confidence, and the reason behind failures.",
  options: [
    "Task completion and severe errors",
    "Speed/efficiency",
    "Comprehension and confidence",
    "Conversion or activation metric",
    "Accessibility task success",
    "Other / custom"
  ]
})
```

### Decision: Accessibility and inclusion coverage

When to ask:
- The product is broadly used, the user asks for a test plan, or accessibility needs may change recruiting, prototype requirements, or implementation guidance.

Do not ask when:
- The user explicitly asks for an accessibility review; proceed with accessibility as the core focus.

Recommended default:
- Include baseline accessibility coverage: keyboard, screen reader, contrast, reduced motion, cognitive load, language clarity, mobile constraints.

Reason:
- Accessibility is a user context and product quality requirement, not a final checklist.

Question tool pattern:
```js
question({
  question: "Are there known accessibility needs, assistive technologies, language needs, or situational constraints to include?",
  recommended_default: "Include baseline coverage for keyboard, screen reader, magnification, contrast, reduced motion, cognitive load, language clarity, and mobile constraints.",
  options: [
    "Known assistive technology users",
    "Known cognitive/language/access constraints",
    "No known data; include baseline accessibility coverage",
    "This is an accessibility-specific study",
    "Other / custom"
  ]
})
```

### Decision: Stakeholder involvement

When to ask:
- Research findings need to influence a team, roadmap, executive decision, or implementation.

Do not ask when:
- The user only needs a personal critique or quick script.

Recommended default:
- Invite product, design, engineering, and one decision-maker to observe or synthesize.

Reason:
- Direct exposure increases action and reduces report-only handoff.

Question tool pattern:
```js
question({
  question: "Who needs to observe or participate so the findings lead to action?",
  recommended_default: "Include product, design, engineering, and one decision-maker in observation or synthesis.",
  options: [
    "Product/design/engineering trio",
    "Include executives or roadmap owners",
    "Include support/sales/operations",
    "Keep research contained for now",
    "Other / custom"
  ]
})
```

### Decision: Privacy, sensitivity, and consent

When to ask:
- The study involves personal data, minors, health/finance/legal topics, workplace surveillance, screenshots, recordings, or sensitive contexts.

Do not ask when:
- The plan can safely use anonymous low-risk feedback and no recording.

Recommended default:
- Use informed consent, minimal data collection, anonymized reporting, and separate consent from NDA/incentive terms.

Reason:
- Ethical failures damage participants, product trust, and research validity.

Question tool pattern:
```js
question({
  question: "Does this study involve sensitive data, vulnerable participants, recordings, minors, or regulated domains?",
  recommended_default: "Use informed consent, minimal data collection, anonymized reporting, and separate consent from NDA/incentive terms.",
  options: [
    "No sensitive data expected",
    "Recordings or screenshots involved",
    "Personal, financial, health, legal, or workplace data involved",
    "Minors or vulnerable participants involved",
    "Other / custom"
  ]
})
```

### Decision: Frontend/design-system constraints

When to ask:
- Recommendations will become frontend implementation or design-system work and constraints are unknown.

Do not ask when:
- The user only asks for a research plan.

Recommended default:
- Prefer semantic, accessible, responsive, design-system-aligned components and identify instrumentation for the target outcome.

Reason:
- UX recommendations that cannot be implemented accessibly and maintainably are not good product decisions.

Question tool pattern:
```js
question({
  question: "What frontend or design-system constraints should the recommendation respect?",
  recommended_default: "Use existing accessible components and tokens where possible, preserve semantic HTML, and add instrumentation for the target behavior.",
  options: [
    "Existing design system/components",
    "Specific frontend framework constraints",
    "Performance or mobile constraints",
    "Analytics/instrumentation requirements",
    "No known constraints",
    "Other / custom"
  ]
})
```
