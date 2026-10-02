# Core Interface Design Contract

Use this reference for new interface work, targeted visual/UX modification, and redesign.

## Classify the change before designing

### New interface

Derive direction from the product, audience, content, usage context, platform, and brand evidence. Establish only enough reusable visual system to keep the work coherent.

### Targeted modification

Recover the incumbent visual language first. Preserve established tokens, spacing, typography, components, information architecture, and interaction vocabulary unless the requested change requires otherwise. Avoid opportunistic redesign.

### Redesign

Separate durable product truth from replaceable design decisions. Keep requirements, content semantics, user tasks, accessibility obligations, and platform constraints unless the redesign explicitly changes them. Reconsider the visual system deliberately rather than layering a new style on top of the old one.

## Stable design constraints

- Make hierarchy communicate importance and sequence.
- Use spacing, density, typography, color, shape, imagery, and motion as one coherent language.
- Prefer a small number of intentional distinctive choices over decoration everywhere.
- Use structural devices only when they encode information or hierarchy.
- Respect real content length and states; do not design only for ideal placeholder copy.
- Keep controls and state language consistent across the flow.
- Account for loading, empty, error, success, disabled, destructive, sparse, dense, and long-content states when they are material to the surface.
- Treat responsive behavior as recomposition when priorities change, not merely proportional shrinking.
- Prefer existing project tokens/components over locally invented values when they can express the intent.

## Design-system proportionality

A design system is a means of consistency, not a mandatory deliverable.

Create or extend tokens/patterns when multiple surfaces need the same decision or when future work would otherwise repeatedly rediscover it. For a bounded change, use the incumbent system and avoid creating a second one.

Style catalogs, palettes, font pairings, and pattern libraries may generate options, but the current product context chooses among them.
