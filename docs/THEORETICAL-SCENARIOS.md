# Theoretical Decision Scenarios

Status: **AUTHORING REGRESSION SPEC**

Use this document when changing Product Interface Designer semantics. It is an instruction-level regression aid, not a runtime checklist and not a model/harness benchmark.

The purpose is to test whether the Skill would make the right **routing, ownership, questioning, evidence, and interface-decision** choices before a change is integrated.

## Contents

[Evaluation dimensions](#evaluation-dimensions) · [A–F: build/change/reference](#a-new-dashboard--build-and-implement) · [G–J: decisions/scope](#g-missing-material-product-behavior) · [K–O: locale/standards/IA/systems](#k-rtl-without-persian) · [P–U: AI/collaboration/adaptive/review/trust/platform](#p-ai-mediated-product-interface) · [V–X: composition](#v-github-project-orchestrator-composition) · [Y–Z: capability/discovery boundaries](#y-missing-renderexternal-authority-capabilities) · [AA–AD: feedback/content/prototype/multimodal](#aa-feedback-channel-and-interruption) · [Regression rule](#regression-rule)

For a semantic change, inspect every scenario whose trigger, owner, evidence assumption, or forbidden behavior could change. Representation-only edits need only the scenarios whose semantics they touch.

## Evaluation dimensions

For each relevant scenario, verify:

1. **Should the Skill trigger at all?**
2. **Which direct runtime references should load?**
3. **What facts should be recovered, inferred, asked, or left as assumptions?**
4. **What decision belongs to Product Interface Designer versus another owner?**
5. **Should it design, implement, review, or return an interface-decision packet?**
6. **What evidence can support the claimed result?**
7. **What behavior would be a regression?**

A scenario fails if the Skill:
- misses intended interface work;
- activates for pure non-interface work;
- asks for ordinary reversible design choices that professional judgment can resolve;
- invents material product/business/brand/platform facts;
- takes project/platform/repository/release authority;
- loads unrelated decision domains by default;
- claims evidence or correctness it does not have;
- lets optional aesthetics override stronger constraints or product truth.

## Core scenarios

### A. New dashboard — build and implement

**Prompt shape:** “Build the admin dashboard for this product.” Source/write/render capabilities are available and an existing application stack is already established.

**Expected:**
- Skill triggers from explicit build/implementation intent.
- Load design-core; add platform/review and other domains only when materially triggered.
- Recover product/task/content/incumbent design truth.
- Infer ordinary reversible layout/visual details rather than asking for a style questionnaire.
- Implement through the established project mechanism and render/review when available.

**Forbidden:** advice-only output when safe authorized implementation is available; framework replacement merely for visual preference.

### B. New dashboard — no write capability

**Prompt shape:** same request, but source/write capability is absent.

**Expected:** still trigger and return an implementation-ready interface decision/specification based only on supplied evidence.

**Forbidden:** claiming files were changed or tests/rendering ran.

### C. Targeted modification in an existing product

**Prompt shape:** “Improve this settings form; keep the rest of the product as-is.”

**Expected:** preserve current tokens, typography, components, terminology, information architecture, and interaction vocabulary except where the accepted change requires adjustment.

**Forbidden:** opportunistic redesign, rebrand, framework migration, or unrelated polish.

### D. Explicit redesign

**Prompt shape:** “Redesign the whole application; current visual language can change.”

**Expected:** preserve product capabilities/business rules/validated terminology/mandatory constraints, but deliberately reconsider visual system, composition, type, color, density, imagery, component expression, and motion.

**Forbidden:** treating redesign as merely recoloring the incumbent layout or preserving old aesthetics without reason.

### E. High-fidelity screenshot/reference implementation

**Prompt shape:** “Implement this screenshot as closely as possible.”

**Expected:**
- Treat observable fidelity as an accepted requirement.
- Distinguish what the reference actually proves from hidden behavior/data/responsive states.
- Preserve higher-precedence product/mandatory constraints.
- Use rendered evidence for material fidelity claims when capability exists.

**Forbidden:** treating the screenshot as loose inspiration; inventing hidden behavior or factual content from the image.

### F. Inspiration-only reference

**Prompt shape:** “Use this site as inspiration, not a copy.”

**Expected:** extract useful hierarchy, rhythm, density, visual character, imagery or interaction principles while designing for the actual product.

**Forbidden:** literal reproduction merely because the reference is visually strong.

### G. Missing material product behavior

**Prompt shape:** “Design the delete flow,” but it is unknown whether deletion is permanent, reversible, delayed, or policy-controlled.

**Expected:** discover the rule if possible; otherwise ask/return the unresolved product/policy decision because it materially changes the interface.

**Forbidden:** inventing deletion semantics and then designing confirmation/undo around the guess.

### H. Missing ordinary design details / delegated judgment

**Prompt shape:** “Make this screen better; you decide the details.”

**Expected:** infer reversible spacing, composition, hierarchy, component expression, and minor style choices from product/context evidence.

**Forbidden:** asking the user to choose routine spacing/radius/layout values or interpreting “you decide” as permission to invent business policy, product facts, durable brand identity, or architecture.

### I. Missing implementation stack: durable product versus disposable prototype

**Prompt shape 1:** “Build this product interface,” but no application framework/platform mechanism has been selected and choosing one would create a durable product architecture decision.

**Expected:** make the interface decision/prototype or implementation-ready guidance; return the durable framework/platform-architecture choice to its proper owner.

**Prompt shape 2:** “Make a disposable prototype of this interface,” with no stack selected and no durable architecture commitment implied.

**Expected:** choose the smallest available reversible mechanism that can express/test the interface, and treat that choice only as prototype implementation.

**Forbidden:** silently turning a prototype mechanism into product architecture, or blocking a disposable prototype merely because no durable stack exists.

### J. Pure backend task

**Prompt shape:** “Optimize this database query” with no user-facing interface consequence.

**Expected:** Skill does not trigger.

**Forbidden:** injecting UI/UX review into unrelated backend work.

### K. RTL without Persian

**Prompt shape:** Arabic/Hebrew RTL interface with no Persian/Iran requirement.

**Expected:** load general internationalization/direction guidance; do not load Persian specialization solely because the interface is RTL.

**Forbidden:** Persian/Iran conventions inferred from RTL direction.

### L. Persian/Iran product

**Prompt shape:** Persian-language Iranian product with date, currency, bidi, forms, and mixed Latin identifiers.

**Expected:** load both internationalization and Persian/RTL guidance, plus platform/review only when relevant.

**Forbidden:** treating Persian as merely mirrored English or conflating language, direction, locale, calendar, numbering system, and currency.

### M. Exact accessibility/platform requirement

**Prompt shape:** “Make this complex widget WCAG-compliant” or “match the current native platform behavior.”

**Expected:** use local principles for durable reasoning and retrieve current official authority when exact version-sensitive semantics matter.

**Forbidden:** claiming exact compliance/platform correctness from memory or from a visual render alone.

### N. Complex search/filter/navigation flow

**Prompt shape:** dense admin product with search, filters, facets, saved views, multistep navigation, or composite widgets.

**Expected:** load information architecture before styling the structure; use design-core for visual/interaction expression; consult current APG/platform authority for exact complex-widget semantics when material.

**Forbidden:** solving structural findability problems by adding decoration/cards alone.

### O. Local component tweak versus design-system work

**Prompt shape 1:** “Adjust this button/card on one surface.”
**Prompt shape 2:** “Redefine tokens, component contracts, themes, and migration rules across products.”

**Expected:** first case reuses current system through design-core; second activates design-system guidance.

**Forbidden:** creating a token taxonomy/component governance process for a local tweak, or treating true system-wide contract work as local styling.

### P. AI-mediated product interface

**Prompt shape:** user-facing generative/predictive AI produces recommendations or actions.

**Expected:** load AI-mediated guidance; additionally load trust/agency when data disclosure, permission, consequential choice, or user control is material. Keep model/backend/risk-policy architecture outside interface ownership.

**Forbidden:** false precision about AI confidence, hidden consequential actions, or interface rules that silently become model-risk policy.

### Q. Collaborative/shared-state editor

**Prompt shape:** simultaneous edits, presence, stale state, overwrite/conflict choices.

**Expected:** load collaboration/concurrency; add adaptive/platform/trust domains only when their own triggers are present. Make shared-state meaning legible without prescribing backend sync/locking algorithms.

**Forbidden:** backend concurrency architecture leaking into interface ownership.

### R. Adaptive/multi-window/input transition

**Prompt shape:** interface must preserve task context through resize, split view, fold/posture changes, restore, and pointer/touch/keyboard transitions.

**Expected:** load adaptive-context guidance, plus the actual target platform when exact behavior matters. Adapt from available space/current capabilities rather than device stereotypes.

**Forbidden:** hard-coding “tablet/desktop” assumptions that ignore actual window/input state.

### S. Screenshot-only review

**Prompt shape:** user provides one screenshot and asks whether the interface is good; no source/runtime access exists.

**Expected:** load review guidance; make only claims supported by that screenshot and label missing responsive/interaction/state evidence where material.

**Forbidden:** claiming the whole system, accessibility, responsiveness, or interaction behavior is validated by one screenshot.

### T. High-consequence/consent/destructive choice

**Prompt shape:** permission, irreversible action, data-sharing choice, billing-like commitment, or another consequential user decision.

**Expected:** load trust/agency; add human factors when comprehension/error/recovery risk is material. Expose consequences and reversal/recovery honestly while leaving legal/security/privacy policy to its owner.

**Forbidden:** coercive hierarchy, hidden consequences, or inventing policy.

### U. Multi-platform product

**Prompt shape:** same capability must work across web, iOS, Android, macOS, Windows, Linux/desktop environments, and/or a cross-platform desktop shell.

**Expected:** define shared product intent first, then load relevant platform sections and allow platform-specific interaction/layout differences while preserving product semantics; retrieve current target authority when exact native desktop conventions materially differ.

**Forbidden:** making one platform’s presentation the hidden source of truth for all targets.

### V. GitHub Project Orchestrator composition

**Prompt shape:** a project Master owns delivery and consults Product Interface Designer for a material interface decision or review.

**Expected:** load composition; receive minimum context; return Intent, Decision, Constraints, Implementation latitude, Evidence, Open assumptions; control then returns to the Master or its assigned implementation/platform owner. If Product Interface Designer also has write capability, composed consultation/review still returns the decision/findings instead of treating capability as authority to mutate the repository.

**Forbidden:** creating a competing roadmap, changing repository scope, taking CI/integration/release ownership, or implementing fixes during composed consultation merely because write capability is available.

### W. WP Native Builder composition

**Prompt shape:** material interface work inside a WordPress project, whether WP Native Builder or Product Interface Designer is active first.

**Expected:** Product Interface Designer owns user-facing interface intent/critique; WP Native Builder owns WordPress mechanism, Gutenberg/theme/plugin/WooCommerce lifecycle, publication, and live implementation safety. A WP-first unresolved interface question returns one decision packet and control to the WordPress owner. A PID-first flow hands off when WordPress mechanism/lifecycle work begins, and WP Native Builder reuses the still-valid packet rather than creating a reciprocal loop. Block/mechanism/CSS/tool/transport choices and ordinary implementation defects do not invalidate the interface decision. Re-review occurs only when material product/design/target/evidence changes or rendered evidence creates a genuinely material interface/fidelity question; pass only the changed evidence/constraint and exact question. Durable accepted interface conclusions reconcile into the project's existing source of truth rather than a composition log.

**Forbidden:** Product Interface Designer prescribing brittle WordPress internals merely to force presentation, reciprocal PID -> WP -> PID invocation without a changed interface question, automatic re-review after every render, or mechanism-only changes invalidating a still-valid interface decision.

### X. Idea Advisor composition

**Prompt shape A:** Idea Advisor has defined the outcome/user/task enough to ask a bounded unresolved interface question whose answer can materially change advisory reasoning, validation, feasibility/user-flow understanding, prototype choice, or execution handoff.

**Expected A:** load composition; receive only minimum decision-relevant context; own the concrete interface decision/review; return Intent, Decision, Constraints, Implementation latitude, Evidence, Open assumptions; then return control to Idea Advisor's advisory workflow rather than jumping to execution.

**Prompt shape B:** Product Interface Designer exploration exposes a material whether/why question, unresolved actual user/outcome, product scope/value question, product capability reuse question, product-local/Foundation/project placement question, or another strategic product boundary.

**Expected B:** return that question to Idea Advisor/caller; only continue interface decisions once enough product truth exists; do not bounce the unchanged question recursively.

**Reuse edge case:** “Should this screen reuse the existing component/design-system pattern or introduce a new interface component?” remains a Product Interface Designer decision when it is an interface/design-system question; the word “reuse” alone does not route it to Idea Advisor.

**Forbidden:** using screens/prototypes to manufacture product certainty, creating a second roadmap/handoff, taking product/advisory/project authority, jumping directly from advisory consultation to execution, or recursively ping-ponging the same unresolved question.

### Y. Missing render/external-authority capabilities

**Prompt shape:** material UI work is possible, but rendered inspection or current external retrieval is unavailable.

**Expected:** continue useful design/static review, narrow claims, and state only material evidence limitations.

**Forbidden:** blocking all interface reasoning because an optional capability is absent, or claiming rendered/exact-standard correctness without evidence.

### Z. Standalone visual/brand work outside product UI

**Prompt shape:** “Design a logo/poster/social graphic/brand identity” with no product-interface surface involved.

**Expected:** Product Interface Designer does not trigger merely because typography, color, or visual design is involved.

**Forbidden:** expanding product-interface ownership into standalone branding, illustration, print, or social-graphic design.

### AA. Feedback channel and interruption

**Prompt shape:** the product needs to communicate a routine save success, a recoverable validation problem, an ongoing cross-surface outage, a critical destructive-risk warning, and a useful event that may complete while the user is away.

**Expected:** use design-core to choose the least disruptive surface that still preserves the needed significance, persistence, scope, actionability, and context. Keep routine/recoverable feedback in context when practical; use persistent surface-level messaging for ongoing conditions; reserve blocking interruption for genuinely immediate understanding/action; use out-of-app/system notification only when the information remains timely and valuable away from the product. Route exact system-notification behavior to the target platform.

**Forbidden:** using toast/modal/system notification as a default style choice; hiding material recovery in a transient message; interrupting routine success merely to show activity.

### AB. Interface copy/content design

**Prompt shape:** a form or error flow is technically correct but uses internal terminology, long explanatory text, generic action labels, or blame-oriented copy.

**Expected:** use design-core interface-copy ownership; prefer user/domain language, front-load decision/action-relevant information, remove filler, use specific action/destination labels, simplify the interface before adding prose that only teaches ordinary controls, and keep tone calm/clear in high-stress or consequential states. Preserve authoritative domain terms where simplification would reduce accuracy.

**Forbidden:** creating a separate content-strategy workflow for ordinary UI copy; using humor/personality that obscures consequence; fixing unclear interaction primarily by adding more explanatory text.

### AC. Prototype fidelity matches the uncertainty

**Prompt shape 1:** test information architecture and task sequence before visual direction is settled.
**Prompt shape 2:** test typography/density/reference fidelity.
**Prompt shape 3:** test focus/keyboard behavior, motion, responsive transition, or assistive/device interaction.

**Expected:** use human-factors guidance to choose the smallest prototype fidelity that makes the actual question observable: rough/minimally interactive for structural questions, sufficient visual fidelity for visual/content questions, and sufficient functional/platform fidelity for behavior questions. Add realistic content/state complexity only when it can change the answer.

**Forbidden:** treating high-fidelity polish as stronger usability evidence by itself; spending effort on visual detail that cannot answer the research/design question; relying on a static mock to validate interaction behavior.

### AD. Multimodal platform feedback

**Prompt shape:** a native/cross-platform interaction could use haptic or audio feedback for confirmation, alignment, success, error, or another state.

**Expected:** load platform guidance when the capability is real and material. Use haptic/audio as supplementary reinforcement, not decoration; preserve essential meaning through another suitable channel; respect user/system preferences and retrieve current target-platform guidance for exact capabilities/patterns.

**Forbidden:** requiring haptics/audio on unsupported targets; making them the sole carrier of essential outcome/state; hard-coding vendor waveform/API details into this Skill.

## Regression rule

A semantic Skill revision is acceptable only when it improves or preserves the expected behavior of every materially affected scenario without:
- widening Product Interface Designer authority;
- adding mandatory ceremony to ordinary reversible interface work;
- weakening evidence language;
- duplicating another canonical runtime owner;
- turning theoretical scenarios into runtime checklists.

The scenario audit is intentionally theoretical. Real rendered, accessibility, user-task, or implementation validation is still required when the actual task makes those forms of evidence material.
