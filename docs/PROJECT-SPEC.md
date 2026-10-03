# Product Interface Designer — Project Specification

Status: **v0.2 RELEASED**

Repository: `AChWorks/product-interface-designer`

This file owns durable product intent, scope, boundaries, and architecture constraints. GitHub Issues/PRs own live work and release planning. Source provenance is owned by `docs/SOURCE-STRATEGY.md`; instruction-authoring/composition structure is owned by `docs/INSTRUCTION-ARCHITECTURE.md`.

First public release: **v0.1**, tagged at `1de9c1042f850f20c7279375c9860347c9a13d76`.

## 1. Outcome

Build a compact, provider-neutral **product-interface decision Skill** that materially improves the quality of user-facing interfaces across web, mobile, and desktop.

The Skill should help an AI make better UI/UX decisions, not merely apply visual styling. It should:

- recover enough product, user, task, content, platform, locale, and incumbent-design truth before deciding;
- turn that evidence into clear interface decisions another AI or implementation specialist can execute;
- when used standalone and an established safe project mechanism exists, implement authorized UI changes without treating execution capability as new project/platform/repository authority;
- preserve established product language for bounded changes and reconsider it deliberately for explicit redesigns;
- reason about visual hierarchy, interaction architecture, information architecture, usability, accessibility, responsive/adaptive behavior, trust/privacy/consent, interface copy, motion, data presentation, localization, and non-ideal states;
- distinguish design hypotheses from stronger usability/rendered/measured evidence;
- support design-system work when the task genuinely requires reusable system decisions;
- support AI-mediated interfaces and collaborative/adaptive interaction when relevant without imposing them on ordinary products;
- treat Persian/RTL as a first-class conditional specialization within a broader internationalization model;
- compose cleanly with project-management and platform-specialist Skills without becoming a second project manager or implementation owner.

The goal is **better interface judgment with less ambiguity and less duplicated instruction**, not more rules.

## 2. Supported work

The Skill covers, proportionally:

- new interfaces and surfaces;
- targeted interface modification;
- explicit redesign;
- interface review/refinement;
- interaction and navigation design;
- information architecture and complex user flows;
- forms, controls, data presentation, search/filter/sort, and complex interaction patterns when relevant;
- human factors and usability reasoning;
- accessibility and user-facing trust/privacy/consent behavior;
- design systems;
- internationalization/localization, including Persian/RTL;
- web, mobile/native, and desktop/adaptive reasoning;
- AI-mediated and collaborative interface behavior when the product actually contains those concerns;
- standalone design/review plus authorized UI implementation through established mechanisms, and bounded composition with other Skills.

Pure backend, infrastructure, database, deployment, business strategy, product-market validation, repository coordination, or platform-specific mechanism selection is outside scope unless it materially affects the user-facing interface decision.

## 3. Ownership boundaries

Product Interface Designer owns the **user-facing interface decision**:

- information/action hierarchy;
- interaction and navigation intent;
- visual direction and design-system intent;
- layout, typography, color, density, imagery/icon direction;
- responsive/adaptive behavior;
- interface accessibility/UX outcome;
- interface copy and locale presentation;
- user-facing trust, consent, recovery, and error-prevention behavior;
- motion/feedback intent;
- visual/interaction critique and evidence requirements.

It does **not** own:

- project priority, repository authority, task coordination, CI, integration, release, or project continuity;
- whether a product/feature should exist when that product decision is still materially unresolved;
- backend/infrastructure/database architecture;
- security/privacy implementation mechanisms outside the interface surface;
- platform-specific implementation ownership when an active specialist owns that decision;
- WordPress mechanism/lifecycle decisions when WP Native Builder is active;
- durable business/product facts owned by authoritative project/product sources.

Standalone use remains supported; missing neighboring Skills must not create fake dependencies.

## 4. Composition model

Product Interface Designer is a **specialist consulted for interface decisions**.

When another Skill/project/platform owner retains surrounding non-interface authority:

1. the caller retains authority for its own workflow;
2. Product Interface Designer receives the smallest sufficient product/task/platform/locale/design context;
3. Product Interface Designer returns the canonical interface-decision packet;
4. the caller resumes its owning workflow;
5. implementation/integration remains with the existing implementation/platform/project owner when applicable;
6. when later implementation produces an interface and review is material, Product Interface Designer may review it without becoming the workflow coordinator.

Specific boundaries:

- **GitHub Project Orchestrator:** owns scope, dependencies, repository mutation, coordination, integration, release, and continuity; invokes Product Interface Designer for material UI/UX decisions or review.
- **WP Native Builder:** Product Interface Designer owns user-facing design/UX intent; WP Native Builder owns WordPress/Gutenberg/theme/plugin/WooCommerce mechanism and lifecycle safety.
- **ACh Idea Advisor:** owns materially unresolved product/outcome, product capability reuse, and product-local/Foundation/project placement decisions; Product Interface Designer should not hide an unresolved product decision inside interface design.

Detailed composition/return-shape rules live in `docs/INSTRUCTION-ARCHITECTURE.md` and the runtime composition reference.

## 5. Skill architecture

The runtime bundle uses progressive loading:

- `SKILL.md` is the compact control plane;
- detailed rules live in direct one-level `references/`;
- each concern has one canonical local owner;
- references are loaded by task conditions, not all at once;
- provider-specific metadata is adapter-only and must not redefine behavior;
- scripts/assets/catalogs are included only when they materially improve repeatability or quality.

The architecture may evolve as new concerns are introduced, but new files must be justified by a distinct decision domain rather than by source provenance or convenience.

## 6. AI-legible instruction architecture

The Skill is written for another AI to use reliably.

Use the representation that best matches the reasoning problem:

