# Anti-patterns

Prioritize these because AI agents commonly produce them when asked for UX, UI, frontend, or research help.

## Anti-pattern: Asking users what they want

What it looks like:
- “What feature do you want?”
- “Would you use this?”
- “Do you like this design?”
- Turning feature requests directly into roadmap items.

Why it fails:
- People often cannot accurately predict future behavior or explain hidden motivations.
- Preference claims are weak evidence and can hide the underlying need.

Better approach:
- Ask for recent specific stories and observed behavior.
- Ask what happened, what triggered it, what tools were used, what got in the way, and what workaround happened.
- If a user proposes a solution, interpret it as evidence of an underlying need.

Ask the user when:
- The product decision depends on whether to discover needs or evaluate a specific solution.

## Anti-pattern: Starting with a solution

What it looks like:
- Jumping straight to features, UI components, or visual redesign.
- Treating stakeholder requests as the problem statement.
- Testing a fully formed solution when a risky assumption could be tested faster.

Why it fails:
- The team may build the wrong thing efficiently.
- Early solution fixation narrows learning and hides better alternatives.

Better approach:
- Frame the business outcome, user behavior, opportunity, assumptions, and smallest test.
- Compare multiple opportunities or solution directions before choosing.

Ask the user when:
- The user asks for a redesign or feature but has not identified the user problem or outcome.

## Anti-pattern: Research theater

What it looks like:
- Running research because it “looks research-y.”
- Using a lab, survey, or focus group because stakeholders expect it.
- Producing a polished report that does not change a decision.

Why it fails:
- It wastes time and can legitimize weak evidence.
- It turns research into politics or decoration instead of decision support.

Better approach:
- Choose methods based on the decision and evidence needed.
- Use concise outputs that show evidence, confidence, recommended action, and next test.

Ask the user when:
- Stakeholder expectations conflict with the most appropriate lightweight method.

## Anti-pattern: One-person research silo

What it looks like:
- The researcher disappears, returns with a report, and expects the team to comply.
- Designers and engineers do not observe sessions or join synthesis.
- Findings are treated as the researcher’s opinion.

Why it fails:
- Teams are less likely to act on findings they did not experience.
- Critical domain knowledge from engineering, content, support, and design is lost.

Better approach:
- Involve the team in planning, observing, note-taking, and synthesis.
- Use visual artifacts and debriefs to create shared ownership.

Ask the user when:
- The recommendation must persuade a team or stakeholder group.

## Anti-pattern: Recruiting by demographics alone

What it looks like:
- “We need women age 25-34.”
- Recruiting whoever is easiest internally.
- Ignoring non-users, competitor users, experts, novices, admins, support, or other affected roles.

Why it fails:
- Demographics often do not predict task behavior, mental model, or context.
- Typical users alone may not reveal the forces shaping behavior.

Better approach:
- Recruit by recent behavior, task, context, relationship to the product, and contrast.
- Include the whole system of roles when the product affects more than one person.

Ask the user when:
- Participant selection is unclear or multiple user roles may matter.

## Anti-pattern: Leading questions and over-talking

What it looks like:
- Asking questions that imply the desired answer.
- Filling silence.
- Talking about yourself.
- Explaining the product during a test.
- Asking participants to validate the team’s opinion.

Why it fails:
- It contaminates evidence and suppresses real stories.
- Participants may try to please the moderator or avoid conflict.

Better approach:
- Ask neutral questions, stay silent, use follow-ups, and let participants struggle during tests.
- Use natural language and participant vocabulary.

Ask the user when:
- A script or guide contains leading wording.

## Anti-pattern: Fixing the participant’s problem during the session

What it looks like:
- Helping participants complete a usability task.
- Taking product support questions during an interview.
- Teaching the intended interaction before observing.

Why it fails:
- It prevents the team from seeing where the design fails.
- It changes task behavior and makes the evidence unreliable.

Better approach:
- Remind yourself that the goal is to learn.
- Save help, answers, or troubleshooting for the end unless participant welfare requires intervention.

Ask the user when:
- The study mixes support, training, sales, and research goals.

## Anti-pattern: Treating small qualitative studies as statistical proof

What it looks like:
- Claiming “80% of users want X” from five interviews.
- Prioritizing solely by count of mentions.
- Reporting percentages without sample and method limitations.

