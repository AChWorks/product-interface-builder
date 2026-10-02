# Product Interface Builder — Project Specification

Status: **V0.1 PRE-RELEASE**

Repository: `AChWorks/product-interface-builder`

This file owns durable product intent, scope, boundaries, architecture constraints, and v0.1 completion criteria. GitHub Issues/PRs own live work. Source provenance is owned by `docs/SOURCE-STRATEGY.md`.

## 1. Outcome

Build a compact, provider-neutral AI Skill that materially improves user-facing product interfaces across web, mobile, and desktop.

The Skill should help an AI:

- understand the product, audience, task, content, incumbent interface, platform, and locale before making design decisions;
- create intentional interface direction without falling back to generic generated-UI habits;
- preserve an established product language for bounded changes and reconsider it deliberately for explicit redesigns;
- reason about hierarchy, layout, typography, color, density, imagery, controls, data presentation, interaction, motion, responsive/adaptive behavior, accessibility, interface copy, and non-ideal states;
- treat Persian/RTL as a first-class conditional capability;
- distinguish static reasoning from rendered evidence when reviewing implemented UI;
- compose with project/platform specialists without taking over their authority.

The goal is better design judgment, not more rules.

## 2. Supported work

v0.1 covers:

- new interfaces and surfaces;
- targeted interface modification;
- explicit redesign;
- interface review/refinement;
- English/LTR and Persian/RTL products;
- web, mobile/native, and desktop reasoning;
- standalone use and bounded composition with other Skills.

Pure backend, infrastructure, database, deployment, or business-policy work is outside scope unless it materially affects the user-facing interface.

## 3. Ownership boundaries

Product Interface Builder owns user-facing interface design intent and quality: hierarchy, visual direction, design-system intent, layout, typography, color, density, imagery/icon direction, interaction/motion intent, responsive/adaptive intent, interface accessibility/UX, interface copy, locale presentation, and visual critique.

It does **not** own:

- project priority, repository authority, integration, CI, release, or project continuity;
- backend/infrastructure/database architecture;
- platform-specific implementation ownership when an active specialist owns that decision;
- WordPress mechanism/lifecycle decisions when WP Native Builder is active;
- durable business/product facts that belong to the project's authoritative sources.

Standalone use remains supported; missing neighboring Skills must not create fake dependencies.

## 4. Source model

Product Interface Builder is original synthesis from an audited source corpus.

Sources are **reference material**, not templates. The local Skill must not preserve an upstream source's chapter order, command taxonomy, mode taxonomy, provider wiring, file tree, or workflow merely because that source uses it.

A source idea belongs only when it:

1. solves a real Product Interface Builder need;
2. fits the local ownership model;
3. can be expressed as a local principle without depending on the source's packaging/taxonomy;
4. does not duplicate an existing local rule;
5. has clear provenance/licensing treatment if copyrightable material is directly imported.

The exact audited sources, revisions, licenses, and import state live in `docs/SOURCE-STRATEGY.md`.

## 5. Skill architecture

The runtime bundle uses progressive loading:

- `SKILL.md` is the compact control plane;
- detailed rules live in direct one-level `references/`;
- each concern has one canonical local owner;
- locale/platform/specialist guidance is loaded only when relevant;
- provider-specific metadata is adapter-only and must not redefine behavior;
- scripts/assets/catalogs are included only when they materially improve repeatability or quality.

The current local concern split is:

- core interface reasoning;
- Persian/RTL;
- platform routing;
- interface review;
- composition/authority.

This split is ours; it is not required to resemble any upstream Skill.

## 6. Design invariants

The implementation should:

- ground visual choices in product/audience/task/content evidence;
- preserve incumbent design for bounded changes unless change is justified;
- separate constraints that must survive from visual choices that may change during redesign;
- keep design systems proportional rather than manufacturing documentation/tokens for trivial work;
- keep locale-specific behavior conditional;
- use platform conventions when they materially affect interaction;
- avoid fabricated product claims, metrics, testimonials, guarantees, or assets;
- treat responsive behavior as recomposition where needed rather than simple scaling;
- account for loading, empty, error, disabled, success, destructive, and long-content states when material;
- keep accessibility and obvious interface-performance concerns proportional to the actual surface;
- avoid checklist theater and duplicated rule ownership.

## 7. Provider neutrality and AChWorks composition

Canonical behavior must not depend on a specific AI vendor, model, hosted product, or harness. Route by capabilities such as source access, write access, rendering, image inspection, command execution, persistent state, and external retrieval.

`agents/openai.yaml` may provide provider UI/discovery metadata but is not a behavioral source of truth.

The repository aligns with Koinon through `achworks.yaml`. Koinon is a governance/discovery/contract dependency, not a runtime dependency. Related repositories remain read-only unless separately authorized for mutation.

## 8. Licensing and provenance

Repository license: **MIT**.

v0.1 contains original Product Interface Builder instructions and currently vendors/adapts no third-party code, datasets, components, scripts, templates, or copyrighted Skill prose.

Conceptual references may be documented without becoming runtime dependencies. If future work directly copies, translates, transforms, or adapts third-party material, the exact source revision/path and every applicable license/NOTICE/attribution/modified-file obligation must be recorded before integration.

## 9. v0.1 completion criteria

v0.1 is ready for release when:

- the canonical Skill has clear triggers, routing, ownership, and progressive loading;
- new design, modification, redesign, and review are covered;
- English/LTR and Persian/RTL are both supported without locale leakage;
- web, mobile/native, and desktop differences are represented;
- design-system behavior is proportional;
- accessibility, responsive behavior, interaction states, interface copy, motion, and obvious UI-performance concerns are represented without checklist bloat;
- composition boundaries with project/platform specialists are clear;
- the final rule set is internally coherent, source-independent in structure, and free of unnecessary duplication;
- provenance/licensing accurately reflects the actual import state;
- repository documentation is sufficient for a fresh Master to continue without chat history;
- the distributable bundle contains only files required by the Skill.

## 10. Locked decisions

- Name: `product-interface-builder`
- Repository: `AChWorks/product-interface-builder`
- Scope: product interface design/UX/visual quality across web, mobile, desktop
- Persian/RTL: first-class conditional capability
- Source model: multi-source original synthesis, not a fork
- Canonical source corpus: Anthropic frontend-design, UI UX Pro Max, Impeccable, VibeFarsi, Vercel Web Interface Guidelines, LottieFiles motion guidance
- Composition: complementary to GitHub Project Orchestrator and WP Native Builder
- Provider model: provider-neutral core; provider-specific metadata adapter-only
- Ecosystem: Koinon-aligned, not Koinon runtime-dependent
- License: MIT

## 11. Recovery

A fresh Master should read this specification, inspect current GitHub Issues/PRs and `main`, then continue the highest-value open work. Current repository/GitHub state outranks old chat history. Mutation scope does not extend to related repositories without separate authorization.
