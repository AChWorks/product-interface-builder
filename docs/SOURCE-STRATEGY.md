# Source Synthesis and Provenance Strategy

Status: **LOCKED FOR v0.1**

Audit snapshot: 2026-10-02

This file records the source corpus, provenance, licensing evidence, and synthesis rules used to create Product Interface Builder. It is **not** a second behavioral rulebook and does not define the runtime file structure.

## Synthesis standard

Product Interface Builder should read like one book written for our own purpose after studying several good books on the same subject.

Apply these rules:

1. **Use sources as inputs, not templates.** Do not preserve an upstream chapter order, command set, mode taxonomy, workflow, file tree, provider adapter, or naming scheme merely because it exists upstream.
2. **Organize locally by our responsibilities.** A useful idea is rewritten into the Product Interface Builder concern that owns it; source identity does not determine its destination.
3. **Do not create one-to-one translations of source taxonomies.** If a source has four modes, ten commands, three dials, or a checklist, those structures are not imported by default.
4. **Prefer convergence over imitation.** Strong local rules should ideally be supported by our product requirements, general interface practice, or more than one source—not only by a distinctive upstream mechanism.
5. **Keep source-specific machinery out unless independently justified.** Catalogs, scripts, binaries, detectors, generated provider copies, presets, and mandatory source workflows require their own local value case.
6. **Resolve overlap once.** When several sources cover the same concern, write one local rule instead of preserving parallel versions.
7. **Keep the Skill lean.** A source idea that adds little beyond competent model knowledge, duplicates an existing rule, or creates ceremony should be omitted.
8. **Separate conceptual influence from direct import.** Concepts may inform original wording. Directly copied/adapted copyrightable material requires explicit provenance and license handling.

## Current import state

**No third-party code, datasets, components, scripts, templates, binaries, catalogs, or copyrighted Skill prose is currently vendored or adapted in this repository.**

All runtime instructions in v0.1 are intended as original AChWorks synthesis. The external projects below are design references only and are not runtime dependencies.

Because there is currently no direct third-party import, a separate `THIRD_PARTY_NOTICES.md` file is unnecessary. Create one if and when directly imported/adapted material first enters the repository and requires retained notices or attribution.

## Audited source corpus

| Source | Audited revision / path | License evidence | Useful input |
|---|---|---|---|
| Anthropic `frontend-design` | `anthropics/skills@8a1541c4a3ffa5a20a5a91de0dcf3f0bab1d1ef4` — `skills/frontend-design/SKILL.md` | `skills/frontend-design/LICENSE.txt` — Apache-2.0 | product/brief-grounded art direction, deliberate visual choices, restraint, anti-generic critique |
| UI UX Pro Max | `nextlevelbuilder/ui-ux-pro-max-skill@09170eec67eefd46a7ae85de61b40c194020f997` | root `LICENSE` — MIT | broad design knowledge, product/style/type/color/data/UX option space, cross-stack awareness |
| Impeccable | `pbakaus/impeccable@5e7914c46890a73460d099a1fae100a169e08c09` | root `LICENSE` — Apache-2.0 | preserve-vs-redesign thinking, interface critique/refinement, edge-state and finish discipline |
| VibeFarsi | `TronIsHere/vibefarsiui@8b2f6abf357c98a61f24acc4132f7aaf715ce914` — reviewed `registry/skills` material | MIT verified for `mcp/` and `packages/cli/`; no repository-wide grant for `registry/skills` verified at this revision | Persian/RTL concerns, bidi, typography, display formatting, Iranian-local patterns |
| Vercel Web Interface Guidelines | `vercel-labs/web-interface-guidelines@e3d624baaf29dc1fc645aff3e38f03e564d2d6b1` | root `LICENSE` — MIT | web interaction, forms, accessibility, content, responsive and interface-performance review signals |
| LottieFiles motion-design-skill | `LottieFiles/motion-design-skill@f9a8a041b85185ee4881b3471d3415e939aac772` — `skills/motion-design/SKILL.md` | root `LICENSE` — MIT | purposeful motion, timing/easing awareness, feedback and choreography concepts |

### Source-specific boundaries

- Do not vendor UI UX Pro Max catalogs/search implementation merely because they exist.
- Do not import Impeccable command/mode taxonomy, provider-generated copies, binaries, scripts, detectors, or persistence workflow as Product Interface Builder architecture.
- Do not directly copy/adapt VibeFarsi `registry/skills` material unless a license grant covering those exact paths is established first.
- Do not promote Vercel-specific brand preferences to universal rules.
- Do not import LottieFiles timing tables, archetype tables, or recipes as canonical presets.
- Do not reproduce Anthropic's distinctive anti-template example lists as our own checklist.

## Direct-import policy

Before any future direct copy, translation, transformation, or derivative import:

1. identify the exact repository, revision, and source path;
2. verify the license that applies to that exact material;
3. record the local destination and whether the material is copied or modified;
4. preserve applicable copyright, license, NOTICE, attribution, and modified-file obligations;
5. create/update `THIRD_PARTY_NOTICES.md` when retained notices or attribution are required;
6. exclude the material when license scope or obligations are unclear.

Repository-level MIT licensing never erases third-party obligations.

## Refresh rule

The pinned revisions are a design/provenance baseline, not dependencies to chase.

Re-audit a source only when:

- direct material may be imported;
- a materially different upstream capability is being considered;
- licensing/provenance facts change;
- a real design gap appears that current synthesis does not cover.

Do not update source pins merely because an upstream branch moved.