Why it fails:
- Small qualitative samples reveal patterns and causes, not population prevalence.
- Counts can hide severity, context, and task importance.

Better approach:
- Report patterns, examples, severity, confidence, and next evidence needed.
- Use quantitative methods when prevalence or precise comparison matters.

Ask the user when:
- They need prevalence, benchmarking, or statistically defensible prioritization.

## Anti-pattern: Analytics without why

What it looks like:
- Treating funnels, clicks, bounce rate, or conversion as self-explanatory.
- Optimizing a metric without understanding the task or context.
- Running A/B tests before knowing what problem is being solved.

Why it fails:
- Quantitative data shows what happened, not necessarily why.
- Local optimization can miss larger product opportunities.

Better approach:
- Pair analytics with qualitative research, usability testing, support evidence, or session review.
- Use A/B testing for specific measurable changes after the problem is understood.

Ask the user when:
- The user asks to optimize a metric but the cause of behavior is unknown.

## Anti-pattern: Opportunity backlog as feature backlog

What it looks like:
- Listing feature ideas under “opportunities.”
- Prioritizing by stakeholder excitement or implementation ease.
- Moving from one quote to one feature.

Why it fails:
- It skips the user need and makes the team overconfident in solutions.
- It prevents comparing opportunities and assumptions.

Better approach:
- Write opportunities as user needs, pain points, desires, barriers, or unmet jobs.
- Map candidate solutions and assumptions beneath each opportunity.

Ask the user when:
- The user asks for roadmap prioritization but the inputs are feature ideas.

## Anti-pattern: Verbose report that arrives too late

What it looks like:
- A long report delivered after the sprint/decision has moved on.
- Findings without recommended actions.
- Dense data with no visual synthesis.

Why it fails:
- Teams do not have time or context to act.
- The output becomes an archive instead of a decision tool.

Better approach:
- Use a concise decision memo, annotated screenshots, severity list, journey map, opportunity tree, or dashboard.
- Involve the team before the report is written.

Ask the user when:
- Stakeholders require a formal report, but immediate action is also needed.

## Anti-pattern: Polished personas without evidence

What it looks like:
- Personas invented from stereotypes.
- Persona details that do not affect design decisions.
- Demographic-heavy profiles with no goals, behaviors, environment, or constraints.

Why it fails:
- Fictional artifacts can create false confidence.
- Teams may optimize for personality details rather than task needs.

Better approach:
- Build personas from research patterns, goals, behavior, environment, and mental models.
- Use as few personas as possible and keep them decision-relevant.

Ask the user when:
- The user asks for personas but no research evidence exists.

## Anti-pattern: Accessibility as post-hoc compliance

What it looks like:
- Adding ARIA or color contrast after design is complete.
- Excluding disabled users from research.
- Treating assistive technology as an edge case.

Why it fails:
- Accessibility affects task context, component choice, content, interaction, and implementation.
- Retrofits are more expensive and less effective.

Better approach:
- Include accessibility needs in participant criteria, task design, prototype fidelity, and implementation guidance from the start.
- Test keyboard, focus, labels, dynamic updates, contrast, motion, and error recovery.

Ask the user when:
- Known accessibility needs or assistive technology contexts may change recruiting or implementation.

## Anti-pattern: Testing only your own product

What it looks like:
- Ignoring competitors or workaround tools.
- Assuming competition is limited to direct market rivals.
- Redesigning without seeing how users solve the problem today.

Why it fails:
- The strongest competitor may be an existing workaround or habit.
- Competitive testing reveals conventions, expectations, and opportunities.

Better approach:
- Test competitor or analogous flows for the same task when relevant.
- Compare strengths, weaknesses, conventions, and unmet needs.

Ask the user when:
- The product category has strong competitors or users already have established workarounds.

## Anti-pattern: Treating the experience map as final truth

What it looks like:
- A beautiful journey map is created and then frozen.
- The map represents internal opinion instead of evolving evidence.
- Teams debate wording instead of learning from users.

Why it fails:
- Maps are working models, not reality.
- Over-polishing can discourage updates and hide uncertainty.

Better approach:
- Start with rough individual maps, merge them, identify gaps, use interviews to update, and treat the map as provisional.

Ask the user when:
- The team asks for a journey map but has limited evidence.
