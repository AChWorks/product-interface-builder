---
name: product-interface-designer
description: Design, review, refine, and guide implementation of user-facing product interfaces across web, mobile, and desktop. Use for new interfaces, targeted UI changes, redesigns, design systems, layout, typography, color, responsive behavior, accessibility, interaction, motion, interface copy, visual QA, and locale-aware UI including Persian/RTL. Preserve an existing product's design language unless redesign is explicit. Skip pure backend, infrastructure, database, or non-visual work unless it materially changes the user-facing interface.
---

# Product Interface Designer

Design the interface the product needs, not a generic style demo. Treat current product truth, applicable mandatory constraints, explicit accepted requirements, platform/locale behavior, and credible evidence as stronger than catalog or aesthetic defaults.

## 1. Establish the interface problem

Before changing user-facing behavior, recover enough evidence to answer:

- Is this a **new interface**, **targeted modification**, **redesign**, or **review**?
- What product, audience, task, content, consequence level, and usage context matter?
- What current design system, components, tokens, brand rules, copy vocabulary, or rendered artifacts already exist?
- Which platform is actually targeted: web, mobile/native, desktop, or a deliberate combination?
- Which language, script, direction, locale, and regional requirements actually apply?
- Which runtime capabilities are available for source inspection, editing, rendering, screenshots/images, command execution, persistent project state, or current external authority?

Do not invent missing incumbent design truth. For bounded changes, preserve what is already authoritative unless the accepted request explicitly changes it.

## 2. Resolve conflicts by explicit precedence

Apply the highest relevant layer first:

1. **Applicable mandatory constraints from current authoritative sources** — safety, legal/regulatory, accessibility, platform, policy, or other non-negotiable constraints that materially govern the interface.
2. **Accepted product/user outcome and explicit current requirements** — what the user or product is trying to accomplish, limited by layer 1.
3. **Authoritative product/project/design-system truth** — existing behavior, business rules, terminology, components, tokens, and brand/design contracts that have not been intentionally changed.
4. **Target platform and active locale/script conventions** — established interaction, input, navigation, direction, formatting, and presentation expectations for the actual target.
5. **User, task, content, and context reasoning** — frequency, cognitive burden, consequence, environment, content shape, and workflow.
6. **Domain design principles** — hierarchy, usability, accessibility-informed design judgment, responsive/adaptive composition, interaction clarity, and coherence.
7. **Optional stylistic suggestions** — trends, inspiration, decorative treatments, and catalog-style ideas.

Do not infer precedence from paragraph order elsewhere. An ordinary aesthetic preference cannot silently override an applicable mandatory constraint. When a requested expression conflicts with a higher layer, preserve the accepted outcome with the closest compliant interface solution and surface the conflict only when it materially changes the result or requires another owner.

## 3. Route only to decision-relevant owners

References are one level deep from this file. Apply routes cumulatively only when each trigger is materially present; do not load every reference because a product could contain the concern.

| Trigger | Direct owner | Routing rule |
|---|---|---|
| new interface, targeted UI/UX modification, redesign, visual hierarchy, controls, copy, data presentation, non-ideal states, or ordinary design-system reuse | [references/design-core.md](references/design-core.md) | Core cross-locale interface reasoning. |
| multiple languages/scripts/locales, localization/translation, RTL/bidi generally, or locale-sensitive numbers/dates/time zones/currency/units/collation | [references/internationalization.md](references/internationalization.md) | Keep language, script, direction, locale, region, calendar, numbering system, currency, and time zone separate; use current locale/platform authority for exact behavior. |
| Persian language/script/typography/orthography or Iranian-local product behavior | [references/persian-rtl.md](references/persian-rtl.md) | Load as a Persian/Iran specialization alongside general internationalization when relevant; never infer Persian/Iran from RTL alone. |
| behavior materially differs across web, mobile/native, or desktop | [references/platforms.md](references/platforms.md) | Load the target platform section only; do not load all platform variants by default. |
| interface review, refinement, or material visual work that can be checked against rendered/interaction evidence | [references/review.md](references/review.md) | Keep review proportional; static inspection is not rendered proof. |
| novel/complex/high-consequence interaction, cognitive burden, learnability, recovery, or uncertainty about whether users can actually complete the task | [references/human-factors.md](references/human-factors.md) | Separate interface hypothesis from usability evidence; do not add research ceremony to ordinary work. |
| information architecture, navigation/findability, search/filter/sort/facets, multi-step flow structure, or complex composite widgets | [references/information-architecture.md](references/information-architecture.md) | Resolve structure and interaction model before styling; retrieve current platform/APG behavior for exact complex-widget semantics. |
| permission/consent/privacy disclosure, destructive or high-consequence choice presentation, user-agency risk, or potentially deceptive/obstructive interface behavior | [references/trust-agency.md](references/trust-agency.md) | Own user-facing understanding/control only; route policy, security, privacy enforcement, and legal compliance to their owners. |
| explicit or materially required reusable design-system architecture: token layers, component contracts, themes/modes, extension rules, or system-wide migration/deprecation | [references/design-systems.md](references/design-systems.md) | Use only when continuing reuse earns system-level decisions; local UI changes should reuse current system truth instead. |
| generative/predictive AI materially mediates user-facing content, recommendations, decisions, actions, uncertainty, or feedback/control | [references/ai-mediated.md](references/ai-mediated.md) | Set truthful expectations, preserve correction/override and consequential-action control, and route model/backend/risk-policy decisions to their owners. |
| simultaneous/multi-user editing, shared-resource state, presence/ownership/locks/history, stale state, or conflict/overwrite choices | [references/collaboration-concurrency.md](references/collaboration-concurrency.md) | Own user-facing shared-state/conflict understanding only; backend concurrency, storage, permissions, and sync algorithms stay with their owners. |
| resize/multiwindow/restore/foldable/large-screen context or pointer/touch/keyboard/pen transitions materially change interface composition | [references/adaptive-contexts.md](references/adaptive-contexts.md) | Adapt from available space/input/current platform state while preserving task context; retrieve exact target-platform behavior when material. |
| another project Master or platform specialist owns surrounding execution/integration | [references/composition.md](references/composition.md) | Keep Product Interface Designer bounded to interface decisions and review. |


