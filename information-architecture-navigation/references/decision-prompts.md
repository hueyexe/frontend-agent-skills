# Decision Prompts for `information-architecture-navigation`

Use these prompts only when the answer changes the IA. Do not ask users to decide routine usability requirements.

## Discovery prompts

### Decision: Primary product goal

When to ask:
- The user asks for navigation, taxonomy, search, or IA work but has not provided the product purpose or primary user task.

Do not ask when:
- The task is already clear from supplied screenshots, specs, or copy.

Recommended default:
- Task-first organization for the user's most common/high-value job.

Reason:
- Task-first IA usually maps better to user intent than internal departments or feature ownership.

Question tool pattern:
```js
question({
  question: "What is the primary job users need this IA to support?",
  recommended_default: "Organize around the highest-frequency user task first, then fit secondary business or content goals around it.",
  options: [
    "Find a known item quickly",
    "Browse and learn what is available",
    "Compare and narrow many options",
    "Complete a step-by-step workflow",
    "Other / custom"
  ]
})
```

### Decision: Primary audience and vocabulary

When to ask:
- Labels, category names, or taxonomy depend on whether users are novices, experts, internal staff, customers, developers, clinicians, students, etc.

Do not ask when:
- The target audience and terminology are already explicit.

Recommended default:
- Plain user-facing language with specialist terms only where the primary audience expects them.

Reason:
- Labels are most useful when they match the user's vocabulary and predict content accurately.

Question tool pattern:
```js
question({
  question: "Who is the primary audience, and what vocabulary should labels use?",
  recommended_default: "Use plain, familiar terms unless the audience is expert and expects domain-specific terminology.",
  options: [
    "General public / new users",
    "Existing customers or returning users",
    "Internal staff / operators",
    "Domain experts / technical users",
    "Other / custom"
  ]
})
```

### Decision: Content scope and content types

When to ask:
- The agent must design a structure but does not know the types, quantity, or lifecycle of content.

Do not ask when:
- The content inventory, sitemap, or objects are supplied.

Recommended default:
- Start with a lightweight content model: object type, title, summary, owner, status, date, topic, audience, and related items.

Reason:
- IA decisions become concrete when content objects and metadata are explicit.

Question tool pattern:
```js
question({
  question: "What content or objects must this structure organize?",
  recommended_default: "Use a lightweight content model first, then add metadata only where it supports navigation, filtering, or search.",
  options: [
    "Pages/articles/docs",
    "Products/catalog items",
    "Tasks/workflows/settings",
    "People/teams/locations",
    "Other / custom"
  ]
})
```

### Decision: Business or compliance constraints

When to ask:
- The IA may be constrained by legal, compliance, sales, support, brand, SEO, analytics, migration, or operational needs.

Do not ask when:
- The request is a quick critique or conceptual recommendation and no constraints are implied.

Recommended default:
- Prioritize user findability while preserving legally required, revenue-critical, or migration-critical paths.

Reason:
- Some structures must reflect obligations outside the user's mental model, but those constraints should be explicit.

Question tool pattern:
```js
question({
  question: "Are there business, compliance, SEO, migration, or operational constraints the IA must preserve?",
  recommended_default: "Optimize for user findability, while preserving required legal/commercial paths and existing URLs where they matter.",
  options: [
    "No major constraints",
    "Must preserve existing URLs or SEO",
    "Must satisfy compliance/legal categories",
    "Must reflect business/product-line priorities",
    "Other / custom"
  ]
})
```

## Structure prompts

### Decision: Dominant organization scheme

When to ask:
- Multiple organization schemes could fit and the choice changes labels/navigation.

Do not ask when:
- The content clearly belongs to a single scheme, such as date-based logs or product categories.

Recommended default:
- Task-first for applications and support; topic-first for learning/reference; facet-first for large catalogs.

Reason:
- Different schemes match different user intents.

