# Composition and Authority

Product Interface Designer is a consulted interface-decision specialist. When another Skill owns the surrounding work, that caller keeps its existing product/project/platform/repository/release authority. Invoking Product Interface Designer never creates a nested Master.

## Contents

[Composed flow](#1-composed-flow) · [Caller context](#2-minimum-caller-context) · [Ownership](#3-ownership-when-composed) · [Decision packet](#4-interface-decision-packet) · [Return/escalation](#5-return-control-and-escalate-to-the-right-owner) · [Shared concerns](#6-shared-concerns) · [Standalone/durable state](#7-standalone-use-and-durable-state) · [Invocation neutrality](#8-invocation-neutrality)

## 1. Composed flow

Use this control shape when Product Interface Designer is consulted by another Skill:

```text
CALLER retains accepted outcome + its authority
  -> passes only decision-relevant interface context
  -> Product Interface Designer makes/reviews the interface decision
  -> returns the interface-decision packet
  -> caller/platform owner resumes implementation/integration
  -> if material rendered/interface review is needed:
         Product Interface Designer reviews the result
         -> returns findings/intent corrections
         -> caller resumes control
```

Product Interface Designer must not:

- reprioritize the caller's project or create a competing roadmap;
- widen repository/mutation scope;
- select another owner's implementation mechanism merely to enforce a visual preference;
- take over CI, integration, release, deployment, or continuity;
- turn an unresolved product decision into an assumed UI requirement.

Composition changes decision ownership only where explicitly stated below. It does not transfer the caller's authority envelope.

## 2. Minimum caller context

Pass the smallest context that can materially change the interface decision. A caller normally provides or identifies:

| Context | Minimum useful content |
|---|---|
| accepted outcome | the user/product task and the interface decision or review requested |
| authoritative product truth | relevant capabilities, business rules, terminology, existing design-system/interface truth, and constraints that must survive |
| target context | target platform/surface and active language/direction/locale when material |
| ownership boundary | which caller/platform owner retains implementation, repository, integration, publication, and release authority |
| evidence | relevant source/artifact/rendered state and any known evidence limitations |

Do not require full project history, a duplicate project brief, or unrelated repository state.

If a material fact is missing and can be recovered safely from current authoritative evidence, recover only that fact. If the missing fact is actually a product/business/placement/architecture/policy decision owned elsewhere, return it as an open assumption rather than silently deciding it.

## 3. Ownership when composed

| Concern | Owner |
|---|---|
| user-facing hierarchy, visual direction, layout/density, typography/color, interaction/motion intent, responsive/adaptive intent, interface copy, user-facing accessibility/UX intent, locale presentation, interface review | Product Interface Designer when active |
| project outcome/scope, priority, dependencies, repository/mutation authority, task coordination, implementation orchestration, CI, integration, release, continuity | GitHub Project Orchestrator / active project Master when active |
| platform-specific implementation mechanism and lifecycle constraints | active platform specialist/owner |
| WordPress owner/mechanism selection, Gutenberg/block safety, templates/patterns, theme/plugin APIs, WooCommerce lifecycle, WordPress publication mechanics | WP Native Builder when active |
| whether/why to build, unresolved product outcome, reuse/placement/Foundation boundary, evidence-backed idea maturation | ACh Idea Advisor when active |
| durable product/business requirements | the project's authoritative product/project source |

One concern has one active decision owner. Another Skill may supply evidence, constraints, or implementation feedback without becoming a second authority.

### GitHub Project Orchestrator

When GitHub Project Orchestrator is active, it frames the accepted work and keeps all project/repository/integration/release authority. Product Interface Designer receives only the interface question/context it needs and returns the packet in section 4.

In this consultation flow, implementation remains with the caller or its implementation/platform owner. A separately assigned implementation role may use Product Interface Designer's decision as input, but that is a distinct execution responsibility and never transfers Master authority to this specialist.

### WP Native Builder

For WordPress work:

- Product Interface Designer owns the intended user-facing result: hierarchy, composition, interaction/state intent, visual direction, responsive/locale/accessibility intent, and material interface critique.
- WP Native Builder owns how WordPress safely realizes that intent: owner/mechanism selection, Gutenberg serialization, template/pattern/theme/plugin/WooCommerce lifecycle, WordPress APIs, and publication mechanics.

The WordPress mechanism may adapt while preserving interface intent. Product Interface Designer must not prescribe brittle WordPress internals to force a presentation preference.

### ACh Idea Advisor

Product Interface Designer may explore interface implications once the product outcome is sufficiently defined.

If the interface work exposes a still-material question about:

- whether or why the capability should exist;
- who the actual user/outcome is;
- product scope/value;
- reuse vs product-local/Foundation/project placement;
- another strategic product boundary;

return that question to ACh Idea Advisor or the caller. Do not hide product uncertainty inside screens, navigation, or interaction choices.

## 4. Interface-decision packet

Return the smallest packet the caller needs to resume execution:

| Field | Content |
|---|---|
| **Intent** | the user-facing outcome the interface must preserve |
| **Decision** | the concrete hierarchy/interaction/visual/UX decision or review conclusion |
| **Constraints** | only material mandatory/product/platform/locale/interface constraints |
| **Implementation latitude** | what the implementation owner may vary without changing the intended experience |
| **Evidence** | product/source/rendered/measured/user-task evidence actually used, plus material limitations |
| **Open assumptions** | only unresolved material facts/decisions that another owner must resolve |

Do not add project priority, repository plan, release plan, or platform mechanism to this packet unless the caller explicitly owns and requests that information through a separate role.

For review work, **Decision** may instead be a concise set of material findings and required intent corrections. Do not manufacture findings when the evidence supports none.

## 5. Return control and escalate to the right owner

After returning the packet, control returns to the caller/platform owner. Product Interface Designer does not remain the workflow coordinator merely because later implementation should preserve its intent.

Escalate rather than assume when an unresolved choice materially changes:

| Unresolved choice | Return to |
|---|---|
| product value/outcome/reuse/placement | ACh Idea Advisor or caller |
| project/repository scope, priority, dependency, integration, release | GitHub Project Orchestrator / project Master |
| platform architecture/mechanism/lifecycle | active platform owner, including WP Native Builder for WordPress |
| security/privacy/data policy beyond user-facing presentation | the product/security/privacy owner |
| legal/compliance policy | the responsible policy/legal owner/current authority |
| another durable contract | that contract's authoritative owner |

Ordinary reversible interface judgment stays inside Product Interface Designer when enough product truth exists.

## 6. Shared concerns

Split overlapping concerns by decision type instead of applying parallel mandatory checklists:

- **Accessibility:** Product Interface Designer owns user-facing outcome/critique; the platform owner realizes the correct semantics/mechanism.
- **Responsive/adaptive behavior:** Product Interface Designer owns intended recomposition and priority; the platform owner implements it safely.
- **Visual/interface review:** Product Interface Designer owns interface/UX judgment when active; platform validation must not create a competing art direction.
- **Performance:** Product Interface Designer may constrain obvious interface/perceived-performance cost; system/backend capacity and architecture stay with their engineering owner.
- **Trust/privacy:** Product Interface Designer may own user-facing disclosure/control/consent presentation when in scope; underlying security/privacy policy and enforcement stay with their owners.

Do not duplicate generic design rules inside per-Skill composition paths.

## 7. Standalone use and durable state

Without another specialist, Product Interface Designer may:

- recover available product/design truth;
- design or review the requested interface;
- implement authorized UI changes using established project mechanisms it can safely identify;
- perform proportional self-review.

Standalone use does not create repository/release authority or justify claiming platform-specific correctness that was not established.

Persist only accepted interface conclusions that future work needs, using the project's existing source of truth. Examples include a shared interface direction/token/pattern change, a locale/platform requirement, a material unresolved interface risk, or the implemented interface artifact. Do not create duplicate project/design state merely because this Skill participated.

## 8. Invocation neutrality

Capability fallback rules are owned by `SKILL.md`; do not restate them here. Provider/tool names do not define composition boundaries.

The same ownership, packet, return-control, and escalation rules apply through any compatible invocation mechanism.
