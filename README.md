# Product Interface Designer

A reusable, provider-neutral AI Skill for designing, reviewing, refining, and guiding implementation of user-facing product interfaces across web, mobile, and desktop.

It focuses on visual direction, UX, design systems, responsive/adaptive behavior, accessibility, interaction, motion, interface copy, localization, Persian/RTL, and interface-quality review.

Former identity: **Product Interface Builder** / `AChWorks/product-interface-builder` for the historical v0.1 release. The canonical identity from v0.2 onward is **Product Interface Designer** / `AChWorks/product-interface-designer`.

## Design model

Product Interface Designer is an **AChWorks-owned synthesis**, not a fork or wrapper around another design Skill.

The project studies several design/UX sources, extracts ideas that fit our requirements, resolves overlap, and rewrites the useful knowledge into one local behavior model. Upstream command names, chapter structures, workflows, catalogs, provider assumptions, and taxonomies are not the architecture of this Skill.

See [docs/SOURCE-STRATEGY.md](docs/SOURCE-STRATEGY.md) for the audited source corpus/provenance policy and [docs/INSTRUCTION-ARCHITECTURE.md](docs/INSTRUCTION-ARCHITECTURE.md) for AI-legible instruction/composition design.

## Structure

- [SKILL.md](SKILL.md) — compact control plane and routing.
- [references/design-core.md](references/design-core.md) — product-grounded interface design reasoning.
- [references/persian-rtl.md](references/persian-rtl.md) — conditional Persian/RTL behavior.
- [references/platforms.md](references/platforms.md) — web, mobile/native, and desktop differences.
- [references/review.md](references/review.md) — proportional interface review and finish guidance.
- [references/composition.md](references/composition.md) — bounded composition with project/platform specialists.
- [agents/openai.yaml](agents/openai.yaml) — optional provider UI/discovery metadata; not a behavioral source of truth.
- [docs/INSTRUCTION-ARCHITECTURE.md](docs/INSTRUCTION-ARCHITECTURE.md) — authoring structure and cross-Skill composition contract.

## Ecosystem boundaries

Product Interface Designer owns user-facing interface intent and quality. It composes with, rather than replaces, project-management and platform-specific specialists such as GitHub Project Orchestrator and WP Native Builder.

Koinon provides AChWorks discovery/governance contracts through [achworks.yaml](achworks.yaml); it is not a runtime dependency of the Skill.

## Project truth

[docs/PROJECT-SPEC.md](docs/PROJECT-SPEC.md) owns durable project intent and release criteria. GitHub Issues/PRs own current work and implementation state. Chat history is not a source of project truth.

## License

Original Product Interface Designer material is licensed under the [MIT License](LICENSE). No third-party code, datasets, components, scripts, templates, or copyrighted Skill prose are currently vendored or adapted in this repository. If that changes, provenance and applicable upstream notice/license obligations must be recorded before integration.
