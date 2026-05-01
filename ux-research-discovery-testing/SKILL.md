---
name: ux-research-discovery-testing
description: "Use when planning UX research, discovery interviews, usability tests, synthesis, or evidence-backed product recommendations."
---

# UX Research Discovery Testing

## Purpose

Help an agent make better product, UX, UI, and frontend recommendations by grounding them in user goals, observed behavior, business outcomes, and testable evidence. Use this skill to choose just-enough research methods, write interview and usability-test plans, synthesize findings, identify opportunities, and explain evidence-backed product decisions.

It is an operating manual for doing practical research under real product constraints.

## When to use this skill

Use this skill when the user asks you to:

- Plan discovery, customer interviews, field visits, contextual inquiry, or stakeholder interviews.
- Review, critique, redesign, or generate a UI where user behavior, task success, accessibility, or product outcomes matter.
- Create an interview guide, screener, usability-test script, research plan, synthesis framework, opportunity map, journey map, persona, task flow, or evidence-backed recommendation.
- Decide what to build, improve, remove, or test next.
- Evaluate a prototype, live UI, design system component, onboarding flow, form, navigation model, dashboard, empty state, error flow, or content hierarchy.
- Turn qualitative notes, analytics, survey findings, support tickets, screenshots, or observations into product decisions.

## When not to use this skill

Do not use this skill as the primary tool when the task is only:

- Visual UI styling with no user goal, task, behavior, or product decision involved.
- Brand identity, illustration, or aesthetic exploration unrelated to use.
- Statistical analysis requiring rigorous sampling, inferential statistics, or experimental design beyond lightweight product research.
- Legal, medical, or regulated human-subjects research advice. In those cases, recommend qualified review and use only general UX planning guidance.
- Production frontend coding where the user has already specified the user problem, behavior, accessibility requirements, and interaction design.

## Core principles

1. **Start with the decision, not the method.** Identify the product, design, or frontend decision the research must inform. Choose only the research activities that reduce uncertainty for that decision.

2. **Separate business questions from research questions.** Convert “What should we build?” into researchable questions about people, tasks, motivations, contexts, constraints, and current workarounds.

3. **Prefer behavior and context over preference claims.** Treat “Do you like it?” and “What do you want?” as weak evidence. Ask for recent, specific stories; observe work; test tasks; and inspect real artifacts.

4. **Balance customer value and business value.** Do not optimize only for shipped features, executive preferences, or isolated user requests. Frame work around outcomes: a behavior change that creates customer value and supports the business.

5. **Use the smallest credible research loop.** Default to lightweight, iterative research that can influence the next decision. Research should accelerate learning, not become theater.

6. **Make assumptions explicit.** Before research or critique, list assumptions about users, contexts, motivations, constraints, accessibility needs, and business goals. Convert risky assumptions into testable questions.

7. **Use mixed evidence.** Qualitative work explains why and how; quantitative evidence shows what, where, how often, and whether a change moved a metric. Do not ask one method to answer every kind of question.

8. **Recruit for behavior, role, and contrast.** Recruit people who have relevant experience with the task or context. Include adjacent roles, non-users, recent defectors, competitor loyalists, extreme users, and affected stakeholders when they can reveal constraints or opportunities.

9. **Research is a team sport.** Involve product, design, engineering, content, accessibility, support, sales, and other stakeholders where useful. Direct exposure to users is more persuasive than a long report.

10. **Synthesize visibly.** Use maps, affinity clusters, opportunity trees, task flows, journey maps, screenshots, and short evidence notes to create shared understanding.

11. **Protect participants.** Explain the purpose, consent, recording, confidentiality, incentives, and use of findings. Separate consent from NDAs and incentives. Respect participant time and welfare.

12. **Recommend action, not just findings.** Findings should lead to prioritized decisions, risks, next tests, and product changes.

## Default recommendations

Use these defaults unless the user provides stronger context.

