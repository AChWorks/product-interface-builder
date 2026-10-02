# Persian / RTL Interface Behavior

Load this reference only when Persian, RTL composition, bidirectional content, or Iranian-local behavior is relevant.

Do not collapse language, direction, locale, calendar, currency, digit style, and regional product conventions into one switch. Evidence for one does not automatically activate the others.

## 1. Resolve the active locale dimensions

Establish only the dimensions the product actually requires:

- interface language/script;
- overall text/layout direction;
- locale/region for formatting and product conventions;
- Persian vs Latin display digits;
- calendar and time-zone behavior;
- currency/unit conventions;
- Iranian-local fields or workflows, if any.

Examples:

- Persian copy can still use Gregorian dates and USD.
- An RTL surface does not automatically need Persian copy.
- A Persian-language product outside Iran does not automatically need Iranian address, banking, calendar, or currency rules.

Current product truth outranks generic Persian-market assumptions.

## 2. Build direction and bidi into structure

Apply RTL at the highest correct surface/root and use logical flow concepts wherever meaning follows reading direction.

Prefer:
- start/end over physical left/right for flow-relative spacing, alignment, borders, radii, and positioning;
- normal document order that works in both directions;
- gap/layout primitives over directional spacing hacks.

Do not reverse rows merely to compensate for LTR-authored components. Fix the component's direction-sensitive semantics instead.

Physical left/right remains valid when the meaning is genuinely spatial rather than reading-order-relative.

### Mixed-direction content

RTL interfaces often contain LTR data such as:

- URLs, paths, commands, and code;
- email addresses;
- IDs/SKUs/version strings;
- phone, card, account, IBAN, OTP, and similar sequences;
- Latin brand or technical names.

Keep the surrounding UI RTL and isolate the intrinsic LTR run with appropriate bidi semantics such as `bdi`, `dir="auto"`, or a scoped LTR input/control.

Do not switch a whole sentence, field group, or form to LTR to repair one token. Check punctuation, parentheses, slashes, hyphens, numbers, selection, and copy/paste around mixed-script content.

Directional icons and spatial transitions should follow actual start/end meaning. Do not mirror every icon or SVG globally.

## 3. Treat Persian text as a real writing system

Use typefaces that genuinely support the required Persian/Arabic glyphs and weights. Confirm the project has the right to ship any commercial Persian font; do not redistribute font files through this Skill.

- Preserve joined-script shaping; arbitrary letter spacing can break or degrade Persian text.
- Give Persian copy enough line height for its glyph shapes and diacritics.
- Avoid synthetic styles when the font does not provide the needed face.
- Verify fallbacks so individual glyphs/words do not silently switch to incompatible type.
- Keep Persian labels readable at the product's real density.
- Let Latin runs coexist intentionally rather than forcing the whole UI into a separate type system.

Preserve meaningful text behavior:

- retain correct ZWNJ (نیم‌فاصله);
- author Persian copy with Persian ی and ک rather than Arabic ي and ك unless source data intentionally preserves another form;
- use Persian punctuation and spacing conventions in Persian prose (for example «گیومه»، «،»، «؛»، «؟»);
- avoid raw-character truncation that can cut joined text badly; prefer layout-aware clamping;
- do not apply Latin-only casing conventions to Persian;
- keep established terminology/glossaries authoritative;
- normalize alternate character/digit forms only where search/validation needs it; do not silently rewrite authoritative display content.

For interface copy, use one consistent product register (formal, neutral conversational, or another established voice). Do not mix formal and colloquial verb forms accidentally across one flow. Prefer familiar product language over literal translation of implementation terms. Keep errors/empty states actionable and technical identifiers untranslated when translation would reduce clarity.

## 4. Separate user-facing formatting from stored values

Display and machine values may legitimately differ.

- Format visible numbers according to the chosen locale/digit style.
- Keep protocol/API/identifier values in the format the system requires.
- When appropriate, accept equivalent Persian/Arabic/Latin digit input and normalize before validation.
- Use tabular numeric styling when aligned comparison benefits from it.

Do not force Persian digits simply because the language is Persian.

### Dates and calendars

Use the calendar the product requires.

When a Persian/Jalali calendar is required:
- use a proven date/calendar implementation rather than hand-written conversion math;
- verify parsing, ranges, leap behavior, labels, week conventions, and time-zone boundaries;
- keep machine timestamps separate from localized display.

When Gregorian or another calendar is required, keep it.

### Currency

Do not infer Toman or Rial from language.

When Iranian money is used:
- label the chosen unit unambiguously;
- never silently mix Rial and Toman;
- keep calculations in the system's canonical unit;
- localize only presentation according to product requirements.

## 5. Recompose components for RTL; do not merely mirror them

Review the actual interaction and reading order of affected components.

### Forms
- keep RTL labels/content flow while isolating LTR-value controls where needed;
- verify prefix/suffix placement;
- keep validation associated with the correct field;
- verify logical focus order;
- verify OTP/multi-cell ordering and paste behavior.

### Navigation and overlays
- place drawers/sheets according to intended start/end semantics;
- verify back/forward, breadcrumb, pagination, tab, and step progression;
- preserve the platform's own navigation conventions when they conflict with naive mirroring.

### Tables and charts
- choose column order from user reading/comparison needs;
- keep numbers and mixed-script cells legible;
- make overflow/filter/sort behavior understandable;
- localize chart axes, legends, tooltips, dates, and numbers as required;
- do not rely on color alone for series/state meaning.

### Responsive behavior
RTL is not an LTR breakpoint with `dir=rtl` added afterward. Re-evaluate alignment, ordering, edge anchoring, truncation, and mixed-script content at narrow and wide sizes.

### Accessibility
Set correct language and direction at the appropriate document/surface level. Verify logical reading/focus order rather than assuming visual reversal produces an accessible order.

## 6. Treat Iranian-local conventions as optional product requirements

Only apply Iran-specific behavior when the product actually needs it, for example:

- Iranian phone formats;
- national identification;
- Sheba/IBAN or local bank-card flows;
- postal/address structures;
- local payment/shipping terminology;
- local working-week expectations.

Do not invent checksums, legal rules, business constraints, or field formats from design memory. Validation rules belong to authoritative product/domain requirements.

## 7. Non-leakage

When Persian/RTL is not activated by the task or project, this reference must not change the English/LTR/global path.

Locale-specific behavior overrides generic design guidance only for the exact surface/context where that language, direction, locale, or regional requirement applies.
