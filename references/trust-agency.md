# Trust, Privacy Presentation, Consent, and User Agency

Use this reference when the interface materially shapes permission, consent, privacy understanding, destructive/high-consequence choices, revocation/cancellation, blocked states, or another decision where visual/interaction design can impair informed user control.

This file owns the **user-facing presentation of understanding and agency**. It does not own security architecture, privacy policy/enforcement, data governance, legal interpretation, billing/business rules, or regulatory compliance.

## Contents

[Ownership](#1-keep-policy-and-presentation-separate) · [Permissions](#2-request-permission-when-context-can-explain-it) · [Consent/control](#3-make-meaningful-choice-and-reversal-legible) · [Consequences](#4-expose-material-consequences-before-commitment) · [Anti-deception](#5-do-not-obscure-or-subvert-user-choice) · [Blocked states](#6-explain-blocked-disabled-and-permission-states) · [Privacy copy](#7-write-privacy-facing-copy-for-the-decision) · [Accessibility](#8-route-exact-accessibility-and-legal-rules-to-current-authority) · [Escalation](#9-return-policy-questions-to-the-right-owner)

## 1. Keep policy and presentation separate

Product Interface Builder may decide how an already-authorized policy/capability is explained and controlled in the interface. It must not decide what data the product is legally allowed to collect, whether processing is lawful, what security control is sufficient, or what a regulatory text requires.

| Question | Owner |
|---|---|
| What must the user understand/see/control in this interface? | Product Interface Builder when policy/product truth is known |
| What data is collected/shared/retained and why? | product/privacy/data owner |
| What authorization/security mechanism enforces the choice? | security/platform/backend owner |
| What consent/legal basis or disclosure is legally sufficient? | current legal/policy authority |
| What exact accessibility criterion applies? | current authoritative accessibility standard/platform guidance |

When the underlying policy is unresolved, do not hide that uncertainty behind polished consent copy.

## 2. Request permission when context can explain it

Permission prompts should arrive when the user can understand the relationship between the requested capability and the action they are trying to complete.

- Explain the user-relevant purpose before or around a system permission request when the platform/product needs explanation.
- Avoid asking for broad permissions earlier than the task requires merely because setup is convenient.
- Make the requested scope understandable at the level the product can truthfully support.
- If a permission is optional, do not imply the product is unusable when only one feature is affected.
- If denial changes behavior, explain the affected capability and the available next step without repeatedly pressuring the user.
- If the platform owns the final permission dialog, design the surrounding product context rather than attempting to imitate or replace protected system behavior.

Use current platform documentation for exact permission APIs, prompt behavior, and settings routes.

## 3. Make meaningful choice and reversal legible

When users have a real choice:

- name choices by their consequence rather than by an internal policy term alone;
- make accept/decline, enable/disable, subscribe/cancel, share/not-share, or equivalent consequence paths discoverable in proportion to their importance;
- do not use visual hierarchy, repeated prompts, confusing toggles, or extra friction primarily to make the product-preferred choice easier than the user's alternative;
- make defaults and preselection truthful and appropriate to current policy/authority; do not invent a consent default from design preference;
- provide a discoverable revoke/opt-out/change path when the product and applicable policy support one;
- after a change, show the resulting state clearly enough that users can tell which choice is active.

A commercial or engagement objective does not authorize an interface to obscure a meaningful alternative.

## 4. Expose material consequences before commitment

For destructive, financial, privacy-sensitive, irreversible, or otherwise high-consequence actions:

- identify the actual object/scope affected;
- distinguish preview/review from final commitment when that reduces meaningful risk;
- disclose material consequences before the committing action, not only afterward;
- use confirmation when the consequence/error cost warrants it rather than for every ordinary action;
- prefer undo/recovery when the product can safely provide it;
- preserve a clear cancel/escape route before commitment;
- after completion, communicate what happened and any available recovery/next action.

[human-factors.md](human-factors.md) owns cognitive/error-tolerance reasoning. This reference adds the transparency/agency constraint.

## 5. Do not obscure or subvert user choice

Do not design or endorse interface behavior whose primary effect is to make users take a materially different action from the one they would understand themselves to be choosing.

Watch for interface-level risks such as:

- important terms, fees, recurring behavior, privacy consequences, or scope disclosed only after commitment;
- advertising/promotion made to look like independent or required content;
- a cancellation, refusal, deletion, or privacy path made intentionally difficult to find or complete;
- false scarcity/countdowns, fabricated urgency, or other product claims unsupported by authoritative truth;
- confusing double negatives or toggle labels where users cannot predict what “on/off” means;
- repeated nagging after a user has made a valid choice, unless a real state/policy change creates a new decision;
- visual interference that makes one meaningful option appear unavailable when it is actually allowed;
- adding optional items/services/data sharing without a clear user action that authorizes them.

Do not label an interface “compliant” or “illegal” from these design principles. When legality matters, retrieve the current jurisdiction-specific authority and return unresolved interpretation to the responsible owner.

## 6. Explain blocked, disabled, and permission states

A blocked or disabled interface should communicate enough truth for the user to decide what to do next.

When material, distinguish:

- unavailable because prerequisite data/task state is missing;
- unavailable because the user lacks permission/role;
- temporarily unavailable because the system is processing/offline/failing;
- unavailable because product/policy prohibits the action;
- disabled only until the user satisfies a visible input requirement.

Prefer explaining the reason and recovery path near the blocked action when users are likely to encounter it. Do not use a disabled control as the only explanation of a policy/permission decision.

Never make a control look disabled merely to discourage an otherwise permitted choice.

## 7. Write privacy-facing copy for the decision

Privacy/disclosure copy should help users understand the current choice, not reproduce an entire policy document inside the interface.

When known and material, communicate the smallest truthful set such as:

- what capability/data the current choice concerns;
- who/what receives or uses it at the level the product can truthfully state;
- why the product is asking now;
- what enabling/refusing changes for the user's experience;
- whether the choice can be changed later and where, when that is actually supported.

Do not invent retention periods, recipients, guarantees, anonymity claims, security claims, or legal bases.

Progressive disclosure may move secondary detail behind a clear route; it must not hide information that materially changes the immediate choice.

## 8. Route exact accessibility and legal rules to current authority

Some trust/agency surfaces also have exact accessibility or regulatory requirements. Keep the durable interface intent here and retrieve current official rules when material.

Examples include:

- repeated/consistent help placement;
- avoiding unnecessary repeated entry in a process;
- accessible authentication behavior;
- consent/cookie/privacy requirements;
- cancellation/subscription rules;
- financial/destructive confirmation requirements.

Do not copy whole standards or jurisdiction-specific rule sets into this Skill. The control plane's mandatory-constraint precedence applies when current authority establishes an exact requirement.

## 9. Return policy questions to the right owner

```text
Is the user-facing consequence/policy already authoritative and clear?
  ├─ yes -> design transparent understanding + meaningful control
  └─ no  -> identify the missing policy/product/security/legal fact
            -> return it to the owner
            -> do not invent a consent/security/legal rule through UI wording
```

If the interface reveals a conflict between business preference and user agency, preserve the accepted product outcome using a transparent choice model and surface the conflict when another owner must resolve policy or scope.
