# Collaboration and Concurrency Interface Guidance

Use this reference when multiple people/sessions/processes can act on shared product state and users must understand presence, ownership, saving/sync, stale state, locks, history, permissions, conflicts, or overwrites.

This file owns the **user-facing shared-state and conflict contract**. It does not own database transactions, CRDT/OT algorithms, sync protocols, locking implementation, authorization policy, storage/version architecture, or backend concurrency guarantees.

## Contents

[State model](#1-make-shared-state-legible-without-overclaiming) · [Presence/ownership](#2-separate-presence-selection-ownership-and-locks) · [Save/sync](#3-distinguish-local-saved-synced-and-stale-state) · [Conflicts](#4-make-conflict-and-overwrite-choices-understandable) · [History](#5-use-history-and-recovery-to-reduce-collaboration-risk) · [Permissions](#6-handle-permission-and-ownership-changes-during-a-session) · [Attention](#7-keep-collaboration-signals-proportional) · [Boundaries](#8-route-backend-concurrency-to-its-owner)

## 1. Make shared state legible without overclaiming

Only expose collaboration state the product can actually know.

When material, distinguish:

- local unsaved/draft state;
- saved to the current client/session;
- accepted by the shared system;
- synchronized/current according to the product's authoritative state model;
- stale/outdated relative to a newer shared version;
- pending/failed sync;
- locked/read-only/permission-limited state;
- conflict requiring user/system resolution.

Do not use “saved,” “synced,” “live,” “up to date,” or “no conflicts” unless the underlying product state supports that claim.

Avoid hiding a material sync failure behind a generic success indicator.

## 2. Separate presence, selection, ownership, and locks

These concepts can look similar but mean different things.

- **Presence** means another participant/session is currently known to be active; it does not automatically mean they are viewing or editing the same object.
- **Selection/cursor/focus** identifies where another participant is interacting only if the product actually tracks that scope.
- **Ownership/assignment** is a durable product role or responsibility, not the same as current presence.
- **Lock** means editing/action is restricted according to a defined product mechanism; do not infer a lock from another person's presence.
- **Permission** defines what an actor is allowed to do and may change independently of presence/ownership.

Use stable labels/avatars/colors only when they help distinguish participants without becoming the sole carrier of identity/state.

If identity attribution is uncertain or privacy-sensitive, follow authoritative product/privacy rules rather than fabricating participant detail.

## 3. Distinguish local, saved, synced, and stale state

Collaborative products often fail users when a single “saved” label hides several states.

Use the smallest state vocabulary the product can support truthfully.

When the distinction matters:

- show pending versus completed persistence/sync;
- make retry/recovery available for failed saves when supported;
- preserve user work across transient sync failure when product architecture permits;
- tell users when displayed data became stale enough that acting on it may cause harm;
- refresh/reconcile automatically only when doing so will not silently destroy local context;
- if a remote update changes the meaning of the current action, surface that before commitment.

Do not constantly interrupt users for harmless remote updates. Prioritize changes that materially affect the current task or decision.

## 4. Make conflict and overwrite choices understandable

A conflict UI should explain the **decision**, not expose the backend merge algorithm.

When multiple valid versions cannot be reconciled invisibly and safely:

- identify the affected object/field/scope;
- show enough difference/context for the user to choose;
- preserve the user's current work until a resolution is accepted where practical;
- distinguish “keep mine,” “use latest/theirs,” “merge,” “duplicate/copy,” and “cancel” by actual consequence;
- explain whether choosing one version discards another and whether recovery/history remains available;
- avoid defaulting to destructive overwrite merely because one version is newer.

If the system can auto-merge safely, do not create unnecessary conflict ceremony. If it cannot, do not pretend a merge succeeded.

For high-consequence overwrites, [trust-agency.md](trust-agency.md) owns transparency/confirmation/recovery expectations.

## 5. Use history and recovery to reduce collaboration risk

History/version UI is useful when users need to understand or recover shared changes.

When supported by product truth:

- show authoritative actor/time/version metadata only at the precision actually known;
- let users inspect a prior state before restoring when consequences warrant it;
- distinguish restoring/copying/reverting from merely viewing history;
- make clear whether a restore creates a new version or rewrites history;
- preserve a path back from destructive resolution when the system supports it.

Do not invent authorship, timestamps, change summaries, or audit guarantees from the interface.

Exact retention/audit requirements belong to product/policy/legal owners.

## 6. Handle permission and ownership changes during a session

Shared state can become invalid while a surface remains open.

If a user's permission/role/ownership changes:

- reflect the new actionable state without making stale controls appear available;
- preserve unsent local work when safe and product rules allow;
- explain why an action is now blocked and the useful next step;
- distinguish temporary sync failure from a real permission loss;
- avoid repeatedly retrying an unauthorized action;
- if an operation was already in flight, report the actual final outcome rather than assuming prior authorization guarantees success.

Permission policy/enforcement stays with the authoritative product/security owner. [trust-agency.md](trust-agency.md) owns user-facing permission/blocked-state clarity.

## 7. Keep collaboration signals proportional

Presence, cursors, change indicators, toasts, activity feeds, and live updates compete for attention.

Use them only where they help the user coordinate or avoid conflict.

- Prefer quiet ambient presence for low-consequence awareness.
- Escalate to explicit notice when another change invalidates the current task/decision.
- Avoid toast storms for routine live updates.
- Preserve the user's reading/editing position when remote data changes where possible.
- Do not move controls/content under the pointer/focus merely to show low-value live activity.
- Keep color-only identity/state cues backed by text/shape/position where needed.
- Treat “someone is typing/editing” as transient state; do not let it become a permanent lock unless the product actually locks.

## 8. Route backend concurrency to its owner

Product Interface Builder decides what users need to understand/control about shared state. The implementation owner decides how shared state is made correct.

Do not prescribe:

- CRDT versus OT;
- pessimistic versus optimistic locking architecture;
- database isolation/transaction levels;
- message queues/event sourcing;
- sync topology;
- retry/idempotency algorithms;
- version storage;
- authorization enforcement.

When backend guarantees are unknown but materially change the interface, return the required product/engineering fact as an open assumption rather than designing a false shared-state model.
