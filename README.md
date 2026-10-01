# Product Interface Builder

A reusable ChatGPT Skill for designing, building, reviewing, and refining product interfaces across web, mobile, and desktop.

The Skill is intended to own **user-facing interface quality**: visual direction, UX, design systems, responsive behavior, accessibility, interaction, motion, typography, color, localization, and rendered interface review.

## Status

**Foundation / planning complete; implementation not started.**

The canonical project definition is [docs/PROJECT-SPEC.md](docs/PROJECT-SPEC.md). Future work must recover from repository and GitHub state rather than chat history.

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

## Next work

Implementation work is tracked in GitHub Issues. Do not start by reconstructing requirements from chat; begin with `docs/PROJECT-SPEC.md` and the current open Issues.
