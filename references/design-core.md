# Core Interface Design

Use this reference for new interface work, targeted visual/UX modification, and redesign. It owns cross-locale product-interface reasoning. Locale, platform, and detailed review rules stay in their dedicated references.

## Contents

[Change type](#1-classify-the-change-before-designing) · [Direction](#2-ground-visual-direction-in-the-product) · [Hierarchy](#3-shape-hierarchy-before-decoration) · [Layout](#4-compose-layout-and-density-deliberately) · [Typography](#5-treat-typography-as-interface-structure) · [Color](#6-build-color-from-roles) · [Visual language](#7-keep-shape-depth-imagery-and-icons-coherent) · [Controls/copy/data](#8-design-controls-around-tasks-and-states) · [Edge states/onboarding](#9-design-the-non-ideal-states) · [Design systems](#10-use-design-systems-proportionally) · [Coherence check](#11-check-coherence-before-adding-detail)

## 1. Classify the change before designing

### New interface

Derive direction from the product, audience, content, usage context, platform, and brand evidence. Establish only enough reusable visual system to keep the work coherent.

A new surface still may belong to an existing product. Recover existing design truth before assuming a blank slate.

### Targeted modification

Recover the incumbent visual language first. Preserve established tokens, spacing, typography, components, information architecture, interaction vocabulary, and copy terminology unless the requested change requires otherwise.

Make the smallest coherent change. Do not use a local feature request as permission for opportunistic rebranding, framework migration, wholesale component replacement, or unrelated polish.

### Redesign

Separate constraints that must survive from visual choices that are open to change.

Keep fixed unless the request or authoritative product evidence changes them:
- user jobs and product capabilities;
- content semantics and information requirements;
- safety/accessibility/legal obligations;
- validated terminology and business rules;
- platform constraints and integrations.

Reconsider deliberately:
- visual direction;
- type scale and font choices;
- color roles;
- spacing/density;
- shape/elevation language;
- composition and component expression;
- imagery/illustration direction;
- motion character.

Do not confuse a redesign with restyling the old layout. Rebuild visual decisions around the retained constraints.

## 2. Ground visual direction in the product

Before choosing a style, identify the strongest product-specific inputs available:

- primary user and task;
- emotional/functional goal of the surface;
- content type and density;
- domain materials, language, imagery, data, or physical/visual references;
- brand attributes already evidenced by the product;
- usage conditions such as quick scanning, long reading, creation, monitoring, purchase, collaboration, or high-stakes confirmation.

Turn those inputs into a short direction, not a mood-board dump. A useful direction explains what should feel distinctive and what should remain quiet.

Treat content as part of the interface material. Prefer real copy, data, imagery, and examples when available. When exploratory work needs realistic volume but factual content is unavailable, use clearly representative/synthetic material to exercise hierarchy, wrapping, density, and states; never let placeholder content masquerade as a real claim, customer, metric, or product fact.

Do not default to whichever visual treatment is currently fashionable. Common patterns are valid when justified by the product; they are weak when selected merely because they are easy to generate.

Allocate visual emphasis according to hierarchy. Use a small number of deliberate identity cues that reinforce the product; competing gestures weaken both hierarchy and character.

### Set priorities from the user job

Before choosing visual treatments, write a compact priority statement for the surface from the evidence you have. Base it on:

- what the user must accomplish, understand, compare, decide, or notice;
- how often and how quickly the surface is used;
- information density and content complexity;
- consequence/trust level of mistakes or decisions;
- how much brand expression helps rather than distracts;
- the dominant input/device context.

Example: a frequently used operations screen may prioritize fast comparison and stable interaction while carrying brand character through type, color, and detail; a product-introduction surface may give sequencing, imagery, and identity more room because attention and trust are part of the task.

Do not turn those priorities into rigid page categories. A single product can need very different priorities on different surfaces.

### Keep visual qualities independent

Do not treat density, visual distinctiveness, contrast, ornament, and motion as one bundled style preset. Decide each from the task and content. A dense interface can still be visually distinctive; a bold interface can remain quiet in motion; a spacious page does not need decorative excess.

### Test every distinctive choice for relevance

For each strong visual device, ask:

- What product, content, hierarchy, state, or interaction does it express?
- Would the same choice survive unchanged in an unrelated product?
- Does repeating it improve comprehension or merely create a pattern?
- If it were removed, would the interface lose useful meaning, orientation, or character?

Keep familiar conventions when they help users. Keep unusual choices when they are earned by the product. Remove decoration that has no defensible role.

## 3. Shape hierarchy before decoration

For each surface, make the intended reading/action order apparent.

Use:
- information order;
- grouping/proximity;
- alignment;
- size and typographic contrast;
- whitespace/density;
- color/weight;
- progressive disclosure;
- placement and repetition.

Structural devices such as cards, borders, dividers, labels, badges, numbering, or containers should encode grouping, state, sequence, or affordance. Do not add them merely to make a screen look designed.

Avoid chopping every idea into equal cards. Equal visual weight implies equal importance.

### Remove competition before adding structure

When a surface feels busy or unclear, simplify the decision model before decorating it.

- Remove or merge redundant labels, repeated explanations, and duplicate actions.
- Keep one clearly dominant action in a decision area unless the task genuinely has co-equal outcomes.
- Use progressive disclosure for secondary complexity that users do not need yet.
- Prefer inline or in-context interaction before introducing interruption/modal behavior.
- Do not add a card, border, heading, or background merely to compensate for weak grouping.

## 4. Compose layout and density deliberately

Choose layout from content and task behavior, not from a preferred grid pattern.

- Keep primary actions near the information that justifies them.
- Align elements to an intentional grid, baseline, edge, or optical relationship.
- Let repeated structures establish rhythm; use exceptions to signal real differences.
- Tune density for the task. Operational/data-heavy screens may need compact scanning; reading, onboarding, and persuasive content may need more breathing room.
- Preserve useful content width. Do not stretch readable text simply because the viewport is wide.
- Avoid large empty areas that have no compositional purpose.
- Design for short, typical, and long content rather than only the ideal string length.

Responsive recomposition and platform-specific layout behavior are owned by the platform/review references.

## 5. Treat typography as interface structure

Typography communicates hierarchy, personality, density, and scanning behavior.

- Start from the project's actual typefaces when modifying an existing product.
- For new work, choose type for the content, script coverage, platform, performance constraints, and intended character. Verify current availability/licensing and the actual weights/scripts the project can ship rather than trusting a static font shortlist.
- Use a small intentional type scale and a small set of weights.
- Distinguish levels by a combination of size, weight, line height, width, spacing, and placement rather than arbitrary one-off values.
- Keep body text comfortably readable and line lengths appropriate to the content.
- Ensure interface labels remain clear at the actual density.
- Avoid decorative display treatment where clarity is the job.
- Do not introduce a second or third family without a specific role it improves.

Script-specific shaping, line-height, bidi, and Persian typography behavior live in the locale reference.

## 6. Build color from roles

Color choices should form a system of roles rather than a collection of attractive swatches.

At minimum distinguish as applicable:
- canvas/surface;
- primary text and secondary text;
- border/separator;
- primary action/brand;
- focus/selection;
- informational/success/warning/destructive states;
- data-series colors when needed.

Prefer semantic tokens or existing project tokens over raw values repeated through components.

Use accent color where attention or identity is earned. If everything is accented, nothing is prioritized.

Color must not be the only carrier of critical meaning. Detailed contrast/accessibility verification belongs to the review reference.

## 7. Keep shape, depth, imagery, and icons coherent

### Shape and depth

Use radius, border, shadow, blur, and elevation consistently enough that users can infer hierarchy. Nested shapes should look optically related. Avoid applying identical radius/shadow treatment to every object regardless of role.

### Imagery and illustration

Choose imagery because it helps explain, orient, demonstrate, or express the product. Match cropping, aspect ratio, treatment, and art direction across the surface. Do not fabricate people, customers, logos, awards, product screenshots, or claims that are supposed to be real.

### Icons

Use one coherent icon language. Icons should clarify actions or categories, not decorate every label. Directional icons must follow the actual interface direction; locale-specific behavior is owned by the locale reference.

## 8. Design controls around tasks and states

Controls should say what happens and expose the state users need to make a decision.

### Actions

- Name actions with specific verbs when possible.
- Keep the same action vocabulary through button, progress, success, and error states.
- Distinguish primary, secondary, tertiary, and destructive actions by actual priority.
- Do not create multiple visually dominant actions in one decision area without reason.

### Forms

- Group fields by user task, not backend schema.
- Use persistent labels for meaningful inputs.
- Make requirements and validation recoverable.
- Keep destructive or irreversible outcomes explicit.
- Avoid asking for data before the product needs it.

Detailed input semantics, focus, keyboard/touch behavior, and accessibility checks live in the platform/review references.

### Navigation

Navigation should reflect the product's information architecture and user mental model. Keep location, return path, and destination meaning predictable. Do not add navigation levels simply to fit a component pattern.

### Interface copy

Treat copy as part of the interaction, not filler around the visual design.

- Use the product's established nouns and verbs consistently.
- Prefer labels that name the actual action or destination over generic words such as "Continue" when a specific label is available.
- Error, empty, permission, and blocked states should explain the next useful step when one exists.
- Keep instructions close to the control or decision they explain.
- Preserve technical identifiers or domain terms when translating or simplifying them would reduce accuracy.
- Write complete messages that can be translated and reordered; avoid assembling user-facing sentences from fragments.
- Keep variables, counts, and dynamic values structurally separate from surrounding copy so pluralization/localization can change their order.
- Let copy expand instead of abbreviating it merely to protect a brittle layout.
- Do not invent proof, metrics, testimonials, guarantees, capabilities, or business facts to make a layout feel complete.

Locale-specific register and Persian wording belong to the locale reference.

### Data presentation

Choose tables, lists, cards, charts, summaries, or detail views from the question users need answered.

- Tables are strong for exact values, aligned comparison, dense scanning, sorting, and accessible fallback.
- Lists are strong for repeated entities with a dominant reading order.
- Use bars for comparing discrete magnitudes, lines for change over time, distribution plots for spread/outliers, and scatter-style views for relationships between continuous variables.
- Use part-to-whole charts only when there are few categories and rough proportion is the actual question; switch to bars/tables when precise comparison matters.
- Do not add a gauge, map, funnel, network, or decorative visualization unless the underlying structure really matches that form.
- For dense or interactive charts, provide direct labels or an equivalent table/summary when users need exact meaning or non-visual access.
- Encode important distinctions with more than hue alone when possible.
- Avoid ornamental charts and unnecessary animation of data.

## 9. Design the non-ideal states

When material to the flow, account for:

- loading and progressive arrival;
- empty/new-user states;
- partial or sparse data;
- dense/overflowing data;
- validation and recoverable errors;
- permission/access limits;
- offline/retry states when the product has them;
- success/confirmation;
- disabled/unavailable actions;
- destructive confirmation or undo;
- very long content and localization expansion.

Each state should help the user understand what happened and what they can do next. Do not use mood, apology, or decorative emptiness instead of direction.

### First use and onboarding

When users need orientation:

- get them to a meaningful product action as early as possible;
- teach features in the context where they become useful rather than front-loading a tour;
- let experienced users skip explanatory guidance when no safety/setup requirement prevents it;
- make empty states explain what belongs there and the next useful action;
- use working examples or realistic previews when they teach the product better than prose;
- do not block ordinary product access merely to force completion of an educational sequence.

## 10. Use design systems proportionally

A design system is a means of continuing reuse, not a mandatory deliverable.

For ordinary interface work:

- reuse authoritative existing tokens/components/patterns;
- make the smallest coherent extension needed by the current product;
- keep one-off exceptions local rather than promoting them into global rules;
- do not create a new token taxonomy, component library, documentation site, or governance process merely because the surface needs visual consistency.

When the work explicitly concerns or materially requires reusable token architecture, component contracts, themes/modes, extension rules, or system-wide change/deprecation, that deeper decision domain is owned by [design-systems.md](design-systems.md) and routed directly from `SKILL.md`.

## 11. Check coherence before adding detail

Before adding more detail, check:

- Does the direction clearly relate to this product and content?
- Is the primary task obvious?
- Are hierarchy and grouping understandable without decoration?
- Did a generic component pattern replace actual information architecture?
- Is there one coherent visual language rather than several fashionable ideas?
- Did a targeted modification accidentally redesign neighboring surfaces?
- Are real states/content lengths represented?
- Could one decorative element be removed without losing meaning?

Then polish the remaining system rather than adding novelty for its own sake.

Rendered visual verification, responsive/accessibility checks, interaction behavior, and motion review are owned by [review.md](review.md).
