# Persian / RTL Activation Contract

Load this reference only when the product actually uses Persian, RTL layout, bidirectional content, or Iranian-local conventions.

Persian language, RTL direction, and Iranian market conventions are related but not identical. Infer none of them solely from another.

## Activation rules

- Use the product's actual language/script/locale requirements as evidence.
- Apply RTL behavior to the relevant document or surface, not as a cosmetic mirror after an LTR design is finished.
- Preserve LTR islands for identifiers, URLs, code, email, phone/card/IBAN-like values, or other content whose intrinsic direction is LTR.
- Prefer logical start/end layout semantics so components can behave correctly across directions.
- Treat typography, line height, shaping/joining, mixed-script text, digits, punctuation, truncation, and icon direction as script-aware concerns.
- Keep display formatting separate from machine/API values when digit or locale formatting differs.
- Apply Jalali calendars, Toman/Rial conventions, Iranian identity/address/payment patterns, weekend rules, or similar local assumptions only when the product requires them.
- Keep locale-specific UI copy consistent with the product's chosen register and vocabulary.
- Directional motion and navigation cues should follow the interface direction; non-directional symbols should not be mirrored without reason.
- Review tables, forms, charts, navigation, drawers, focus order, responsive behavior, and assistive labels under the actual RTL composition.

When Persian/RTL is not relevant, this reference must not change the global/LTR path.