| Area | Default recommendation | Why this is usually best | Override when |
|---|---|---|---|
| Research goal | Define one decision and one primary research question before choosing methods. | Prevents unfocused research and over-asking. | The user is explicitly exploring a broad product area. |
| Discovery method | Start with 5-8 semi-structured interviews or contextual sessions anchored in recent real experiences. | Fast enough for product work and rich enough to reveal behaviors, context, language, and assumptions. | The task is safety-critical, highly regulated, or needs statistical confidence. |
| Interview cadence | For ongoing product teams, schedule weekly customer contact. For one-off work, run the smallest batch that can inform the next decision. | Continuous exposure prevents stale assumptions. | The team has no participant access; then use secondary research, support logs, analytics, or internal experts while flagging lower confidence. |
| Interview style | Use a guide, but keep it flexible. Ask about recent stories, examples, artifacts, workarounds, and context. | Specific episodes beat abstract opinions. | The study requires comparable metrics across participants. |
| Usability testing | Test realistic tasks with representative or high-learning participants; ask participants to think aloud only when it does not distort the task. | Task performance reveals usability issues better than opinions. | The product context makes think-aloud unsafe, unrealistic, or too disruptive. |
| Sample size | Start small, iterate, and keep recruiting. Use small tests to find issues, not to estimate population prevalence. | Small batches expose high-impact issues quickly. | The user needs prevalence, segmentation, or statistical confidence. |
| Participant criteria | Recruit by behavior, task, context, and relationship to the product, not demographics alone. | Demographics rarely describe the job-to-be-done or mental model by themselves. | Demographics directly affect access, safety, needs, culture, or equity. |
| Synthesis | Analyze immediately after sessions with multiple team members. Separate observations from interpretations and recommendations. | Reduces memory loss, bias, and report-only handoff. | Confidentiality or team structure prevents broad participation. |
| Opportunity framing | Map findings into outcomes, opportunities, candidate solutions, assumptions, and tests. | Keeps teams from jumping from one quote to a feature. | The user only needs a quick usability defect list. |
| Evidence strength | Treat observed behavior, task success, analytics, and controlled tests as stronger evidence than preference surveys. | Reduces credulity and self-report bias. | The research question is about awareness, sentiment, brand perception, or stated expectations. |
| Reporting | Produce a concise decision memo: decision, evidence, confidence, recommended action, alternatives, risks, and next test. | Stakeholders need action, not a research archive. | The user requests a formal report or compliance artifact. |
| Accessibility | Include accessibility needs as research criteria and testable requirements from the start. | Accessibility changes task context, interaction cost, and implementation choices. | Never fully omit; only scale depth to project scope. |

## Required user questions

Ask only when the answer materially changes the research plan, critique, or recommendation. Use the recommended default first; do not ask routine best-practice questions.

### Ask when the product decision is unclear

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

### Ask when the target user or context is unclear

```js
question({
  question: "Who is the primary user or participant group, and what real-world context should we design or test for?",
  recommended_default: "Recruit people who recently tried to complete the target task, plus one adjacent or contrasting group if it may reveal hidden constraints.",
  options: [
    "Current users performing the target task",
    "Prospective users or non-users",
    "Competitor users / recent switchers",
    "Internal users, operators, support, or admins",
    "Other / custom"
  ]
})
```

### Ask when the success outcome is unclear

```js
question({
  question: "What user behavior or business outcome should improve if this work succeeds?",
  recommended_default: "Use one user behavior metric tied to a business outcome, such as task completion, activation, retention, conversion, reduced support contact, or successful self-service.",
  options: [
    "Task completion / fewer errors",
    "Activation or onboarding success",
    "Conversion or revenue action",
    "Retention or repeat use",
    "Support reduction or operational efficiency",
    "Other / custom"
  ]
})
```

### Ask when participant access or research constraints are unclear

```js
question({
  question: "What access do we have to users, artifacts, analytics, and the product/prototype?",
  recommended_default: "Use the best available evidence now, flag confidence, and propose the next smallest research loop.",
  options: [
    "Can interview or observe users directly",
    "Can run moderated or unmoderated usability tests",
    "Have analytics/support tickets/session recordings",
    "Only have stakeholder knowledge right now",
    "Other / custom"
  ]
})
```

### Ask when accessibility needs may change the plan

```js
question({
  question: "Are there known accessibility needs, assistive technologies, language needs, or situational constraints that must be included?",
  recommended_default: "Plan for keyboard, screen reader, magnification, color contrast, reduced motion, cognitive load, mobile constraints, and diverse language proficiency unless the product scope clearly narrows this.",
  options: [
    "Known assistive technology users",
    "Known cognitive/language/access constraints",
    "No known data; include baseline accessibility coverage",
    "This is an accessibility-specific study",
    "Other / custom"
  ]
})
```

