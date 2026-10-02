# Third-Party Sources and Notices

This repository is licensed under MIT and synthesizes design/UX ideas from multiple external sources. Repository-level MIT does not supersede any third-party license, NOTICE, attribution, or modified-file obligation for material copied or adapted from an upstream source.

**Current import state (Issue #1 / 2026-10-02): no third-party code, datasets, components, scripts, templates, or copyrighted Skill prose is vendored or adapted in this repository.** The audited sources below are conceptual references only. The implementation baseline is original synthesis.

The implementation-safe decision record and capability map are in [docs/SOURCE-STRATEGY.md](docs/SOURCE-STRATEGY.md).

Before any future direct copy, translation, transformation, or derivative import, update this file with:

- source project, repository and exact source path;
- exact commit/tag/version;
- imported local files/data;
- applicable license;
- upstream copyright/NOTICE/attribution requirements;
- required modified-file notice, if any;
- whether the material is copied, modified, translated, transformed, or only conceptually referenced;
- local files containing the derivative material.

## Audited reference sources

### Anthropic — frontend-design

- Repository: https://github.com/anthropics/skills
- Audited revision: `8a1541c4a3ffa5a20a5a91de0dcf3f0bab1d1ef4`
- Audited path: `skills/frontend-design/SKILL.md`
- License path: `skills/frontend-design/LICENSE.txt`
- License: Apache License 2.0
- Role: visual direction, brief grounding, anti-template design, restraint, self-critique
- Current import status: **conceptual reference only / nothing copied or adapted**
- Future direct-import rule: retain applicable Apache-2.0 terms and notices; check exact NOTICE obligations and mark modified derivative files as required before import.

### UI UX Pro Max

- Repository: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- Audited revision: `09170eec67eefd46a7ae85de61b40c194020f997`
- License path: root `LICENSE`
- License: MIT
- Role: structured/searchable design intelligence, domain routing, design-system option generation
- Current import status: **conceptual reference only / nothing copied or adapted**
- Future direct-import rule: retain upstream MIT copyright/permission notice for substantial copied material. Bulk catalogs/search assets require a separate value/maintenance review before import.

### Impeccable

- Repository: https://github.com/pbakaus/impeccable
- Audited revision: `5e7914c46890a73460d099a1fae100a169e08c09`
- License path: root `LICENSE`
- License: Apache License 2.0
- Role: product/design truth separation, craft/review lifecycle, rendered evidence, provider-output architecture concepts
- Current import status: **conceptual reference only / nothing copied or adapted**
- Future direct-import rule: retain applicable Apache-2.0 terms and notices; check exact NOTICE obligations and mark modified derivative files as required before import.

### VibeFarsi

- Repository: https://github.com/TronIsHere/vibefarsiui
- Audited revision: `8b2f6abf357c98a61f24acc4132f7aaf715ce914`
- Relevant reviewed paths: `registry/skills/persian-rtl-ui/SKILL.md`, `registry/skills/persian-typography.md`
- Verified MIT license scope at this revision: `mcp/LICENSE`, `packages/cli/LICENSE`, and corresponding package metadata
- Repository-root / `registry/skills` license finding: **no root LICENSE or formal repository-wide grant covering these Skill files was verified**
- Role: Persian/RTL, typography, bidi/LTR islands, locale-aware numbers/dates/forms and Iranian interface patterns
- Current import status: **conceptual reference only / nothing copied or adapted**
- Direct-import rule: **do not copy or adapt `registry/skills` material unless the exact applicable license grant for those paths is established first.**

### Vercel — Web Interface Guidelines

- Repository: https://github.com/vercel-labs/web-interface-guidelines
- Audited revision: `e3d624baaf29dc1fc645aff3e38f03e564d2d6b1`
- License path: root `LICENSE`
- License: MIT
- Role: web interface review/audit input
- Current import status: **conceptual reference only / nothing copied or adapted**
- Future direct-import rule: retain upstream MIT copyright/permission notice for substantial copied material; keep Vercel-specific preferences non-universal.

### LottieFiles — motion-design-skill

- Repository: https://github.com/LottieFiles/motion-design-skill
- Audited revision: `f9a8a041b85185ee4881b3471d3415e939aac772`
- Audited path: `skills/motion-design/SKILL.md`
- License path: root `LICENSE`
- License: MIT
- Role: optional motion-design reasoning
- Current import status: **conceptual reference only / nothing copied or adapted**
- Future direct-import rule: retain upstream MIT copyright/permission notice for substantial copied material.

## Provenance invariant

A moving upstream branch is never sufficient provenance for directly imported material. Any future import must pin the exact source revision and path before it is integrated.

Conceptual influence may be documented here even when no copyrightable material is copied, but such attribution does not turn the external source into a runtime dependency or a second behavioral source of truth.
