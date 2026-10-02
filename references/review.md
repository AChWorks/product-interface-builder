# Interface Review and Finish Loop

Use for explicit interface review requests and for proportional self-review of material visual work.

This reference owns review evidence, visual QA, responsive/adaptive checks, accessibility, interaction states, motion review, and obvious interface-performance risks. It does not replace platform- or locale-specific guidance.

## 1. Scale the review to the change

### Trivial/local change

Review the changed control/surface and its immediate states. Do not run a product-wide audit because a label, icon, spacing value, or isolated component changed.

### Material surface change

Review the changed surface across representative content states, sizes, interactions, and accessibility concerns.

### System/redesign change

Review representative surfaces and shared patterns, including edge states and cross-surface consistency. Do not pretend one screenshot proves the whole system.

The goal is to catch consequential defects, not maximize checklist count.

## 2. Keep evidence levels distinct

Use the strongest evidence available:

1. **Product/design truth** — requirements, tokens, components, copy rules, platform/locale constraints.
2. **Static implementation evidence** — source, styles, structure, state logic, test fixtures.
3. **Rendered evidence** — running UI, screenshots, visual-regression artifacts, actual interaction at relevant sizes/devices.
4. **Measured/assistive evidence** — browser/device/accessibility tooling, performance traces, automated checks, screen-reader or keyboard/touch exercise when actually available.

Rendered evidence is stronger for visual correctness. Static inspection can identify likely problems but is not proof that layout, typography, overflow, responsive behavior, focus, motion, or platform rendering is correct.

Never claim an evidence level that was not actually exercised.

## 3. Recover the intended result before judging

Review against:
- explicit requirements;
- current product/design-system truth;
- the actual target platform/locale;
- the intended user task;
- the scope of the change.

Separate:
- **defect** — contradicts requirements, breaks usability/accessibility, causes visual/interaction failure, or violates established design truth;
- **risk** — plausible failure needing stronger evidence;
- **subjective alternative** — another defensible design direction, not automatically a problem.

Do not rewrite intentional product character into a generic preferred style.

## 4. Static review pass

Before rendering, inspect the implementation for likely failure points relevant to the change.

### Structure and semantics
- information/action order matches intended hierarchy;
- navigation and controls use appropriate semantics for the target platform;
- repeated structures are actually reusable where consistency matters;
- labels, names, states, and status cues are present where users need them;
- hidden/conditional content has a reachable state path.

### Layout
- no suspicious fixed dimensions where content must grow;
- no fragile absolute positioning for normal document/component flow unless justified;
- long strings, localization expansion, empty data, and dense data have a strategy;
- overflow/scroll behavior is intentional;
- spacing/alignment values follow the existing system rather than arbitrary local drift.

### State handling
- loading, error, success, disabled/unavailable, empty, destructive, and unsaved states exist when the flow requires them;
- async state changes do not erase user input or orientation;
- destructive actions have the product's required confirmation/undo path.

### Responsive/adaptive logic
- breakpoints/size classes correspond to composition changes rather than device folklore;
- containers and controls can shrink/grow without clipping;
- priority changes at narrow/wide sizes are reflected in layout behavior;
- platform safe areas/insets are accounted for where relevant.

Static findings remain provisional when rendering could disprove them.

## 5. Rendered visual pass

When render/browser/screenshot capability exists for material work, inspect the actual result.

Use representative sizes/states rather than only one ideal screenshot.

Check:

### Hierarchy and composition
- primary task/action reads first at a glance;
- related elements group visually;
- alignment/rhythm feels intentional;
- secondary content does not compete with the primary task;
- decorative treatment is not masking weak information structure.

### Spacing and density
- repeated spacing is consistent enough to establish rhythm;
- control/content density suits the task;
- empty areas are intentional;
- compact areas remain scannable;
- nested containers do not accumulate excessive padding/borders/radii.

### Typography
- correct fonts/weights actually load;
- fallback does not visibly break script or metrics;
- body/label sizes remain legible;
- line length/line height support the content;
- headings wrap without awkward orphaned fragments where avoidable;
- localized/mixed-script text shapes correctly.

### Color and visual states
- text/control/state distinctions remain visible in the actual theme;
- focus, hover, active, selected, disabled, success/warning/destructive states are distinguishable;
- color is not the only carrier of critical meaning;
- dark/light variants remain coherent when both are supported.

### Overflow and reflow
- no unintended horizontal scroll;
- menus/dialogs/popovers stay within usable bounds;
- text does not overlap controls;
- sticky/fixed elements do not hide focused/important content;
- images/media preserve useful cropping and aspect ratio.

### Content realism
Use real or representative content lengths when available. A polished empty mock is weak evidence for a production interface.

## 6. Responsive and adaptive review

Test the sizes the product actually supports. When exact device/browser coverage is unknown, choose representative narrow, medium, and wide compositions without presenting them as exhaustive device certification.