Question tool pattern:
```js
question({
  question: "Which organizing principle should be primary?",
  recommended_default: "Use task-first for apps/support, topic-first for reference content, and facets for large catalogs with many attributes.",
  options: [
    "By task / user goal",
    "By topic / subject",
    "By audience / role",
    "By lifecycle / process stage",
    "Other / custom"
  ]
})
```

### Decision: Hierarchy versus facets

When to ask:
- Items can plausibly live in multiple categories or users need to narrow by several attributes.

Do not ask when:
- The content set is small or categories are mutually exclusive.

Recommended default:
- Use hierarchy for stable parent-child structure; use facets for multidimensional narrowing.

Reason:
- A single tree forces "one right place"; facets preserve multiple findability paths.

Question tool pattern:
```js
question({
  question: "Do items mostly belong in one stable category, or do users need to find them through multiple attributes?",
  recommended_default: "Use a simple hierarchy for stable categories; add facets when users commonly narrow by multiple attributes.",
  options: [
    "Mostly one stable category",
    "Multiple attributes matter",
    "Both: hierarchy for browsing, facets for narrowing",
    "Unsure / needs research",
    "Other / custom"
  ]
})
```

### Decision: Navigation model

When to ask:
- The agent must choose between global nav, sidebar/local nav, tabs, breadcrumbs, wizard steps, mega menu, or search-first navigation.

Do not ask when:
- The platform or existing design system clearly dictates the pattern.

Recommended default:
- Global nav for major areas, local nav for deep sections, breadcrumbs for deep hierarchy, and contextual links for related content.

Reason:
- This combination provides orientation without forcing every path into one menu.

Question tool pattern:
```js
question({
  question: "How do users usually move through this product?",
  recommended_default: "Use global navigation for major areas, local navigation for deep sections, breadcrumbs for hierarchy, and contextual links for related content.",
  options: [
    "Browse major categories",
    "Work within one deep section",
    "Follow a step-by-step process",
    "Search or filter first",
    "Other / custom"
  ]
})
```

### Decision: Cross-channel consistency

When to ask:
- The IA must work across web, mobile, native app, kiosk, voice, email, or embedded surfaces.

Do not ask when:
- The deliverable targets one platform only.

Recommended default:
- Keep the conceptual model consistent while adapting presentation and interaction per channel.

Reason:
- Users need coherent meaning across channels, but device constraints and task context change interaction.

Question tool pattern:
```js
question({
  question: "Should the same IA work across multiple platforms or channels?",
  recommended_default: "Keep the conceptual categories consistent across channels, then adapt presentation for each device and context.",
  options: [
    "Web only",
    "Responsive web",
    "Web and native mobile",
    "Multiple channels with different tasks",
    "Other / custom"
  ]
})
```

## Label and taxonomy prompts

### Decision: Label source of truth

When to ask:
- The agent is renaming categories, labels, headings, or navigation items and there may already be a vocabulary.

Do not ask when:
- No existing terminology is implied and labels can be proposed with rationale.

Recommended default:
- Preserve validated labels; replace unclear/internal labels with user-tested or plain-language alternatives.

Reason:
- Label changes can break recognition, search, support documentation, and analytics.

Question tool pattern:
```js
question({
  question: "Is there an existing vocabulary, taxonomy, or label set I should preserve?",
  recommended_default: "Preserve validated labels and replace only unclear, duplicate, or internal terms.",
  options: [
    "No existing vocabulary",
    "Use current product labels where possible",
    "Use research/customer language",
    "Use regulated/domain terminology",
    "Other / custom"
  ]
})
```

### Decision: Tone of labels

When to ask:
- The label tone could reasonably be plain/professional versus branded/playful, and the product has a defined voice.

Do not ask when:
- The IA is safety-, finance-, healthcare-, developer-, or enterprise-critical; use clear and plain labels.

Recommended default:
- Professional, plain, and warm.

Reason:
- Navigation labels are functional promises; clarity usually beats personality.

