# Principle Cards

These cards consolidate the reusable lessons from the uploaded sources into agent behavior.

## Principle: Frame the decision before the method

Rule:
- Start by identifying the decision, research problem, target user/context, and expected output. Then choose the method.

Why it matters:
- Method-first research wastes time and can produce findings that do not change a product decision.

Use when:
- Planning research, critiquing a UI, choosing between concepts, or recommending next steps.

Do not use when:
- The user only asks for a narrowly specified deliverable and already provides the decision context.

Default recommendation:
- Write a one-sentence decision statement and one primary research question.

Ask the user when:
- The decision is missing and cannot be safely inferred.

Question prompt:
- `question({ question: "What decision should this research or UX critique help you make?", recommended_default: "Decide the next product/design change that best improves the user's primary task while supporting the business outcome.", options: ["Decide what problem/opportunity to pursue", "Decide which solution to build", "Find usability issues", "Prioritize shipped-product improvements", "Other / custom"] })`

Agent behavior:
- Do not draft a method-heavy plan until the decision and question are clear. If missing, ask once or proceed with a stated assumption.

## Principle: Separate business questions from research questions

Rule:
- Translate broad business questions into researchable questions about people, tasks, motivations, constraints, and context.

Why it matters:
- “What should we build?” is not directly answerable by users; “How do people currently solve this and where do they struggle?” is.

Use when:
- The user asks about roadmap, features, redesign, product-market fit, or opportunity discovery.

Do not use when:
- The request is purely evaluative and the test task is already clear.

Default recommendation:
- Convert the business question into 3-5 research questions before writing interview or test materials.

Ask the user when:
- Business outcome or intended user behavior is unclear.

Question prompt:
- `question({ question: "What user behavior or business result should improve if this work succeeds?", recommended_default: "Use one behavior metric tied to business value, such as completion, activation, retention, conversion, self-service, or support reduction.", options: ["Task completion", "Activation/onboarding", "Conversion/revenue", "Retention/repeat use", "Support reduction", "Other / custom"] })`

Agent behavior:
- Show the translation from business decision to research question so the user can see why the method fits.

## Principle: Prefer observed behavior over preferences

Rule:
- Treat behavior, context, artifacts, task performance, and recent stories as stronger evidence than likes, hypotheticals, and generic feature requests.

Why it matters:
- People often report idealized or socially acceptable answers; behavior reveals constraints and workarounds.

Use when:
- Writing interview questions, interpreting survey results, critiquing findings, or designing tests.

Do not use when:
- The research question is genuinely about preference, brand association, or sentiment; even then, label evidence appropriately.

Default recommendation:
- Ask “Tell me about the last time…” and “Show me how…” before asking opinions.

Ask the user when:
- They want preference data to drive a high-risk product decision.

Question prompt:
- `question({ question: "Do you need to understand actual behavior or stated preference for this decision?", recommended_default: "Study actual behavior first; use stated preference only as secondary evidence.", options: ["Actual behavior/task success", "Motivations and context", "Preference/sentiment", "Both, triangulated", "Other / custom"] })`

Agent behavior:
- Rewrite leading or preference questions into behavior-based prompts.

## Principle: Use continuous, small learning loops

Rule:
- Prefer frequent lightweight customer contact and iterative tests over one large, late research phase.

Why it matters:
- Product decisions happen continuously; stale or one-time research decays quickly.

Use when:
- The team owns an ongoing product, roadmap, or design system.

Do not use when:
- The domain requires formal longitudinal research, regulatory review, or high statistical confidence before action.

Default recommendation:
- For product teams, schedule weekly customer contact and synthesize continuously. For one-off projects, run the smallest credible loop.

Ask the user when:
- User access, cadence, or team availability is unknown.

Question prompt:
- `question({ question: "What research cadence is realistic for this team?", recommended_default: "Use weekly customer contact for ongoing product teams; use a one-week lightweight loop for one-off decisions.", options: ["Weekly continuous interviews/tests", "One-week lightweight loop", "One-time study", "No user access yet", "Other / custom"] })`

Agent behavior:
- Recommend a cadence and recruiting mechanism, not just a one-time plan.

