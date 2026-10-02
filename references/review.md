# Interface Review Evidence Contract

Use for explicit review requests and for proportional self-review of material visual work.

## Evidence levels

1. **Product/design truth** — current requirements, tokens, components, copy rules, platform and locale constraints.
2. **Static implementation evidence** — source, styles, component structure, state handling.
3. **Rendered evidence** — running UI, screenshots, visual-regression artifacts, interaction behavior on relevant viewports/devices.

Rendered evidence is stronger for visual correctness. Static inspection can identify likely problems but must not be presented as proof that layout, typography, overflow, responsive behavior, or motion renders correctly.

## Review behavior

- Prioritize findings by actual user impact and evidence.
- Separate defects from subjective alternatives.
- Preserve intentional product-specific choices unless they conflict with requirements or materially harm usability/accessibility.
- Review only concerns relevant to the changed surface; avoid checklist dumping.
- When rendering is available, inspect representative states and sizes rather than only the happy-path screenshot.
- When rendering is unavailable, state that visual conclusions are static/inferred.
- Do not claim a test, device, browser, assistive technology, or interaction was exercised unless it actually was.

Detailed visual, responsive, accessibility, interaction, motion, and performance review rules remain owned by this reference as they evolve; do not duplicate them into provider adapters.
