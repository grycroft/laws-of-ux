---
name: "laws-of-ux"
description: "Apply the 30 Laws of UX (lawsofux.com) when designing, building or reviewing any web or mobile user interface, component, screen, form or flow."
---

# Laws of UX

Use this skill whenever you design, build, refactor or review a user interface for web or mobile: pages, screens, components, forms, navigation, onboarding, checkout, dashboards, modals, empty states, loading states. The laws come from Jon Yablonski's Laws of UX (https://lawsofux.com/). They are grounded in psychology research and are applied here as concrete build rules.

The laws are not decoration for a write-up. They should change what you build: fewer options, bigger targets, clearer grouping, faster feedback, familiar patterns.

## Workflow

1. **Frame the task before writing UI code.** Identify the user's primary goal on this screen, the one or two primary actions, and the 20% of features that 80% of users need (Pareto). Note who the users are and what conventions they already know (Jakob's Law, Mental Model).
2. **Use the existing design system first.** If the project has tokens, components or a design system, use them. Consistency with the product and with the wider web is itself a UX law (Jakob's Law, Similarity).
3. **Build with the laws below.** Work through the six groups. Not every law applies to every screen, but check each group.
4. **Run the review checklist** at the end of this file before calling the work done.
5. **Report briefly.** After building, add a short "UX laws applied" note: the handful of laws that drove real decisions, any trade-offs made, and anything that needs user testing to confirm. Do not list all 30 laws.

## 1. Perception and grouping (Gestalt)

**Law of Proximity.** Objects near each other are seen as a group.
- Spacing is structure. Put less space inside a group than between groups (e.g. label-to-input 4 to 8px, field-to-field 16 to 24px, section-to-section 32 to 48px).
- A form label must sit closer to its own field than to the previous field.
- Keep related actions together (Save next to Cancel), and keep destructive actions apart from frequent ones.

**Law of Common Region.** Elements sharing a clearly bounded area are seen as a group.
- Use cards, panels, borders or background fills to group related content and controls.
- Do not nest regions more than two levels deep; boxes inside boxes inside boxes add noise.
- On mobile, list sections, grouped table rows and bottom sheets are common regions. Use them.

**Law of Similarity.** Elements that look alike are seen as related and as sharing a function.
- Same function means same look: one style for all primary buttons, one for all links, one for all tags.
- Different function means different look. Links must be visibly distinct from body text (not colour alone: underline or weight too).
- Never style non-interactive text like a link or button.

**Law of Uniform Connectedness.** Visually connected elements are seen as more related than unconnected ones.
- Use lines, connectors, shared frames or shared colour to tie together steps in a stepper, items in a timeline, or a control and the content it affects.
- Tabs should visually connect to the panel they control.

**Law of Prägnanz.** People interpret complex or ambiguous visuals in the simplest form possible.
- Prefer simple shapes, clear alignment and a consistent grid.
- Icons should be simple and recognisable; add text labels where meaning is not universal.
- Reduce visual noise: fewer borders, fewer competing colours, fewer font sizes.

## 2. Attention and memory

**Selective Attention.** People focus on stimuli tied to their goal and filter out the rest.
- Guide attention to the one thing that matters on the screen using hierarchy, size, position and contrast.
- Avoid banner blindness: never style real content like an ad, and never place key content inside or beside ad slots.
- Avoid change blindness: when something important changes (error, cart update, saved state), signal it near where the user is looking, and do not fire several changes at once.

**Von Restorff Effect (Isolation Effect).** The item that differs from similar items is the one remembered.
- Make the primary action visually distinct. One primary button per view or section.
- Use emphasis sparingly. If everything is highlighted, nothing is, and heavy emphasis can read as an ad.
- Never rely on colour alone to create the contrast; add shape, weight, icon or label for colour-blind and low-vision users.
- Respect `prefers-reduced-motion` before using motion to draw attention.

**Serial Position Effect.** First and last items in a series are remembered best.
- Put the most important navigation items at the start and end (e.g. Home first, Account or Basket last; on mobile tab bars, key tabs at the edges).
- Put the least important items in the middle of lists and menus.
- In long pages, lead with the key message and end with a clear call to action.

**Working Memory.** People hold roughly 4 to 7 chunks for 20 to 30 seconds.
- Show only what is needed for the current step.
- Favour recognition over recall: visited-link styles, breadcrumbs, recently viewed items, autocomplete, visible selected filters.
- Carry information across screens so users do not have to remember it: order summaries, comparison tables, persistent context headers, never make users re-type what they already entered.

**Miller's Law.** Average working memory is about 7 plus or minus 2 items.
- Use it as a reason to chunk, not as a hard cap. Do not cite "7 items" to justify arbitrary limits on navigation or menus; people scan menus, they do not memorise them.
- Capacity varies with prior knowledge, so expert tools can show more than consumer onboarding.

**Chunking.** Break information into meaningful groups.
- Format long numbers and codes in groups (phone numbers, card numbers, membership numbers, postcodes).
- Break long pages into sections with clear headings, and long forms into logical groups or steps.
- Use headings, dividers and hierarchy so content is scannable.

**Cognitive Load.** The mental effort needed to understand and use an interface.
- Intrinsic load is the task itself; you cannot remove it, only support it.
- Extraneous load is waste: remove decorative elements, redundant copy, unclear labels, unexpected layouts and anything that does not help the user's goal.
- Use plain language, sensible defaults and progressive disclosure ("Advanced options").

## 3. Decisions and complexity

**Hick's Law.** Decision time grows with the number and complexity of choices.
- Reduce choices where speed matters (checkout, sign-up, primary navigation).
- Split complex tasks into smaller steps.
- Highlight a recommended option (a default plan, a suggested action).
- Use progressive onboarding instead of front-loading every feature.
- Do not simplify to the point of abstraction; hiding everything behind vague icons or a single menu makes decisions harder, not easier.

**Choice Overload.** Too many options overwhelm and sour the whole experience.
- Curate: feature a small set first, then provide search, filters and sort to narrow the rest.
- When users must compare (pricing tiers, membership types, products), show options side by side with aligned attributes.
- Prefer 3 to 4 pricing or plan options, with one marked as recommended.

**Occam's Razor.** Prefer the solution with the fewest assumptions; avoid complexity from the start.
- For every element, ask whether removing it harms the function. If not, remove it.
- The design is done when nothing more can be taken away, not when nothing more can be added.
- Prefer one clear path over several optional ones.

**Tesler's Law (Conservation of Complexity).** Every system has irreducible complexity; either the system or the user carries it.
- Move complexity into the system: smart defaults, autofill, address lookup, input formatting, inferred values, saved preferences.
- Spend engineering effort so users do not have to spend effort (an extra week of build beats millions of extra user minutes).
- Design for real, non-rational users, and provide contextual help (tooltips, inline hints) rather than manuals.

**Pareto Principle.** Roughly 80% of effects come from 20% of causes.
- Identify the few features and flows most users rely on and make them excellent, fast and prominent.
- Put secondary features one level down.
- Prioritise fixes and polish where they help the most users.

**Cognitive Bias.** Systematic errors in judgement, driven by mental shortcuts.
- Design for how people actually decide: defaults, framing, anchoring and social proof all shape choices.
- Use this to help users, never to manipulate them. No dark patterns: no pre-ticked consent or add-ons, no confirmshaming, no fake scarcity or fake urgency, no hidden costs, no roach-motel cancellation.
- Guard your own biases as the builder (confirmation bias about your design); test with real users.

## 4. Expectations and learning

**Jakob's Law.** Users spend most of their time on other sites and expect yours to work the same way.
- Use established conventions: logo top-left links home, search at the top, basket or account top-right, underlined links, standard form controls, standard checkout flow.
- On mobile, follow platform conventions (iOS Human Interface Guidelines, Android Material): back behaviour, tab bars, swipe gestures, system sheets, native pickers.
- When redesigning, reduce friction by letting users keep the familiar version for a limited time or by introducing changes gradually.

**Mental Model.** Users carry a compressed model of how a system works and apply it to similar systems.
- Match labels, structure and flow to how users think, not to internal org structure or database schema.
- Use familiar metaphors that hold up (basket, favourites, inbox) and keep them consistent.
- Close the gap between designer and user models with research: interviews, card sorting, journey maps, usability tests.

**Paradox of the Active User.** Users never read manuals; they start using software immediately.
- Make the interface self-explanatory. Assume no one reads onboarding carousels or help pages.
- Provide help in context and at the point of need: inline hints, tooltips, empty-state guidance, examples in placeholders (never as the only label).
- Make errors recoverable (undo, confirmation for destructive actions) because users will explore by doing.

**Postel's Law.** Be liberal in what you accept and conservative in what you send.
- Accept varied input and normalise it: phone numbers with or without spaces, postcodes in any case, dates in several formats, pasted text with stray whitespace.
- Do not reject input for trivial formatting reasons; fix it for the user.
- Output should be consistent and predictable. Set sensible limits and give clear, specific feedback when input truly cannot be used.
- Anticipate varied devices, input methods (touch, mouse, keyboard, screen reader, voice) and capabilities. Keep the interface accessible (WCAG 2.2 AA as the baseline).

## 5. Interaction and performance

**Fitts's Law.** Time to acquire a target depends on its distance and size.
- Touch targets: at least 44x44pt on iOS, 48x48dp on Android, and at least 24x24 CSS px on web (WCAG 2.2 AA), with 44x44 preferred for primary actions.
- Leave enough space between targets to prevent mis-taps.
- Place frequent actions where they are easy to reach: on mobile, the lower half of the screen within thumb reach (bottom navigation, bottom sheets, sticky primary buttons).
- Make the whole row or card clickable when it represents one action, not just a small link inside it.
- Put confirm buttons near the content they act on; keep destructive actions away from primary ones.

**Doherty Threshold.** Productivity soars when the system responds in under 400ms.
- Give visible feedback within 100ms for any interaction (pressed state, spinner, optimistic update) and aim for full response under 400ms.
- Use perceived performance: skeleton screens, optimistic UI, lazy loading, prefetching, instant client-side validation.
- Use progress indicators for waits over about 1 second; show determinate progress for longer tasks.
- Animation can keep users engaged during background work; keep it short and respect reduced-motion settings.
- Only add deliberate delay when it honestly helps users trust a result (e.g. a brief "checking" state). Never fake slowness to manipulate.

**Parkinson's Law.** A task expands to fill the time available.
- Keep task duration within or below what users expect; beating expectations improves the whole experience.
- Use autofill, saved details, address lookup, one-tap payment methods (Apple Pay, Google Pay) and correct input types (`type="email"`, `inputmode="numeric"`, `autocomplete` attributes) to shorten forms.
- Remove optional fields from critical flows or clearly mark them.

**Flow.** Full immersion with energised focus happens when challenge matches skill.
- Remove needless friction: interruptions, unnecessary modals, forced account creation, surprise pop-ups.
- Give continuous feedback so users know what they did and what they achieved.
- Keep features discoverable without cluttering the path; offer shortcuts and power-user paths for experts without burdening beginners.

## 6. Motivation and emotion

**Goal-Gradient Effect.** Motivation increases as people get closer to a goal.
- Show progress clearly in multi-step flows: step indicators ("Step 2 of 4"), progress bars, profile completion.
- Starting users with genuine progress (e.g. steps already completed by earlier actions) boosts completion. Only show real progress; do not fake it.

**Zeigarnik Effect.** People remember incomplete or interrupted tasks better than completed ones.
- Signal that more content exists (partial cards at the scroll edge, "3 of 12 shown").
- Save progress and invite users back to finish (draft saved, resume where you left off, incomplete profile prompts).
- Use gently; nagging about incomplete tasks becomes annoying.

**Peak-End Rule.** People judge an experience by its most intense moment and its end.
- Identify the peak moments (the most helpful, valuable or emotional) and design them to delight.
- Design the end of every journey well: clear confirmation pages, a friendly success state, a useful next step, a receipt email that makes sense.
- Negative moments are remembered more vividly, so put extra care into errors, failures, waits and cancellation: helpful error messages, honest wait times, easy recovery.

**Aesthetic-Usability Effect.** Attractive designs are perceived as more usable.
- Invest in visual polish: consistent spacing, typography, alignment and colour. It builds trust and tolerance for minor issues.
- Do not let polish hide problems. Beautiful prototypes can mask usability issues in testing, so observe what users do, not only what they say.

## Tensions to manage

- **Simplify vs over-abstract.** Hick's Law and Occam's Razor push for fewer elements, but hiding everything behind icons or menus increases load. Keep labels and keep primary actions visible.
- **Emphasis vs noise.** Von Restorff only works if emphasis is rare. One primary action per area.
- **Familiar vs novel.** Jakob's Law beats novelty for core interactions. Innovate where it adds real value, not on navigation or forms.
- **Motivation vs manipulation.** Goal-Gradient, Zeigarnik, Cognitive Bias and deliberate delay can all become dark patterns. Test: would the user thank you if they knew exactly what you were doing?
- **Miller's number.** Chunk content, but do not use "7 plus or minus 2" to justify arbitrary limits.
- **Pretty vs usable.** Aesthetic-Usability means polish matters, and also means polish can hide flaws. Measure task success.

## Review checklist

Run this before finishing any UI work. Fix what fails, or note it as a known trade-off.

- [ ] One clear primary goal and one visually distinct primary action per view (Selective Attention, Von Restorff)
- [ ] Spacing and containers show structure; labels sit closest to their own fields (Proximity, Common Region)
- [ ] Same function looks the same; links and buttons are clearly distinct from text (Similarity)
- [ ] Choices are few, a recommended option is highlighted, long lists have search or filters (Hick's, Choice Overload)
- [ ] Nothing on screen can be removed without harming function (Occam's Razor)
- [ ] Complexity is handled by the system: defaults, autofill, input normalisation (Tesler's, Postel's, Parkinson's)
- [ ] Content is chunked; users recognise rather than recall; context carries across steps (Chunking, Working Memory)
- [ ] Conventions and platform patterns are followed; labels match users' language (Jakob's, Mental Model)
- [ ] Help is inline and contextual; destructive actions can be undone or are confirmed (Paradox of the Active User)
- [ ] Touch targets meet size minimums with enough spacing; key mobile actions are in thumb reach (Fitts's)
- [ ] Feedback under 100ms, response under 400ms or a loading state is shown (Doherty Threshold)
- [ ] Multi-step flows show real progress; drafts are saved (Goal-Gradient, Zeigarnik)
- [ ] Success, error and end states are designed, not left as defaults (Peak-End)
- [ ] Key items are at the start and end of navigation and lists (Serial Position)
- [ ] No dark patterns; no colour-only meaning; reduced motion respected; WCAG 2.2 AA met (Cognitive Bias, Von Restorff, Postel's)
- [ ] Visual polish is consistent, and usability is validated by behaviour, not looks (Aesthetic-Usability)

## Source

Laws of UX by Jon Yablonski: https://lawsofux.com/ . Each law has its own page (e.g. https://lawsofux.com/hicks-law/) with origins and further reading if deeper justification is needed.