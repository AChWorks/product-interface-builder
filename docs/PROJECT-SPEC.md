# Product Interface Builder — Project Specification

Status: **FOUNDATION_LOCKED / IMPLEMENTATION_NOT_STARTED**

Repository: `AChWorks/product-interface-builder`

This file is the canonical owner of durable project intent, scope, boundaries, source strategy, and v0.1 completion criteria. GitHub Issues own current work, sequencing, dependencies, and blockers. Chat history is disposable.

## 1. Outcome

Build a reusable, provider-neutral AI Skill that materially improves the quality of user-facing product interfaces across **web, mobile, and desktop** while remaining compact, composable, portable across compatible AI-agent environments, and useful both standalone and alongside other AChWorks Skills.

The Skill should help an AI:

- understand the product, audience, usage context, content, existing interface system, and platform before choosing a visual direction;
- create intentional, non-generic visual and interaction design;
- establish or respect coherent design systems;
- handle responsive behavior, accessibility, interaction states, motion, typography, color, data presentation, forms, navigation, and UI copy proportionally;
- treat Persian/RTL as a first-class product interface mode rather than an after-the-fact mirror of English/LTR;
- inspect rendered output when available, identify clear visual/UX defects, correct them, and distinguish static reasoning from rendered evidence;
- preserve project-specific design truth across future work only when durable persistence is justified;
- compose cleanly with project-management and platform-specific Skills without duplicating their authority.

The goal is not to maximize rules. The goal is to improve design judgment and execution while loading only the guidance needed for the current interface problem.

## 2. Primary use cases

The Skill must support at least:

1. **New interface or surface**
   - derive product-specific design direction;
   - establish a compact design system when one is warranted;
   - shape information hierarchy, layout, interaction, states, responsive behavior, and visual language;
   - implement or provide implementation-ready guidance when requested.

2. **Existing interface modification**
   - recover and preserve the incumbent design system and product language unless redesign/rebrand is explicit;
   - change only the requested or materially necessary surface.

3. **Redesign**
   - distinguish retained product constraints from replaceable visual decisions;
   - propose an intentional direction grounded in audience, product, content, platform, and brand rather than generic style defaults.

4. **Interface review / QA**
   - review hierarchy, clarity, spacing, typography, consistency, responsive behavior, accessibility, interaction, motion, edge states, copy, and obvious performance risks;
   - use rendered evidence when available;
   - surface high-signal findings rather than checklist noise.

5. **Persian / Iranian products**
   - support RTL layout, bidirectional content, Persian typography, digits, UI copy/register, Jalali/date behavior, currency and common Iranian interface conventions where applicable;
   - keep locale-specific rules conditional rather than forcing Iranian assumptions onto global products.

6. **Cross-platform work**
   - support web, native/mobile, and desktop interface reasoning;
   - load platform-specific conventions only when the target platform makes them relevant.

## 3. Ownership boundaries

### 3.1 Product Interface Builder owns

- interface design reasoning;
- visual direction and design-system guidance;
- layout, typography, color, spacing, density, imagery treatment, iconography direction;
- interaction and motion design;
- user-facing information hierarchy and interface copy guidance;
- responsive/adaptive behavior;
- accessibility as it affects interface design and interaction;
- locale-aware interface behavior, including Persian/RTL;
- visual/UX review and rendered self-critique;
- durable design artifacts only when substantial continuing work earns them.

### 3.2 `github-project-orchestrator` owns

When the GitHub Project Orchestrator is the project Master, it remains authoritative for:

- project outcome and scope;
- priority and dependency management;
- repository mutation scope and action gates;
- Task Contracts / Worker dispatch;
- implementation coordination;
- PR review/integration;
- CI and release;
- project continuity and current work state.

Product Interface Builder acts as a bounded design/interface specialist in that composition. Its findings are evidence/advice/implementation input; they do not independently reprioritize the project, widen accepted scope, merge, release, or redefine project authority.

### 3.3 `wp-native-builder` owns

For WordPress work, WP Native Builder remains authoritative for:

