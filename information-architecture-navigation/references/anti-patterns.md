# Anti-patterns for `information-architecture-navigation`

## Anti-pattern: Org-chart navigation

What it looks like:
- Top-level navigation mirrors departments, business units, product ownership, or internal team names.
- Users must know how the organization works to find what they need.

Why it fails:
- Internal structure rarely matches the user's task or vocabulary.

Better approach:
- Organize around user tasks, topics, or objects first; map internal owners behind the scenes.

Ask the user when:
- Legal, compliance, or enterprise buying processes require internal business-line visibility.

## Anti-pattern: One right tree for multidimensional content

What it looks like:
- Every item is forced into a single category even though users expect to find it by audience, topic, format, status, date, location, or other attributes.

Why it fails:
- Users approach the same content from different mental models, and one hierarchy cannot serve all of them.

Better approach:
- Use hierarchy for stable relationships and facets/tags/metadata for alternative paths.

Ask the user when:
- Metadata quality or maintenance ownership is uncertain.

## Anti-pattern: Mixed scheme menu

What it looks like:
- A single menu mixes "Products," "For Managers," "Pricing," "New," "Videos," and "Europe" as peers without separating task, audience, format, time, and geography.

Why it fails:
- Users cannot predict what belongs where or compare sibling options.

Better approach:
- Choose one dominant organizing principle per menu or create visibly separate entry groups.

Ask the user when:
- Multiple entry modes are genuinely needed on a landing page.

## Anti-pattern: Search as a bandage

What it looks like:
- The product adds a search box while labels, categories, metadata, and page structure remain unclear.

Why it fails:
- Search depends on good content structure, indexing, vocabulary, and result presentation; it does not erase IA problems.

Better approach:
- Fix labels/grouping and define indexed fields, search zones, query support, and result design.

Ask the user when:
- Search is expected to be the primary discovery mode for a large or dynamic collection.

## Anti-pattern: Ambiguous catch-all labels

What it looks like:
- Navigation depends on labels like "Resources," "Solutions," "Tools," "Insights," "Learn," "More," or branded names without clear contents.

Why it fails:
- Labels stop acting as promises and become guessing games.

Better approach:
- Rename to content-specific labels or split the bucket into task/topic groups.

Ask the user when:
- Brand terminology has been validated with the target audience.

## Anti-pattern: Cute or branded navigation labels

What it looks like:
- Labels prioritize personality over predictability, such as metaphorical section names or campaign slogans.

Why it fails:
- Navigation is functional; unclear labels increase hesitation and wrong turns.

Better approach:
- Use plain labels for structure; reserve brand voice for content and supporting microcopy.

Ask the user when:
- The product is entertainment/community-oriented and labels have been tested.

## Anti-pattern: Navigation without place

What it looks like:
- Users cannot tell current section, parent category, active filters, or how to get back.
- Deep pages have no breadcrumbs, local nav, heading context, or related paths.

Why it fails:
- Users lose orientation and confidence, especially when entering from search or external links.

Better approach:
- Provide current-state indicators, breadcrumbs for hierarchy, local nav, contextual links, and clear page headings.

Ask the user when:
- The product is a single-screen app where hierarchy is minimal.

## Anti-pattern: Deep hidden hierarchy

What it looks like:
- Users must click through many levels before seeing useful choices.
- Parent categories are vague and sibling distinctions are weak.

Why it fails:
- Deep trees increase memory load and hide options.

Better approach:
- Flatten where possible, expose important choices earlier, and add search/facets/contextual links for scale.

Ask the user when:
- The domain requires formal hierarchical structure, such as policies, documentation, or catalogs.

## Anti-pattern: Mega menu as junk drawer

What it looks like:
- A large dropdown exposes every product, page, campaign, role, and resource without coherent grouping.

Why it fails:
- Visibility becomes noise; users must parse the organization's unresolved taxonomy.