Question tool pattern:
```js
question({
  question: "What personality should navigation labels communicate?",
  recommended_default: "Professional, plain, and warm, because navigation labels need to be predictable before they are expressive.",
  options: [
    "Plain and utilitarian",
    "Professional but warm",
    "Expert/domain-specific",
    "Branded/playful",
    "Other / custom"
  ]
})
```

### Decision: Taxonomy governance

When to ask:
- The recommendation includes controlled vocabularies, tags, metadata fields, aliases, deprecations, or editorial search tuning.

Do not ask when:
- The IA is small, static, and can be maintained directly in code/content.

Recommended default:
- Lightweight governance: owner, allowed values, aliases, review cadence, and deprecation process.

Reason:
- Taxonomies decay without maintenance.

Question tool pattern:
```js
question({
  question: "Who will maintain taxonomy terms, aliases, metadata, and deprecated labels after launch?",
  recommended_default: "Assign a lightweight owner and review cadence for any controlled vocabulary or metadata used in navigation/search.",
  options: [
    "Product/design owner",
    "Content/editorial owner",
    "Support/operations owner",
    "No owner yet",
    "Other / custom"
  ]
})
```

## Search and discovery prompts

### Decision: Need for search

When to ask:
- The user asks whether to add search, or content scale/dynamism is unclear.

Do not ask when:
- The product clearly has a large, dynamic, or known-item content set.

Recommended default:
- Add search only when browsing alone cannot support known-item lookup, large scale, or dynamic content.

Reason:
- Search is powerful but costly; it requires indexing, result design, tuning, and maintenance.

Question tool pattern:
```js
question({
  question: "What role should search play in this product?",
  recommended_default: "Use search when content is large, dynamic, or users know what they want; otherwise improve navigation and labels first.",
  options: [
    "Primary entry point",
    "Secondary support for known-item lookup",
    "Scoped search within a section",
    "No search for now",
    "Other / custom"
  ]
})
```

### Decision: Search scope and zones

When to ask:
- Search could span heterogeneous content types or separate repositories.

Do not ask when:
- Search scope is obvious from a single collection or page.

Recommended default:
- Search the smallest coherent useful scope first; add zones for meaningfully different content types.

Reason:
- Mixed result sets can create apples-and-oranges confusion.

Question tool pattern:
```js
question({
  question: "What should search include by default?",
  recommended_default: "Search the smallest coherent useful scope first, and offer scoped zones when content types differ meaningfully.",
  options: [
    "Entire product/site",
    "Current section only",
    "Specific content type only",
    "Federated search across multiple systems",
    "Other / custom"
  ]
})
```

### Decision: Result ranking and sorting

When to ask:
- Results can be ranked by relevance, date, popularity, editorial priority, availability, price, rating, or business rules.

Do not ask when:
- A standard relevance-first result set is sufficient.

Recommended default:
- Rank by relevance, expose sorting only for decision criteria users understand.

Reason:
- Too many sort controls increase effort; invisible business ranking can erode trust.

Question tool pattern:
```js
question({
  question: "What should make a search result appear first?",
  recommended_default: "Rank by user relevance first, then expose sort controls for date, popularity, price, or status only when users need them.",
  options: [
    "Text relevance",
    "Newest/recently updated",
    "Popularity/usage",
    "Business/editorial priority",
    "Other / custom"
  ]
})
```

### Decision: Facets and filters

When to ask:
- The result set is large and the relevant narrowing attributes are unknown.

Do not ask when:
- The content model or analytics already identifies the key attributes.

Recommended default:
- Start with 3-6 high-signal facets that users understand and metadata can support.

Reason:
- Facets are only useful when labels and values are trustworthy.

Question tool pattern:
```js
question({
  question: "Which attributes do users actually use to narrow or compare results?",
  recommended_default: "Start with 3-6 high-signal facets that users understand and that the content can support reliably.",
  options: [
    "Type/category",
    "Audience/role",
    "Status/availability",
    "Date/location",
    "Other / custom"
  ]
})
```

