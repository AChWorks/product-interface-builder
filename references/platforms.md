# Platform Routing

Load only the section matching the known target platform. Determine platform from the request, repository/artifact evidence, or current product truth; do not guess from visual appearance.

Preserve product identity across platforms while respecting each platform's interaction model, navigation expectations, input methods, accessibility model, layout/window behavior, and lifecycle constraints.

## Contents

[Shared rules](#1-shared-cross-platform-rules) · [Web](#2-web) · [Mobile/native](#3-mobile--native) · [Desktop](#4-desktop) · [Multiple targets](#5-multiple-targets) · [Unknown target](#6-unknown-target)

## 1. Shared cross-platform rules

Across web, mobile/native, and desktop:

- keep core product concepts and terminology stable unless platform convention requires a different expression;
- reuse brand/design tokens only where they remain legible and native to the target;
- adapt composition, density, navigation, input, and feedback instead of blindly scaling the same screen;
- distinguish pointer, touch, keyboard, gamepad/remote, pen, and assistive input where relevant;
- respect safe areas, text scaling, localization expansion, high contrast, reduced motion, and platform accessibility settings when supported;
- prefer the project's existing platform component system before adding another UI framework.

A cross-platform product may share semantics without sharing identical component markup.

## 2. Web

Use browser-native behavior as a strength.

### Semantics and navigation
- Use actual navigation semantics for navigation and actual controls for actions.
- Preserve standard browser behaviors such as link opening, history, refresh, Back/Forward, selection, copy/paste, and zoom.
- Deep-link meaningful navigational state when the product needs share/refresh/history continuity.
- Prefer semantic document/control structure before ARIA-like augmentation.

### Input
Support keyboard as well as pointer where the flow permits it. Hover may enrich but must not be the sole way to discover or operate required actions.

Forms should cooperate with browser autofill, password managers, input modes, validation feedback, and paste rather than fighting them. Do not disable browser zoom to hide layout/input problems. On mobile Safari, size text inputs so focusing them does not create avoidable viewport zoom/readability problems; use current Safari/platform guidance when an exact threshold materially affects implementation.

### Layout
Design for the real viewport range the product supports:
- narrow mobile web;
- common laptop/desktop sizes;
- wider windows where layout otherwise becomes sparse or over-stretched.

Prefer intrinsic responsive layout over measuring everything in script. Account for content reflow, browser zoom, dynamic viewport units, scrollbars, and safe-area insets where they matter.

### Feedback and async behavior
Keep loading, optimistic, saved/unsaved, error, retry, and destructive state visible. Preserve focus/reading continuity when content changes asynchronously.

Framework-specific behavior follows the actual stack; this Skill does not choose React/Next/Vue/etc. by default.

## 3. Mobile / native

Resolve the actual platform when platform-specific behavior matters.

### Touch and reach
- Give important controls a comfortable hit target and spacing.
- Do not depend on hover.
- Avoid gesture-only critical actions unless a clear accessible alternative exists.
- Consider one-handed reach and bottom/top system areas when relevant.

### System navigation and presentation
Respect the target platform's expectations for:
- back/navigation behavior;
- tab/navigation hierarchy;
- sheets/dialogs/full-screen transitions;
- system bars and safe areas;
- keyboard dismissal and focus;
- app lifecycle/restoration.

Do not reproduce browser chrome, web history patterns, or desktop menu behavior merely because the product also has a web app.

### Text and accessibility
Support the platform's user text-size/accessibility settings when feasible. Layout must tolerate larger text and translated strings without hiding primary actions.

Use native accessibility semantics/labels through the actual UI framework.

### Software keyboard and forms
Account for keyboard appearance, viewport reduction, field scrolling, submit/next actions, autofill/OTP/password-manager integration, and content that must remain visible while typing.

### iOS

When the target is iOS/iPadOS and the product expects native behavior:

- keep controls and content clear of safe-area/system UI;
- preserve system back/navigation gestures and use platform navigation patterns rather than web-style history chrome;
- support Dynamic Type/text scaling without hiding primary actions;
- prefer semantic system colors/materials and established native controls when they satisfy the product need;
- keep interactive targets comfortably usable; use current Apple platform guidance when an exact target-size requirement matters;
- use the platform's established icon/navigation language when product identity does not require a justified exception;
- honor Reduce Motion and avoid custom transitions that fight the navigation model.

### Android

When the target is Android and the product expects native behavior:

- respect system Back/predictive-back behavior and edge-to-edge/window insets;
- adapt top-level navigation to available window size rather than shipping one phone pattern unchanged to larger screens;
- support scalable text and system accessibility/font settings;
- prefer semantic theme roles and established Material/native controls when they fit the product;
- keep touch targets comfortably usable; use current Android/Material guidance when an exact target-size requirement matters;
- preserve IME/keyboard visibility and inset behavior during forms;
- honor the system's reduced/removed-animation preference.

### Platform distinction

If iOS and Android conventions materially differ, follow the actual target. A shared product convention is valid only when it preserves the important navigation, input, accessibility, and lifecycle expectations of each platform. Do not invent a pseudo-native hybrid by default.

## 4. Desktop

Desktop interfaces should use the capabilities of windows, keyboard, pointer precision, and dense workflows when the product benefits.

Native desktop targets are not interchangeable. When macOS, Windows, Linux/desktop-environment, or a cross-platform desktop framework materially changes menu placement, window chrome, standard commands/shortcuts, document/file behavior, accessibility, or lifecycle expectations, follow the actual target's current platform/framework authority instead of treating generic desktop guidance as exact behavior.

### Application windows and layout
- Handle resize rather than assuming one fixed canvas.
- Define sensible minimum/maximum content widths and panel behavior.
- Preserve state across resize/reopen when the application expects it.
- Account for multiple monitors, scaling, and high-density displays where relevant.

### Keyboard and commands
Power-user workflows may justify shortcuts, command palettes, menu items, multi-select, and context actions. Provide discoverability for important shortcuts and avoid conflicting with platform/system conventions.

### Pointer and selection
Desktop can support precision hover, drag/drop, selection ranges, resize handles, context menus, and dense tables, but critical tasks should remain understandable without hidden hover-only meaning.

### Menus, dialogs, and window chrome
Use platform-native conventions when the desktop framework exposes them and the product is expected to feel native. A cross-platform desktop shell may deliberately use product-specific chrome, but must still handle window controls, focus, modality, and system shortcuts correctly.

## 5. Multiple targets

When the same feature is requested for several platforms:

1. define the shared product intent and information;
2. identify platform-specific interaction/layout differences;
3. reuse visual tokens only where they survive platform constraints;
4. implement/test each target using its own native conventions;
5. avoid making one platform the hidden source of truth for all presentation decisions.

## 6. Unknown target

If platform evidence is missing and platform choice materially changes the answer, state the unresolved assumption or ask only when the choice cannot be made safely.

If platform choice does not materially affect the requested design reasoning, stay at the shared cross-platform layer and avoid invented implementation details.
