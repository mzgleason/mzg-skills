---
name: design-architect
description: "Design direction selection and design-planning support for product, page, and feature UI work. Use when a user needs help choosing a visual style, wants the top three design directions based on content and best practices, wants quick mock concepts to compare before picking a direction, or wants design tickets created after a direction is chosen."
---

# Design Architect

Shortlist strong UI directions before design work starts, then turn the chosen direction into an actionable design backlog.

Default to producing visuals first, not just verbal descriptions.

If the user provides screenshots, a product URL, copy, a PRD, or existing brand/design system files, inspect them first. Preserve an established design system unless the user clearly wants a new direction.

## Modes

Classify the request into one of these modes before recommending styles:

- `Product UI mode`: dashboards, app shells, flows, onboarding, settings, admin, data-heavy features, B2B surfaces, transactional product UX
- `Brand / Marketing mode`: landing pages, launch pages, campaigns, portfolio pages, event sites, editorial or storytelling surfaces

Use the mode to filter style choices:

- In `Product UI mode`, prioritize clarity, hierarchy, trust, accessibility, and component scalability. Treat expressive styles as accent systems unless the user explicitly wants a bold reset.
- In `Brand / Marketing mode`, allow more visual range and emotional differentiation, but still protect legibility and content flow.

If the request spans both, say so and recommend one mode as primary and the other as secondary.

## Workflow

Work through this sequence:

1. **Build the design brief**
   - Identify what is being designed: product, page, flow, feature, deck, or artifact.
   - Capture the content shape: marketing-heavy, data-dense, transactional, onboarding, editorial, community, developer tool, etc.
   - Capture constraints: platform, audience trust expectations, accessibility, brand tone, existing design system, implementation speed, and whether the design needs to feel safe or distinctive.
   - If key details are missing, make reasonable assumptions and state them briefly instead of blocking.

2. **Generate a style shortlist**
   - Start from the style matrix in [references/design-styles.md](references/design-styles.md).
   - Consider several plausible styles, then score them before ranking the top three.
   - Do not pick trendy directions just because they are visually interesting. Penalize styles that hurt readability, discoverability, or credibility for the given use case.
   - When the design is part of an existing product, bias toward evolution instead of a jarring visual reset.

3. **Score candidates**
   - Score each plausible candidate from `1-5` on:
     - `Content fit`
     - `Clarity and hierarchy`
     - `Trust and credibility`
     - `Distinctiveness`
     - `Accessibility safety`
     - `Implementation fit`
   - Treat `Accessibility safety` and `Implementation fit` as gating checks, not just decorative scores.
   - Eliminate a style from the final three if:
     - it is likely to create contrast or discoverability problems
     - it clashes with an existing design system the user wants to preserve
     - it requires a level of custom illustration, motion, or craft the project likely cannot support
   - Use the scores to justify the ranking. Do not present raw numbers without explanation.

4. **Present the top three options**
   - Present exactly three style options unless the user asks for more.
   - Use the same structure for each option:
     - `Style`
     - `Why it fits this content`
     - `Where it could fail`
     - `Visual recipe`: palette, typography, shapes, spacing, depth, motion, imagery, and component feel
     - `Best applied to`: landing page, dashboard, onboarding, ecommerce, portfolio, AI product, etc.
   - Be decisive. Rank them `1`, `2`, `3` and explain why the top option wins.

5. **Show rejected directions**
   - Include `1-2` plausible styles that were considered but rejected.
   - For each rejected direction, explain briefly why it did not make the final three.
   - Favor rejected options that a user might reasonably expect, so the tradeoff is visible.

6. **Mock up fast comparison concepts**
   - Create a visual comparison for each of the three shortlisted styles before asking the user to choose.
   - Default to a visuals-first output. Use the best available format in this order:
     - `Image mockup`: preferred when an image-generation tool or skill is available
     - `HTML/CSS or React concept`: preferred when code-based visual mockups are more practical
     - `Structured wireframe block`: fallback when no rendering capability is available
   - Use `Textual concept` only when the user explicitly wants strategy without visuals or when no visual format is realistically possible.
   - Reuse the same underlying content across all three concepts so the comparison is about style, not scope.
   - Keep each concept short: enough to make the direction legible, not a full production design.
   - State which visual format you are using and why.

7. **Ask the user to choose a direction**
   - After showing the three concepts, ask which direction they want to pursue or whether they want a hybrid.
   - If the user hesitates, recommend one option and say why.

8. **Offer follow-up design tickets**
   - After the user selects a direction, explicitly ask whether they want design tickets created.
   - If yes, ask which ticket scope they want:
     - `Simple page`
     - `Feature or flow`
     - `System-level redesign`
   - If the user does not specify a scope, recommend one based on the request before writing tickets.
   - Tailor the ticket set to the selected scope:
     - `Simple page`: use a lean set focused on direction, page design, responsive states, and handoff
     - `Feature or flow`: include user-flow definition, states, edge cases, component updates, prototype, and handoff
     - `System-level redesign`: include foundation work, design principles, system updates, migration planning, critical templates, validation, and handoff

## Ticket Format

When generating design tickets, use this structure unless the user requests another format:

- `Title`
- `Goal`
- `Scope`
- `Deliverables`
- `Dependencies`
- `Acceptance criteria`

Keep tickets specific enough that a designer can execute them without another discovery round. Include research, copy, or engineering dependencies when relevant.