## Workflow

### 1. Triage the request

Identify:

- Product or feature area.
- Stage: discovery, concept, prototype, shipped UI, redesign, or ongoing optimization.
- Decision to be made.
- Target users, affected roles, and context.
- Existing evidence and artifacts.
- Risks: accessibility, privacy, safety, trust, business impact, technical constraints.
- Deadline and research access.

If any of these are missing but essential, ask one focused question. Otherwise proceed with assumptions and label them.

### 2. Choose the research mode

Use the research mode that matches the decision:

- **Generative / exploratory:** Use when the team does not yet know the right problem or opportunity. Use interviews, field visits, diary/logging, stakeholder interviews, secondary research, support-ticket review, and competitive observation.
- **Descriptive / explanatory:** Use when the problem exists but the team needs to understand the workflow, context, user groups, mental models, tasks, or constraints.
- **Evaluative:** Use when there is a concept, prototype, UI, flow, or competitor experience to test. Use task-based usability testing, heuristic review, accessibility review, cognitive walkthroughs, and prototype tests.
- **Causal / quantitative:** Use when a shipped product has measurable behavior and the team needs to know whether a change affects a metric. Use analytics, A/B tests, funnel analysis, and task metrics, while using qualitative work to explain why.

### 3. Frame the decision and assumptions

Before writing a plan or recommendation:

1. State the business outcome.
2. State the user behavior that would drive it.
3. State the target user/context.
4. List known facts.
5. List assumptions.
6. Identify the riskiest assumptions.
7. Choose the smallest method that can reduce those risks.

### 4. Plan lightweight discovery

For discovery or interviews, produce:

- Research objective.
- Research questions.
- Participant criteria based on behavior/context.
- Recruiting channels and screener questions.
- Interview/session guide.
- Consent and recording plan.
- Roles: moderator, note-taker, observer, recruiter, analyst.
- Schedule and synthesis plan.
- Decision output: opportunity map, findings memo, journey/task map, or recommendations.

### 5. Conduct interviews or contextual sessions

Use these moderation rules:

- Start with consent, purpose, timing, confidentiality, recording, and permission to skip questions.
- Build rapport with just enough small talk.
- Ask for recent, concrete stories: “Tell me about the last time…”
- Ask follow-ups before moving on.
- Use silence after asking and after answers.
- Use the participant’s language.
- Ask about artifacts, tools, environment, interruptions, workarounds, triggers, relationships, and constraints.
- Avoid putting answers in the question.
- Avoid teaching, fixing, selling, or defending the design during the session.
- Save participant questions or troubleshooting for the end.
- Capture exact phrases where useful for interface language.

### 6. Plan usability testing

For usability tests, produce:

- Test objective and product decision.
- Artifact under test: sketch, prototype, live UI, competitor flow, or component.
- Participants and why they are high-learning.
- Critical tasks in realistic wording.
- Success criteria: completion, errors, time/effort, confidence, comprehension, accessibility, and severe friction.
- Moderator script.
- Data capture plan.
- Severity rubric.
- Post-test synthesis and next action.

Task wording should describe the participant’s goal, not the UI steps. Do not ask participants to find a specific button unless the button is the object being tested.

### 7. Synthesize evidence

During synthesis:

1. Review notes and recordings quickly.
2. Capture observations, not interpretations, first.
3. Cluster behaviors, quotes, obstacles, motivations, workarounds, tools, triggers, environments, and relationships.
4. Distinguish what happened, what it means, and what to do.
5. Map findings to opportunities, assumptions, and candidate tests.
6. Prioritize by customer impact, business impact, frequency/confidence, risk, accessibility impact, and implementation effort.
7. State confidence level and what would change your mind.

Use visual artifacts when they help: affinity diagram, journey map, task flow, opportunity solution tree, screenshot forensics, mental model map, workflow diagram, or severity matrix.

### 8. Make research-backed recommendations

Every recommendation should include:

