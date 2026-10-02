# Information Architecture, Findability, and Complex Interactions

Use this reference when users must find, navigate, refine, sequence, or manipulate information through a structure whose organization or interaction model materially affects success.

This file owns interface-level information architecture, findability, wayfinding, and selection of complex interaction patterns. [human-factors.md](human-factors.md) owns cognitive/usability confidence, [platforms.md](platforms.md) owns target-platform conventions, and [review.md](review.md) owns validation evidence.

## Contents

[Structure first](#1-separate-information-architecture-from-navigation-presentation) · [Wayfinding](#2-make-location-scope-and-return-path-legible) · [Findability tools](#3-choose-search-filter-sort-and-saved-views-by-the-task) · [Flows](#4-preserve-context-through-multi-step-flows) · [Complex widgets](#5-prefer-established-interaction-models-for-complex-widgets) · [Authority](#6-route-exact-widget-behavior-to-current-authority) · [Overlap](#7-keep-domain-boundaries-clean)

## 1. Separate information architecture from navigation presentation

Decide what exists and how it is related before deciding whether it appears as tabs, a sidebar, cards, a menu, or another visual component.

Clarify:

- the user's primary objects, tasks, and destinations;
- hierarchy versus peer relationships;
- categories/taxonomy and the labels users can predict;
- global destinations that remain useful across the product;
- local destinations within the current area/object;
- contextual actions or related destinations that depend on current state;
- utility/account/help destinations that should not compete with task structure.

Prefer one stable conceptual home for each important thing. Cross-links and shortcuts may provide alternate paths without creating multiple contradictory taxonomies.

Do not expose implementation/service boundaries as navigation merely because the backend is divided that way.

## 2. Make location, scope, and return path legible

Users should be able to answer, when relevant:

- Where am I?
- What does this section/object contain?
- What scope will this action or filter affect?
- How did I get here or where can I safely return?
- What is the next likely destination?

Use the lightest wayfinding mechanism that answers the real question:

- persistent global/local navigation for stable destinations;
- active/current-location state where peers could be confused;
- breadcrumbs for meaningful hierarchy, not as decoration;
- page/object titles that match navigation language;
- contextual back/return links when the previous task context matters more than hierarchy;
- visible filter/search scope when results can otherwise be misinterpreted.

Browser/system Back should remain useful where the platform supports it; do not replace expected history behavior with a fragile custom imitation.

## 3. Choose search, filter, sort, and saved views by the task

Do not add every findability control to every collection.

| User need / collection shape | Prefer |
|---|---|
| small, understandable set that can be scanned | clear browse/navigation; search may be unnecessary |
| known-item lookup or large heterogeneous corpus | search with clear scope and result feedback |
| narrowing by a few meaningful attributes | filters |
| repeated multi-attribute exploration | faceted filtering when attributes and result counts genuinely help decisions |
| changing order without excluding items | sort |
| returning often to the same useful state | recent/saved views only when persistence reduces repeated work |
| resuming interrupted discovery | preserve query/filter/sort/context when safe and expected |

For search/refinement:

- use labels and facet names that reflect the domain rather than database fields;
- distinguish an empty corpus from “no results for these criteria”;
- make active constraints visible and individually removable when complexity warrants it;
- make clear whether filters combine as intersection, alternatives, ranges, or another model when ambiguity would change results;
- avoid filters with no decision value merely because metadata exists;
- preserve the user's position/context when opening an item and returning to results where practical;
- do not silently reset a meaningful query/refinement state.

Exact search ranking, indexing, normalization, and backend query architecture belong outside this Skill. Interface decisions should make current scope/state understandable.

## 4. Preserve context through multi-step flows

Use a multi-step flow when the task has a meaningful sequence, dependency, or review boundary; do not fragment a short independent form merely to create a wizard.

When steps are material:

- communicate current step/status and remaining shape at a level users can understand;
- keep earlier choices available for review/edit when product rules allow;
- preserve valid progress across validation errors and ordinary navigation;
- avoid forcing users to re-enter information the product already has unless a current security/legal/product rule requires it;
- separate review/confirmation from irreversible commitment when consequences warrant it;
- define what happens on interruption, expiry, partial completion, or returning later;
- keep branching paths explicit enough that users understand why a step appears or disappears.

[human-factors.md](human-factors.md) owns whether the flow remains a usability hypothesis and what task evidence would strengthen confidence.

## 5. Prefer established interaction models for complex widgets

For dialogs, tabs, comboboxes, menus, listboxes, trees, grids, toolbars, drag/drop, and other composite interactions:

1. Prefer a native platform/HTML control when it expresses the required behavior well.
2. Otherwise prefer an established platform/accessibility pattern whose interaction model matches the task.
3. Use a custom interaction model only when the product requirement cannot be met coherently by established patterns.
4. Treat a materially novel custom widget as a human-factors/usability hypothesis and validate it proportionally.

Do not choose a widget because its visual shape looks familiar while changing its established behavior.

Before selecting a complex widget, distinguish the user's actual need. For example:

- choosing one value is not automatically a menu;
- navigating a hierarchical structure is not automatically a tree;
- displaying tabular data is not automatically an interactive grid;
- showing a temporary surface is not automatically a modal dialog;
- visually grouped controls do not automatically require a toolbar interaction model.

For drag/drop, preserve clear selection, destination, state change, failure, and recovery. When exact keyboard/assistive alternatives are material, use the current authoritative platform/accessibility guidance rather than inventing behavior.

## 6. Route exact widget behavior to current authority

Complex controls have coupled semantics, focus, keyboard, state, and announcement behavior. Exact requirements can change and differ by platform.

```text
Does the selected interaction use a native/established complex pattern?
  ├─ native platform control
  |    -> follow current target-platform documentation
  ├─ web custom/composite widget
  |    -> consult current W3C/WAI-ARIA Authoring Practices + applicable standards
  └─ materially novel pattern
       -> minimize novelty
       -> define user-facing state/escape/recovery
       -> use human-factors evidence proportional to the risk
```

Do not freeze complete keyboard maps, ARIA role/state recipes, or platform API behavior into this Skill. Retrieve the current authoritative pattern for the actual widget when implementation/review depends on it.

For web, native HTML semantics remain preferable when they meet the need; ARIA does not make an interaction model correct merely by adding roles.

## 7. Keep domain boundaries clean

- **Human factors:** whether users can understand/learn/complete/recover from the structure or interaction, and the evidence confidence.
- **Platform:** target-platform presentation/interaction conventions and implementation constraints.
- **Review:** static/rendered/interaction evidence and actual defects.
- **Accessibility/current authority:** exact semantic, focus, keyboard, announcement, and conformance requirements when material.
- **Backend/search architecture:** indexing, ranking algorithms, storage, concurrency, and service implementation stay with their engineering owner.

This reference defines the interface structure and pattern choice; it does not vendor a component catalog or create a second accessibility specification.