## Ticket Scope Guidance

Use these defaults after the user answers the scope question:

- `Simple page`
  - Usually `4-5` tickets
  - Best for landing pages, microsites, one-off marketing pages, or a single static surface
- `Feature or flow`
  - Usually `6-8` tickets
  - Best for onboarding, checkout, settings, search, dashboards, or other multi-state UX work
- `System-level redesign`
  - Usually `8-12` tickets
  - Best for app-wide visual refreshes, design-system overhauls, or broad product-area redesigns

Do not force the largest ticket pack if the work is clearly smaller.

## Output Guidance

- Lead with a short brief summary of the design problem and the assumptions used.
- State the active mode: `Product UI mode` or `Brand / Marketing mode`.
- Keep option names human-readable. Prefer names like `Editorial Minimalism`, `Structured Bauhaus`, or `Bold Neubrutalism` over vague labels.
- Tie every recommendation back to the content and audience, not just aesthetics.
- If the user is designing a core workflow or enterprise surface, prioritize readability, hierarchy, accessibility, and trust.
- If the user is designing a campaign, concept page, or brand-forward launch surface, allow more visual risk.
- If the user asks for implementation after selecting a direction, carry the chosen visual recipe into the actual design or frontend work.

## Example: Product UI Mode

User request:

`Help me choose a design direction for our B2B analytics dashboard for operations managers.`

Good output shape:

- Brief summary + assumptions
- Active mode
- Top 3 ranked styles
- Rejected directions
- Mockup format used
- 3 quick comparison concepts
- Question asking the user to choose a direction
- Question asking whether to create tickets and which scope

Sample:

`Summary`: Designing a data-dense analytics dashboard for operations managers. I am assuming the product needs high trust, fast scanning, and low learning cost.

`Mode`: Product UI mode

`Top directions`

1. `Editorial Minimalism`
   - Best fit because it supports dense tables, clear hierarchy, and enterprise trust.
   - Risk: can feel generic without a strong type scale and restrained accent system.

2. `Bento Grid`
   - Strong option for modular KPI storytelling and responsive dashboard cards.
   - Risk: can become visually noisy if every tile competes for attention.

3. `Bauhaus / Geometric Modernism`
   - Adds more personality while still preserving layout discipline.
   - Risk: decorative geometry can interfere with fast scanning if overused.

`Rejected directions`

- `Neubrutalism`: too aggressive for a high-trust operations surface
- `Glassmorphism`: likely to reduce legibility in a dense dashboard

`Mockup format`: HTML/CSS or React concept, because a product UI request benefits from a concrete visual artifact and code is often the most portable way to produce one.

`Concept 1`
- Header with concise KPI ribbon
- Left nav in neutral tones
- Main area uses clear chart cards, restrained color, dense but readable tables

`Concept 2`
- Modular tile layout with grouped KPI clusters
- Mixed card sizes for narrative emphasis
- Slightly more visual energy for summaries and alerts

`Concept 3`
- Strong grid with bold section dividers
- Geometric accent panels and clearer feature separation
- More visual identity, but still structured

`Question`: Which direction do you want to pursue: `1`, `2`, `3`, or a hybrid?

`Follow-up`: Do you want design tickets created, and if so which scope: `Simple page`, `Feature or flow`, or `System-level redesign`?

## Example: Brand / Marketing Mode

User request:

`Show me design directions for a landing page for an AI meeting assistant launch.`

Good output shape:

- Brief summary + assumptions
- Active mode
- Top 3 ranked styles
- Rejected directions
- Mockup format used
- 3 fast concepts
- Question asking the user to choose a direction
- Question asking whether to create tickets and which scope

Sample:

`Summary`: Designing a launch landing page for an AI meeting assistant. I am assuming the page needs differentiation, product clarity, and a modern tech feel without losing credibility.

`Mode`: Brand / Marketing mode

`Top directions`

1. `Aurora Gradient`
   - Best fit because it gives the page a modern AI atmosphere while keeping the layout flexible and legible.
   - Risk: without strong typography, it can feel visually thin.

2. `Bento Grid`
   - Strong for communicating multiple features, proof points, and use cases quickly.
   - Risk: can feel product-marketing standard if the visual system is too safe.

3. `Bold Neubrutalism`
   - Good if the brand wants more edge and memorability.
   - Risk: may reduce trust for more mainstream or enterprise buyers.

`Rejected directions`

- `Neumorphism`: too soft and low-contrast for a launch page with dense messaging
- `Art Nouveau`: visually distinctive, but too ornamental for this product story

`Mockup format`: Image mockup, because a marketing landing page benefits from a fast rendered visual when image-generation capability is available.

`Concept 1`
- Large gradient hero with sharp headline
- Floating translucent product preview
- Clean proof section with logos and testimonials

`Concept 2`
- Modular hero with stacked feature cards
- Bento-style grid for use cases, integrations, and outcomes
- Crisp CTA blocks between sections

`Concept 3`
- Thick borders, oversized headings, blunt CTA buttons
- Loud contrast and asymmetric sections
- Strong personality with a startup-native tone

`Question`: Which direction do you want to pursue: `1`, `2`, `3`, or a hybrid?

`Follow-up`: Do you want design tickets created, and if so which scope: `Simple page`, `Feature or flow`, or `System-level redesign`?
