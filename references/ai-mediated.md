# AI-Mediated Interface Guidance

Use this reference when generative or predictive AI materially shapes what users see, decide, create, trust, or allow the product to do.

This file owns the **user-facing interaction contract around AI behavior**. It does not own model/provider selection, prompts/model architecture, training/fine-tuning, evaluation infrastructure, safety/security enforcement, data policy, or legal/compliance policy. [human-factors.md](human-factors.md) owns general usability confidence; [trust-agency.md](trust-agency.md) owns user-facing consent/privacy/agency constraints.

## Contents

[Trigger](#1-expose-ai-only-when-it-changes-the-users-decision) · [Expectations](#2-set-truthful-capability-and-quality-expectations) · [Uncertainty/provenance](#3-represent-uncertainty-and-provenance-without-false-precision) · [Control](#4-make-ai-output-correctable-and-dismissible) · [Actions](#5-require-understanding-before-consequential-ai-mediated-actions) · [Latency](#6-design-streaming-progress-and-latency-as-real-system-state) · [Failure](#7-make-failure-and-recovery-task-oriented) · [Feedback](#8-separate-user-feedback-from-hidden-promises) · [Privacy](#9-route-ai-data-implications-to-trust-and-policy-owners) · [Authority](#10-keep-interface-guidance-separate-from-ai-risk-policy)

## 1. Expose AI only when it changes the user's decision

Do not add “AI” badges everywhere merely because a feature uses an AI component.

Make AI involvement legible when knowing it would materially affect how a reasonable user should:

- evaluate accuracy or uncertainty;
- distinguish generated/suggested content from authoritative/human-authored content;
- understand why behavior may vary between attempts;
- decide whether to review before acting;
- understand personalization/adaptation;
- know what data/feedback choice is being offered;
- attribute a consequential recommendation/action.

When AI involvement does not change the user's interpretation or control, prefer clear task-oriented interface language over technology branding.

Never imply human review, expert authorship, determinism, or authoritative verification unless current product truth establishes it.

## 2. Set truthful capability and quality expectations

Users should understand what the AI feature is for and the meaningful limits that affect the task.

Prefer expectations tied to the actual user job:

- what the system can help produce, infer, summarize, recommend, classify, or automate;
- which inputs/context it actually receives when that affects results;
- where human review is still important;
- whether outputs can vary or contain errors;
- whether a feature is advisory versus committing a real product action.

Do not:

- promise “always correct,” “fully automatic,” “expert-level,” or similar capability without authoritative evidence;
- present a demo/example as proof of expected performance;
- expose internal model jargon when it does not help the user act;
- use generic warning text as a substitute for designing the risky decision correctly.

For material novel/high-consequence use, [human-factors.md](human-factors.md) owns whether the proposed interaction remains a usability hypothesis.

## 3. Represent uncertainty and provenance without false precision

Communicate uncertainty only at a level the underlying product can truthfully support.

- Prefer actionable uncertainty language or alternative choices when a numeric confidence would be misleading.
- Show a confidence/probability only when the value is actually available, calibrated/meaningful for the user decision, and the product has defined how it should be interpreted.
- Do not invent a confidence percentage from wording, token probabilities, visual style, or model self-assessment.
- When the product has authoritative sources/provenance, distinguish sourced material from generated synthesis at the level needed for verification.
- When provenance is absent, do not create citation-like UI that implies a source was checked.
- Clearly distinguish generated drafts/suggestions from committed records or human-approved content when that distinction changes responsibility or trust.

Exact provenance, record-retention, audit, and regulated-explanation requirements belong to current product/policy/legal owners.

## 4. Make AI output correctable and dismissible

AI should help users progress without becoming unquestionable system truth.

Where the product permits it, support the controls that match the task:

- edit or directly modify generated output;
- refine the request/context;
- retry/regenerate when another attempt is meaningful;
- choose among alternatives;
- reject/dismiss a suggestion;
- restore/undo a reversible AI-applied change;
- switch to a manual/non-AI path when the task requires independent control.

Do not create a retry button that silently repeats a consequential action rather than regenerating/re-evaluating the intended output.

Preserve useful user edits and context when retrying unless product truth requires a fresh start.

If the AI cannot satisfy a constraint confidently, asking for clarification or narrowing the action is often better than pretending certainty. The underlying capability to detect uncertainty belongs to the AI/product owner; the interface must not fabricate it.

## 5. Require understanding before consequential AI-mediated actions

Separate **AI proposing** from **the product committing** when the action has material financial, destructive, external, privacy, permission, safety, or other high-consequence effects.

Before commitment, make relevant scope/consequence understandable and preserve a user-controlled review/confirm/edit/cancel path unless current authoritative product/policy rules establish a different safe mechanism.

Examples include:

- sending/publishing on the user's behalf;
- deleting or overwriting durable data;
- purchasing/transferring/submitting;
- changing access/permissions;
- applying bulk modifications;
- contacting external people/services;
- making a consequential recommendation appear already decided.

Do not use “AI decided” as justification for removing meaningful user control.

[trust-agency.md](trust-agency.md) owns transparent choice, consent/privacy presentation, and anti-deceptive constraints. Backend authorization/idempotency/transaction safety belongs to the implementation/security owner.

## 6. Design streaming, progress, and latency as real system state

AI work may have variable latency and incremental output.

- Distinguish queued/waiting, generating/processing, tool/action execution, completed, cancelled, and failed states only when the product can actually know them.
- For streaming text/content, let users understand that output may still change or be incomplete until the relevant completion state.
- Provide cancel/stop when the underlying product supports it and stopping has user value.
- Preserve already useful partial output when safe rather than clearing it without explanation.
- Avoid fake deterministic progress percentages for work whose completion percentage is not known.
- If a long-running action continues after the surface changes, make ownership/status/re-entry understandable.

Do not interpret mere animation as evidence the AI is still making progress; interface state should reflect actual product state.

## 7. Make failure and recovery task-oriented

AI failure can be partial, ambiguous, or content-specific.

Distinguish when product evidence permits:

- request/input cannot be handled;
- output is incomplete/low-confidence according to an authoritative system signal;
- generation/service failed;
- a downstream tool/action failed after generation;
- result violates a product rule and cannot be used;
- user cancelled/stopped the operation.

Then expose the next useful path: edit input, retry safely, choose a manual path, inspect partial output, return later, or contact the responsible owner/support path when appropriate.

Do not expose raw model/provider errors as primary user copy unless technical users genuinely need them.

Do not claim a failed external action succeeded just because the AI generated text describing it.

## 8. Separate user feedback from hidden promises

Feedback controls should have a clear user-facing purpose.

- Ask for feedback at a useful granularity when it can improve the product/workflow or let users communicate a problem.
- Distinguish “edit this result for my task” from “send product/model feedback” when they have different consequences.
- Do not imply that thumbs-up/down, edits, or corrections will train/personalize the model unless current product truth actually says so.
- Do not make required task completion depend on optional model-quality feedback unless an authoritative product requirement justifies it.
- When reporting harmful/incorrect output is important, provide a path that does not force users to expose more private content than the product needs.

Any data collection/use/retention implication routes to [trust-agency.md](trust-agency.md) plus the authoritative privacy/data owner.

## 9. Route AI data implications to trust and policy owners

If the interface asks users to provide sensitive/contextual data, share history/files, enable personalization/memory, or permit external tool/action access:

- explain the immediate user-facing choice only from authoritative product truth;
- expose meaningful scope/control/revocation where the product supports it;
- distinguish temporary task context from durable memory/history when that difference exists;
- do not invent privacy guarantees, retention periods, model-training exclusions, encryption claims, or third-party data behavior.

Product Interface Designer owns how known choices are presented. Privacy/data/security policy and enforcement remain outside this Skill.

## 10. Keep interface guidance separate from AI risk policy

Current AI risk frameworks, platform policies, regulations, model/provider behavior, and legal duties can change.

```text
Does an exact AI policy/risk/legal/platform rule materially constrain this interface?
  ├─ no  -> use this reference's durable interaction principles
  └─ yes -> retrieve the current authoritative requirement for the actual product/context
            -> apply it as a mandatory constraint
            -> return to the interface decision
```

Do not freeze model-specific capability tables, safety taxonomies, regulatory rules, provider policy, or risk-framework requirements into this Skill.

The interface must not imply certainty or authority the underlying system cannot support. When product truth is missing, surface the material assumption/owner rather than inventing AI behavior.