- Product decision or change.
- Evidence used.
- User problem or opportunity.
- Expected behavior change.
- Business value.
- Accessibility and inclusion implications.
- Frontend/design-system implications.
- Tradeoffs and risks.
- Confidence level.
- Next test or metric.

Prefer “Based on the evidence, do X next because…” over “Users said they want X.”

## Decision framework

### Evidence ladder

Use this ladder to communicate confidence:

1. **Observed behavior in context:** field visits, contextual inquiry, usability tests, support/session evidence.
2. **Behavioral product data:** analytics, funnels, search logs, task success, A/B tests.
3. **Artifacts and workarounds:** screenshots, spreadsheets, notes, tickets, forms, tools people actually use.
4. **Structured self-report:** interviews about recent behavior, diary studies, well-designed surveys.
5. **Weak preference claims:** likes, hypotheticals, feature requests, generic survey responses.

Do not discard weaker evidence; label it appropriately and triangulate it.

### Method selection

- Need to know **who users are and what they do**: interview, observe, contextual inquiry, stakeholder/support review.
- Need to know **whether a UI works**: task-based usability test, accessibility review, heuristic review.
- Need to know **what changed after launch**: analytics, funnels, A/B test, support-volume change, task metric.
- Need to know **why a metric changed**: combine analytics with interviews, session review, usability testing, or support analysis.
- Need to know **what to build next**: opportunity discovery, experience map, opportunity solution tree, assumption mapping, concept tests.
- Need to know **how to prioritize**: compare opportunities, not just solutions; use customer impact, business outcome, reversibility, risk, and effort.

### Prioritization rules

- Prioritize opportunities before solutions.
- Treat early product decisions as reversible when possible.
- Compare sets of opportunities or solutions instead of evaluating one idea in isolation.
- Test assumptions, not whole ideas, when a smaller test can reduce the risk.
- Start with high-impact usability and accessibility blockers.
- Do not delay all action while waiting for perfect data.

## Practical rules

### Research planning

- Write a one-paragraph problem statement before any guide or test script.
- Include only methods that support the decision.
- Start with a pilot or pre-pilot when the script, task, prototype, or logistics are uncertain.
- Record known assumptions and potential biases.
- Plan synthesis before collecting data.

### Interview guides

A good guide includes:

1. Intro, consent, purpose, timing.
2. Participant background relevant to the task.
3. Main body organized by research question.
4. Specific recent stories and demonstrations.
5. Artifact/environment probes.
6. Optional projection or ideal-experience prompts, clearly treated as exploratory.
7. Wrap-up: missed topics, participant questions, incentive/next steps.

### Usability test scripts

A good script includes:

1. Intro and consent.
2. Reminder that the design is being tested, not the participant.
3. Scenario setup.
4. Realistic tasks.
5. Success criteria and note-taking fields.
6. Non-leading probes.
7. Post-task questions about confidence and expectations.
8. Wrap-up.

### Synthesis

- Analyze as a group when possible.
- Separate observations from interpretations.
- Keep traceability back to source notes.
- Turn repeated patterns into insights.
- Turn insights into product opportunities, design principles, and testable changes.
- Avoid solving too early during analysis.

### Reporting

Default to a concise memo or annotated artifact:

- Summary.
- Top findings.
- Evidence and confidence.
- Recommended decisions.
- Prioritized fixes or opportunities.
- Risks and tradeoffs.
- Next research/test.
- Appendix only when useful.

## Accessibility and inclusion requirements

Always treat accessibility as part of user context, not as a final compliance pass.

- Include participants with relevant disabilities, assistive technologies, device constraints, language needs, and situational limitations when the product is broadly used.
- Ask about actual tools and settings: keyboard use, screen reader, magnification, voice input, reduced motion, captions, contrast, translation, mobile constraints, and cognitive load.
- Test critical tasks with keyboard-only interaction when UI behavior is relevant.
- Inspect focus order, visible focus states, labels, roles, error messages, dynamic updates, reduced-motion behavior, and touch target size.
- Avoid research plans that exclude people because recruiting them is inconvenient.
- Provide accommodations, accessible prototypes, clear consent, and flexible session logistics.
- Flag when research evidence lacks accessibility coverage and propose a follow-up.

## Frontend implementation guidance

When recommendations affect frontend work, include implementation implications:

