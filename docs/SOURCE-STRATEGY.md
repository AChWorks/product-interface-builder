# Source Synthesis and Provenance Strategy

Status: **LOCKED FOR v0.1 BASELINE**

Audit snapshot: 2026-10-02

This document is the implementation-safe source map for Issue #1. It records why each upstream source is useful, the exact revision inspected, what may influence Product Interface Builder, and what must not be imported blindly.

The repository remains MIT-licensed. For the v0.1 baseline established by this audit, **no third-party Skill prose, source code, datasets, scripts, templates, or components are vendored or adapted into this repository**. The first implementation is intentionally original synthesis. This keeps one canonical behavioral rulebook and avoids carrying upstream packaging/runtime assumptions into the Skill.

## Decision rules

1. Treat upstream projects as evidence and design references, not parallel rulebooks.
2. Convert useful concepts into original, project-owned principles and tests.
3. Give each concern one canonical local owner; do not preserve upstream file structures merely because they exist.
4. Do not import an upstream catalog just because it is available. An import must materially improve quality or repeatability enough to justify package size, context cost, maintenance, provenance, and update burden.
5. A future direct copy, translation, transformation, or derivative import must be reviewed separately before it lands:
   - pin repository + commit/tag + exact source path;
   - verify the license that applies to that exact material;
   - verify NOTICE/copyright/attribution and modified-file obligations;
   - record local derivative paths in `THIRD_PARTY_NOTICES.md`;
   - retain the upstream license/notice where required;
   - exclude the material when scope or licensing remains unclear.
6. Provider-specific upstream packaging is never copied into canonical behavior merely to support a particular harness.

## Audited source map

| Source | Audited revision | License evidence | Value to synthesize | v0.1 disposition | Canonical local owner |
|---|---|---|---|---|---|
| Anthropic `frontend-design` | `anthropics/skills@8a1541c4a3ffa5a20a5a91de0dcf3f0bab1d1ef4`, `skills/frontend-design/SKILL.md` | `skills/frontend-design/LICENSE.txt`: Apache-2.0 | brief-grounded art direction, deliberate visual choices, anti-template critique, restraint, rendered self-critique | Concepts only; no prose/code import | core design reasoning + review guidance |
| UI UX Pro Max | `nextlevelbuilder/ui-ux-pro-max-skill@09170eec67eefd46a7ae85de61b40c194020f997` | root `LICENSE`: MIT | structured/searchable design intelligence, domain routing, design-system option generation, stack/platform-aware lookup | Concepts only for v0.1; do not vendor its large catalogs/search implementation unless later evidence proves the maintenance cost worthwhile | design reasoning; optional future knowledge/data layer |
| Impeccable | `pbakaus/impeccable@5e7914c46890a73460d099a1fae100a169e08c09` | root `LICENSE`: Apache-2.0 | separation of durable product truth from replaceable design direction; shape/craft/critique/audit/polish/harden/adapt lifecycle; rendered evidence; one-source/provider-output pattern | Concepts only; no provider-generated copies, binaries, prose, scripts, or detectors imported | workflow/control kernel + visual review |
| VibeFarsi | `TronIsHere/vibefarsiui@8b2f6abf357c98a61f24acc4132f7aaf715ce914` | MIT files exist for `mcp/` and `packages/cli/`; no root LICENSE or repository-wide grant for `registry/skills` was verified at this revision | Persian/RTL concerns: logical direction, bidi/LTR islands, Persian typography, display-vs-machine digit handling, locale-aware dates/currency/forms, directional UI behavior | **Concepts only. No direct copy/adaptation from `registry/skills` unless exact license scope for those files is later established.** Product-specific Iranian defaults must not become universal rules. | conditional Persian/RTL locale layer |
| Vercel Web Interface Guidelines | `vercel-labs/web-interface-guidelines@e3d624baaf29dc1fc645aff3e38f03e564d2d6b1` | root `LICENSE`: MIT | web-focused interaction/accessibility/responsive/forms/content/performance review signals | Concepts only; use as web audit input, not art direction. Vercel-specific preferences remain non-universal. | web branch of review guidance |
| LottieFiles `motion-design-skill` | `LottieFiles/motion-design-skill@f9a8a041b85185ee4881b3471d3415e939aac772`, `skills/motion-design/SKILL.md` | root `LICENSE`: MIT; Skill frontmatter also declares MIT | motion purpose, timing/easing/choreography reasoning, interaction feedback, restraint | Optional conceptual input only; no default dependency and no prose/data import | motion section of interaction/review guidance |

## Synthesis ownership

The upstream concepts normalize into these local concerns instead of remaining source-shaped:

| Concern | Canonical behavior owner |
|---|---|
| task routing, capability checks, progressive loading, graceful degradation | root `SKILL.md` control kernel |
| product/audience/content grounding, new design, modification, redesign, hierarchy, visual direction, design systems | core design reference |
| locale/script behavior, Persian/RTL, bidi, locale-sensitive copy/formatting | locale reference |
| web/mobile/desktop conventions | platform reference |
| rendered/static review, accessibility, responsive behavior, interaction states, motion and obvious UI performance risks | review reference |
| project-management and WordPress composition boundaries | composition reference |

Exact filenames are implementation details for Issue #2 and may be collapsed when a smaller structure is clearer. The ownership table, not an upstream folder tree, is the durable constraint.

## Explicit exclusions for v0.1

- no wholesale upstream Skill copies;
- no mirrored provider-specific rulebooks;
- no UI UX Pro Max bulk CSV/catalog import by default;
- no Impeccable executable/binary/provider-output import;
- no VibeFarsi component library, CLI/MCP code, or `registry/skills` prose import;
- no Vercel-brand-specific preferences promoted to universal interface rules;
- no LottieFiles timing tables/archetype prose copied as canonical defaults;
- no Premium, proprietary, commercial-font asset, or unclear-license material.

The Skill may still recommend a commercial font or external product when the user's project already licenses or selects it; that is not permission to redistribute the asset.

## License coexistence rules for future imports

### Apache-2.0 sources

Anthropic `frontend-design` and Impeccable are usable as conceptual references now. If a future change directly copies or creates a derivative of Apache-2.0 material, repository-level MIT does not erase Apache-2.0 obligations. The imported/derivative material must retain the applicable Apache license and attribution requirements, and modified files must carry required change notices. Any upstream NOTICE obligations must be checked at the exact pinned source path/revision before the import.

### MIT sources

UI UX Pro Max, Vercel Web Interface Guidelines, and LottieFiles are MIT at the audited revisions. A future substantial direct copy must retain the applicable upstream copyright and permission notice. Product Interface Builder's original material can remain MIT; copied third-party material must remain traceable as third-party material.

### VibeFarsi

The audited repository describes itself publicly as free/open-source and contains MIT licensing for the CLI and MCP subpackages, but the audit did not establish a formal license grant covering `registry/skills`. Therefore those files are not eligible for direct import under the current evidence. Product Interface Builder will independently author its Persian/RTL behavior from general platform/i18n principles plus conceptual review of the source. If a future formal grant clearly covers the exact files, direct-import eligibility can be reconsidered without reopening the value of Persian/RTL as a first-class capability.

## Refresh rule

Pinned revisions above are the evidence baseline for v0.1 design. They are not runtime dependencies and do not need to track every upstream commit. Re-audit an upstream source only when:
- direct material will actually be imported;
- a materially different upstream capability is being adopted;
- a licensing/provenance fact changes;
- an evaluation exposes a gap that current synthesis cannot resolve.

Do not update pins merely to chase upstream movement.
