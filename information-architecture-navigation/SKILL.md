---
name: information-architecture-navigation
description: "Use when organizing, critiquing, or implementing navigation, labels, taxonomy, hierarchy, search, content grouping, or wayfinding for a digital product."
---

# Information Architecture Navigation

## Purpose

Help an agent make information easier to find, navigate, and understand. Treat information architecture as a product system made from organization, labeling, navigation, search, metadata, content structure, and wayfinding. Optimize for user tasks and comprehension before visual styling.

## When to use this skill

Use this skill when the user asks you to:

- Critique or redesign navigation, menus, breadcrumbs, tabs, sidebars, search, filters, faceted browsing, category pages, documentation structure, content hubs, settings IA, onboarding flows, product dashboards, or information-dense pages.
- Create an information model, sitemap, taxonomy, label set, navigation model, content grouping, search UX, metadata schema, or IA style guide.
- Improve findability, discoverability, wayfinding, content hierarchy, cross-linking, or search result quality.
- Translate a content inventory or product feature set into a usable structure.
- Implement IA-related frontend components such as nav landmarks, search forms, breadcrumbs, filters, result lists, menus, tabs, and content templates.

## When not to use this skill

Do not use this skill as the main skill when the user is only asking for:

- Visual styling, brand expression, color, illustration, or motion with no navigation/findability impact.
- Persuasive marketing copy that does not involve content structure or labels.
- Backend search ranking algorithms, database indexing, or IR tuning beyond UX-level requirements.
- Pure content writing unless structure, headings, labels, or navigation are part of the task.

## Core principles

1. **Design for finding and understanding together.** A structure that helps users locate information should also help them understand what the product contains, where they are, and what they can do next.
2. **Start from users, content, and context.** Do not design from the company org chart alone. Inspect user tasks, actual content, business constraints, platform constraints, governance, and vocabulary.
3. **Support multiple paths when content is multidimensional.** Use hierarchy for stable, mutually exclusive structures; use facets, tags, search zones, and contextual links when users approach the same content from different angles.
4. **Make the invisible IA explicit.** Metadata, controlled vocabularies, aliases, result tuning, redirects, and editorial best bets shape the user experience even when users cannot see them.
5. **Use labels as promises.** Every label should accurately predict the content or action behind it. Prefer familiar user language over internal terms or clever branding.
6. **Give users a sense of place.** Every screen should answer: Where am I? What is here? Where can I go? What just changed? How do I get back?
7. **Treat search as a system, not a box.** Search includes the indexed content, query entry, suggestions, spelling/synonym support, result presentation, ranking/sorting/filtering, no-results recovery, and analytics.
8. **Structure content from the bottom up.** Headings, chunks, metadata, related links, and content templates should help users who enter deep from search, notifications, external links, or social sharing.
9. **Document decisions for reuse.** IA must be maintained. Capture label rules, taxonomy rules, metadata fields, navigation placement rules, and exceptions in a style guide or design-system guidance.
10. **Accessibility is part of findability.** Semantic structure, headings, landmarks, keyboard operation, visible focus, readable labels, and screen-reader names are IA requirements, not polish.

## Default recommendations

Use these defaults unless the user's product context makes another choice clearly better.

### Product goal

Default to organizing around the user's primary tasks and mental model, then reconcile business priorities second.

Override when the product is a regulated, archival, legal, or reference system where formal domain structure is the user expectation.

Ask before overriding: "Is this product primarily task-driven, reference/lookup-driven, commerce-driven, or compliance/archive-driven?"

### Audience and vocabulary

Default to plain, familiar, user-centered labels. Use internal terminology only when the target audience already uses it.

Override when the audience is expert, regulated, or domain-specific and precision matters more than beginner familiarity.

Ask before overriding: "Who is the primary audience, and what terms do they already use for these concepts?"

### Navigation model

Default to a small global navigation, local navigation for deep sections, contextual links for related content, and breadcrumbs when hierarchy is deeper than two levels.

Override when the product is a single-purpose app, a flat marketing site, or a workflow where progress navigation matters more than place navigation.

Ask before overriding: "Do users usually browse by category, perform a task step-by-step, search for a known item, or compare/filter many items?"

### Hierarchy depth

Default to broad-and-shallow enough to expose major choices without overwhelming users. Avoid deep trees unless categories are stable and predictable.

Override when the domain naturally requires hierarchy, such as documentation, file systems, policies, or catalog taxonomies.

Ask before overriding: "Are the categories stable and mutually exclusive, or do items naturally belong in multiple groups?"

### Content grouping

