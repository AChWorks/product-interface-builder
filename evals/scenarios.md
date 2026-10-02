# v0.1 Evaluation Scenarios

These scenarios validate Product Interface Builder behavior without depending on chat history. Run them in a fresh context with only the packaged Skill plus the scenario prompt and any explicitly named collaborating Skill.

Record the runtime/harness, model/provider, Skill revision, loaded references, output, and pass/fail evidence. A different runtime may expose different tools; evaluate behavior, ownership, and evidence claims rather than exact wording.

## Core scenarios

### E01 — New interface design

**Prompt:** Design a new analytics dashboard for operations staff. No incumbent visual system exists. The interface is English/LTR web.

**Pass when:**
- direction is grounded in product, audience, task, content, and platform;
- it establishes only enough reusable design system for coherence;
- it does not activate Persian/RTL guidance;
- it does not invent product claims or data.

### E02 — Targeted modification preserves incumbent design

**Prompt:** An existing SaaS settings page uses Inter, compact 8px spacing, blue primary actions, and established components. Improve only the destructive account-delete confirmation.

**Pass when:**
- neighboring UI is not opportunistically redesigned;
- incumbent tokens/components/terminology are preserved unless the requested change requires otherwise;
- review depth remains local/proportional;
- Persian/RTL guidance does not leak into the task.

### E03 — Explicit redesign

**Prompt:** Redesign an existing project-management dashboard while preserving validated product capabilities, terminology, and accessibility obligations.

**Pass when:**
- durable product truth is separated from replaceable visual direction;
- visual system choices may change deliberately;
- redesign is not treated as a targeted patch.

### E04 — Static review without rendered evidence

**Prompt:** Review supplied interface source code, but no browser/render/screenshot capability is available.

**Pass when:**
- findings are explicitly static/inferred;
- rendered correctness, responsive behavior, motion, and visual fidelity are not claimed as verified;
- the Skill still produces useful prioritized review findings.

### E05 — Review with rendered evidence

**Prompt:** Review a material UI change with source plus representative screenshots/renders at supported sizes.

**Pass when:**
- rendered evidence is treated as stronger than static inference for visual correctness;
- clear in-scope defects are corrected or precisely surfaced before completion;
- findings are prioritized by user impact rather than checklist volume.

### E06 — Persian/RTL with non-Iranian locale choices

**Prompt:** Design a Persian mobile-native checkout. It is RTL and uses Persian UI copy, but the product explicitly requires Gregorian dates and USD.

**Pass when:**
- Persian/RTL typography, bidi, logical direction, and directional UI rules activate;
- Jalali, Toman/Rial, Iranian validation/address/payment assumptions are not invented;
- mobile-native concerns are applied;
- machine values remain separate from display localization where relevant.

### E07 — English/LTR locale non-leakage

**Prompt:** Modify an English/LTR desktop interface with no Persian, RTL, or Iranian-local requirements.

**Pass when:**
- Persian/RTL reference does not affect the result;
- locale-specific rules are not loaded/applied by default.

### E08 — Platform routing

Run equivalent feature prompts for web, mobile/native, and desktop.

**Pass when:**
- web uses browser semantics/history/keyboard-pointer behavior;
- mobile/native accounts for touch, safe areas, system navigation and software keyboard;
- desktop accounts for windows, keyboard/pointer precision and dense workflows;
- one platform is not blindly used as the presentation source of truth for the others.

### E09 — Project Master composition

**Prompt:** Product Interface Builder is invoked under GitHub Project Orchestrator for an interface task inside an authorized repository.

**Pass when:**
- Product Interface Builder owns design/UX decisions and evidence only;
- the Master retains scope, priority, repository authority, integration, CI, release, and continuity;
- no competing project plan or duplicate durable state is created.

### E10 — WordPress composition

**Prompt:** Design and implement a material WordPress interface change with WP Native Builder available.

**Pass when:**
- Product Interface Builder owns intended user-facing result and visual/UX review;
- WP Native Builder owns WordPress owner/mechanism, Gutenberg safety, theme/plugin placement and lifecycle concerns;
- Product Interface Builder does not prescribe brittle raw block/plugin mechanisms as design authority.

### E11 — Graceful degradation

Run a material design task with one optional capability removed: write, render, shell/test, or persistent project state.

**Pass when:**
- work degrades to the strongest available evidence/output;
- missing capability is not fabricated;
- ordinary design reasoning remains useful.

### E12 — Proportional durable state

**Prompt:** Make one small spacing/alignment correction in an established product.

**Pass when:**
- no new MASTER/design-system/project artifact is created by ritual;
- existing design truth is reused;
- only future-useful durable changes are persisted.

## Cross-runtime gate

Before v0.1 release, run representative scenarios in at least two independent compatible AI-agent environments from different vendors or harness families.

The gate passes only when both environments:
- discover/load the canonical `SKILL.md` without a behavioral fork;
- can resolve supporting `references/` progressively;
- preserve provider-neutral ownership and capability degradation semantics;
- do not require `agents/openai.yaml` as a behavioral source of truth.

A runtime-specific metadata adapter may be present, but it must remain removable without changing canonical behavior.
