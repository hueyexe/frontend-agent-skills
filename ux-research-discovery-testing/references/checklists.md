# Checklists

Use these checklists before finalizing a research plan, interview guide, usability test, UX critique, or recommendation.

## Discovery/context checklist

- The product or feature area is named.
- The decision the research should inform is explicit.
- The desired user behavior or business outcome is stated.
- The primary user group is defined by behavior, task, and context.
- Adjacent or affected roles are considered: chooser, approver, admin, support, operator, influencer, non-user, competitor user.
- Existing evidence is listed: prior research, analytics, support tickets, sales calls, session recordings, stakeholder knowledge, screenshots, prototypes.
- Known assumptions are separated from facts.
- The riskiest assumptions are identified.
- Accessibility, language, device, connectivity, environment, and assistive-technology contexts are considered.
- Business, technical, legal, brand, design-system, and timeline constraints are listed.
- The proposed research method directly supports the decision.
- The expected output is clear: opportunity map, test findings, prioritized issues, decision memo, journey map, task flow, persona, or implementation guidance.

## Research plan checklist

- Problem statement uses an outcome verb such as identify, describe, evaluate, compare, or prioritize.
- Research questions are answerable through the chosen method.
- The plan avoids trying to answer prevalence, causality, and motivation with one lightweight method.
- Participant criteria are based on recent behavior or relevant context, not demographics alone.
- Recruiting channel and screener are specified.
- Screener questions do not reveal the “right” answers too obviously.
- Incentive, scheduling, reminders, and no-show handling are planned.
- Roles are assigned: lead, moderator, note-taker, recruiter/scheduler, observer, analyst/documenter.
- Consent, recording, privacy, and data handling are addressed.
- A pilot or pre-pilot is planned when the script, prototype, tasks, or logistics are uncertain.
- Synthesis is scheduled before data collection starts.
- Stakeholders who need to act on findings have an observation or debrief role.

## Interview guide checklist

- The guide starts with purpose, timing, consent, recording, confidentiality, and permission to skip questions.
- The opening questions build rapport without collecting irrelevant biography.
- Questions are neutral and do not contain the desired answer.
- Questions ask about recent specific experiences before asking general opinions.
- The guide includes prompts for triggers, goals, steps, tools, workarounds, people involved, environment, constraints, interruptions, emotions, and outcomes.
- The guide asks participants to show artifacts or demonstrate behavior when possible.
- The guide uses participant-friendly language rather than internal terminology.
- The guide includes follow-up prompts such as “Tell me more,” “What happened next,” and “Why was that important?”
- Hypothetical or future-state questions are clearly treated as exploratory, not reliable predictions.
- The moderator is instructed not to pitch, teach, fix, or defend the design.
- The wrap-up asks what important topic was missed.
- Post-session note cleanup and immediate synthesis are planned.

## Usability test checklist

- The artifact under test is identified: sketch, prototype, live UI, competitor flow, or component.
- The test objective is tied to a decision.
- Participants match the task context.
- Tasks are realistic scenarios, not instructions to click specific UI elements.
- The most critical task is tested first or protected from fatigue.
- Success criteria are defined: completion, major errors, assistance, time/effort, confidence, comprehension, accessibility blockers.
- The script reminds participants the design is being tested, not them.
- The moderator avoids leading, rescuing, or explaining during the task.
- The note template captures observed behavior, quotes, errors, workarounds, confusion points, and recovery paths.
- Accessibility checks include keyboard, focus order, labels, error announcements, contrast, motion, touch target size, and screen-reader-relevant behavior where applicable.
- Observers know when to stay silent and how to record notes.
- The severity scale is defined before the test.
- Findings will be prioritized by severity, frequency/confidence, task importance, and implementation effort.
- The plan includes a follow-up test or validation path for major fixes.

## Synthesis checklist

