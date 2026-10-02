# Adaptive Contexts

Use this reference when window size, multi-window state, fold/posture, restoration, available space, or active input method materially changes how the interface should compose or behave.

This file owns **user-facing adaptation and context-preservation intent**. [platforms.md](platforms.md) owns target-platform conventions; exact version-sensitive windowing, posture, input, and lifecycle behavior stays with current platform authority.

## Contents

[Activation](#1-activate-only-when-context-can-change-the-experience) · [Available space](#2-adapt-to-available-space-not-device-labels) · [Context preservation](#3-preserve-task-context-across-change) · [Input](#4-handle-input-capability-transitions) · [Posture/windowing](#5-treat-window-and-posture-as-current-state) · [Continuity](#6-keep-navigation-and-state-continuous) · [Authority](#7-route-exact-platform-behavior-to-current-authority)

## 1. Activate only when context can change the experience

Do not load adaptive guidance for a fixed-context interface merely because responsive design exists.

Use it when one or more of these can materially change during use:

- application/window size or orientation;
- split view, multi-window, stage/window management, or external display;
- fold/posture/hinge geometry;
- restoration after resize/reopen/process interruption;
- available pointer, touch, keyboard, pen, gamepad/remote, or assistive input;
- density/navigation structure that must recompose rather than simply scale.

Ordinary breakpoint styling remains local design/platform work unless the context change can alter task structure, control placement, continuity, or input assumptions.

## 2. Adapt to available space, not device labels

Prefer actual constraints over device stereotypes.

- Base layout decisions on usable space, content need, input capability, and product task rather than labels such as “tablet” or “desktop.”
- Recompose when hierarchy or workflow benefits: columns may become panels, secondary navigation may become persistent, or supporting content may move without changing its meaning.
- Keep the primary task and important state understandable across compact and expanded layouts.
- Do not assume a large physical screen means a large application window.
- Do not assume foldables or tablets always use one posture, orientation, or navigation arrangement.
- Avoid arbitrary breakpoints that merely reproduce a device catalog when intrinsic layout or content thresholds are clearer.

When the project already has authoritative layout/container thresholds, preserve them unless the accepted work changes them.

## 3. Preserve task context across change

A context transition should not make users restart ordinary work.

Where product/platform behavior allows:

- preserve current object, selection, draft, filters, scroll/reading position, and navigation state when those remain meaningful;
- keep focused/active work visible or restore focus deliberately rather than letting it jump unpredictably;
- avoid dismissing a form, dialog, editor, or in-progress task merely because the window resized;
- if a layout mode cannot preserve an exact presentation, preserve the underlying task and make the changed presentation understandable;
- do not duplicate or silently discard user input while moving content between regions;
- distinguish intentional navigation from responsive relocation.

If preserving state would be unsafe or semantically invalid, surface the changed state and recovery path rather than pretending continuity.

## 4. Handle input capability transitions

Input method can change while the product remains open.

Design the interaction contract so that:

- required actions are not available only through hover, precision pointer, gesture, or keyboard shortcut unless the product explicitly targets that input;
- pointer hover may enrich but must not be the sole carrier of required information when touch/keyboard may also be active;
- touch-friendly target size/spacing can coexist with keyboard and pointer efficiency where multiple inputs are expected;
- keyboard focus/order remains logical when layout regions move or collapse;
- drag/drop has an equivalent path when another supported input cannot perform it;
- pen or gamepad/remote behavior is added only when the actual product/platform supports and benefits from it;
- input hints/affordances reflect the active capability when the platform reliably exposes it rather than hard-coding a device assumption.

Do not infer the user's current input solely from viewport size.

## 5. Treat window and posture as current state

When windowing or fold/posture materially affects the interface:

- treat the current usable region as input to composition, not as a permanent product mode;
- keep critical controls/content away from unusable/occluded regions when current platform geometry exposes them;
- allow secondary panes/toolbars to appear or collapse according to available space without changing product semantics;
- avoid placing one indispensable control across a hinge/seam or outside the currently usable interaction region;
- preserve a sensible minimum viable layout instead of squeezing a wide composition until it becomes unusable.

Do not encode platform-specific posture enums, window APIs, inset rules, or lifecycle callbacks here. Use the target platform's current official guidance when exact behavior matters.

## 6. Keep navigation and state continuous

Adaptive recomposition may change presentation without changing navigation meaning.

- Do not create duplicate navigation histories when the same destination moves between sidebar, tab, pane, or menu.
- Preserve destination identity and back/return expectations across compact/expanded transitions.
- Keep master-detail or multi-pane selection coherent when panes collapse/expand.
- When restoring a prior session/window, restore only state the product can still validate; stale or permission-changed state should use the applicable shared-state/trust guidance.
- Multi-window instances may legitimately show different objects or states; do not assume every window must mirror another unless product truth requires it.

When simultaneous windows/sessions act on shared state, also use [collaboration-concurrency.md](collaboration-concurrency.md).

## 7. Route exact platform behavior to current authority

Durable adaptive principles belong here. Exact behavior for:

- iOS/iPadOS/visionOS windowing and scene lifecycle;
- Android window size classes, fold/posture, predictive/back/lifecycle behavior;
- desktop window restoration, scaling, multi-monitor behavior;
- browser viewport, viewport units, resize, input media queries, and related APIs

must come from current official platform/browser authority when it materially affects implementation.

Product Interface Builder defines the intended adaptive experience. The platform/implementation owner chooses the supported mechanism and validates it on the actual target.
