# Product Interface Builder

A reusable, provider-neutral AI Skill for designing, building, reviewing, and refining product interfaces across web, mobile, and desktop.

The Skill is intended to own **user-facing interface quality**: visual direction, UX, design systems, responsive behavior, accessibility, interaction, motion, typography, color, localization, and rendered interface review.

## Portability

The canonical Skill must not depend on one AI vendor, model family, or agent harness.

- Keep core instructions, references, knowledge, and scripts provider-neutral.
- Isolate provider-specific metadata or installation adapters from the canonical behavior.
- Prefer capability-based routing (for example: browser/render access, filesystem access, shell access, image/screenshot inspection) over vendor-specific tool names.
- Allow graceful degradation when a particular runtime lacks an optional capability.
- Avoid maintaining separate behavioral rulebooks per provider.

Provider adapters may exist where a platform requires its own packaging or metadata, but they must not become the source of truth for the Skill.

## Status

**v0.1 implementation in progress.**

The canonical project definition is [docs/PROJECT-SPEC.md](docs/PROJECT-SPEC.md). The provider-neutral control kernel lives in [SKILL.md](SKILL.md), with direct progressive-loading references under `references/`. Future work must recover from repository and GitHub state rather than chat history.

## AChWorks / Koinon alignment

This repository participates in the AChWorks ecosystem through the root [`achworks.yaml`](achworks.yaml) descriptor.

- This repository owns its Skill implementation, roadmap, releases, and design-domain behavior.
- Koinon owns cross-project governance/discovery/contracts and remains a coordination layer, not a runtime dependency.
- Product Interface Builder consumes applicable Koinon governance/validation contracts without duplicating Koinon's live state.
- Cross-repository mutation still requires explicit authorization for each exact repository.

## Ecosystem role

Product Interface Builder is designed to compose with, not replace:

- `github-project-orchestrator` — project framing, GitHub lifecycle, Workers, review/integration, CI, release, and continuity.
- `wp-native-builder` — WordPress ownership/mechanism decisions, Gutenberg safety, WooCommerce, themes/plugins, and WordPress-native implementation.

When composed, Product Interface Builder owns **what the user-facing experience should be and how its quality is evaluated**. The surrounding specialist or Master retains its own execution authority.

## Source strategy

The project will synthesize ideas from multiple sources rather than clone one upstream Skill:

- Anthropic `frontend-design` — visual taste, intentional art direction, anti-generic design, self-critique.
- `ui-ux-pro-max` — design intelligence, structured catalogs, product/style/typography/palette guidance, cross-stack ideas.
- Impeccable — product/design separation, shaping, critique, audit, polish, hardening, and visual iteration concepts.
- VibeFarsi — Persian/RTL, Persian typography and UI copy, Iranian interface conventions, Jalali/numeric/local patterns.
- Vercel Web Interface Guidelines — review/audit input for web interface quality.
- LottieFiles motion-design guidance — optional specialist input when motion needs deeper treatment.

Directly imported or adapted third-party material must be traceable in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## License

Product Interface Builder is licensed under the [MIT License](LICENSE). Third-party material retains its own applicable notice/license obligations as recorded in `THIRD_PARTY_NOTICES.md`.

## Next work

Implementation work is tracked in GitHub Issues. Do not start by reconstructing requirements from chat; begin with `docs/PROJECT-SPEC.md` and the current open Issues.