### Decision: No-results recovery

When to ask:
- The product domain has special recovery paths, support channels, or content request workflows.

Do not ask when:
- A generic no-results state is sufficient.

Recommended default:
- Show what was searched, offer spelling/synonym suggestions, relax filters, provide popular/related links, and offer support/contact if appropriate.

Reason:
- No-results states are high-friction points where users need next steps, not blame.

Question tool pattern:
```js
question({
  question: "What should users do if search or filters return no results?",
  recommended_default: "Offer query correction, filter removal, related/popular paths, and support/contact only when users still cannot recover.",
  options: [
    "Try alternate terms",
    "Remove or relax filters",
    "Browse related categories",
    "Contact support / request content",
    "Other / custom"
  ]
})
```

## Implementation prompts

### Decision: URL/state persistence

When to ask:
- The IA includes search, filters, tabs, category states, or pagination on the web.

Do not ask when:
- The state clearly should be shareable/bookmarkable, or the product is native-only.

Recommended default:
- Persist navigational state in the URL.

Reason:
- Shareable, restorable states improve wayfinding and reduce frustration.

Question tool pattern:
```js
question({
  question: "Should users be able to share, bookmark, or return to this exact navigation/search/filter state?",
  recommended_default: "Persist category, query, filters, sort, and pagination in the URL for web products unless privacy or security prevents it.",
  options: [
    "Yes, make states shareable",
    "Only category/page state",
    "No, state is private or temporary",
    "Native app only",
    "Other / custom"
  ]
})
```

### Decision: Accessibility target

When to ask:
- The user is making implementation commitments or the product has regulatory obligations.

Do not ask when:
- Giving general design advice; apply accessible defaults.

Recommended default:
- WCAG-aware accessible structure with semantic HTML, keyboard support, visible focus, and accessible names.

Reason:
- Accessibility is a baseline for navigation and findability.

Question tool pattern:
```js
question({
  question: "Is there a specific accessibility compliance target or assistive-technology context to support?",
  recommended_default: "Use accessible defaults: semantic structure, keyboard support, visible focus, accessible names, and clear headings.",
  options: [
    "Accessible defaults only",
    "WCAG 2.2 AA",
    "Screen-reader/keyboard-heavy audience",
    "Regulated/public-sector requirement",
    "Other / custom"
  ]
})
```

### Decision: Design-system integration

When to ask:
- The agent is producing implementation guidance and existing components may constrain choices.

Do not ask when:
- The user asked only for IA strategy or critique.

Recommended default:
- Reuse existing design-system navigation/search/filter components, extending them only for missing IA behavior.

Reason:
- IA is easier to maintain when structural patterns are consistent across product surfaces.

Question tool pattern:
```js
question({
  question: "Should recommendations use an existing design system or component library?",
  recommended_default: "Reuse existing navigation, search, breadcrumb, tab, menu, and filter components where they support the IA; extend only for missing behavior.",
  options: [
    "Use existing design system",
    "Create new reusable components",
    "Frontend prototype only",
    "No implementation constraints",
    "Other / custom"
  ]
})
```

### Decision: Analytics and validation

When to ask:
- The agent proposes changes to search, labels, taxonomy, or navigation and success measurement is not defined.

Do not ask when:
- The user only needs a quick conceptual answer.

Recommended default:
- Track task success, search/no-results, navigation paths, filter usage, top exits, and support contacts.

Reason:
- IA decisions need evidence and ongoing tuning.

Question tool pattern:
```js
question({
  question: "How should we validate whether the IA works?",
  recommended_default: "Use task testing plus analytics for search/no-results, nav paths, filter use, top exits, and support contacts.",
  options: [
    "Usability/task testing",
    "Analytics/search logs",
    "Tree testing/card sorting",
    "Support/contact deflection",
    "Other / custom"
  ]
})
```
