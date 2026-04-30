# Anti-patterns — accessibility-inclusive-design

Prioritize these when critiquing or generating UI. These are common mistakes an AI agent may accidentally produce.

## Anti-pattern: Clickable `div` pretending to be a button

What it looks like:
- A `div` or `span` styled like a button with a click handler.
- Text or label stored in a background image.
- No native focus or keyboard behavior.

Why it fails:
- It may not be focusable, operable by keyboard, announced as a button, translated, zoomed, or visible in high contrast mode.

Better approach:
- Use a real `<button>` for actions.
- Keep the visible label as text.
- Style the button without removing semantics or focus.

Ask the user when:
- Only if the action has non-button semantics or must be integrated into an existing custom component.

---

## Anti-pattern: ARIA as a substitute for correct HTML

What it looks like:
- Adding `role="button"` to a non-button instead of using `<button>`.
- Creating custom radio groups, tabs, or menus without matching keyboard behavior.
- Adding roles and states to patch broken markup.

Why it fails:
- ARIA affects semantics but does not automatically provide native behavior, focus, or robust platform support.

Better approach:
- Use native HTML where possible.
- Use ARIA only for missing names, relationships, states, and dynamic announcements after the native baseline is sound.

Ask the user when:
- A custom component is unavoidable and the agent must choose a full ARIA pattern.

---

## Anti-pattern: Placeholder text used as the only label

What it looks like:
- Input fields have only placeholder text such as “Email” or “Search.”
- The label disappears when the user types or when autofill populates the field.

Why it fails:
- Placeholders can have low contrast, may not be reliably exposed, disappear during entry, and create cognitive load when reviewing autofilled forms.

Better approach:
- Use persistent visible labels associated with inputs.
- Use placeholders only for hints or examples.

Ask the user when:
- Severe space constraints are cited; then recommend compact persistent labels or tested floating labels.

---

## Anti-pattern: Removing focus styles

What it looks like:
- CSS uses `outline: none`.
- Keyboard focus is invisible or too subtle.
- Focus styles exist only on hover.

Why it fails:
- Keyboard users cannot tell where they are or what will activate.

Better approach:
- Preserve browser focus styles or provide a stronger custom focus style with clear contrast and shape.

Ask the user when:
- Only if brand/design-system constraints require a custom focus token.

---

## Anti-pattern: Positive `tabindex` to force focus order

What it looks like:
- Elements use `tabindex="1"`, `tabindex="2"`, etc.
- Focus order differs from source order.

Why it fails:
- It creates brittle and confusing keyboard navigation, especially as content changes.

Better approach:
- Fix DOM/source order.
- Use `tabindex="0"` only for custom focusable elements when unavoidable.
- Use `tabindex="-1"` only for programmatic focus targets.

Ask the user when:
- A legacy system prevents source-order changes.

---

## Anti-pattern: Disabling pinch zoom or text resizing

What it looks like:
- Viewport meta includes `maximum-scale=1` or `user-scalable=no`.
- CSS sets rigid pixel-based type and containers.
- Layout breaks when zoomed, so zoom is blocked.

Why it fails:
- Users rely on zoom for reading, image detail, selection, distraction reduction, or compensating for bad responsive layout.

Better approach:
- Allow zoom.
- Use flexible layout and relative units.
- Fix the layout instead of blocking user controls.

Ask the user when:
- The interface is a controlled kiosk or fixed embedded surface; still document mitigation.

---

## Anti-pattern: Device-specific breakpoints

What it looks like:
- Breakpoints are designed around specific phone/tablet names.
- Content overlaps, clips, or wraps badly between named breakpoints.

Why it fails:
- Viewport sizes, zoom levels, user font settings, and devices are too varied to target reliably.

Better approach:
- Use flexible layout and add breakpoints where content breaks.
- Test by resizing continuously and with zoom/text changes.

Ask the user when:
- The target is a fixed embedded or native app surface.

---