Default to one dominant organizing principle per view: task, topic, audience, lifecycle, chronology, geography, format, or alphabetic. Do not mix schemes in the same menu unless sections are clearly separated.

Override when a landing page intentionally offers multiple entry modes, such as "By role," "By task," and "By topic."

Ask before overriding: "Which entry mode matters most for this user at this moment?"

### Labels

Default to concise text labels with nouns for destinations and verbs for actions. Pair icons with text for primary navigation.

Override only when space is severely constrained and icons are universally recognized, tested, and accessible.

Ask before overriding: "Does the product already have validated terminology or a controlled vocabulary I should preserve?"

### Search

Default to adding search when content is large, dynamic, heterogeneous, or when users often know the thing they want. Provide a simple search box first, with scoped search or filters when content types differ.

Do not add search merely to compensate for poor organization. Fix labels, grouping, and metadata first.

Ask before implementing search-heavy UX: "What content should search cover, and are there content types that should be searched separately?"

### Facets and filters

Default to facets when users need to narrow many items by stable attributes such as type, topic, date, location, audience, status, price, format, owner, or compatibility.

Override when the set is small, the attribute data is unreliable, or filtering would create empty/meaningless combinations.

Ask before adding facets: "Which attributes do users actually use to decide among results?"

### Metadata and controlled vocabulary

Default to a lightweight controlled vocabulary for high-value fields, plus aliases/synonyms for common user language.

Override when content is low-volume, short-lived, or manually curated enough that formal vocabulary management would add more overhead than value.

Ask before formalizing vocabulary: "Who will maintain terms, aliases, metadata fields, and deprecated labels after launch?"

### Responsive and cross-channel behavior

Default to preserving the same conceptual structure across web, mobile, and other channels while adapting presentation and interaction to each device.

Override when channel context changes the user's task, such as quick mobile lookup versus desktop bulk management.

Ask before changing IA across channels: "Do users need the same tasks on every platform, or does each platform support a different job?"

### Accessibility

Default to WCAG-aware semantic structure, visible focus, keyboard navigation, accessible names, text alternatives for icons, valid heading order, and state announcements for dynamic search/filter changes.

Do not ask whether accessibility matters. Ask only when a legal or internal compliance target must be named.

### Frontend state

Default to making navigation, search queries, selected filters, sort order, and pagination shareable/restorable in URLs for web products.

Override for privacy-sensitive, ephemeral, or native-only contexts.

Ask before overriding: "Should users be able to share, bookmark, or return to this exact filtered/search state?"

## Required user questions

Ask only when the answer changes the IA. Recommend a default in the question.

Use a `question` tool or equivalent for these cases:

1. **Goal ambiguity.** If the user has not supplied the product, feature, user task, or content domain.
2. **Audience ambiguity.** If labels or taxonomy depend on specialist versus general-public vocabulary.
3. **Navigation model uncertainty.** If it is unclear whether users browse, search, filter, compare, or complete a sequence.
4. **Content/model uncertainty.** If you need to know content types, metadata, scale, lifecycle, or ownership.
5. **Search scope uncertainty.** If adding or redesigning search and the indexed content is not defined.
6. **Governance uncertainty.** If the recommendation requires ongoing taxonomy, metadata, redirects, or editorial maintenance.
7. **Platform/accessibility constraints.** If the implementation differs substantially across web, native, kiosk, voice, or assistive technology contexts.
8. **Legacy constraints.** If migration, existing URLs, analytics, SEO, or design-system compatibility may constrain the structure.

Do not ask routine questions such as whether labels should be clear, whether the design should be accessible, or whether users should understand navigation. Apply the default.

## Workflow

### A. Critique existing IA or UI

Inspect in this order:

1. **User goal and entry point.** Identify the user's job, prior context, and likely entry route: homepage, deep link, search result, notification, ad, bookmark, or internal workflow.
2. **Content inventory and content types.** List the main objects, actions, metadata, states, and relationships visible or implied.
3. **Organization scheme.** Determine the dominant grouping principle. Flag mixed, overlapping, or org-chart-driven groupings.
4. **Hierarchy and structure.** Check whether the depth, breadth, sequence, and parent-child relationships match user expectations.
5. **Labels and language.** Evaluate clarity, consistency, specificity, distinctiveness, and vocabulary fit.
6. **Navigation and wayfinding.** Check global, local, contextual, supplemental, and process navigation. Verify that the screen answers "where am I, what is here, where can I go?"
7. **Search and discovery.** Inspect query entry, scope, suggestions, results, filters, sorting, ranking cues, snippets, empty/no-results states, and recovery paths.
8. **Metadata and invisible IA.** Identify missing fields, synonyms, aliases, content ownership, redirects, result tuning, and analytics needs.
9. **Accessibility and keyboard behavior.** Check semantic landmarks, headings, links/buttons, focus order, menu behavior, ARIA names, and dynamic announcements.
10. **Frontend feasibility.** Check URL/state persistence, component reuse, responsive behavior, performance, localization, and design-system fit.
11. **Prioritize fixes.** Separate blocking findability problems from polish. Recommend the smallest structural change that solves the user's task.