- Use semantic HTML for controls, navigation, headings, forms, lists, tables, and landmarks.
- Preserve native behavior unless a custom component is necessary.
- Specify keyboard interaction, focus management, ARIA only where needed, and screen-reader announcements for dynamic states.
- Design and test empty, loading, error, offline, success, permission, and partial-data states.
- Align recommendations with design tokens, component APIs, responsive breakpoints, and existing design-system patterns.
- Add analytics or event instrumentation for the target behavior, but do not instrument without a decision-relevant metric.
- Consider performance and latency as UX variables, especially for task success and perceived trust.
- Include content requirements: labels, helper text, error copy, confirmation messages, and progressive disclosure.
- Avoid recommendations that require brittle one-off UI if a reusable component or pattern is appropriate.

## Critique workflow

When reviewing an existing UI, prototype, or frontend implementation, inspect in this order:

1. **User goal and product outcome:** What task is this supposed to support and what behavior should change?
2. **Context and audience fit:** Who is using it, where, under what constraints, with what prior knowledge?
3. **Evidence:** What is known from research, analytics, support, stakeholder knowledge, or observed behavior?
4. **Task flow:** Can users start, progress, recover, and finish?
5. **Information hierarchy:** Are the most important decisions, content, and actions obvious?
6. **Interaction clarity:** Are controls, states, validation, navigation, and feedback understandable?
7. **Accessibility and inclusion:** Can users operate and understand it across input modes, assistive tech, language needs, and cognitive load?
8. **Content and terminology:** Does the UI use language users understand from their context?
9. **Visual design only as it supports use:** Does spacing, contrast, grouping, typography, and emphasis clarify the task?
10. **Frontend feasibility:** Can this be built maintainably with semantic, responsive, performant, design-system-aligned components?
11. **Risks and next test:** What evidence is missing, and what is the smallest credible test?

## Creation workflow

When creating a research plan, UX recommendation, or design improvement:

1. Clarify the decision and desired outcome.
2. Identify users, contexts, and constraints.
3. List assumptions and unknowns.
4. Choose the smallest research or testing method that can reduce risk.
5. Create the guide, script, task list, or analysis structure.
6. Include recruiting, consent, roles, and logistics.
7. Define evidence to collect and success criteria.
8. Include accessibility coverage.
9. Plan synthesis and reporting.
10. Recommend next actions and how to measure impact.

## Quality checklist

Before finalizing, verify:

- The product/design decision is explicit.
- The research question is answerable.
- The method matches the decision.
- Participant criteria are behavior/context-based.
- Questions are neutral and anchored in real experiences.
- Usability tasks are realistic and not step-by-step instructions.
- Consent, recording, privacy, incentives, and accessibility accommodations are addressed.
- Synthesis separates observations, interpretations, and recommendations.
- Recommendations are prioritized by impact, confidence, risk, and effort.
- Business value and user value are both represented.
- Frontend implications are practical and accessible.
- Limitations and confidence are stated.

## Common mistakes to avoid

- Asking users what they want and treating the answer as a roadmap.
- Asking whether users like a design.
- Starting with a feature idea instead of a decision or opportunity.
- Using research to validate a foregone conclusion.
- Recruiting only easy internal participants.
- Confusing demographics with behavior.
- Running usability tests without realistic tasks.
- Helping participants during the test.
- Producing long reports that arrive too late to affect decisions.
- Treating analytics as self-explanatory.
- Treating interviews as statistically representative.
- Optimizing the current UI into a local maximum while ignoring larger opportunities.
- Forgetting accessibility until after design or implementation.
- Over-asking the user for context when a safe default is available.

## How to explain recommendations to the user

Use this structure:

1. **Recommendation:** State the action clearly.
2. **Why:** Tie it to user behavior and business outcome.
3. **Evidence:** Identify the source and confidence level.
4. **Tradeoff:** Explain what is gained and what risk remains.
5. **Next step:** Propose the smallest test, implementation step, or metric.

Example:

> Recommend testing the checkout error flow before redesigning the entire checkout. The likely risk is not visual polish but task recovery: users need to understand what failed, how to fix it, and whether their payment was charged. Start with five task-based sessions on the current flow and prototype the top two fixes. Measure completion rate, error recovery, and support contacts after launch.