## Principle: Recruit for behavior, context, and contrast

Rule:
- Recruit participants based on what they do, recently did, are trying to do, or are affected by—not demographics alone.

Why it matters:
- Behavioral contrast reveals hidden influences, roles, and constraints that typical-user sampling can miss.

Use when:
- Planning interviews, usability tests, diary studies, or discovery.

Do not use when:
- Demographic criteria directly affect access, legal requirements, safety, culture, or equity; then combine demographics with behavior.

Default recommendation:
- Start with people who recently attempted the target task; add one contrasting group if uncertainty is high.

Ask the user when:
- The target user or participant criteria are not specified.

Question prompt:
- `question({ question: "Who should we learn from first?", recommended_default: "Start with people who recently tried to complete the target task, then add one contrasting group if it may reveal hidden constraints.", options: ["Current task performers", "Prospective/non-users", "Competitor users/switchers", "Internal operators/admins/support", "Other / custom"] })`

Agent behavior:
- Draft screeners around behaviors, recency, tools, contexts, and role in the decision system.

## Principle: Use a guide, then listen beyond it

Rule:
- Prepare a field guide to align the team, but follow the participant’s story when it reveals useful evidence.

Why it matters:
- Rigid scripts miss the unexpected; unplanned conversations drift. Good interviews balance structure and curiosity.

Use when:
- Conducting interviews, contextual inquiry, stakeholder interviews, or concept exploration.

Do not use when:
- The method requires standardized task metrics or survey consistency.

Default recommendation:
- Use a semi-structured guide with intro, main topics, probes, artifacts/demonstrations, and wrap-up.

Ask the user when:
- The study requires comparability versus exploration.

Question prompt:
- `question({ question: "Should this session optimize for comparability or exploration?", recommended_default: "Use a semi-structured guide: consistent core questions with flexible follow-ups.", options: ["Comparable metrics across participants", "Exploratory discovery", "Hybrid semi-structured", "Other / custom"] })`

Agent behavior:
- Include follow-up prompts and instructions for silence, transitions, and non-leading language.

## Principle: Test tasks, not opinions

Rule:
- Usability tests should ask participants to accomplish realistic goals and observe whether they can complete them.

Why it matters:
- A user may like a design that still fails the task; a confusing flow may not be obvious until use.

Use when:
- Evaluating sketches, prototypes, live UIs, competitors, flows, forms, navigation, dashboards, or components.

Do not use when:
- The question is about brand perception or desirability; then use concept exploration and label it separately.

Default recommendation:
- Test 3-5 critical tasks with clear success criteria and severity scoring.

Ask the user when:
- The critical task is not obvious.

Question prompt:
- `question({ question: "Which task is most important to test first?", recommended_default: "Start with the task whose failure would block user value or business value.", options: ["Find/understand information", "Sign up/onboard/configure", "Complete a transaction/submission", "Recover from an error", "Use a repeated workflow", "Other / custom"] })`

Agent behavior:
- Write task scenarios in user-goal language and instruct the moderator not to help unless participant welfare requires it.

## Principle: Synthesize collaboratively and visually

Rule:
- Turn raw notes into visible patterns, maps, issue lists, opportunity trees, or annotated screenshots with the team.

Why it matters:
- Shared synthesis builds shared understanding and action. Visual artifacts make evidence easier to inspect and challenge.

Use when:
- Translating interviews/tests into recommendations or persuading stakeholders.

Do not use when:
- Confidentiality limits who can see raw data; then anonymize and synthesize with a smaller approved group.

Default recommendation:
- Run a same-day synthesis session after each batch of sessions.

Ask the user when:
- Stakeholders need to act but have not been included.

Question prompt:
- `question({ question: "Who needs to observe or join synthesis so the findings lead to action?", recommended_default: "Include product, design, engineering, and one decision-maker in observation or synthesis.", options: ["Product/design/engineering trio", "Executives/roadmap owners", "Support/sales/operations", "Keep research contained", "Other / custom"] })`

Agent behavior:
- Produce concise visual structures and trace findings back to evidence.