## Anti-pattern: Fixed heights that clip real content

What it looks like:
- Cards, buttons, labels, or inputs have fixed heights.
- Long translated strings or zoomed text overflow or disappear.
- Layout assumes idealized content length.

Why it fails:
- Real content varies by language, user data, zoom, and editorial input.

Better approach:
- Use flexible containers, wrapping, min/max constraints, and realistic edge-case content in prototypes.

Ask the user when:
- Platform constraints require fixed dimensions.

---

## Anti-pattern: Color-only meaning

What it looks like:
- Required, selected, error, current page, or status is communicated only by color.
- Instructions say “choose the red option” without another cue.

Why it fails:
- Users with color vision differences, low vision, monochrome/high contrast settings, or screen readers may miss the meaning.

Better approach:
- Add text, icon, border, shape, position, pattern, or programmatic state.
- Keep contrast sufficient.

Ask the user when:
- The state meaning is product-specific and needs a label.

---

## Anti-pattern: Low-contrast decorative minimalism

What it looks like:
- Pale gray text on white.
- Subtle field borders, disabled-looking active controls, or low-contrast placeholders.
- Visual hierarchy depends on barely visible differences.

Why it fails:
- Text and controls become hard to perceive, especially for low vision, older users, glare, poor displays, or mobile contexts.

Better approach:
- Meet contrast expectations and use clear visual affordances.
- Avoid making placeholder text the only field cue.

Ask the user when:
- Brand palette is fixed; recommend accessible token adjustments.

---

## Anti-pattern: Extreme contrast as the only reading mode

What it looks like:
- The only reading theme is stark black text on pure white.
- No support for user theme preferences or softer accessible palettes.

Why it fails:
- Very high glare can reduce comfort for some users and environments.

Better approach:
- Use sufficient but comfortable contrast and support customization where possible.
- Provide theme tokens rather than hard-coded colors.

Ask the user when:
- Brand or product theme choices are open.

---

## Anti-pattern: Vague or context-dependent links

What it looks like:
- “Click here,” “read more,” “learn more,” or runs of separate links across generic words.
- Link text only makes sense after reading the surrounding paragraph.

Why it fails:
- Screen readers can list links out of context; users scanning links need destinations or actions.

Better approach:
- Make link text describe the destination or action.
- Include product/article names in CTAs, visually hidden if necessary.

Ask the user when:
- Link destination or product name is unknown.

---

## Anti-pattern: Heading levels chosen for visual size

What it looks like:
- Skipping from `h1` to `h3` because `h2` looks too large.
- Subtitles marked as headings when they are not sections.

Why it fails:
- It breaks the document outline and disorients users navigating by heading.

Better approach:
- Choose heading levels by structure.
- Use CSS classes/tokens carefully for style, but avoid visual/semantic divergence that misleads users.

Ask the user when:
- The content hierarchy is unclear.

---

## Anti-pattern: JavaScript-dependent static content

What it looks like:
- An article, marketing page, documentation page, or product content renders only after client-side JavaScript.
- Without JS, the page is empty or unusable.

Why it fails:
- Content can disappear under script failure, blocked assets, slow networks, search tools, and some assistive/automation contexts.

Better approach:
- Serve meaningful content as HTML.
- Use JavaScript to enhance interaction, not to gate basic reading.

Ask the user when:
- The product is a full app shell and architecture constraints matter.

---

## Anti-pattern: Infinite scroll by default

What it looks like:
- More content loads automatically when the user reaches the bottom.
- Footer or below-list controls become unreachable.
- Focus remains on a button or jumps unpredictably after content insertion.

Why it fails:
- It hijacks scrolling, disorients users, and can make keyboard navigation effectively endless.

Better approach:
- Use explicit pagination or “Load more.”
- Announce loading and completion.
- Move focus intentionally to the first newly loaded item when appropriate.

Ask the user when:
- The product insists on infinite scroll; require accessible fallback and testing.

---

