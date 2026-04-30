# Principle Cards for `information-architecture-navigation`

## Principle: Findability and understanding are inseparable

Rule:
- Design structures that both help users find information and understand what the information means in context.

Why it matters:
- Navigation that gets users to a page but leaves them disoriented still fails the task.

Use when:
- Designing navigation, content hubs, documentation, dashboards, search, or settings.

Do not use when:
- The task is purely visual styling with no structure or findability impact.

Default recommendation:
- Start every IA recommendation by naming the user task, current context, destination, and next step.

Ask the user when:
- The user goal or product context is missing.

Question prompt:
```js
question({
  question: "What is the primary job users need this IA to support?",
  recommended_default: "Organize around the highest-frequency user task first, because findability and understanding both depend on task context.",
  options: ["Find a known item", "Browse/learn", "Compare/filter", "Complete a workflow", "Other / custom"]
})
```

Agent behavior:
- Before proposing menus or labels, identify the user's task, entry point, and success condition.

## Principle: Balance users, content, and context

Rule:
- Evaluate IA decisions through users, content, and context instead of applying a generic structure.

Why it matters:
- Good IA depends on who uses it, what content exists, and what the organization/platform can maintain.

Use when:
- Starting any critique or redesign.

Do not use when:
- The user asks for a tiny label rewrite with all context already supplied.

Default recommendation:
- Use a small research frame: primary audience, top tasks, content types, constraints, and maintenance owner.

Ask the user when:
- Any of those variables would change the recommendation.

Question prompt:
```js
question({
  question: "What should I optimize for first: user task, content model, or business/technical constraint?",
  recommended_default: "Optimize for the user's primary task first, then reconcile content and constraints.",
  options: ["User task", "Content model", "Business constraint", "Technical/platform constraint", "Other / custom"]
})
```

Agent behavior:
- State assumptions and use defaults instead of asking for every missing detail.

## Principle: Use hierarchy for stable structure, facets for multidimensional choice

Rule:
- Use a tree only when categories are stable and meaningful. Use facets when users need multiple routes to the same items.

Why it matters:
- A single hierarchy breaks down when items belong in several meaningful groups.

Use when:
- Organizing catalogs, documentation, resource libraries, support centers, dashboards, or search results.

Do not use when:
- The content set is tiny or facets would rely on unreliable metadata.

Default recommendation:
- Start with a simple hierarchy for major areas, then add facets for high-volume lists and search results.

Ask the user when:
- It is unclear whether content belongs in one category or many.

Question prompt:
```js
question({
  question: "Do items mostly belong in one stable category, or do users need to find them through multiple attributes?",
  recommended_default: "Use hierarchy for stable parent-child categories; use facets when multiple attributes are important.",
  options: ["One stable category", "Multiple attributes", "Both hierarchy and facets", "Unsure / needs research", "Other / custom"]
})
```

Agent behavior:
- Do not force a single "correct" location for multidimensional content.

## Principle: Labels are predictions

Rule:
- A label should let users predict what they will get before they click or act.

Why it matters:
- Labels are the visible expression of the organization scheme.

Use when:
- Naming navigation items, headings, tabs, filters, categories, and actions.

Do not use when:
- The label is legally fixed; then clarify with helper text or synonyms.

Default recommendation:
- Use short, plain, familiar labels with parallel grammar.

Ask the user when:
- The audience uses specialist vocabulary or a validated term set exists.

Question prompt:
```js
question({
  question: "Is there an existing vocabulary or audience-specific terminology I should preserve?",
  recommended_default: "Use plain user-facing labels unless a validated/domain vocabulary exists.",
  options: ["No existing vocabulary", "Use current product labels", "Use customer research language", "Use regulated/domain terminology", "Other / custom"]
})
```

Agent behavior:
- Replace vague catch-alls with specific labels and provide aliases for common alternate terms.

## Principle: Navigation should create a sense of place

Rule:
- Every screen should communicate current location, available routes, related paths, and how to recover from a wrong turn.

Why it matters:
- Users experience information environments as places; place cues reduce confusion.

Use when:
- Designing global nav, local nav, breadcrumbs, sidebar nav, tabs, flows, or contextual links.

Do not use when:
- A one-screen, single-task interface has no meaningful hierarchy; still provide state and exit cues.

