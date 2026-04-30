# Checklists for `information-architecture-navigation`

## Discovery / context checklist

- The primary user task is stated in one sentence.
- The primary audience and vocabulary level are identified.
- The content types or objects are listed.
- The content scale is known or estimated: small/static, medium/editorial, large/dynamic, or federated.
- The main entry points are identified: homepage, deep link, search, notification, external referral, support, or workflow.
- Business, legal, SEO, migration, analytics, and design-system constraints are noted.
- The platform context is clear: responsive web, native app, desktop app, kiosk, voice, or cross-channel.
- Accessibility obligations are known or accessible defaults are assumed.
- The maintenance owner for taxonomy, metadata, labels, and redirects is identified when needed.
- Open questions have recommended defaults and are not routine best-practice questions.

## IA strategy checklist

- The IA is organized around user intent, not only internal departments.
- The dominant organization scheme is named: task, topic, audience, lifecycle, chronology, geography, format, alphabetic, or hybrid.
- Any hybrid structure has clear boundaries between entry modes.
- Hierarchy is used only where parent-child relationships are stable and meaningful.
- Facets are used only where attributes are reliable, meaningful, and useful for narrowing.
- Search is included only when content scale, dynamism, or known-item lookup justifies it.
- Multiple paths exist for content that users reasonably expect to find in multiple ways.
- The structure supports known-item lookup, exploratory browsing, and recovery from wrong turns.
- Deep-entry users can orient themselves without starting at the homepage.
- The structure can be maintained by the team after launch.

## Navigation quality checklist

- Primary navigation contains only major destinations or task areas.
- Local navigation explains the current section without duplicating all global navigation.
- Breadcrumbs reflect hierarchy and include the current page when useful.
- Contextual links point to genuinely related or next-step content.
- Footer/supplemental navigation is not used as a dumping ground for unresolved IA.
- Process navigation shows progress, current step, completed steps, and next action.
- Tabs are used for peer views of the same object, not unrelated destinations.
- Navigation labels are parallel in grammar and granularity.
- Navigation works without hover-only interactions.
- Mobile navigation preserves access to primary tasks and current location.
- Users can return, backtrack, or reset without losing orientation.

## Labeling checklist

- Labels use user language, not unexplained internal terms.
- Each label predicts the content or action behind it.
- Sibling labels are mutually distinct.
- Labels are short enough for navigation but not so short that meaning is lost.
- Nouns are used for destinations; verbs are used for actions.
- "Resources," "Solutions," "Learn," "Tools," and "More" are replaced or clarified when too vague.
- Abbreviations and acronyms are expanded unless the audience reliably knows them.
- Icon labels include visible or accessible text.
- Deprecated labels and synonyms are mapped for redirects/search aliases.
- Localization and translation effects are considered.

## Search and discovery checklist

- Search scope is explicit: whole product, current section, content type, or federated.
- The indexed content and fields are named: title, body, summary, tags, author, date, ID, metadata, etc.
- Search zones are used when heterogeneous content would otherwise create confusing results.
- Query assistance is considered: autocomplete, recent searches, spelling correction, stemming, synonyms, or suggested queries.
- Results show enough information to choose: title, snippet, type/source, date/status, owner, image/thumbnail when useful.
- Ranking/default sort is defined.
- Sort controls are exposed only for criteria users understand.
- Facets/filters use reliable metadata and understandable values.
- Active filters are visible and removable.
- Result counts and loading states are clear.
- No-results states include query echo, correction, filter removal, alternate paths, and support/contact when appropriate.
- Search logs and no-results queries are used to improve labels and vocabulary over time.

## Metadata and taxonomy checklist

- Each metadata field has a purpose tied to navigation, search, filtering, display, governance, or analytics.
- Controlled vocabulary fields have allowed values.
- Synonyms/aliases are captured for user language, acronyms, old names, and spelling variants.
- Preferred labels and deprecated labels are documented.
- Polyhierarchy or multiple classification is used only where it helps users find content from multiple routes.
- Tags are not allowed to become uncontrolled duplicates of categories.
- Ownership, review cadence, and update process are defined.
- The content management workflow supports required metadata without excessive burden.
- Metadata rules are documented in an IA or content style guide.

## Content/template checklist

- Page titles are unique and descriptive.
- Heading structure reflects the content hierarchy.
- Important content is chunked into meaningful sections.
- Each template has slots for summary, metadata, related links, and next steps when useful.
- Related links are based on defined relationships, not arbitrary cross-promotion.
- Empty, loading, error, archived, restricted, and outdated states are designed.
- Content pages answer: what is this, who is it for, what can I do, and where should I go next?
- Deep content includes enough context for users arriving from search or external links.

## Accessibility checklist

- Navigation regions use semantic `<nav>` landmarks with descriptive labels when more than one exists.
- Main content is reachable by a skip link or equivalent.
- Heading order is logical and not chosen solely for visual style.
- Links and buttons are semantically correct.
- Focus states are visible and not clipped.
- Keyboard order matches visual and task order.
- Menus, tabs, disclosures, comboboxes, and dialogs follow expected keyboard interaction.
- Search input has a programmatic label.
- Dynamic search/filter changes are announced or otherwise perceivable.
- Icon-only controls have accessible names and, for primary nav, visible text unless validated.
- Current page/section state is programmatically indicated where needed.
- Color, position, or icon shape is not the only indicator.
- Touch targets and spacing are adequate for mobile/touch use.

## Frontend implementation feasibility checklist

- Navigation, search, filters, tabs, and pagination have component owners.
- Route structure and URLs align with IA labels where appropriate.
- Search query, active filters, sort, and pagination persist in the URL unless intentionally private.
- Existing URLs and SEO-critical paths have redirects during migration.
- Long menus/facet lists have performance strategy: grouping, lazy loading, virtualization, or search-within-list.
- Responsive behavior is specified for global nav, local nav, breadcrumbs, filters, and result lists.
- State restoration works after refresh, back/forward, and shared links.
- Loading, empty, error, and permission states are implemented.
- Analytics events are defined for search, no-results, facet usage, nav clicks, exits, and task completion.
- Localization affects labels, alphabetical indexes, date/location facets, sorting, and string length.
- Design-system tokens/components are reused where possible.

## Critique response checklist

- The critique starts with the user/task impact, not visual taste.
- Findings are prioritized by severity and effort.
- Each finding includes evidence from the UI or content.
- Recommendations are specific enough to implement.
- Tradeoffs and assumptions are explicit.
- The response separates structural IA issues from visual polish.
- Accessibility and frontend implications are included where relevant.
- The final recommendation includes a small next step or validation method.

## Final answer checklist

- The answer tells the user what structure or change to use.
- Defaults are opinionated and justified.
- Questions are asked only when necessary, with recommended defaults.
- Limitations or missing context are disclosed.