- WordPress ownership/mechanism selection;
- Gutenberg/block serialization safety;
- theme/builder/plugin/native mechanism decisions;
- WooCommerce and WordPress data/lifecycle behavior;
- placement and maintainability of WordPress implementation.

Product Interface Builder owns the design intent and user-facing quality criteria. WP Native Builder decides how that intent is safely and natively implemented in WordPress.

### 3.4 Standalone behavior

Product Interface Builder must remain useful without either neighboring Skill. Composition improves routing and authority separation; it must not be a runtime dependency for basic use.

## 4. Composition principles

1. Do not hard-code specific external Skill names into generic specialist-selection logic unless a cross-AChWorks contract genuinely requires a named peer.
2. One concern should have one canonical owner in the active composition.
3. A specialist may provide evidence or implementation input but does not inherit another Skill's project authority.
4. The absence of a specialist must not block ordinary work that the active Skill can safely perform.
5. Do not invoke a specialist when repository/project evidence plus ordinary professional judgment are already sufficient.
6. Persist accepted durable conclusions in the project source of truth, not in chat memory or transient specialist state.
7. Cross-repository changes require their own repository mutation authorization; dependency or composition does not widen writable scope.

## 5. Decision precedence

When guidance conflicts, use this order unless an applicable higher-level rule owns the decision:

1. explicit current user requirement;
2. current authoritative product/project/design-system truth;
3. accessibility, safety, legal, or platform requirements that actually apply;
4. platform-specific conventions;
5. locale/script-specific conventions;
6. product/audience/content-specific design reasoning;
7. general design principles;
8. style/catalog suggestions.

Catalog output is evidence/options, never automatic design authority.

## 6. Source synthesis strategy

The Skill is intentionally multi-source. It must synthesize a coherent AChWorks rule set rather than load several conflicting rulebooks at once.

| Source | Primary value | Intended use |
|---|---|---|
| Anthropic `frontend-design` | visual taste, intentional art direction, anti-template defaults, self-critique | design philosophy and visual-direction reasoning |
| `nextlevelbuilder/ui-ux-pro-max-skill` | structured design intelligence, product/style/palette/type data, UX guidance, stack ideas | searchable knowledge/data and option generation |
| `pbakaus/impeccable` | product-vs-design truth separation, shape/craft/critique/audit/polish/harden/adapt workflows, detector concepts | lifecycle and visual-review workflow patterns |
| `TronIsHere/vibefarsiui` | Persian/RTL implementation conventions, typography, UI copy, Iranian product patterns and components | locale-specific Persian/Iranian layer |
| Vercel Web Interface Guidelines | web review guidance | validation/audit input, not primary art direction |
| LottieFiles motion-design guidance | motion timing/easing/choreography | optional deep specialist input |

### Synthesis rules

- Prefer principles and normalized knowledge over wholesale copying.
- Resolve duplication into one canonical internal rule owner.
- Keep generic defaults separate from locale/platform overrides.
- A locale-specific rule may override a generic default only for the matching locale/script/context.
- Do not import Premium, proprietary, or otherwise unlicensed material.
- Any direct copy or derivative must record exact provenance and applicable license obligations in `THIRD_PARTY_NOTICES.md`.
- When actual upstream content is imported, pin its source commit/release rather than relying only on a moving branch name.

## 7. Provider neutrality and portability

Provider neutrality is a product requirement, not an optional packaging detail.

The canonical Skill must:

- avoid depending on a specific AI vendor, model name, hosted product, or agent harness for its identity or core behavior;
- keep core instructions, references, knowledge, and deterministic scripts portable;
- use capability-based language and routing instead of vendor-specific tool names when the underlying capability is generic;
- isolate provider-specific metadata, installation helpers, adapters, or manifests so they can be added/removed without changing canonical behavior;
- maintain one behavioral source of truth rather than divergent provider-specific copies;
- degrade gracefully when an environment lacks optional capabilities such as browser rendering, screenshots, shell execution, image inspection, connectors, or persistent workspace state;
- preserve the same ownership and quality principles even when the exact runtime/tool surface differs;
- prefer portable durable formats such as Markdown, YAML, JSON, JSON Schema, and ordinary Git history where practical.