## Principle: Triangulate qualitative and quantitative evidence

Rule:
- Use qualitative methods to understand context and causes; use quantitative methods to monitor scale, change, and outcomes.

Why it matters:
- Numbers without stories lack explanation; stories without metrics lack scale.

Use when:
- The product is live, analytics exist, or stakeholders ask “how many” or “how much.”

Do not use when:
- There is no traffic or metric yet; use qualitative discovery or concept tests first.

Default recommendation:
- Pair analytics or survey signals with interviews/usability tests before recommending major changes.

Ask the user when:
- The required confidence level or metric is unclear.

Question prompt:
- `question({ question: "Do you need directional insight or quantified confidence for this decision?", recommended_default: "Use directional qualitative evidence for early decisions; use quantitative methods for prevalence, benchmarks, and post-launch impact.", options: ["Directional insight", "Quantified confidence", "Both, triangulated", "Other / custom"] })`

Agent behavior:
- State what each evidence source can and cannot prove.

## Principle: Prioritize opportunities before solutions

Rule:
- Express opportunities as user needs, barriers, desires, or unmet jobs; map multiple solutions beneath them.

Why it matters:
- Prioritizing feature ideas too early produces roadmaps disconnected from user and business value.

Use when:
- Creating roadmaps, redesign priorities, opportunity maps, or product recommendations.

Do not use when:
- The user only needs a narrow defect fix; then still identify the user problem briefly.

Default recommendation:
- Use an opportunity solution tree or equivalent structure: outcome → opportunities → solutions → assumptions/tests.

Ask the user when:
- The target outcome is missing.

Question prompt:
- `question({ question: "What outcome should the opportunity map support?", recommended_default: "Use one measurable user behavior tied to business value.", options: ["Activation", "Task completion", "Conversion", "Retention", "Support reduction", "Other / custom"] })`

Agent behavior:
- Rewrite feature requests into opportunity statements before prioritizing.

## Principle: Make recommendations action-ready

Rule:
- Findings should culminate in prioritized actions, confidence, risks, and next tests.

Why it matters:
- Reports that do not drive action fail even if the research was good.

Use when:
- Delivering critique, research synthesis, findings, or roadmap recommendations.

Do not use when:
- The user explicitly asks only for raw notes or transcript cleanup.

Default recommendation:
- Provide a decision memo with top findings, action, evidence, confidence, tradeoffs, and next step.

Ask the user when:
- The audience for the recommendation affects format or detail.

Question prompt:
- `question({ question: "Who will use these findings and what format will help them act?", recommended_default: "Use a concise decision memo plus annotated screenshots or a prioritized issue list.", options: ["Product/design/engineering team", "Executives/roadmap decision-makers", "Frontend implementers", "Formal research archive", "Other / custom"] })`

Agent behavior:
- Do not stop at “users struggled.” Say what to change, why, how confident to be, and how to validate.

## Principle: Treat accessibility as user context

- Skill author synthesis from source emphasis on context, behavior, and task success.

Rule:
- Include accessibility needs, assistive technology, device constraints, language, and situational limitations in research and recommendations from the beginning.

Why it matters:
- Accessibility affects task performance, content, interaction patterns, frontend implementation, and product inclusion.

Use when:
- Reviewing or creating any UI, test plan, prototype, form, flow, or component.

Do not use when:
- Never omit accessibility entirely; scale the depth to the risk and scope.

Default recommendation:
- Include baseline keyboard, screen reader, contrast, focus, motion, error recovery, and language clarity coverage.

Ask the user when:
- Known accessibility groups, assistive technologies, or compliance constraints may alter the plan.

Question prompt:
- `question({ question: "Are there known accessibility needs, assistive technologies, language needs, or situational constraints to include?", recommended_default: "Include baseline coverage for keyboard, screen reader, magnification, contrast, reduced motion, cognitive load, language clarity, and mobile constraints.", options: ["Known assistive technology users", "Known cognitive/language/access constraints", "Baseline coverage", "Accessibility-specific study", "Other / custom"] })`

Agent behavior:
- Flag evidence gaps when research excludes relevant accessibility contexts.
