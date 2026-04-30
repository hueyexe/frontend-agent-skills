# Checklists for `ui-visual-composition`

Use these checklists before finalizing critiques, recommendations, or frontend UI output. Each item should be testable from the design, code, or written recommendation.

## Discovery / context checklist

- The primary user task is identified.
- The intended audience or user expertise level is identified or reasonably assumed.
- The platform and input context are identified or defaulted to responsive web.
- The primary action is known and distinguished from secondary/tertiary actions.
- The content type is known: prose, data, form, media, cards, dashboard, table, marketing, settings, or mixed.
- The expected information density is known or defaulted to comfortable.
- The brand personality is known or defaulted to professional, warm, restrained, and content-first.
- Existing design-system constraints are known, requested, or explicitly absent.
- Color/brand constraints are known or a local accessible palette will be created.
- Accessibility target is known or defaulted to WCAG AA-equivalent production expectations.
- Real-content risks are identified: long labels, localization, UGC, missing images, dense data, empty states, permissions, errors, or slow loading.
- Technical constraints are known when producing implementation: framework, CSS approach, token source, component library, and responsive needs.

## Critique checklist

- The critique begins with task fit before visual polish.
- Findings distinguish high-impact issues from polish details.
- Each critique explains the user impact, not just the designer preference.
- The primary content/action is visually stronger than secondary and tertiary actions.
- The visual hierarchy matches user and business priorities, or the conflict is called out.
- Common mental models are respected for controls, navigation, search, forms, and feedback.
- Related elements are grouped by proximity, alignment, or common region.
- Unrelated elements are sufficiently separated.
- The UI works in grayscale without relying on color to create the hierarchy.
- Color, shadows, gradients, borders, and icons are not compensating for poor structure.
- The design handles at least one realistic non-happy path.
- Recommendations are small enough to act on and prioritized by impact.

## Layout and grouping checklist

- The layout starts from the feature/content, not the surrounding chrome.
- The page has a clear focal region.
- The user's first scan path has a clear entry point.
- Related labels, controls, and descriptions are close to the elements they describe.
- Section spacing is larger than item spacing.
- Group spacing is not ambiguous: users can tell which label belongs to which field or value.
- Alignment paths reinforce relationships rather than creating accidental columns.
- Containers, cards, and common regions are used only where they clarify grouping or state.
- The layout does not fill the full viewport merely because space exists.
- Text columns have appropriate max-widths.
- Dense layouts are justified by expert use, high-frequency use, or monitoring needs.
- Grids are flexible and content-led, not rigid decoration.
- Responsive behavior preserves grouping and hierarchy at narrow, medium, and wide sizes.

## Visual hierarchy checklist

- The primary action has the strongest action treatment.
- Secondary actions are visible but quieter than the primary action.
- Tertiary actions are discoverable without competing.
- Destructive actions are styled according to their role in the current step, not only severity.
- Headings, labels, values, helper text, and metadata have distinct roles.
- Important information is emphasized by one or two strong cues, not many competing cues.
- Less important information is deliberately de-emphasized.
- Highlighted items are rare enough to remain salient.
- The screen does not contain several unrelated elements with equal maximum emphasis.
- Visual hierarchy does not conflict with semantics in a way that would harm accessibility.

## Typography checklist

- Font choice fits the product context and is legible at UI sizes.
- The type scale has a limited number of reusable levels.
- Differences between type sizes are large enough to look intentional.
- Body text is comfortable to read at the target viewport.
- Long prose line length is constrained.
- Small text has sufficient line height.
- Large headings have tighter line height than body text.
- Text alignment supports readability; long Latin-script text is not centered by default.
- Labels and values align by baseline or stable edges where appropriate.
- Emphasis uses one clear cue in ordinary text.
- All-caps labels use appropriate letter spacing and are not overused.
- Links are identifiable through more than color when needed.
- Pseudo-italics, fake bold, horizontal stretching, and distorted letterforms are avoided.
- Tables use alignment that supports comparison: numbers align consistently, headers are clear, and dense cells remain readable.
- Captions or supporting text clarify media rather than duplicating obvious content.

## Color and contrast checklist

