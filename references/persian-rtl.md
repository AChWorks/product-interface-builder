# Persian / RTL Interface Behavior

Load this reference only when the product actually uses Persian, RTL composition, bidirectional content, or Iranian-local conventions.

Persian language, RTL direction, locale, calendar, currency, and Iranian market conventions are separate dimensions. Evidence for one does not automatically activate the others.

## 1. Determine what actually applies

Resolve, from product truth or the request:

- interface language and script;
- direction of the overall surface;
- locale/region used for numbers, dates, currency, addresses, and validation;
- whether users expect Persian or Latin digits;
- calendar/time-zone requirements;
- whether Iranian-local fields or conventions are part of the product.

If only RTL layout is required, do not invent Persian copy or Iranian business rules. If Persian copy is required for a non-Iranian audience, do not assume Iran-specific currency/calendar/forms.

## 2. Direction is structural

Set direction at the highest correct surface/root rather than manually reversing every child.

Prefer logical concepts:
- start/end rather than left/right for flow-relative spacing, inset, border, radius, and alignment;
- document-order semantics that remain correct in both directions;
- gap/layout primitives rather than directional margin hacks.

Do not add row reversal merely to compensate for a component that was authored with physical LTR assumptions. Fix the component's direction-sensitive semantics instead.

Physical left/right remains valid when the meaning is genuinely physical rather than flow-relative, such as a fixed map control or visual coordinate.

## 3. Handle bidirectional content explicitly

An RTL interface commonly contains intrinsically LTR runs:

- URLs and file paths;
- code/commands;
- email addresses;
- product IDs/SKUs;
- phone/card/account-like sequences;
- version strings;
- Latin brand names or technical identifiers.

Keep the surrounding UI RTL while isolating those runs with appropriate bidi semantics such as `bdi`, `dir="auto"`, or a scoped LTR control when implementation permits.

Do not switch an entire Persian sentence or form to LTR to fix one token. Test punctuation, parentheses, slashes, hyphens, numbers, and copy/paste around mixed-script content.

## 4. Use Persian-capable typography

Choose fonts that actually support the required Arabic/Persian glyphs and weights.

- Preserve joined-script shaping; arbitrary positive/negative letter spacing can damage Persian/Arabic text.
- Give Persian body copy enough line height for ascenders, descenders, diacritics, and dense dot patterns.
- Avoid synthetic bold/italic when the selected family does not provide a suitable face.
- Verify fallback behavior so a missing glyph does not silently switch part of a word to an incompatible font.
- Keep long Persian copy and UI labels legible at the product's actual density.
- Mixed Latin/Persian typography should look intentional without forcing all Latin runs into a different visual system.

Commercial fonts may be recommended only when the project has the needed license. Do not redistribute font files through this Skill.

## 5. Preserve Persian text semantics

Persian copy may contain ZWNJ (نیم‌فاصله) and locale-specific punctuation. Treat them as real text semantics.

- Preserve ZWNJ in rendered copy when it is linguistically correct.
- Avoid string truncation that cuts joined-script text by raw character count; prefer layout-aware clamping/truncation.
- Normalize user input only for a specific search/validation need, and keep display text separate from normalized comparison values.
- Do not apply casing transformations that are meaningful only for Latin text to Persian labels.

## 6. Separate display formatting from machine values

User-facing formatting and stored/transmitted values serve different purposes.

- Format visible numbers for the product's chosen locale and digit style.
- Keep API payloads, identifiers, URLs, and protocol-defined numeric strings in the machine format the system expects.
- Accept equivalent Persian/Arabic/Latin digits in user input when the product reasonably should, then normalize before validation.
- Use tabular numeric styling when aligned comparison benefits from it.

Do not force Persian digits merely because the surrounding language is Persian; some products deliberately use Latin digits. Follow current product truth.

## 7. Dates, calendars, time zones, and money are conditional

### Dates and calendars

Use the calendar the product requires. Persian-language UI does not by itself prove that the Jalali/Persian calendar is desired.

When Jalali/Persian calendar behavior is required:
- use a proven calendar/date implementation rather than hand-authored conversion math;
- verify month/day names, week-start rules, leap-year behavior, parsing, ranges, and time-zone boundaries;
- keep machine timestamps separate from localized display.

When Gregorian or another calendar is required, use it even inside an RTL/Persian surface.

### Currency

Do not assume Toman or Rial from language alone.

When the product uses Iranian money:
- label the chosen unit unambiguously;
- never silently mix Rial and Toman;
- keep calculations in the system's canonical unit and localize only display;
- follow product truth for separators, digit style, decimals, and currency wording.

## 8. Directional icons and motion

Mirror or redirect only symbols whose meaning depends on reading/navigation direction.

Commonly direction-sensitive:
- previous/next or back/forward chevrons when they represent flow;
- start/end disclosure or pagination indicators;
- directional enter/exit movement tied to start/end edges.

Commonly not direction-sensitive:
- search, delete, settings, download/upload semantics;
- media play direction when platform convention keeps it fixed;
- logos and branded marks;
- arbitrary illustration details.

Prefer logical start/end motion. Do not mirror all SVGs globally.

## 9. Persian UI copy

Use the product's chosen register: formal, neutral conversational, or another documented voice.

- Keep action labels concrete and consistent through the flow.
- Prefer familiar product language over literal translation of English implementation terms.
- Keep error and empty states actionable.
- Preserve English technical identifiers when translation would reduce clarity.
- Avoid mixing formal and colloquial register accidentally across neighboring controls.

If the project already has a glossary or established vocabulary, it outranks generic wording advice.

## 10. Iranian-local product patterns are opt-in

Only load or design these when the product actually needs them, for example:

- Iranian mobile/telephone formats;
- national identification fields;
- Sheba/IBAN or bank-card flows;
- Iranian postal/address structures;
- local payment/shipping terminology;
- local working-week expectations.

Validation rules belong to the product/domain implementation and must be sourced from current authoritative requirements. Do not invent checksums, legal requirements, or business rules from design memory.

## 11. Review real RTL composition

When relevant, inspect:

### Forms
- RTL labels with correctly isolated LTR-value controls;
- prefix/suffix placement;
- validation messages and focus order;
- OTP/multi-cell input order and paste behavior.

### Navigation and drawers
- start/end edge behavior;
- back/forward semantics;
- breadcrumb and pagination order;
- tab/step progression.

### Tables and data
- column reading order;
- numeric alignment;
- mixed-script cells;
- overflow and horizontal scrolling;
- sort/filter affordances.

### Charts
- axis/legend/tooltip text direction;
- number/date formatting;
- series order only when direction changes its semantic reading;
- labels that remain understandable without color alone.

### Responsive
Do not assume an LTR breakpoint composition will become correct by mirroring. Re-evaluate alignment, control order, edge anchoring, truncation, and mixed-script content at narrow sizes.

### Accessibility
Use the correct document/surface language and direction so assistive technology receives the intended reading context. Verify logical focus/reading order rather than relying on visual reversal.

## 12. Non-leakage invariant

When Persian/RTL is not activated by the task or project, this reference changes nothing about the English/LTR/global path.

Locale-specific guidance may override a generic design default only for the surface/context where that locale/script requirement actually applies.