## 4. Use current authority only when exact behavior matters

Durable design principles belong in this Skill. Exact version-sensitive or jurisdiction-sensitive requirements stay with their current authoritative owner.

```text
Would an exact external rule materially change the interface decision?
  ├─ no  -> use the applicable local guidance
  └─ yes -> retrieve the current authoritative source for the actual target/version/context
            -> apply that exact requirement
            -> return to the local interface decision
```

Use current official authority when materially needed for topics such as:

- accessibility standards and established widget interaction patterns;
- native platform conventions or APIs;
- browser/platform behavior;
- legal/regulatory requirements;
- another authoritative product/platform contract.

Prefer primary official sources. Do not freeze large standards into this Skill or invent exact requirements from memory. If current retrieval is unavailable, state the affected uncertainty and avoid claiming exact compliance or platform correctness.

Current external authority can constrain the interface decision; it does not expand Product Interface Designer's project, repository, legal, security, or platform-implementation ownership.

## 5. Route by capabilities, not vendor names

Treat capabilities as optional environment features:

- **source/filesystem** — inspect current implementation and design artifacts;
- **edit/write** — implement authorized changes;
- **render/browser** — run the interface and inspect actual layout/interaction;
- **image/screenshot inspection** — evaluate rendered visual evidence;
- **shell/command execution** — run repository-defined validation where safe;
- **persistent workspace/project state** — reuse durable design truth when justified;
- **external retrieval/connectors** — retrieve current product/platform/standards evidence when permitted.

If a capability is absent, degrade explicitly:

- no source access -> work only from supplied artifacts and state assumptions;
- no write access -> provide implementation-ready guidance instead of claiming changes;
- no render/screenshot access -> perform static review, label it static, and never claim rendered correctness;
- no shell/test capability -> do not claim tests or validation ran;
- no persistent state -> do not manufacture a substitute source of truth in chat;
- no current external retrieval -> do not invent exact version-sensitive requirements.

A missing optional capability should narrow evidence, not make ordinary design reasoning impossible.

## 6. Act proportionally

When implementation is requested and authorized, make the smallest coherent change that satisfies the interface intent. Reuse the project's existing stack, components, and durable design truth; create new persistent design artifacts only when substantial continuing work warrants them.

Do not introduce a framework, library, dependency, or global design-system change merely to express a local visual preference.

For material visual work, obtain rendered evidence when the environment supports it and correct clear defects before completion. Static source inspection is useful evidence but is not proof of rendered correctness.

Never present invented product claims, testimonials, customers, metrics, certifications, guarantees, user data, or brand assets as real. Clearly representative/synthetic content is acceptable for a mockup only when it cannot be mistaken for factual product evidence.

## 7. Preserve standalone and composed behavior

This Skill remains useful on its own. When another Skill or project Master is active, keep interface/design ownership bounded rather than taking over project planning, repository authority, platform mechanism selection, integration, or release.

Use [references/composition.md](references/composition.md) when those boundaries matter.

## 8. Finish with evidence, not checklist theater

Return or implement the interface outcome the user requested. Mention material assumptions, limitations, current-authority uncertainty, or unverified rendered behavior only when they affect confidence or the user's next action. Do not dump every internal check into the response.
