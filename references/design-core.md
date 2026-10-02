# Core Interface Design

Use this reference for new interface work, targeted visual/UX modification, and redesign. It owns cross-locale product-interface reasoning. Locale, platform, and detailed review rules stay in their dedicated references.

## 1. Classify the change before designing

### New interface

Derive direction from the product, audience, content, usage context, platform, and brand evidence. Establish only enough reusable visual system to keep the work coherent.

A new surface still may belong to an existing product. Recover existing design truth before assuming a blank slate.

### Targeted modification

Recover the incumbent visual language first. Preserve established tokens, spacing, typography, components, information architecture, interaction vocabulary, and copy terminology unless the requested change requires otherwise.

Make the smallest coherent change. Do not use a local feature request as permission for opportunistic rebranding, framework migration, wholesale component replacement, or unrelated polish.

### Redesign

Separate durable product truth from replaceable design decisions.

Usually durable:
- user jobs and product capabilities;
- content semantics and information requirements;
- safety/accessibility/legal obligations;
- validated terminology and business rules;
- platform constraints and integrations.

Potentially replaceable:
- visual direction;
- type scale and font choices;
- color roles;
- spacing/density;
- shape/elevation language;
- composition and component expression;
- imagery/illustration direction;
- motion personality.

A redesign should reconsider the system deliberately instead of painting a new style over the existing structure.

## 2. Ground visual direction in the product

Before choosing a style, identify the strongest product-specific inputs available:

- primary user and task;
- emotional/functional goal of the surface;
- content type and density;
- domain materials, language, imagery, data, or physical/visual references;
- brand attributes already evidenced by the product;
- usage conditions such as quick scanning, long reading, creation, monitoring, purchase, collaboration, or high-stakes confirmation.

Turn those inputs into a short direction, not a mood-board dump. A useful direction explains what should feel distinctive and what should remain quiet.

Do not default to whichever visual treatment is currently fashionable. Common patterns are valid when justified by the product; they are weak when selected merely because they are easy to generate.

Spend distinctiveness selectively. One memorable compositional, typographic, imagery, or interaction idea is usually stronger than many unrelated flourishes.

### Choose the surface posture

Decide what success means **on this surface**, not what category the whole product belongs to.

- **Task/operation:** the user needs to complete work, scan status, compare data, or repeat actions efficiently. Familiarity, consistency, state clarity, density, and native expectations usually outrank spectacle.
- **Reading/learning:** the user needs to understand material. Typography, information structure, source fidelity, comfortable measure, and wayfinding carry more weight than component novelty.
- **Decision/persuasion:** the user needs to understand value, trust the offer, and decide or act. Real proof/content, clear sequencing, and a distinctive identity can carry more visual weight.
- **Experience/showcase:** the user is primarily exploring or appreciating the work itself. The interface can recede while sequencing, imagery, and selective interaction lead.

Choose the posture per surface. A productivity product can have a persuasive marketing page and a highly operational dashboard. Do not force one visual register across both.

For task-heavy interfaces, express domain character through typography, color, imagery, language, and precise details rather than literally costuming the UI as a terminal, control panel, or physical instrument unless that metaphor improves the task.

### Keep design dials independent

Treat these as separate decisions:

- **distinctiveness:** conventional ↔ highly characteristic;
- **density:** spacious ↔ information-dense;
- **motion intensity:** quiet ↔ expressive.

Do not assume bold design requires more animation, dense tools must look conservative, or spacious pages must be minimal. Set each axis from the surface's task, audience, and brand evidence.

### Guard against generic defaults

When the brief leaves room for invention, challenge choices that could be pasted into many unrelated products unchanged.

Common warning signs include:
- every section becoming the same rounded card;
- one radius/shadow treatment applied to every level of hierarchy;
- decorative gradients or glows with no connection to product content;
- repetitive eyebrow or all-caps micro-labels above every heading;
- arbitrary numbering that does not represent real sequence or structure;
- default emphasis on a single headline word just to create visual interest;
- decorative arrows appended to every link or action;
- monospace used as generic decoration for ordinary labels or metadata.

These patterns are not banned. Use them when the brief, content, or information structure actually earns them.

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
- For new work, choose type for the content, script coverage, platform, performance constraints, and intended character.
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

### Data presentation

Choose tables, lists, cards, charts, summaries, or detail views based on the comparison and action users need.

- Tables are strong for aligned comparison and dense scanning.
- Lists are strong for repeated entities with a dominant reading order.
- Charts are strong for patterns, change, distribution, and relationships—not for displaying exact values that a table would communicate better.
- Pair visual encodings with labels/legends or direct annotations where users need exact meaning.
- Avoid ornamental charts.

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

## 10. Use design systems proportionally

A design system is a means of consistency, not a mandatory deliverable.

### Reuse first

If authoritative tokens/components/patterns exist, use them. Extend them only when the new need cannot be expressed cleanly.

### Establish only what earns reuse

For new or substantial work, define the smallest shared system that prevents repeated arbitrary decisions, commonly:

- semantic color roles;
- typography scale;
- spacing/density rhythm;
- radius/border/elevation language;
- layout/container conventions;
- control/state patterns;
- motion principles when motion is material.

Prefer relationships and semantic roles over a giant token catalog.

### Local exceptions

A surface-specific exception may be justified, but it should not silently become a global token or pattern. Keep the exception local unless repeated evidence shows it belongs in the shared system.

### Durable artifacts

Persist design decisions only when continuing work benefits from recovery across sessions/people/tools. Reuse the project's existing design source of truth when one exists. Do not manufacture a MASTER/design-system document for a trivial change.

## 11. Self-critique before polishing

Before adding more visual detail, check:

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