- Notes, recordings, screenshots, and artifacts are organized with consistent names.
- The team reviews data while it is fresh.
- Observations are separated from interpretations.
- Exact participant language is captured where it affects labels, content, or mental models.
- Findings are traceable to source sessions or artifacts.
- Patterns are grouped by behavior, motivation, barrier, trigger, workaround, tool, relationship, environment, and task.
- Outliers are considered rather than discarded automatically.
- The synthesis distinguishes user needs from requested solutions.
- Opportunities are framed from the user's perspective.
- Assumptions behind solution ideas are identified.
- Evidence strength and confidence are stated.
- Accessibility and inclusion findings are not buried under “edge cases.”
- Recommendations are prioritized and connected to the product decision.

## Opportunity/discovery checklist

- The business outcome is stated.
- The user behavior that drives the outcome is stated.
- The opportunity is expressed as a user need, pain point, desire, barrier, or unmet job—not as a feature.
- The opportunity map/tree separates outcome, opportunities, solutions, assumptions, and tests.
- The team has considered multiple opportunities before choosing one.
- The team has considered multiple solution directions before choosing one.
- The selected opportunity has evidence, not just executive enthusiasm.
- Prioritization considers customer value, business value, risk, reversibility, accessibility impact, and effort.
- The next test targets an assumption, not the entire solution when a smaller test would suffice.
- Stakeholders can understand the path from evidence to decision.

## UX/design quality checklist

- The primary user goal is clear.
- The primary action is visually and semantically stronger than secondary actions.
- The UI follows the user's task flow rather than the organization's internal structure.
- Content and labels use user language.
- Required information appears before it is needed.
- Feedback is timely and specific.
- Errors help users prevent, recognize, and recover from problems.
- Empty, loading, error, offline, and success states are designed.
- Navigation and wayfinding match user expectations.
- Grouping, spacing, and hierarchy reduce cognitive load.
- The design does not rely on color alone.
- The design avoids unnecessary steps, choices, and fields.
- The design supports novice users without blocking efficient expert use.
- The critique separates evidence-backed issues from taste preferences.

## Accessibility checklist

- Semantic HTML or platform-native semantics can represent the interaction.
- All interactive elements are keyboard reachable and operable.
- Focus order matches visual and task order.
- Visible focus indicators are present and high contrast.
- Form fields have programmatic labels, helper text, and error associations.
- Error messages state what happened and how to fix it.
- Dynamic updates are announced appropriately.
- Color contrast supports text and important graphical information.
- The design does not require color alone, hover alone, pointer precision, sound alone, or motion.
- Motion can be reduced or avoided for users who prefer reduced motion.
- Touch targets and spacing support mobile and motor constraints.
- Content is written in clear language and does not depend on insider vocabulary.
- Screen reader, magnification, zoom, and reflow implications are considered.
- Research participants with relevant accessibility needs are included or the limitation is explicitly flagged.

## Implementation feasibility checklist

- The recommendation can be built with semantic HTML or native controls where possible.
- Custom components have defined roles, states, properties, keyboard behavior, focus management, and announcements.
- Existing design-system components/tokens are reused unless there is a reason not to.
- The responsive behavior is specified for key breakpoints and content lengths.
- Loading, error, empty, success, disabled, and permission states are specified.
- Content requirements are included: labels, helper text, validation, confirmation, microcopy.
- Performance risks are identified for flows where delay affects trust or completion.
- Analytics/instrumentation events match the target behavior and avoid collecting unnecessary personal data.
- The recommendation avoids brittle one-off implementation.
- QA can test the critical task, accessibility behaviors, and edge states.

## Final response checklist

- The answer states assumptions and limitations.
- The recommendation is concise and action-oriented.
- The user value and business value are both clear.
- Evidence strength and confidence are clear.
- Tradeoffs are acknowledged.
- The next step is the smallest useful action.
- The response does not overclaim from small qualitative samples.
- The response does not present user preferences as facts.
- The response does not paste unnecessary long source text.
- Accessibility and frontend implications are included when relevant.