Output critiques as: finding → evidence → impact → recommendation → implementation note.

### B. Create or redesign an IA

Proceed in this order:

1. **Clarify the product problem.** Identify primary users, top tasks, content scope, business goals, platform, constraints, and success signals.
2. **Choose the simplest useful structure.** Prefer a clear hierarchy for simple/stable domains; add facets/search/contextual links only where content scale or user behavior requires it.
3. **Define content objects.** Name each object type, required fields, optional metadata, states, owners, and relationships.
4. **Pick organization schemes.** Choose task/topic/audience/etc. per view. Avoid mixing schemes unless you create distinct entry sections.
5. **Draft hierarchy and navigation.** Produce primary nav, local nav, breadcrumbs/process steps, contextual links, and supplemental aids.
6. **Draft labels.** Use user vocabulary, consistent grammatical patterns, and distinct labels. Include aliases for common alternate terms.
7. **Design search/discovery.** Define searchable content, zones, query support, filters/facets, result snippets, sort order, and empty states.
8. **Design bottom-up structure.** Add page templates, headings, related links, metadata, "next best" links, and content chunks for deep-entry users.
9. **Validate against scenarios.** Walk through at least three tasks: known-item lookup, exploratory browsing, and recovery from a wrong turn/no result.
10. **Specify frontend behavior.** Define semantic markup, URL state, keyboard behavior, focus management, loading/error/empty states, and analytics events.
11. **Document governance.** Note who maintains labels, taxonomy, metadata, redirects, and search tuning.

Output design recommendations as a structured IA proposal, not a decorative layout.

## Decision framework

### Choose hierarchy when

- Content has clear parent-child relationships.
- Users expect a table-of-contents, policy, documentation, file, or catalog structure.
- Items mostly belong in one place.
- The path itself helps users understand the domain.

### Choose facets when

- Items can be described along multiple independent dimensions.
- Users compare, narrow, and combine attributes.
- Content volume is high enough that flat lists are unhelpful.
- Metadata quality can be maintained.

### Choose search when

- Users often know the name, ID, keyword, location, or attribute of the target.
- Content changes too quickly for manual navigation alone.
- The content set is too large or heterogeneous for browsing alone.
- Search logs can be used to improve labels, synonyms, and result tuning.

### Choose contextual navigation when

- Users enter deep pages from search or external links.
- Related content is more useful than a full hierarchy.
- A workflow needs "next step," "related," "also applies to," or "learn more" links.
- Content models can reliably express relationships.

### Choose supplemental navigation when

- Users need overview, alternative access, or recovery tools.
- The system has long-tail content or multiple audiences.
- A-Z indexes, sitemaps, guides, glossaries, onboarding tours, or wizards reduce cognitive load.

## Practical rules

- Each navigation region needs a clear purpose. Do not duplicate the same links in multiple regions unless repetition helps orientation or task completion.
- Do not expose all taxonomy levels at once. Reveal depth progressively.
- Keep sibling labels parallel in grammar and granularity.
- Use category labels that describe the group, not marketing priorities.
- Avoid "Resources," "Solutions," "Learn," and "More" unless the contained items are genuinely coherent and users can predict what belongs there.
- Place high-frequency, high-value tasks in visible navigation; do not hide them behind search, footers, or catch-all menus.
- Use breadcrumbs for location in hierarchy, not as a record of the user's click history.
- Use tabs for peer views of the same object, not for unrelated destinations.
- Use filters to narrow a result set, not as primary navigation across unrelated sections.
- Provide result counts and active filter summaries when filtering.
- Always provide a recovery path for empty states and no-results states.
- Use analytics as evidence, not as the only source of truth. Pair search logs and click data with user research or task analysis.
- Document deprecated labels and redirects during migrations.

## Accessibility and inclusion requirements

