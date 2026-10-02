# Platform Routing Contract

Load only the section matching the known target platform. Do not guess a platform merely because a visual pattern resembles one.

## Shared rule

Preserve product identity across platforms while respecting the target platform's interaction model, navigation expectations, input methods, density, safe areas, accessibility APIs, window/viewport behavior, and lifecycle constraints.

Do not force web conventions onto native UI or native conventions onto the web.

## Web

Use browser-native semantics and navigation behavior where possible. Account for keyboard and pointer use, focus, zoom, responsive viewport ranges, browser history/deep links, content reflow, safe overflow, and semantic HTML. Framework-specific implementation details should follow the project's actual stack rather than a preferred default.

## Mobile / native

Account for touch ergonomics, system navigation/back behavior, safe areas, software keyboard effects, platform text/input controls, accessibility semantics, gesture alternatives, orientation/size-class changes, and native state/lifecycle behavior. Avoid web-shaped navigation or hover-dependent interactions.

When iOS/Android behavior materially differs, follow the actual target platform rather than inventing a hybrid convention.

## Desktop

Account for resizable windows, dense information use, keyboard shortcuts, pointer precision, focus traversal, menus/context actions, multi-window expectations, selection, and platform-native window/chrome behavior where applicable.

For cross-platform products, keep shared product semantics consistent while allowing platform-specific composition and interaction details.