Better approach:
- Use mega menus only for coherent grouped choices with clear labels and hierarchy; move secondary content to landing pages or contextual modules.

Ask the user when:
- Analytics show users need broad cross-category access from the top level.

## Anti-pattern: Icon-only primary navigation

What it looks like:
- Primary destinations are represented only by icons, especially custom or abstract icons.

Why it fails:
- Icons are often ambiguous, inaccessible without names, and hard to learn across audiences.

Better approach:
- Pair icons with text for primary navigation; ensure accessible names and focus states.

Ask the user when:
- Space-constrained native interfaces require icons and the meanings are validated.

## Anti-pattern: Facets without a content model

What it looks like:
- Filters are added before the team knows which attributes are complete, reliable, and useful.
- Filter values overlap, are empty, or use inconsistent labels.

Why it fails:
- Faceted navigation depends on trustworthy metadata and controlled vocabulary.

Better approach:
- Define object types, metadata fields, allowed values, synonyms, and governance before exposing facets.

Ask the user when:
- Content scale is small enough that filters may not be needed.

## Anti-pattern: No-results dead end

What it looks like:
- Search or filtered results show "No results" with no suggestions, no active-filter visibility, and no alternate path.

Why it fails:
- Users are left without a recovery strategy.

Better approach:
- Echo the query, suggest spelling/synonyms, relax filters, show related categories, and offer support/request paths when appropriate.

Ask the user when:
- Domain-specific recovery paths exist.

## Anti-pattern: Unmanaged synonym chaos

What it looks like:
- Multiple labels refer to the same concept; old product names, abbreviations, and user terms are not mapped.

Why it fails:
- Users miss content when their words do not match system words.

Better approach:
- Maintain synonym rings, aliases, preferred terms, and deprecated labels for navigation and search.

Ask the user when:
- The domain has regulated or expert terms where loose synonyms may be misleading.

## Anti-pattern: Breadcrumbs as history

What it looks like:
- Breadcrumbs show the user's click path instead of the location in the hierarchy.

Why it fails:
- The same page appears to live in different places and users cannot build a stable mental model.

Better approach:
- Use breadcrumbs for hierarchy. Use browser history/back controls or "recently viewed" for history.

Ask the user when:
- The product has polyhierarchical content and must choose one canonical breadcrumb path.

## Anti-pattern: Advanced search by default

What it looks like:
- Users face Boolean options, field selectors, and complex forms before they have tried basic search.

Why it fails:
- Most users need a simple starting point and iterative refinement.

Better approach:
- Start with simple search, then offer scoped filters, suggestions, and advanced controls progressively.

Ask the user when:
- The primary audience is trained expert searchers, such as librarians, legal researchers, or analysts.

## Anti-pattern: Invisible IA without ownership

What it looks like:
- Search best bets, redirects, metadata, aliases, and result tuning exist but no one owns or reviews them.

Why it fails:
- Hidden rules decay and can contradict visible navigation.

Better approach:
- Document invisible IA in governance and analytics reviews.

Ask the user when:
- The system has distributed content authors or multiple repositories.

## Anti-pattern: Mobile drawer hides the primary task

What it looks like:
- The desktop nav exposes important tasks, but mobile hides all tasks in a hamburger or secondary drawer.

Why it fails:
- Mobile users often need quick access and orientation, not more navigation work.

Better approach:
- Keep primary task access visible or one tap away, preserve current location, and adapt local nav thoughtfully.

Ask the user when:
- Mobile users have different tasks than desktop users.

## Anti-pattern: Content pages without bottom-up IA

What it looks like:
- Pages have content but no meaningful headings, metadata, related links, next steps, or contextual navigation.

Why it fails:
- Users who enter deep from search cannot orient or continue.

Better approach:
- Add structured chunks, descriptive headings, content metadata, related content, and next-step links.

Ask the user when:
- Content templates are constrained by CMS or design-system limits.