- **ordered precedence** for conflict resolution and authority;
- **decision tables/trees** for conditional routing or materially different branches;
- **tables** for ownership, comparisons, and mutually distinct responsibilities;
- **compact flow/state notation** for sequential workflows;
- **short prose/bullets** for principles, heuristics, and context-sensitive judgment;
- **examples** only when they disambiguate behavior that rules alone may not communicate clearly.

Do not turn every concept into a table, every task into a checklist, or every principle into prose. Avoid duplicated rules across references. One concern should have one canonical runtime owner, with other files linking/routing to it.

Detailed authoring rules live in `docs/INSTRUCTION-ARCHITECTURE.md`.

## 7. Interface-quality model

The Skill should help the AI reason from user/product needs outward rather than from visual fashion inward.

Durable expectations include:

- ground choices in the user job, content, product truth, and context of use;
- distinguish mandatory safety/legal/accessibility/platform constraints from user aesthetic preferences;
- preserve incumbent design for bounded changes unless change is justified;
- reduce cognitive burden and support recognition, predictability, learnability, control, recovery, and error tolerance;
- treat navigation/findability/information architecture as interaction structure, not merely page chrome;
- distinguish visual correctness from task usability; do not claim user-task validation without corresponding evidence;
- avoid deceptive or coercive interface patterns and make consequential consent/permission/data-sharing choices understandable;
- keep design systems proportional and reusable rather than decorative documentation;
- keep locale-specific behavior conditional and make general internationalization concerns explicit;
- use platform conventions when they materially affect interaction;
- avoid fabricated product claims, metrics, testimonials, guarantees, or assets;
- treat responsive/adaptive behavior as recomposition where needed rather than simple scaling;
- account for loading, empty, error, disabled, success, destructive, permission, long-content, and recovery states when material;
- consult current authoritative standards/platform guidance when exact version-sensitive behavior matters;
- avoid checklist theater and duplicated rule ownership.

## 8. Standards and current authority

Canonical Skill behavior must not freeze fast-changing normative/platform details when current authoritative documentation is the correct owner.

When exact requirements materially affect a task, current official authorities outrank generalized Skill guidance, including as applicable:

- W3C/WCAG and ARIA Authoring Practices;
- Apple Human Interface Guidelines/current Apple platform documentation;
- Android/Material/current Android platform documentation;
- Microsoft/current Windows app design and platform documentation;
- Unicode/CLDR/W3C internationalization guidance for exact locale/script/bidi behavior;
- browser/platform API documentation;
- applicable legal/regulatory/product policy owned outside this Skill.

The runtime should contain enough routing guidance for the AI to know **when** current authority is required without vendoring entire external standards.

## 9. Provider neutrality and AChWorks ecosystem

Canonical behavior must not depend on a specific AI vendor, model, hosted product, or harness. Route by capabilities such as source access, write access, rendering, image inspection, command execution, persistent state, and external retrieval.

`agents/openai.yaml` may provide provider UI/discovery metadata but is not a behavioral source of truth.

The repository aligns with Koinon through `achworks.yaml`. Koinon is a governance/discovery/contract dependency, not a runtime dependency. Related repositories remain read-only unless separately authorized for mutation.

## 10. Licensing and provenance

Repository license: **MIT**.

The project contains original Product Interface Designer instructions and currently vendors/adapts no third-party code, datasets, components, scripts, templates, or copyrighted Skill prose.

Conceptual references may inform original synthesis without becoming runtime dependencies. Future direct copy/translation/transformation/adaptation of third-party material requires exact provenance and license/NOTICE/attribution handling before integration.

## 11. Release history and evolution

### v0.1

v0.1 established the provider-neutral control plane, core design reasoning, Persian/RTL specialization, platform routing, review behavior, composition boundaries, source-independent synthesis model, and canonical packaging.

### v0.2

Released as **Product Interface Designer v0.2** on tag `v0.2` at `c2eede9372549897b7ed59ba011a69e2e7fd7723`.

Canonical runtime asset: `product-interface-designer-v0.2.zip` — SHA-256 `36d9fd415f02f579d974aee3325fce3d2d04680df2ca02c8029339e861d54698` (61,092 bytes).

v0.2 implements the accepted post-v0.1 direction without reintroducing source-shaped structure:

- explicit AI-legible precedence/routing and current-authority gates;
- formal consulted-specialist composition and interface-decision packets;
- human-factors/usability-evidence reasoning;
- information architecture, findability, and complex interaction guidance;
- trust/privacy/consent/user-agency and anti-deceptive-interface guidance;
- general internationalization/localization with Persian/RTL as a specialization;
- proportional design-system decision support;
- conditional AI-mediated interface guidance;
- conditional collaboration/concurrency and adaptive-context guidance.

The v0.2 release continues the canonical **Product Interface Designer** identity.

## 12. Locked decisions

- Name: `product-interface-designer`
- Repository: `AChWorks/product-interface-designer`
- Scope: product interface design/UX/interaction/visual quality across web, mobile, desktop
- Role: interface decision specialist; not project manager or platform mechanism owner
- Persian/RTL: first-class conditional specialization
- Source model: original synthesis; upstream sources are not runtime dependencies
- Provider model: provider-neutral core; provider-specific metadata adapter-only
- Composition: complementary to GitHub Project Orchestrator, WP Native Builder, and ACh Idea Advisor
- Ecosystem: Koinon-aligned, not Koinon runtime-dependent
- License: MIT

## 13. Recovery

A fresh Master should read this specification, inspect current GitHub Issues/PRs and `main`, then continue the highest-value open work. Current repository/GitHub state outranks old chat history. Mutation scope does not extend to related repositories without separate authorization.
