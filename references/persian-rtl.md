# Persian / Iranian Interface Specialization

Load this reference only when **Persian language/script behavior or Iranian-local product behavior** is materially active.

General language/script/direction/locale/formatting rules are owned by [internationalization.md](internationalization.md). RTL alone does **not** activate this specialization: Arabic, Hebrew, Urdu, and other RTL contexts must not inherit Persian orthography, typography, digits, calendar, currency, or Iranian product conventions.

## Contents

[Activation](#1-separate-persian-from-rtl-and-iran) · [Typography](#2-treat-persian-text-as-a-real-writing-system) · [Mixed direction](#3-handle-persian-mixed-direction-content-deliberately) · [Digits/calendar/currency](#4-keep-persian-display-choices-separate-from-iranian-product-rules) · [Components](#5-review-persian-interface-composition) · [Iran](#6-apply-iranian-local-conventions-only-when-required) · [Non-leakage](#7-non-leakage)

## 1. Separate Persian from RTL and Iran

Resolve the active context before applying a Persian-specific rule.

- Persian language/script does not automatically mean Iran as the product region.
- An Iranian product may still use another interface language or calendar/number presentation.
- Persian copy can legitimately use Gregorian dates, Latin digits, non-Iranian currency, or another regional convention when product truth requires it.
- RTL direction alone does not imply Persian language, Persian digits, Jalali calendar, Toman/Rial, Iranian address/banking fields, or Persian typography.
- Another language written with an Arabic-derived script may have different orthography, terminology, punctuation, glyph expectations, and locale conventions.

Use [internationalization.md](internationalization.md) to resolve language, script, direction, locale, numbering, calendar, time zone, currency, and region as separate dimensions.

## 2. Treat Persian text as a real writing system

Use typefaces that genuinely support the required Persian/Arabic-script glyphs and weights. Confirm the project has the right to ship any commercial Persian font; do not redistribute font files through this Skill.

- Preserve joined-script shaping; arbitrary letter spacing can break or degrade Persian text.
- Give Persian copy enough line height for glyph shapes and diacritics.
- Avoid synthetic styles when the font does not provide the needed face.
- Verify fallback behavior so individual glyphs/words do not silently switch to an incompatible visual system.
- Keep Persian labels readable at the product's real density.
- Let Latin runs coexist intentionally rather than forcing the whole surface into a separate type system.

Preserve meaningful Persian text behavior:

- retain correct ZWNJ (نیم‌فاصله) where Persian orthography requires it;
- author Persian copy with Persian ی and ک rather than Arabic ي and ك unless authoritative source data intentionally preserves another form;
- use Persian punctuation/spacing conventions in Persian prose where appropriate, such as «گیومه»، «،»، «؛»، and «؟»;
- avoid raw-character truncation that can cut joined text badly; prefer layout-aware clamping;
- do not apply Latin-only casing conventions to Persian;
- keep established product terminology/glossaries authoritative;
- normalize alternate character/digit forms only where search/validation requirements justify it; do not silently rewrite authoritative display content.

For interface copy, keep one product-appropriate register and avoid accidental mixing of formal and colloquial verb forms in the same flow. Prefer familiar Persian product language over literal translation of implementation terms.

## 3. Handle Persian mixed-direction content deliberately

Persian surfaces frequently contain intrinsically LTR data such as URLs, email addresses, file paths, commands, code, IDs/SKUs, version strings, Latin technical names, phone/account/card/IBAN/OTP sequences, and mixed-script user content.

Use the general bidi structure from [internationalization.md](internationalization.md), then check Persian-specific presentation in context:

- keep surrounding Persian copy RTL while isolating intrinsic LTR runs with the target platform's correct bidi mechanism;
- verify punctuation, parentheses, slashes, hyphens, numbers, cursor/selection behavior, and copy/paste around Persian + Latin runs;
- do not switch a whole sentence/form/group to LTR to repair one token;
- keep technical identifiers untranslated when translation would reduce correctness;
- verify directional arrows/navigation meaning from the actual interaction, not from blanket mirroring.

Do not hard-code Unicode control characters or platform-specific bidi recipes from memory; use current platform/Unicode/W3C authority when exact behavior matters.

## 4. Keep Persian display choices separate from Iranian product rules

### Digits

Do not force Persian digits merely because the language is Persian.

When the product chooses Persian digits:

- localize visible number presentation consistently;
- keep protocol/API/identifier values in the format their owner requires;
- when product requirements allow, accept equivalent Persian/Arabic/Latin digit input through locale-aware normalization before validation rather than visual substitution hacks.

### Dates and calendars

Do not infer Jalali/Solar Hijri solely from Persian language or RTL.

When the product requires a Persian/Jalali calendar:

- use a maintained, proven calendar/date implementation;
- verify parsing, ranges, leap behavior, labels, week conventions, time zones, and boundary cases through current authoritative product/library/platform evidence;
- keep canonical timestamps/data separate from localized display.

When Gregorian or another calendar is required, keep it.

### Currency

Do not infer Toman or Rial from language.

When Iranian money is used:

- label the chosen unit unambiguously;
- never silently mix Rial and Toman;
- keep calculations/accounting in the system's authoritative canonical unit;
- localize presentation only according to current product requirements.

## 5. Review Persian interface composition

Generic RTL layout rules live in [internationalization.md](internationalization.md). For active Persian surfaces, additionally inspect the places where Persian typography and common mixed-direction data make defects easy to miss.

### Forms

- keep Persian labels/content flow coherent while isolating intrinsically LTR-value controls where needed;
- verify prefix/suffix placement and validation association;
- verify logical focus/order and Persian + numeric input behavior;
- verify OTP/multi-cell ordering and paste behavior when the product uses them.

### Navigation and overlays

- preserve platform navigation behavior while checking back/forward, breadcrumb, pagination, tabs, steps, drawers, and sheets in the actual Persian direction;
- do not mirror platform/system conventions merely because the content is Persian.

### Tables, charts, and dense data

- choose column order from the user's comparison task;
- keep Persian labels, numbers, and mixed-script cells legible;
- localize axes, legends, tooltips, dates, and numbers only to the dimensions the product actually selected.

### Responsive/accessibility

- test Persian strings at narrow and wide sizes instead of assuming the LTR breakpoint still works;
- set correct language/direction metadata at the appropriate surface;
- verify logical reading/focus order rather than treating visual mirroring as proof.

Rendered verification remains owned by [review.md](review.md).

## 6. Apply Iranian-local conventions only when required

Only apply Iran-specific product behavior when current product/domain truth requires it, for example:

- Iranian phone-number expectations;
- national identification fields;
- Sheba/IBAN or local bank-card/payment flows;
- Iranian postal/address structures;
- local shipping/payment terminology;
- local working-week/holiday expectations.

Do not invent checksums, legal rules, field formats, banking rules, address schemas, or validation behavior from design memory. Retrieve the current authoritative product/domain/legal/platform source when exact rules matter.

## 7. Non-leakage

When Persian language/script and Iranian-local behavior are both irrelevant, this reference must not affect the interface.

When Persian is active without Iran-specific product requirements, apply Persian language/script rules only. When Iran-specific behavior is active without Persian copy, apply only the current Iranian product/domain requirement.

Persian/Iran rules never become defaults for Arabic, Hebrew, Urdu, other RTL languages, or global RTL behavior.