Verify:
- navigation transformation;
- content priority/reordering;
- table/list/card strategy;
- touch vs pointer affordances where applicable;
- readable text and usable controls under zoom/text scaling;
- orientation/size changes for native/desktop targets when relevant;
- very long localized strings;
- RTL recomposition when RTL is active.

Responsive work can change composition; it is not merely scaling every value down.

## 7. Accessibility review

Apply the accessibility model and standard appropriate to the target platform/product.

At minimum, when relevant, review:

### Perception
- text/control contrast is sufficient for the applicable requirement;
- meaning does not rely on color alone;
- essential images/media have appropriate alternatives;
- text can enlarge/reflow without loss of required content or operation.

### Operability
- keyboard/touch/assistive input can reach required actions;
- focus is visible and not obscured;
- focus order follows logical task order;
- gesture/drag-only actions have an alternative unless the gesture is genuinely essential;
- hit targets are usable for the target platform.

### Semantics and names
- controls expose meaningful names/roles/states;
- headings/landmarks/labels or native equivalents match visual structure;
- errors and validation associate with the relevant control;
- status/async updates are exposed appropriately when users need them.

### Focus and modality
- dialogs/sheets/popovers move/contain/restore focus appropriately for the platform;
- closing/dismissing behavior is predictable;
- keyboard or screen-reader users do not get trapped behind visual overlays.

Automation can find some defects; it is not proof of full accessibility.

## 8. Interaction-state review

For each material interactive control/flow, verify the relevant states:

- rest;
- hover when the platform has hover;
- focus;
- active/pressed;
- selected/current;
- disabled/unavailable;
- loading/in-flight;
- success/confirmed;
- error/retry;
- destructive/undo.

Feedback should be close to the action and preserve context.

Avoid:
- controls that look interactive but contain dead zones;
- hover-only essential information;
- loading states that silently change button meaning;
- disabled actions with no way to understand or resolve why when that information is material;
- ambiguous generic labels when a specific action verb is available.

## 9. Motion review

Motion must earn its cost.

Use motion primarily to:
- explain cause/effect;
- preserve spatial continuity;
- confirm state change;
- direct attention to a meaningful transition;
- express product character without obstructing the task.


When motion is material, keep a small coherent motion vocabulary instead of inventing a new personality for every component. Distinguish at most a few roles such as direct input feedback, ordinary spatial/state transition, and a rare expressive moment. Tune them to the product and platform rather than importing preset timing tables.


Review:
- purpose: would removing the motion reduce understanding or intended character?
- timing: does feedback feel immediate enough for direct manipulation?
- easing: does movement fit the distance/change rather than reuse one curve everywhere?
- choreography: are simultaneous/staggered elements guiding attention rather than creating noise?
- interruption: can user input interrupt/replace animation without fighting stale transitions?
- performance: prefer compositor-friendly transformations where practical; avoid layout-thrashing animation;
- reduced motion: honor the platform/user preference and remove/replace nonessential movement.

Avoid autoplaying decorative motion that competes with content or cannot be paused/stopped when the applicable accessibility requirement demands it.

Do not import external motion tables as rigid canonical timings; tune to product/platform and verify in context.

## 10. Loading and transition quality

Fast responses should not produce distracting flicker. Slow operations should communicate progress without pretending certainty that the system does not have.

When applicable:
- preserve the original action label/context while showing in-flight state;
- avoid layout shift between skeleton/loading and resolved content;
- keep user input stable during hydration/data refresh;
- make retry/recovery clear;
- do not block the whole interface when only one region is busy.

## 11. Obvious interface-performance risks

This Skill does not own backend or systems performance, but visual work should not knowingly introduce obvious UI cost.

Flag or correct, when evident:
- huge unoptimized media above the fold;
- image/video without reserved layout space causing visible shift;
- unnecessary animation of layout-affecting properties;
- rendering enormous lists without an appropriate strategy;
- repeated expensive measurement/reflow in interaction loops;
- gratuitous third-party UI/motion dependencies for a simple effect;
- loading too many fonts/weights/assets for the actual design;
- effects that visibly jank on target hardware.

Use measurement tools when available before making quantitative performance claims.

## 12. Correct before declaring completion

For material implementation work, fix clear in-scope defects you can safely correct before reporting the work complete.

Do not:
- leave an obvious broken responsive state only because it was discovered during review;
- expand into unrelated redesign;
- hide uncertainty by saying "looks good" when the UI was never rendered;
- manufacture extra work after the requested quality bar is met.

If an unresolved defect requires authority, missing product truth, unavailable capability, or a separate owner, state the exact boundary and evidence needed.

## 13. Report high-signal findings

Prioritize by:
1. user harm/blocking behavior;
2. accessibility/interaction failure;
3. broken layout/state/responsive behavior;
4. inconsistency with authoritative product/design truth;
5. polish that materially improves comprehension;
6. subjective alternatives.

Keep findings concise, evidence-linked, and scoped. Do not dump every checked item.

A review can legitimately return no material findings when the evidence supports that result.