## Anti-pattern: Loading spinner visible only to sighted users

What it looks like:
- A spinner appears during XHR/loading but no text or live-region announcement exists.
- Screen reader users receive no indication that the action worked.

Why it fails:
- Non-visual users may think the action failed or may not know when content is ready.

Better approach:
- Provide visible loading text or status where needed.
- Use an appropriate live region for asynchronous status changes.

Ask the user when:
- The loading status has product-specific wording or urgency.

---

## Anti-pattern: Hidden content remains focusable

What it looks like:
- A collapsed menu is visually hidden with height/opacity but links can still receive focus.
- Keyboard users tab through invisible controls.

Why it fails:
- It makes focus appear lost and exposes controls that cannot be seen or understood.

Better approach:
- Use `hidden` or another method that removes hidden content from the focus order.
- Reveal content before making it operable.

Ask the user when:
- Animation requirements conflict with removing content from focus order.

---

## Anti-pattern: Icon-only controls without accessible names

What it looks like:
- Search, close, play, menu, trash, or filter icons with no text, `aria-label`, or visible label.
- Icon fonts or Unicode icons are announced as strange glyph names.

Why it fails:
- Users may not understand or hear the control’s purpose; icons can fail in high contrast, font overrides, or blocked assets.

Better approach:
- Prefer visible text plus icon.
- If icon-only is necessary, give the control an accessible name.
- Use robust SVG/currentColor where suitable and hide decorative icon parts.

Ask the user when:
- Space constraints require icon-only controls.

---

## Anti-pattern: Hiding navigation behind a hamburger when it is short

What it looks like:
- Three or four primary nav items hidden behind a menu button on desktop or wide screens.
- Users must take an extra action to reveal basic navigation.

Why it fails:
- It hides functionality, increases interaction cost, and creates disclosure/focus/state complexity.

Better approach:
- Keep short menus visible.
- Use a menu button only when screen space or item count genuinely requires it.

Ask the user when:
- Product IA or viewport constraints are unclear.

---

## Anti-pattern: Tiny or crowded touch targets

What it looks like:
- Adjacent links or buttons in a tight row.
- Mobile nav items too short or close together.
- Tappable areas only around the text, not the row/control.

Why it fails:
- Users with limited dexterity, tremor, large fingers, or situational movement errors mis-tap.

Better approach:
- Use generous target size and spacing.
- On narrow viewports, put navigation items in a vertical column with generous padding.

Ask the user when:
- Space constraints force dense controls; recommend an alternate layout.

---

## Anti-pattern: Redundant controls with the same destination

What it looks like:
- A logo links home and the first navigation link also says home.
- Current page link reloads the same page.

Why it fails:
- Redundancy adds noise, extra tab stops, and confusing repeated options.

Better approach:
- Use one canonical link where possible.
- Convert current-page links into useful same-page/skip behavior or mark current state clearly.

Ask the user when:
- Brand requirements mandate logo behavior and duplicate nav links.

---

## Anti-pattern: Unlabeled multiple navigation regions

What it looks like:
- Several `nav` landmarks all announced simply as “navigation.”
- Site nav, pagination, breadcrumbs, and table of contents are not distinguished.

Why it fails:
- Assistive technology users cannot tell which navigation region they are choosing.

Better approach:
- Label navigation landmarks with visible headings and `aria-labelledby`, or use `aria-label`.

Ask the user when:
- The nav region’s purpose is not clear.

---

## Anti-pattern: Visual order contradicts source order

What it looks like:
- CSS grid/flex reorders content visually.
- Metadata appears before heading in source but visual design suggests the opposite.
- Keyboard order jumps around.

Why it fails:
- Screen reader and keyboard users experience a different sequence and may miss context.

Better approach:
- Make source order match logical reading and focus order.
- Use visual styling without changing fundamental sequence.

Ask the user when:
- Visual layout constraints require complex reordering.

---

## Anti-pattern: Aggressive live validation

