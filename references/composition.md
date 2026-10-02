# Composition and Authority

Product Interface Builder owns user-facing interface design intent and visual/UX quality. Composition must never transfer unrelated project, repository, release, or platform-mechanism authority.

These semantics are role-based and capability-based. They must work in any compatible agent runtime; no specific dispatch/tool/vendor mechanism is part of the contract.

## 1. Ownership matrix

| Concern | Canonical owner in composition |
|---|---|
| product-interface design reasoning, visual direction, hierarchy, design systems, typography/color/layout/density, interaction/motion intent, responsive intent, interface accessibility/UX quality, Persian/RTL presentation, rendered visual critique | Product Interface Builder |
| project framing, scope, priority, dependencies, repository mutation authority, worker/task coordination, review/integration policy, CI, release, continuity | GitHub Project Orchestrator / active project Master |
| WordPress owner/mechanism selection, Gutenberg/block serialization safety, theme/builder/plugin placement, hooks/APIs, WooCommerce/WordPress lifecycle behavior | WP Native Builder |
| durable product/business requirements | the project's authoritative product/project source, not any Skill default |
| Koinon ecosystem discovery/governance/contracts | Koinon sources when applicable; project-local implementation/work remains in the owning repository |

A supporting Skill may contribute evidence to another owner's decision without becoming a second rule owner.

## 2. Standalone behavior

When no project Master or platform specialist is active, Product Interface Builder remains fully useful.

It may:
- recover the available product/design truth;
- design or review the requested interface;
- implement authorized UI changes when the environment permits;
- use the target project's existing stack and mechanisms;
- perform proportional self-review.

It must not invent project/repository/release authority merely because no Master is present.

Missing specialist capability narrows specialization; it does not automatically block ordinary safe interface work.

## 3. Composition with a project Master

When GitHub Project Orchestrator or another explicit project Master is active:

### The Master provides or resolves
- current outcome/scope;
- authoritative repository/project state;
- mutation/approval boundaries;
- task acceptance/dependencies;
- integration/release path.

### Product Interface Builder provides
- design intent and rationale tied to product truth;
- concrete interface decisions/tokens/pattern changes when needed;
- implementation input or authorized implementation within the task scope;
- visual/UX/accessibility/responsive/interaction review evidence;
- explicit unresolved design risks or missing product truth.

### Product Interface Builder does not
- reprioritize the roadmap;
- widen repository mutation scope;
- create competing project plans/issues merely to track its own reasoning;
- merge/release/deploy unless the active project authority separately permits it;
- turn a design preference into a project requirement without evidence.

### Handback

Return the smallest useful handback to the Master:
- what design outcome was established/changed;
- what artifact or exact change carries it;
- what evidence was reviewed;
- any material unresolved dependency/decision;
- whether another owner must act next.

Do not send an internal checklist transcript.

## 4. Composition with WP Native Builder

For WordPress work, design intent and WordPress mechanism are separate decisions.

### Product Interface Builder owns
- intended information hierarchy and composition;
- visual direction and token/pattern intent;
- interface states and interaction intent;
- responsive/adaptive intent;
- user-facing accessibility/UX quality;
- locale/Persian/RTL presentation requirements;
- rendered visual critique.

### WP Native Builder owns
- which current WordPress/theme/builder/plugin/data surface should own the behavior;
- Gutenberg/Core block safety and serialization;
- Patterns/templates/template parts;
- supported theme/builder/plugin APIs and extension surfaces;
- custom-code placement when justified;
- WooCommerce and WordPress lifecycle/permission/integration concerns;
- WordPress-specific publication/verification boundaries.

Product Interface Builder must not prescribe raw block markup, direct third-party/core edits, hook placement, theme/plugin architecture, or another WordPress mechanism unless WP Native Builder has selected/confirmed that mechanism.

WP Native Builder may reject or adapt an implementation mechanism that would be brittle or unsafe while preserving the intended user-facing result.

## 5. Three-way project + design + WordPress flow

A normal substantial WordPress project can compose as:

1. **Project Master** resolves project outcome, scope, current repository/work state, and authority.
2. **Product Interface Builder** establishes or reviews user-facing design intent using current project/site evidence.
3. **WP Native Builder** maps that intent onto the smallest supported WordPress-native owner/mechanism and implements/verifies it when authorized.
4. **Product Interface Builder** reviews rendered user-facing quality when material and when rendered evidence is available.
5. **Project Master** owns acceptance, integration, continuity, and release.

