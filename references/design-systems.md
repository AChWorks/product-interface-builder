# Design-System Decision Support

Use this reference only when the interface work explicitly concerns or materially requires a **reusable design system**: shared token architecture, reusable component contracts, themes/modes, cross-surface extension rules, or system-wide change/deprecation.

This file does not turn ordinary UI work into design-system work. [design-core.md](design-core.md) owns local visual/interface decisions and ordinary reuse of an existing system.

## Contents

[Activation](#1-decide-whether-system-level-work-is-earned) · [Token layers](#2-model-tokens-by-role-not-by-volume) · [Components](#3-define-component-contracts-not-just-appearance) · [Themes](#4-keep-themes-and-modes-semantic) · [Extension](#5-separate-legitimate-exceptions-from-system-growth) · [Change](#6-treat-shared-change-as-a-consumer-contract) · [Artifacts](#7-persist-only-what-continuing-reuse-needs) · [Interop](#8-use-external-token-formats-only-when-the-ecosystem-needs-them)

## 1. Decide whether system-level work is earned

Use the smallest level that matches the real reuse problem.

| Situation | Preferred response |
|---|---|
| one bounded UI change inside an existing product | reuse existing system truth; keep local exceptions local |
| a few repeated choices on one feature/surface | establish only the shared local roles/patterns that prevent duplication |
| repeated components/roles across several product surfaces | define reusable contracts where recurrence is evidenced |
| explicit design-system work, multi-brand/theme needs, cross-platform/shared library work, or system-wide migration | use this reference fully |

Do not create a new design system because the current project lacks one neat document. Existing code, components, tokens, style libraries, product artifacts, and established conventions may already be the authoritative system.

Before expanding the system, identify:

- which decisions truly recur;
- which consumers/surfaces depend on them;
- which variability is intentional;
- which current source owns those decisions;
- whether the new abstraction reduces arbitrary repetition rather than merely renaming values.

## 2. Model tokens by role, not by volume

Token structure should make shared intent easier to preserve.

Conceptually distinguish when useful:

- **foundational/reference values** — reusable raw scales or source values;
- **semantic roles** — meaning such as surface, text, border, action, focus, success, warning, destructive, spacing role, or typography role;
- **component-scoped roles** — values/aliases needed to express a reusable component contract without leaking one implementation across the whole product.

These are reasoning layers, not a mandatory folder/schema taxonomy. Omit a layer when it adds no useful abstraction.

Prefer:

- stable semantic names over visual names tied to one current appearance;
- aliases/relationships where they express shared intent;
- a small coherent scale over hundreds of near-duplicate values;
- explicit ownership for global versus component-specific roles;
- naming that survives theme/mode changes without becoming misleading.

Avoid:

- encoding implementation location in a token name when the meaning is broader;
- promoting a one-off visual tweak into a global token;
- duplicating complete token sets merely to create a mode that could be expressed through semantic mapping;
- creating aliases so deep that the final meaning becomes difficult to trace.

When exact contrast/accessibility requirements constrain token values, current accessibility authority and actual rendered evidence remain decisive.

## 3. Define component contracts, not just appearance

A reusable component needs an interface contract, not only a screenshot.

Define only the dimensions that consumers need:

- purpose and when to use/not use;
- anatomy/slots/required versus optional content;
- meaningful states such as default, hover/pressed/focus, selected, loading, disabled, error, success, empty, or permission-limited when applicable;
- variants/sizes only when they represent recurring product needs;
- composition/nesting constraints where misuse would break hierarchy or interaction;
- content/copy constraints that protect usability;
- responsive/adaptive and localization behavior that materially affect the component;
- accessibility/interaction intent, with exact platform semantics owned by current platform/accessibility authority.

Keep variants orthogonal where practical. Avoid a combinatorial API in which every visual difference becomes a boolean/variant.

Do not standardize a component whose use cases are still materially different. A shared visual shape does not prove a shared semantic component.

## 4. Keep themes and modes semantic

Themes/modes should change presentation while preserving product meaning unless a different experience is explicitly intended.

When supporting light/dark, high-contrast, brand, density, or other modes:

- map semantic roles to mode-specific values;
- preserve hierarchy and state meaning across modes;
- verify that destructive/success/focus/selection meaning survives color changes;
- avoid assuming every token needs a mode override;
- distinguish user/system preference from product-specific themes;
- define fallback/default behavior when a requested mode is unavailable or partial.

A theme is not permission to fork the component architecture or duplicate all component definitions.

For exact target-platform theme APIs or accessibility modes, use current platform authority.

## 5. Separate legitimate exceptions from system growth

Use this decision rule:

```text
Does the need recur or represent a stable shared product rule?
  ├─ yes -> can the existing token/component contract express it cleanly?
  |          ├─ yes -> reuse/extend within the existing contract
  |          └─ no  -> add the smallest shared abstraction that fits known consumers
  └─ no  -> keep the exception local and documented only if future maintainers need to know why
```

A system is healthy when it allows justified exceptions without turning each exception into a new global rule.

Promote local behavior only when recurrence, shared meaning, or maintenance cost provides evidence for reuse.

## 6. Treat shared change as a consumer contract

System-wide changes can affect many surfaces even when the edit is small.

Before changing a shared token/component contract, identify:

- affected consumers/surfaces;
- whether meaning or only representation changes;
- compatible versus breaking changes;
- migration/transition strategy where consumers cannot update atomically;
- deprecation/removal timing only when the surrounding project/release owner actually needs it;
- visual/accessibility regressions that need rendered evidence.

Prefer migrations that preserve intent while allowing bounded consumer updates.

Do not silently repurpose an established semantic token/component name to mean something materially different. If a shared contract must change meaning, make that change explicit to its consumers.

Product/repository/version/release orchestration stays with the caller/Master; this reference only defines the interface-system consequence.

## 7. Persist only what continuing reuse needs

For substantial continuing design-system work, durable artifacts may be justified. Reuse the project's existing source of truth before creating another.

Persist the smallest set needed for reliable future use, such as:

- token source/semantic mapping;
- reusable component contract and states;
- theme/mode mapping;
- extension/override rule that prevents recurring ambiguity;
- migration/deprecation note for a shared contract;
- implementation examples when they prevent misuse better than prose.

Do not create documentation merely to prove process occurred. A local change that is obvious from code/design truth does not need a new design-system document.

The implementation/platform owner decides the actual code/package/file structure.

## 8. Use external token formats only when the ecosystem needs them

A standardized token exchange format can be useful when multiple design/development tools or platforms need interoperable token data.

Treat that as a tooling/interchange decision, not a universal requirement:

- preserve the project's semantic design model first;
- use the current Design Tokens Community Group format or another current ecosystem format only when the actual tools/consumers benefit;
- verify the currently supported specification/tool versions before committing to syntax or feature support;
- do not force a project to migrate formats solely because a standard exists;
- do not copy the external specification into this Skill.

Likewise, do not select React/Vue/SwiftUI/Compose/Flutter/CSS architecture, a component framework, documentation site, or token tool by default. Product Interface Designer defines the reusable interface contract; the active platform/implementation owner chooses the mechanism.
