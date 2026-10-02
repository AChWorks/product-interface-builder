# Product Interface Designer

A reusable, provider-neutral AI Skill for designing, building, prototyping, reviewing, and refining user-facing product interfaces across web, mobile, and desktop.

Product Interface Designer helps an AI make product-grounded interface decisions across visual design, UX, interaction, responsive/adaptive behavior, accessibility, design systems, motion, interface copy, localization, Persian/RTL, and interface-quality review. When implementation is requested and write capability exists, it can also make authorized UI changes while preserving the ownership boundaries of the surrounding project or platform.

## When to use it

Use Product Interface Designer for work such as:

- designing new screens, surfaces, dashboards, landing pages, forms, or navigation;
- targeted UI/UX changes and redesigns;
- wireframes, mockups, prototypes, and screenshot/reference-led work;
- visual and interaction design;
- responsive/adaptive behavior and multi-context interfaces;
- accessibility-informed interface decisions;
- design-system and reusable component decisions;
- interface copy and presentation;
- localization and locale-aware UI, including Persian/RTL;
- interface review, refinement, visual QA, and usability-oriented critique.

Do not use it as the primary owner for standalone branding/graphic work or pure backend, infrastructure, data, or deployment work unless those concerns materially change the user-facing interface.

## Install

Download the installable [`skill.zip`](https://github.com/AChWorks/product-interface-designer/releases/latest/download/skill.zip) from the [latest GitHub release](https://github.com/AChWorks/product-interface-designer/releases/latest).

The release asset is intentionally the minimal install bundle. It contains only:

- `SKILL.md`
- `agents/openai.yaml`
- the canonical `references/*.md` runtime files

Repository-only files such as `README.md`, `LICENSE`, `achworks.yaml`, and `docs/` are not included in the install ZIP.

For ChatGPT, upload/import `skill.zip` through the available Skills workflow. In another compatible AI/agent runtime, use the same Skill directory or ZIP according to that runtime's import mechanism. The behavioral instructions are provider-neutral; `agents/openai.yaml` is optional provider UI/discovery metadata rather than a behavioral source of truth.

## How to use it

Once installed, invoke Product Interface Designer explicitly or ask for interface work normally when your runtime supports Skill discovery.

Example requests:

```text
Design the checkout interface for this web app while preserving the existing design system.
```

```text
Review this dashboard screenshot for UX, hierarchy, responsive, and accessibility issues.
```

```text
Make this settings interface work correctly in Persian/RTL without changing the product behavior.
```

```text
Redesign this mobile onboarding flow using the existing product constraints and visual language.
```

```text
Implement this approved interface change in the existing frontend without changing application architecture.
```

Useful context includes the user/product outcome, target surface/platform, existing design system or UI, screenshots/source files, important business constraints, active locale/direction, and whether a reference should be followed closely or used only as inspiration. The Skill should recover available context before asking for information that can already be discovered safely.

## How it works

[`SKILL.md`](SKILL.md) is the compact control plane. It establishes the interface problem, preserves accepted product/design truth, resolves constraint precedence, and routes only to the reference domains that materially apply.

Detailed guidance lives under [`references/`](references/) and is progressively loaded only when relevant. This keeps the active context smaller while still supporting domains such as design systems, human factors, information architecture, internationalization, Persian/RTL, platform behavior, trust/agency, collaboration, adaptive contexts, AI-mediated interfaces, and interface review.

Version-sensitive platform or standards behavior is not frozen into the Skill when a current authoritative source should own the exact rule.

## Composition with other Skills

Product Interface Designer owns **user-facing interface intent and quality**, not the entire project.

| Concern | Primary owner |
| --- | --- |
| Interface design, interaction, hierarchy, responsive/adaptive intent, accessibility UX, interface copy, locale presentation, interface review | Product Interface Designer |
| Project scope, repository work, CI, integration, release, deployment, continuity | GitHub Project Orchestrator |
| WordPress mechanisms, Gutenberg/theme/plugin/WooCommerce lifecycle, publication | WP Native Builder |
| Product/idea framing, value, evidence, alternatives, reuse/placement decisions | Idea Advisor |

When these Skills compose, Product Interface Designer returns the interface decision and implementation latitude, then control returns to the project/platform/advisory owner. It does not create a nested project manager or take over repository/release authority.

These integrations are composition boundaries, not mandatory runtime dependencies.

## Design model

Product Interface Designer is an **AChWorks-owned synthesis**, not a fork or wrapper around another design Skill.

The project studies relevant design/UX sources, extracts ideas that fit its requirements, resolves overlap, and rewrites useful knowledge into one local behavior model. Upstream command names, chapter structures, workflows, catalogs, provider assumptions, and taxonomies are not the architecture of this Skill.

See [`docs/SOURCE-STRATEGY.md`](docs/SOURCE-STRATEGY.md) for source/provenance policy and [`docs/INSTRUCTION-ARCHITECTURE.md`](docs/INSTRUCTION-ARCHITECTURE.md) for instruction and cross-Skill composition design.

## Repository structure

The installable runtime consists of:

```text
product-interface-designer/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── *.md
```

The repository additionally contains authoring and project-management material that is intentionally excluded from the install ZIP:

- [`docs/PROJECT-SPEC.md`](docs/PROJECT-SPEC.md) — durable project intent and release criteria;
- [`docs/INSTRUCTION-ARCHITECTURE.md`](docs/INSTRUCTION-ARCHITECTURE.md) — instruction architecture and composition contract;
- [`docs/THEORETICAL-SCENARIOS.md`](docs/THEORETICAL-SCENARIOS.md) — authoring-only semantic regression scenarios;
- [`docs/SOURCE-STRATEGY.md`](docs/SOURCE-STRATEGY.md) — source corpus and provenance policy;
- [`achworks.yaml`](achworks.yaml) — AChWorks/Koinon discovery and governance metadata;
- [`LICENSE`](LICENSE) — repository license.

## Project truth

[`docs/PROJECT-SPEC.md`](docs/PROJECT-SPEC.md) owns durable project intent and release criteria. GitHub Issues and pull requests own current work and implementation state. The README is the user/developer entry surface, not a duplicate project specification or status log.

## License

Original Product Interface Designer material is licensed under the [MIT License](LICENSE). No third-party code, datasets, components, scripts, templates, or copyrighted Skill prose are currently vendored or adapted in this repository. If that changes, provenance and applicable upstream notice/license obligations must be recorded before integration.