- Use semantic landmarks: `header`, `nav`, `main`, `aside`, `footer`, and descriptive `aria-label` values when multiple nav regions exist.
- Use a logical heading hierarchy that reflects the content structure, not just visual size.
- Use real links for navigation and real buttons for actions.
- Provide visible focus states and predictable keyboard order.
- Menus, comboboxes, tabs, accordions, and disclosure navigation must follow expected keyboard patterns.
- Do not rely on icon-only navigation for primary tasks unless accessible text labels are present and the icon meaning is validated.
- Make search inputs programmatically labeled. Use `type="search"` when appropriate.
- Announce dynamic result updates, filter changes, loading, and errors with appropriate live regions when the page does not reload.
- Ensure labels and instructions do not rely only on color, position, or shape.
- Maintain readable target sizes and spacing across touch devices.
- Support localization: avoid labels that break when translated, and expect category order, alphabetical indexes, and sort logic to vary by locale.

## Frontend implementation guidance

### Semantic structure

- Primary navigation: `<nav aria-label="Primary">` containing lists of links.
- Breadcrumbs: `<nav aria-label="Breadcrumb"><ol>...` with the current page identified by `aria-current="page"`.
- Search: `<form role="search">` or a labeled search form, with a visible label or accessible name.
- Results: use headings, list semantics, result titles as links, meaningful snippets, metadata, and source/type indicators.
- Filters/facets: use fieldsets/legends for groups, checkboxes for multi-select facets, radios for exclusive options, and buttons/links for applying/removing filters depending on behavior.
- Pagination: use navigation landmarks and `aria-current` for current page.

### Responsive behavior

- Preserve conceptual navigation across breakpoints.
- Do not hide essential primary tasks in a mobile drawer without an equivalent visible path.
- For complex side navigation, collapse sections while preserving current location and search/filter access.
- Keep filter state visible or easily resumable on mobile.

### State and URLs

- Encode search query, selected facets, sort, pagination, and active category in the URL for shareable web states unless privacy or security prevents it.
- Use canonical URLs and redirects during IA migrations.
- Keep route names and slugs stable, readable, and aligned with labels where possible.

### Componentization

Create reusable components for:

- Primary navigation
- Section/local navigation
- Breadcrumbs
- Tabs for object subviews
- Search form
- Suggestions/autocomplete
- Result list/card
- Facet/filter group
- Active filter chips
- Empty/no-results states
- Related-content modules
- Content templates with metadata slots

### Performance and maintainability

- Do not render huge navigation trees or facet lists unbounded; virtualize, paginate, group, or search within long lists.
- Lazy-load secondary navigation only if the current location remains clear.
- Cache taxonomy and vocabulary data carefully, with invalidation for editorial updates.
- Instrument search queries, no-results queries, filter usage, top exits, and navigation dead ends.

## Quality checklist

Before finalizing an IA recommendation, verify:

- The structure supports at least one known-item task, one exploratory task, and one recovery task.
- Primary navigation represents user priorities, not only internal departments.
- Labels are distinct, predictable, and consistent.
- Content can be found by more than one path when user mental models differ.
- Deep-entry users can orient themselves without visiting the homepage.
- Search has defined scope, indexed fields, result presentation, and no-results recovery.
- Facets use reliable metadata and do not produce many meaningless empty states.
- Accessibility semantics and keyboard behavior are specified.
- Frontend state, URLs, responsive behavior, and design-system reuse are addressed.
- Maintenance responsibilities are explicit.

## Common mistakes to avoid

- Designing a sitemap before understanding user tasks and content types.
- Treating the homepage or main menu as the whole IA.
- Copying the organization chart into navigation.
- Using brand slogans or internal project names as labels.
- Adding search as a substitute for fixing taxonomy and labels.
- Exposing advanced search controls before users need them.
- Creating too many top-level items or too many hierarchy levels.
- Mixing topic, audience, task, format, and lifecycle labels in the same undifferentiated menu.
- Relying on hover-only menus.
- Failing to design no-results and empty states.
- Forgetting redirects, aliases, and deprecated terms during migrations.
- Ignoring bottom-up IA inside content templates.
- Creating a taxonomy without governance.

## How to explain recommendations to the user

Explain IA recommendations in task-centered language:

- Start with the user problem: "Users need to compare plans by price and feature without knowing internal product families."
- Name the structural choice: "Use a task-first primary nav and faceted comparison on the listing page."
- State why it helps: "This supports both browsing and narrowing without forcing one category path."
- Mention tradeoffs: "This requires reliable metadata for plan type, audience, and feature set."
- Give the implementation implication: "Persist selected filters in the URL and expose them as accessible checkbox groups."
- Identify validation: "Test with known-item lookup, exploratory browsing, and no-results recovery."

Avoid saying "this is best practice" without tying it to the user's task, content, and constraints.

