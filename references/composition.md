# Composition and Authority

Product Interface Builder owns user-facing interface intent and visual/UX quality. It does not inherit project-management, repository, release, or platform-implementation authority from the fact that it is active.

## 1. Ownership

| Concern | Owner when composed |
|---|---|
| interface hierarchy, visual direction, design-system intent, typography/color/layout/density, interaction/motion intent, responsive intent, interface accessibility/UX quality, Persian/RTL presentation, visual critique | Product Interface Builder |
| project outcome/scope, priority, dependencies, repository authority, task coordination, integration/CI/release/continuity | active project Master |
| platform-specific implementation mechanism and lifecycle constraints | the active platform specialist/owner |
| WordPress mechanism, Gutenberg safety, theme/plugin placement, WooCommerce/WordPress lifecycle | WP Native Builder when active |
| durable product/business requirements | the project's authoritative product/project source |

One concern should have one active owner. Another Skill may contribute evidence without becoming a second authority.

## 2. Standalone use

Without another specialist, Product Interface Builder may:

- recover available product/design truth;
- design or review the requested interface;
- implement authorized UI changes with the project's existing mechanisms;
- perform proportional self-review.

The absence of another Skill does not justify inventing repository/release authority or claiming platform-specific correctness that was not established.

## 3. Under a project Master

The Master supplies or resolves project scope, current repository state, mutation boundaries, dependencies, and integration/release policy.

Product Interface Builder supplies the smallest useful interface contribution:

- design intent tied to current product truth;
- concrete interface decisions or implementation input;
- authorized UI implementation when assigned;
- visual/UX/accessibility/responsive/interaction findings;
- unresolved design assumptions that materially affect the result.

Do not create a competing roadmap, widen scope, or turn a design preference into a project requirement.

Hand back only what the Master needs: what changed, where it lives, material evidence/limitations, and any decision or owner still required.

## 4. With a platform specialist

Product Interface Builder defines the intended user-facing result. The platform specialist chooses how to realize it safely in that platform.

For WordPress specifically:

- Product Interface Builder owns composition, visual intent, interface states, responsive intent, user-facing accessibility/UX, locale presentation, and visual critique.
- WP Native Builder owns WordPress owner/mechanism selection, Gutenberg/block safety, templates/patterns, theme/plugin APIs, WooCommerce lifecycle concerns, and WordPress-specific placement.

Do not prescribe brittle platform internals merely to achieve a visual preference. The platform owner may adapt the mechanism while preserving the intended experience.

## 5. Shared concerns

When concerns overlap, divide them by decision type:

- **Accessibility:** Product Interface Builder owns user-facing outcome/critique; the platform owner implements the correct semantics/mechanism.
- **Responsive behavior:** Product Interface Builder owns intended recomposition; the platform owner implements it safely.
- **Visual review:** Product Interface Builder owns visual/UX judgment when active; platform checks should not introduce a competing art direction.
- **Performance:** Product Interface Builder may flag obvious interface/perceived-performance costs; system/backend performance belongs elsewhere.

Do not apply overlapping guidance from multiple Skills as parallel mandatory checklists.

## 6. Durable state

Persist only accepted conclusions that future work will need, using the project's existing source of truth.

Examples:
- shared interface direction or token/pattern change;
- locale/platform requirement;
- unresolved material UI/accessibility risk;
- the implemented interface artifact itself.

Do not create duplicate design/project state merely because this Skill participated.

## 7. Invocation neutrality

Capability fallback rules are owned by `SKILL.md`; do not restate them here. Composition changes ownership, not the underlying evidence standard.

Provider/tool names do not define these boundaries. The same ownership rules apply through any compatible invocation mechanism.