A provider-specific adapter may exist when needed for discovery, packaging, installation, UI metadata, or tool wiring. Such an adapter is not the authority for the Skill's core behavior.

The first release must validate the canonical Skill in at least two independent compatible AI-agent environments from different vendors or harness families, without maintaining separate rulebooks.

## 8. Koinon alignment

Product Interface Builder is an independent AChWorks component aligned with Koinon's technology-agnostic coordination model.

Rules:

- this repository remains authoritative for product intent, Skill behavior, implementation, Issues, PRs, CI, releases, and provider adapters;
- root `achworks.yaml` provides stable discovery metadata and points to this repository rather than duplicating mutable state;
- Koinon remains a governance/discovery/contract layer, not a runtime dependency;
- consume applicable Koinon capabilities/contracts, including ecosystem governance, capability discovery, cross-project engineering standards, and validation/evidence guidance;
- do not copy Koinon live work state into this repository;
- do not make AChrix or any other Foundation a dependency unless future evidence shows an actual fit;
- cross-repository coordination never widens mutation authority;
- provider neutrality and portable durable formats should remain consistent with Koinon's technology-neutral model.

## 9. Skill architecture requirements

Implementation must follow progressive loading:

- keep `SKILL.md` a compact control plane, targeting well below the 500-line Skill guidance;
- put detailed domain rules in direct references loaded only by relevant triggers;
- avoid deep reference nesting;
- keep large design catalogs/search data outside the entrypoint;
- use scripts only for deterministic, repeatable, or fragile operations where code materially improves reliability;
- do not consume context by loading datasets or platform/locale guidance that the current task does not need.

Likely domain separation includes:

- design direction / visual taste;
- design systems and tokens;
- layout/responsive/adaptation;
- typography and color;
- interaction/motion;
- accessibility;
- content/UI copy;
- visual QA/review;
- platform-specific guidance;
- locale/script guidance, especially Persian/RTL;
- optional searchable design knowledge.

The exact file tree is an implementation decision and may change if a smaller structure proves sufficient.

## 10. Durable project design state

The Skill may create or update durable product/design artifacts only for substantial continuing work where doing so prevents material re-discovery or inconsistency.

Rules:

- reuse an existing authoritative product/design-system artifact when fit;
- do not create a second source of truth merely because this Skill is active;
- keep durable product truth distinct from replaceable visual direction when that distinction is useful;
- page/surface overrides must not silently rewrite global design-system truth;
- trivial or one-off interface changes must not manufacture persistent design artifacts.

Exact artifact names/formats are deferred to implementation/evaluation; interoperability with existing repository conventions is more important than imposing a universal filename.

## 11. Quality principles

The Skill should:

- be an advisor, not a passive copier;
- make one or a few intentional distinctive choices rather than decorate every surface;
- avoid recurring AI-generated UI clichés unless the brief genuinely calls for them;
- use real content/assets when available and never fabricate business claims, testimonials, metrics, certifications, or guarantees;
- preserve one coherent vocabulary and interaction model;
- account for loading, empty, error, disabled, success, destructive, and long-content states when material;
- treat mobile/responsive behavior as recomposition, not only shrinking;
- use accessibility and performance proportionally to the actual surface/failure model;
- prefer rendering/screenshot inspection when available before declaring material visual work finished;
- distinguish static code review from proof of rendered correctness.

## 12. Persian / RTL requirements

Persian/RTL is a first-class conditional layer.

When applicable, the Skill must reason about:

- document direction and logical layout primitives;
- bidi/LTR islands for phone, email, URL, code, OTP, card, IBAN, identifiers;
- Persian typography, line height, joining, ZWNJ, mixed-script behavior;
- Persian digits/display formatting while preserving machine/API values appropriately;
- currency/date/calendar conventions when the product requires them;
- directional icons and motion;
- Persian UI copy/register consistency;
- RTL tables, forms, navigation, drawers, charts, responsive behavior, and accessibility.

Do not assume every Persian-language product uses every Iranian-local convention; derive product locale and requirements from current evidence.

## 13. Non-goals

v0.1 is not intended to:

- replace GitHub/project management;
- replace WordPress architecture/mechanism ownership;
- become a full branding/logo/marketing-asset suite;
- own backend, infrastructure, database, deployment, or business-policy architecture;
- bundle every third-party component library;
- force a universal design style;
- force a universal frontend framework;
- duplicate official platform documentation wholesale;
- create design-system documents for trivial work;
- turn every UI change into a long checklist or mandatory ceremony.

## 14. Third-party and licensing policy

Foundation phase vendors **no third-party code or copyrighted Skill text**.

Before any future direct source import:

1. identify exact source repository/file/version or commit;
2. verify the applicable license for that material;
3. record copyright/license/notice obligations;
4. record whether the material is copied, modified, translated, or only conceptually synthesized;
5. retain required notices;
6. keep incompatible or unclear material out until resolved.

The repository license is **MIT**. This does not replace or erase third-party obligations: any directly copied or derivative material must retain every applicable upstream license, NOTICE, attribution, and modified-file requirement. Material whose terms cannot be cleanly satisfied alongside this repository must remain external or be excluded.

## 15. v0.1 completion criteria

v0.1 is complete only when all of the following are true:

- a valid installable provider-neutral Skill exists, with any provider-specific packaging isolated as adapters;
- `SKILL.md` has clear triggers, scope, routing, and progressive loading;
- core interface workflow covers new design, modification, redesign, and review;
- English/LTR/global use is first-class;
- Persian/RTL use is first-class and does not contaminate unrelated locales;
- web plus at least representative mobile/native and desktop reasoning paths are covered;
- design-system preservation/creation behavior is proportional and recoverable;
- material visual work includes a self-review/render-review path when capability exists;
- accessibility, responsive behavior, interaction states, UI copy, and motion are represented without universal checklist bloat;
- composition behavior with `github-project-orchestrator` and `wp-native-builder` is specified and regression-tested;
- source provenance and third-party notices are complete for all imported material;
- evaluation scenarios demonstrate no authority takeover, no unnecessary specialist invocation, no duplicated ownership, and no locale leakage;
- canonical packaging/validation succeeds and representative portability checks pass in at least two independent compatible AI-agent environments from different vendors or harness families;
- repository documentation is sufficient for a fresh Master to continue without chat history;
- a first release is created only after the above criteria pass.

## 16. Current locked decisions

- Name: `product-interface-builder`
- Repository: `AChWorks/product-interface-builder`
- Product type: reusable provider-neutral AI Skill
- Scope: user-facing product interface design/UX/visual quality across web, mobile, desktop
- Persian/RTL: first-class conditional capability
- Source model: multi-source synthesis, not a renamed fork
- Core reference set: Anthropic frontend-design, UI UX Pro Max, Impeccable, VibeFarsi, Vercel review guidance
- Composition: complementary specialist alongside GitHub Project Orchestrator and WP Native Builder
- Portability: canonical core is vendor-neutral; provider-specific metadata/tool wiring is adapter-only
- Ecosystem alignment: root `achworks.yaml` aligned with Koinon discovery/governance model; Koinon is not a runtime dependency
- Repository license: MIT; third-party obligations remain independently enforceable
- Implementation status: not started

## 17. Deferred implementation decisions

The implementation Master may decide these when evidence is available, without reopening project intent:

- exact internal file tree;
- which source data is copied, transformed, summarized, or replaced with original synthesis;
- whether a searchable local catalog is worth its package/context/maintenance cost;
- which deterministic validators/detectors justify scripts;
- exact durable design-artifact naming;
- whether live-browser iteration tooling belongs in v0.1 or later;
- exact packaging automation and CI shape.

Third-party attribution/import mechanics remain implementation decisions, but they must preserve the locked MIT repository license and every applicable upstream obligation.

## 18. Recovery / next-session rule

A fresh Master must:

1. read this file;
2. inspect current GitHub Issues/PRs and repository state;
3. treat merged repository content and current GitHub state as authoritative over prior chat summaries;
4. continue the highest-value unblocked roadmap Issue;
5. keep mutation scope limited to repositories explicitly authorized for that work;
6. do not implement changes in `github-project-orchestrator` or `wp-native-builder` merely because this repository depends on future coordination—those repositories require separate explicit mutation scope.