What it looks like:
- Errors fire on every keystroke.
- Screen readers repeatedly announce partial validation messages.
- Fields are marked invalid before the user has had a chance to complete them.

Why it fails:
- It creates noise, stress, and performance issues.

Better approach:
- Validate on submit first.
- After errors exist, provide debounced, supportive feedback while users correct.
- Use `aria-invalid` and descriptions intentionally.

Ask the user when:
- Immediate validation is necessary for security or cost reasons.

---

## Anti-pattern: Errors only at the top of the form

What it looks like:
- A long form shows an error summary at the top while the user is at the submit button or a field far below.
- The field itself has no associated repair instruction.

Why it fails:
- The message may be outside the zoomed viewport or disconnected from the field that needs attention.

Better approach:
- Provide a concise form-level error notice near the user’s current action and field-level instructions associated with each invalid input.

Ask the user when:
- The form is long and focus strategy must follow product conventions.

---

## Anti-pattern: Password confirmation as the only error prevention

What it looks like:
- Users must type the same password twice.
- There is no way to inspect the typed password.

Why it fails:
- It increases motor and cognitive burden and can still leave users unsure what they typed.

Better approach:
- Provide a show-password control unless security policy prohibits it.

Ask the user when:
- Security policy or threat model restricts password reveal.

---

## Anti-pattern: Clever brand labels for task-critical controls

What it looks like:
- “Secret incantation” instead of “Password.”
- Vague, playful error messages that do not say what to fix.
- Navigation labels that prioritize voice over clarity.

Why it fails:
- Users need labels, headings, and errors to describe purpose, especially during task completion.

Better approach:
- Use direct, descriptive labels for task-critical UI.
- Put brand personality in secondary or supportive text.

Ask the user when:
- Brand voice is a core requirement and must be balanced with clarity.

---

## Anti-pattern: Media without alternatives

What it looks like:
- Images without alt text.
- Video without captions/transcript.
- Instructions dependent on color, position, or sound.
- Captions omit speaker changes or important sounds.

Why it fails:
- Some users cannot perceive the media channel, cannot play it, or are in a context where sound/visuals are unavailable.

Better approach:
- Provide purpose-based alt text, captions, transcripts, audio descriptions where needed, and redundant non-color cues.
- Use empty alt for decorative images.

Ask the user when:
- The purpose or meaning of media is not clear.

---

## Anti-pattern: Background images for essential icons or text

What it looks like:
- Button label or icon exists only as a CSS background image.
- Essential content disappears when images or CSS fail.

Why it fails:
- Backgrounds can be hidden in high contrast modes, blocked on low bandwidth, unavailable to screen readers, and untranslatable.

Better approach:
- Use real text for labels.
- Use robust inline SVG/currentColor for icons when needed.
- Ensure the control remains meaningful without decorative assets.

Ask the user when:
- Existing brand assets must be preserved; recommend equivalent text and semantic fallback.

---

## Anti-pattern: Web fonts that block reading

What it looks like:
- Text stays invisible while a web font loads.
- The page depends on a large font file before rendering readable content.

Why it fails:
- Slow networks or stalled font resources can make the page unreadable.

Better approach:
- Treat web fonts as enhancement.
- Use system fallback fonts and avoid flash of invisible text.
- Subset fonts where appropriate and match fallback metrics.

Ask the user when:
- Brand typography is fixed and performance tradeoffs must be managed.

---

## Anti-pattern: Relying only on automated accessibility tests

What it looks like:
- Declaring the UI accessible because a checker passed.
- Ignoring keyboard walkthroughs, screen reader behavior, content clarity, and user testing.

Why it fails:
- Automation misses technically valid but confusing patterns, poor focus movement, wording problems, and unsupported combinations.

Better approach:
- Combine automated checks with keyboard-only testing, screen reader smoke tests, zoom/reflow, device/browser matrix, and disabled-user testing where possible.

Ask the user when:
- Choosing a validation depth for release or audit.
