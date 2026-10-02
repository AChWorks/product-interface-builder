---
name: product-interface-builder
description: Design, build, review, and refine user-facing product interfaces across web, mobile, and desktop. Use for new interfaces, targeted UI changes, redesigns, design systems, layout, typography, color, responsive behavior, accessibility, interaction, motion, interface copy, visual QA, and locale-aware UI including Persian/RTL. Preserve an existing product's design language unless redesign is explicit. Skip pure backend, infrastructure, database, or non-visual work unless it materially changes the user-facing interface.
---

# Product Interface Builder

Build the interface the product needs, not a generic style demo. Treat current product truth, explicit requirements, platform constraints, locale/script behavior, and rendered evidence as stronger than catalog or aesthetic defaults.

## 1. Establish the interface problem

Before changing visual behavior, recover enough evidence to answer:

- Is this a **new interface**, **targeted modification**, **redesign**, or **review**?
- What product, audience, task, content, and usage context matter?
- What current design system, components, tokens, brand rules, copy vocabulary, or screenshots already exist?
- Which platform is actually targeted: web, mobile/native, desktop, or a deliberate combination?
- Which locale/script requirements actually apply?
- Which runtime capabilities are available for source inspection, editing, rendering, screenshots/images, command execution, or persistent project state?

Do not invent missing incumbent design truth. For bounded changes, preserve what is already authoritative unless the request explicitly changes it.

## 2. Use decision precedence

When guidance conflicts, prefer:

1. explicit current user requirements;
2. authoritative product/project/design-system truth;
3. applicable accessibility, safety, legal, and platform requirements;
4. platform conventions;
5. locale/script conventions;
6. product, audience, content, and task reasoning;
7. general design principles;
8. style/catalog suggestions.

A style suggestion is an option, never authority.

## 3. Load only the guidance the task needs

References are one level deep from this file. Do not load them all by default.

- For **new design, modification, or redesign**, read [references/design-core.md](references/design-core.md).
- When **Persian, RTL, bidirectional content, or Iranian-local interface behavior** is actually relevant, read [references/persian-rtl.md](references/persian-rtl.md).
- When platform conventions or implementation behavior differ across **web, mobile/native, or desktop**, read [references/platforms.md](references/platforms.md).
- For **interface review**, or before declaring material visual work complete when review evidence can be obtained, read [references/review.md](references/review.md).
- When working under another project Master or with a platform specialist, read [references/composition.md](references/composition.md).

Do not load Persian/RTL guidance for unrelated LTR work. Do not load every platform section when one target is known. Do not turn review guidance into ceremony for a trivial local change.

## 4. Route by capabilities, not vendor names

Treat capabilities as optional environment features:

- **source/filesystem** — inspect current implementation and design artifacts;
- **edit/write** — implement authorized changes;
- **render/browser** — run the interface and inspect actual layout/interaction;
- **image/screenshot inspection** — evaluate rendered visual evidence;
- **shell/command execution** — run repository-defined validation where safe;
- **persistent workspace/project state** — reuse durable design truth when justified;
- **external retrieval/connectors** — retrieve current product/platform evidence when permitted.

If a capability is absent, degrade explicitly:

- no source access -> work only from supplied artifacts and state assumptions;
- no write access -> provide implementation-ready guidance instead of claiming changes;
- no render/screenshot access -> perform static review, label it static, and never claim rendered correctness;
- no shell/test capability -> do not claim tests or validation ran;
- no persistent state -> do not manufacture a substitute source of truth in chat.

A missing optional capability should narrow evidence, not make ordinary design reasoning impossible.

## 5. Act proportionally

When implementation is requested and authorized, make the smallest coherent change that satisfies the design intent. Reuse the project's existing stack, components, and durable design truth; create new persistent design artifacts only when substantial continuing work warrants them.

Do not introduce a framework, library, dependency, or global design-system change merely to express a local visual preference.

For material visual work, obtain rendered evidence when the environment supports it and correct clear defects before completion. Static source inspection is useful evidence but is not proof of rendered correctness.

Never fabricate product claims, testimonials, metrics, certifications, guarantees, user data, or brand assets.

## 6. Preserve standalone and composed behavior

This Skill remains useful on its own. When another Skill or project Master is active, keep interface/design ownership bounded rather than taking over project planning, repository authority, platform mechanism selection, integration, or release.

Use [references/composition.md](references/composition.md) when those boundaries matter.

## 7. Finish with evidence, not checklist theater

Return or implement the interface outcome the user requested. Mention material assumptions, limitations, or unverified rendered behavior only when they affect confidence or the user's next action. Do not dump every internal check into the response.