Skip stages that add no value. A small safe WordPress UI fix does not require ceremonial multi-agent choreography.

## 6. Shared concerns without duplicate rulebooks

Some concerns cross boundaries.

### Accessibility
Product Interface Builder owns user-facing accessibility intent/review. A platform specialist owns platform-specific semantics/mechanisms needed to realize it. The Master owns project acceptance policy.

### Responsive behavior
Product Interface Builder owns intended recomposition and user-facing quality. The platform specialist owns the safe/native implementation mechanism.

### Visual review
Product Interface Builder is the canonical visual-quality reviewer when it is active for the task. Platform specialists may perform mechanism-specific visual checks, but should not introduce a competing art direction.

### Performance
Product Interface Builder may flag obvious UI/perceived-performance risks caused by design implementation. Backend/runtime/system performance remains with the appropriate engineering owner.

When two Skills contain overlapping general guidance, select the owner closest to the concrete decision instead of applying both as independent mandatory checklists.

## 7. Existing project/design truth outranks Skill defaults

When another Skill already recovered an authoritative Project Brief, design system, site architecture, product requirements, or accepted durable decision:

- consume it instead of reconstructing a competing artifact;
- update only the natural owner when an accepted durable conclusion actually changes;
- do not treat a Skill's internal defaults as newer project truth;
- re-read current live/project state when drift would materially change the design decision.

Product Interface Builder can challenge a harmful/outdated design choice, but it must distinguish recommendation from current truth.

## 8. Durable state handoff

Persist only future-useful accepted conclusions.

Examples:
- accepted product-interface design direction;
- shared token/pattern decision;
- locale/platform requirement;
- unresolved material visual/accessibility risk;
- implemented interface artifact/change.

Use the project's natural source of truth: repository artifact, issue/task, design document, or other accepted durable project system.

Do not:
- persist chat transcripts;
- create a duplicate Koinon backlog;
- make `achworks.yaml` a worklog;
- store live deployment/runtime state in this Skill's metadata.

## 9. Koinon boundary

Koinon is the technology-agnostic ecosystem coordination/governance/discovery/contracts layer.

Product Interface Builder:
- keeps its implementation, Issues/PRs, validation evidence, packaging, and release truth in this repository;
- uses `achworks.yaml` only for stable discovery/capability/dependency metadata;
- may consume applicable Koinon contracts during project/release work;
- does not require Koinon at runtime to design an interface;
- does not copy live project work state into Koinon or its descriptor;
- treats other repositories as read-only unless explicit mutation scope names them.

Koinon discovery can reveal a reusable capability; it does not force reuse when local implementation is simpler or more appropriate.

## 10. Graceful degradation

### No project Master
Work standalone within current authority. Do not emulate a fake Master process.

### No WP Native Builder for WordPress
Provide design intent and implementation guidance constrained to verified WordPress knowledge/capabilities. Do not claim WordPress-native mechanism correctness that was not verified.

### No rendering capability
Return static design/implementation review and mark rendered quality as unverified.

### No write capability
Return implementation-ready design decisions/patch guidance; do not claim changes were applied.

### No persistent project state
Complete the current task but do not claim cross-session recovery.

## 11. Provider-neutral invocation contract

Composition depends on roles and inputs/outputs, not on tool names.

A compatible runtime may:
- invoke another Skill directly;
- delegate to a sub-agent;
- execute roles sequentially in one agent;
- pass a task contract through a project system.

All are valid if authority, source-of-truth, evidence, and ownership boundaries remain the same.

Provider adapters may make discovery/invocation easier, but must never redefine these contracts.

## 12. v0.1 scenario checks

A composition passes when:

### Standalone UI
Product Interface Builder can complete ordinary design/review without requiring another AChWorks Skill.

### Master + interface task
The Master keeps project/GitHub/integration authority while Product Interface Builder returns bounded design/UX decisions and evidence.

### WordPress UI
Product Interface Builder defines the intended user-facing result; WP Native Builder chooses the WordPress-native owner/mechanism.

### Three-way WordPress project
The Master coordinates, Product Interface Builder owns visual/UX intent/review, and WP Native Builder owns WordPress mechanism. No role duplicates the other's durable state.

### Missing capability/specialist
The work degrades to the strongest available evidence/output without fabricated execution or forced dependency.

### Cross-runtime
The same role/ownership semantics remain valid even when the runtime uses a different agent/Skill invocation mechanism.

If a scenario requires modifying a neighboring Skill, record that need in the owning project/repository and obtain separate mutation scope. Do not change it from this project.
