# Internationalization and Localization

Use this reference when an interface materially supports more than one language, script, direction, locale/region, numbering/formatting convention, calendar/time zone, currency/unit system, or locale-sensitive search/sort behavior.

This file owns **general interface internationalization/localization reasoning**. Locale-specific specializations may add rules only for their active context. [persian-rtl.md](persian-rtl.md) owns Persian/Iran-specific behavior; [platforms.md](platforms.md) owns target-platform conventions; [review.md](review.md) owns verification evidence.

## Contents

[Dimensions](#1-resolve-dimensions-independently) · [Messages](#2-design-copy-and-messages-for-localization) · [Formatting](#3-localize-formatting-without-changing-canonical-data) · [Direction/bidi](#4-treat-direction-and-bidirectional-text-as-structure) · [Layout](#5-design-for-script-and-content-variation) · [Search/sort](#6-handle-locale-sensitive-search-and-sorting-deliberately) · [Product conventions](#7-keep-locale-specific-product-rules-authoritative) · [Authority](#8-use-current-locale-authority-for-exact-behavior) · [Specializations](#9-load-specializations-only-for-the-active-context)

## 1. Resolve dimensions independently

Do not collapse internationalization into a single locale/RTL switch.

| Dimension | Interface question |
|---|---|
| **language** | What language are labels, messages, content, and assistive text written in? |
| **script** | What writing system and glyph/shaping/font support are required? |
| **direction** | What is the base direction and where can mixed-direction text occur? |
| **locale/region** | Which formatting and regional conventions are actually required? |
| **numbering system/digit style** | Which visible digits, grouping, decimal, percent, and sign conventions apply? |
| **calendar/date/time** | Which calendar, date/time pattern, hour cycle, and time zone should users see? |
| **currency/units** | Which currency/unit is semantically correct, and how is it displayed? |
| **names/addresses/domain data** | Which field shapes/order/labels are valid for the product's real locales? |
| **collation/search** | How should users expect text to sort, match, normalize, or transliterate? |

Evidence for one dimension does not determine the others. For example:

- an Arabic-script interface is not automatically Arabic-language, Persian, Iranian, or one specific numbering system;
- an RTL interface does not imply one locale, calendar, currency, or address format;
- one language may be used in multiple regions with different formatting conventions;
- a locale may permit multiple scripts/calendars/numbering systems depending on product requirements.

Current product truth decides supported combinations.

## 2. Design copy and messages for localization

Treat translated text as structured content, not a final-length visual decoration.

- Write complete translatable messages instead of stitching visible sentences from fragments.
- Keep variables/placeholders structurally separate so translators/localization systems can reorder them.
- Use the localization system's plural/select/message capabilities when grammar depends on count, gender, case, or another locale-sensitive category; do not encode English sentence order as a universal grammar.
- Keep terminology/glossaries and product nouns consistent across surfaces.
- Avoid embedding essential user-facing text in images when translated/localized alternatives are expected.
- Do not assume capitalization, word boundaries, punctuation, abbreviation, or plural behavior from English.
- Keep technical identifiers untranslated when translation would change their meaning.
- Let labels/messages expand and wrap; do not force unnatural abbreviations merely to protect an LTR/English layout.

When interface text changes language inside a surface, preserve the language metadata the target platform needs for correct rendering/accessibility where applicable.

## 3. Localize formatting without changing canonical data

Display formatting and stored/protocol values may legitimately differ.

When relevant, localize:

- decimal/grouping/sign/percent presentation;
- visible digit/numbering system;
- dates, times, hour cycles, intervals, and time zones;
- currency presentation and symbol/code placement;
- measurement units and localized unit names.

Keep canonical machine data in the format required by the product/API/storage model. Parse/normalize accepted localized input through established locale-aware libraries or product rules rather than ad-hoc string replacement.

Do not:

- infer a currency from language alone;
- infer a calendar from text direction;
- silently convert a semantic unit merely because another unit is common in a region;
- hand-code calendar conversion, pluralization, or locale formatting when a maintained platform/locale implementation exists;
- display an ambiguous local time when the task requires users to understand the relevant time zone or instant.

Names and addresses are product/domain data, not universal Western forms. Ask only for fields the product needs and follow current product/domain requirements for the active locale.

## 4. Treat direction and bidirectional text as structure

Base direction and language are related but separate metadata.

- Apply direction at the highest correct surface/string scope rather than reversing individual elements as a visual patch.
- Prefer logical start/end concepts for reading-flow-relative spacing, alignment, placement, and borders.
- Keep source/document order semantically meaningful; do not reverse DOM/control order merely to imitate RTL.
- Isolate intrinsic opposite-direction runs such as URLs, email addresses, code, identifiers, phone/account numbers, and mixed-script user content using the target platform's current bidi mechanisms.
- Keep physical left/right when the meaning is genuinely spatial rather than reading-order-relative.
- Mirror directional icons/transitions only when their meaning follows reading direction; do not mirror all icons/assets globally.
- Verify punctuation, parentheses, slashes, neutral characters, selection, copy/paste, and editable mixed-direction content where they matter.

For exact bidi behavior, use current Unicode/W3C/target-platform guidance rather than inventing character/control rules from memory.

## 5. Design for script and content variation

Localization changes more than string length.

When relevant:

- verify the chosen fonts and weights actually cover the active scripts and shaping behavior;
- allow text expansion/contraction, wrapping, different word boundaries, and taller/different glyph metrics;
- avoid fixed-width/fixed-height controls that only fit one source language;
- preserve hierarchy when labels become longer or line-break differently;
- test short, typical, and long localized content in dense controls, tables, navigation, forms, charts, and overlays;
- avoid relying on manual letter spacing or Latin-specific text transforms for scripts where they do not apply;
- let layout reflow/recompose at realistic widths rather than clipping translated text.

[review.md](review.md) owns actual rendered/localized verification and evidence claims.

## 6. Handle locale-sensitive search and sorting deliberately

Search and sort can change meaning across languages/scripts.

- Do not assume Unicode code-point order or a single ASCII-style case fold matches user expectations.
- Use locale-aware collation where user-facing alphabetical order matters.
- Normalize alternate forms only when current product/search requirements justify it; preserve authoritative content rather than rewriting it for display.
- Consider diacritics, script variants, alternate digits, punctuation, whitespace, transliteration, and mixed-script queries only where the product's users/content make them relevant.
- Keep search matching behavior and displayed content conceptually separate.
- If locale-sensitive search behavior is product-critical, verify it against representative data rather than inferring correctness from one language.

Indexing/ranking/backend search architecture belongs to its engineering owner.

## 7. Keep locale-specific product rules authoritative

Regional conventions can affect address, phone, payment, identity, tax, shipping, legal, calendar, work-week, name, or document flows.

Apply these only when the product actually supports that locale/use case.

Do not invent:

- field formats/checksums;
- national identifiers;
- legal requirements;
- payment/banking rules;
- address schemas;
- cultural preferences;
- default locale/country behavior

from design memory. Use current product/domain/legal/platform authority when exact rules matter.

## 8. Use current locale authority for exact behavior

Durable interface principles belong here; exact locale data and algorithms stay with their maintained owners.

```text
Does the decision depend on an exact locale/platform rule?
  ├─ no  -> use the durable interface principles in this reference
  └─ yes -> retrieve current product/platform/Unicode CLDR/Unicode/W3C or other
            authoritative domain data for the actual locale and target
            -> apply that exact requirement
            -> keep Product Interface Builder focused on the interface result
```

Prefer maintained locale-aware APIs/libraries backed by current authoritative data. Do not freeze large locale tables, date/number patterns, plural rules, collation rules, or bidi algorithms into this Skill.

## 9. Load specializations only for the active context

- **Persian or Iranian-local behavior:** also load [persian-rtl.md](persian-rtl.md).
- **Other RTL languages/scripts:** use this general direction/bidi guidance plus current language/locale/platform authority. Do not load Persian/Iran rules merely because the interface is RTL.
- **Other locale-specific behavior:** use current product/domain/platform/locale authority; do not extrapolate a different specialization.

If the task is genuinely single-language/single-locale and none of these dimensions materially affect the decision, do not load this reference.