- The palette has defined roles: surface, text, muted text, border, primary, focus, success, warning, error, info.
- Each role has enough shade steps for hover, active, selected, background, border, and text treatments.
- Text contrast is sufficient on all surfaces.
- Icon and control contrast is sufficient in normal, hover, active, disabled, and focus states.
- Color is never the only cue for error, success, warning, selected, required, or status.
- Gray text is not placed on colored backgrounds when a tuned foreground color would read better.
- Light colors retain enough saturation to remain distinct.
- Dark mode is tuned rather than mechanically inverted.
- Semantic colors are used consistently across components.
- Charts and status systems are understandable for users with color-vision differences.
- Focus color is visible on all relevant backgrounds.

## Depth, surfaces, and borders checklist

- The interface uses a consistent light source or intentionally flat system.
- Shadow strength corresponds to elevation and importance.
- Popovers/dropdowns appear above cards; modals appear above page content.
- Sticky elements, overlays, and drawers have sufficient separation from background content.
- Borders are used where they clarify structure, not as default decoration.
- Adjacent surfaces can be distinguished without excessive outlines.
- Overlaps do not obscure important text or controls.
- Background decoration does not reduce readability or compete with content.
- High-elevation elements are rare and reserved for blocking or focused interactions.
- Elevation values are tokenized or reusable.

## Imagery and media checklist

- Images have a purpose: evidence, product detail, identity, mood, instruction, or illustration.
- Image crops preserve the subject and avoid accidental meaning.
- Image resolution is sufficient for intended display size.
- Text overlays have a protective contrast strategy: solid panel, scrim, gradient, blur, or controlled crop.
- User-uploaded images have safe aspect ratios, placeholders, fallbacks, and contrast protection.
- Broken/missing media states are designed.
- Avatar and thumbnail treatments work with initials, missing images, and varied aspect ratios.
- Decorative images have empty alt text or are hidden from assistive technology.
- Informative images have useful alt text or adjacent descriptions.
- Loading behavior for media does not cause disruptive layout shift.

## State and resilience checklist

- Empty state explains what is missing and offers a useful next action.
- Loading state gives immediate feedback and preserves layout where possible.
- Error state is close to the relevant problem and tells users how to recover.
- Validation messages preserve user input.
- Disabled states are visually distinct and accompanied by explanation when the reason is not obvious.
- Focus states are visible and not color-only.
- Hover and active states feel related to the default state.
- Selected/current states are distinct from hover and focus.
- Success feedback confirms important completed actions.
- Destructive flows include confirmation or undo according to risk.
- Long text, missing data, zero values, overflow, and localization are handled.
- Permission or locked states show why content is unavailable and what can be done.

## Accessibility checklist

- Text, icon, and control contrast meet the product’s target standard.
- Color-dependent meaning has redundant cues.
- Controls have comfortable target sizes and spacing.
- Keyboard users can reach and operate all interactive elements.
- Focus order follows the visual/task order.
- Focus indicators are visible and consistent.
- Buttons and links use correct semantics.
- Forms have programmatic labels, helper text, error text, and required indicators.
- Error summaries are provided when forms are long or errors are distributed.
- Modals trap focus, label themselves, and return focus appropriately.
- Motion respects reduced-motion preferences.
- Dynamic updates have appropriate announcements when needed.
- Images and icons have appropriate alt text or are marked decorative.
- Tables use headers and semantic structure when presenting tabular data.
- The design remains usable at zoom and with larger text.

## Frontend implementation feasibility checklist

- Visual values are expressible as tokens or reusable classes.
- Component variants cover primary, secondary, tertiary, destructive, disabled, loading, selected, hover, active, and focus states.
- Layout uses semantic HTML and CSS layout primitives instead of inaccessible hacks.
- Responsive rules are defined for the key breakpoints or containers.
- Text truncation and wrapping rules are explicit.
- Images have explicit dimensions/aspect ratios to prevent layout shift.
- Z-index/elevation is governed by a small scale.
- Theme variables can support light/dark mode if needed.
- CSS does not depend on fragile absolute positioning unless the component truly requires it.
- Interaction states are implemented with accessible elements, not only visual styling.
- Code does not remove native focus behavior without replacement.
- The proposed visual design can be maintained by the target team.

## Final response checklist

- The answer identifies the main visual/design issue or design direction.
- Recommendations are prioritized.
- Defaults and assumptions are stated where context is missing.
- User questions are limited to decisions that matter.
- Accessibility is integrated into recommendations.
- Frontend constraints are addressed when code or implementation is involved.
- The response does not over-quote source material.
- The explanation is practical and actionable, not a generic design lecture.
- The answer includes specific changes the user can apply.
- Tradeoffs and exceptions are included when recommendations depend on context.