Default recommendation:
- Use global nav for major areas, local nav for section depth, breadcrumbs for hierarchy, and contextual links for related content.

Ask the user when:
- The movement pattern is unclear.

Question prompt:
```js
question({
  question: "How do users usually move through this product?",
  recommended_default: "Combine global, local, breadcrumb, and contextual navigation according to task depth.",
  options: ["Browse categories", "Work inside one section", "Follow steps", "Search/filter first", "Other / custom"]
})
```

Agent behavior:
- In critiques, explicitly test "Where am I? What is here? Where can I go?"

## Principle: Search is a full discovery system

Rule:
- Design search as query entry, indexed scope, query support, ranking/sorting, result display, filtering, and recovery.

Why it matters:
- A search box without scope, metadata, results design, or no-results behavior does not support discovery.

Use when:
- Content is large, dynamic, heterogeneous, or known-item lookup is common.

Do not use when:
- Content is small and navigation can solve the task more clearly.

Default recommendation:
- Provide simple search first, add scopes/facets progressively, and design no-results recovery.

Ask the user when:
- Search scope or ranking priorities are unclear.

Question prompt:
```js
question({
  question: "What should search include by default?",
  recommended_default: "Search the smallest coherent useful scope first, and add zones for meaningfully different content types.",
  options: ["Entire product/site", "Current section", "Specific content type", "Federated search", "Other / custom"]
})
```

Agent behavior:
- Include search states and analytics in recommendations, not just the input.

## Principle: Invisible IA must be managed

Rule:
- Document and maintain metadata, controlled vocabularies, synonyms, best bets, redirects, and deprecated terms.

Why it matters:
- Hidden rules shape visible findability and can silently decay.

Use when:
- Search, filters, content management, taxonomy, or migration is involved.

Do not use when:
- The product is a short-lived prototype with no maintained content.

Default recommendation:
- Assign an owner and lightweight governance for any controlled vocabulary or search tuning.

Ask the user when:
- Ongoing ownership is unknown.

Question prompt:
```js
question({
  question: "Who will maintain taxonomy terms, aliases, metadata, redirects, and search tuning after launch?",
  recommended_default: "Assign a lightweight owner and review cadence for any invisible IA that affects findability.",
  options: ["Product/design", "Content/editorial", "Operations/support", "No owner yet", "Other / custom"]
})
```

Agent behavior:
- Flag governance as an implementation requirement, not an optional extra.

## Principle: Design bottom-up entry paths

Rule:
- Structure individual content pages so users arriving from search or external links can orient and continue.

Why it matters:
- Users often bypass top-down navigation and land deep in the system.

Use when:
- Designing templates, article pages, docs, product detail pages, or support content.

Do not use when:
- The surface is a modal or step in a closed workflow; still provide context and exit.

Default recommendation:
- Add descriptive titles, headings, chunks, metadata, related links, and next steps.

Ask the user when:
- Template/CMS constraints are unknown.

Question prompt:
```js
question({
  question: "Are content templates or CMS fields constrained?",
  recommended_default: "Use titles, headings, summaries, metadata, related links, and next steps to support deep-entry users.",
  options: ["No major constraints", "Fixed CMS template", "Design-system components only", "Engineering constraints", "Other / custom"]
})
```

Agent behavior:
- Never evaluate IA only from the homepage.

## Principle: IA deliverables need multiple views

Rule:
- Represent IA through the right artifact for the audience: sitemap, content model, wireframe, metadata matrix, vocabulary table, flow, or style guide.

Why it matters:
- IA is abstract; one diagram rarely communicates all important relationships.

Use when:
- Producing documentation, specs, or handoff guidance.

Do not use when:
- The user only needs a quick verbal recommendation.

Default recommendation:
- Provide at least a sitemap/structure view plus a page/template behavior view for implementation work.

Ask the user when:
- The deliverable audience is unclear.

Question prompt:
```js
question({
  question: "Who needs to use the IA deliverable?",
  recommended_default: "Create the simplest artifact that helps the next team act: sitemap for structure, wireframe/template for behavior, metadata matrix for search/filtering.",
  options: ["Design/product", "Engineering/frontend", "Content/editorial", "Stakeholders/executives", "Other / custom"]
})
```

Agent behavior:
- Match the output format to the decision it must support.
