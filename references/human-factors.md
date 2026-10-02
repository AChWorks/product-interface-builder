# Human Factors and Usability Evidence

Use this reference when the interface decision materially depends on how people understand, learn, remember, predict, recover from, or complete an interaction — especially for novel, complex, repeated, high-consequence, or error-prone tasks.

This file owns human-factors reasoning and usability-evidence confidence. Detailed visual QA, accessibility conformance checks, information architecture, platform mechanics, and research operations belong to their own owners.

## Contents

[Trigger](#1-decide-whether-human-factors-depth-is-needed) · [Mental models](#2-fit-the-users-mental-model) · [Memory/load](#3-reduce-unnecessary-memory-and-attention-load) · [Control/recovery](#4-make-control-and-recovery-visible) · [Help/disclosure](#5-use-help-and-progressive-disclosure-to-reduce-burden) · [Task outcome](#6-design-for-task-completion-not-interface-polish) · [Evidence](#7-separate-hypotheses-from-evidence) · [Prototype fidelity](#match-prototype-fidelity-to-the-question) · [Uncertainty](#8-handle-usability-uncertainty-proportionally)

## 1. Decide whether human-factors depth is needed

Do not turn every interface change into a research program.

Use ordinary design/review guidance when the interaction is familiar, low-consequence, reversible, and well supported by current product/platform patterns.

Increase human-factors scrutiny when one or more are material:

- users must learn a new interaction model or unusual control;
- the task has many steps, states, choices, dependencies, or interruptions;
- users must remember information across screens or time;
- mistakes are costly, difficult to detect, or difficult to reverse;
- the interface is used frequently enough that small friction compounds;
- users may be under time pressure, stress, distraction, or low familiarity;
- success depends on discovering hidden actions or interpreting unfamiliar system state;
- current evidence shows abandonment, repeated errors, support burden, or confusion;
- a polished/rendered interface still leaves uncertainty about whether people can complete the task.

A novel interaction is a design hypothesis until evidence justifies stronger confidence.

## 2. Fit the user's mental model

Prefer mappings, terminology, ordering, and behavior that users can predict from the product/domain/platform context.

- Use the language users need for the task; do not make them translate internal system architecture into actions.
- Keep the same concept named and represented consistently unless a real distinction exists.
- Make cause and effect legible: users should be able to tell what an action applies to and what changed.
- Preserve useful transfer from established product/platform patterns instead of inventing new behavior for novelty.
- When the product must introduce a new concept, expose enough explanation/state to build the model progressively rather than requiring users to infer it all at once.
- Avoid visually identical controls with materially different behavior or different-looking controls with the same role unless the distinction helps the task.

Do not assume the implementation model is the user mental model.

## 3. Reduce unnecessary memory and attention load

Prefer recognition and visible context over recall when the task permits it.

- Keep relevant choices, state, constraints, and prior selections visible near the decision they affect.
- Preserve entered work and task context across recoverable errors, navigation, refresh, or interruption when product rules allow it.
- Break long or complex work into meaningful chunks only when the grouping helps orientation; do not fragment a simple task into needless steps.
- Keep important comparison information simultaneously available when forcing users to remember it would increase error or effort.
- Use defaults, recent values, suggestions, autofill, and summaries only when they are trustworthy and do not remove meaningful user control.
- Avoid simultaneous competing demands for attention; motion, alerts, secondary actions, and dense detail should not obscure the current task.
- Re-orient users after state changes: make current location/status and the next meaningful action understandable without reconstructing the whole history.

Do not hide essential task context behind progressive disclosure merely to make the surface look simpler.

## 4. Make control and recovery visible

Predictability and recoverability reduce both error cost and learning burden.

- The same action in the same state should have a stable, explainable effect.
- Show material system state and action feedback close enough to the action for users to connect cause and effect.
- Preserve a clear way to cancel, go back, edit, retry, or undo when the product can safely support it.
- For consequential actions, make scope/consequence understandable before commitment and provide the appropriate confirmation or recovery path.
- Prevent avoidable errors through constraints, sensible sequencing, and clear expectations before relying on error messages.
- When an error occurs, preserve valid work, identify what needs attention, and make recovery actionable.
- Avoid dead ends that force users to restart a task merely because the interface lost state or hid the recovery route.

Exact accessibility/legal requirements for errors, help, timing, or confirmations come from the current authoritative owner when material.

## 5. Use help and progressive disclosure to reduce burden

Help should appear where it can change the user's next action.

- Prefer clear labels, examples, constraints, and inline explanations over forcing users to consult distant documentation for ordinary tasks.
- Keep repeated help discoverable in a stable place.
- Reveal advanced or infrequent detail progressively when doing so reduces distraction without hiding required information.
- Explain non-standard controls close to first use; prefer established controls when novelty adds no product value.
- Use onboarding only for knowledge users cannot reasonably infer at the moment of need. Do not use a tour to compensate for unclear everyday controls.
- Let experienced users proceed without repeatedly dismissing beginner guidance where practical.

Progressive disclosure is successful only when users can still discover the hidden capability at the time they need it.

## 6. Design for task completion, not interface polish

Evaluate the whole task path, including failure and resumption.

Ask:

- Can the user tell what outcome this surface supports?
- Can they find the next meaningful action without guessing?
- Can they understand enough state to make the decision?
- What happens after interruption, validation failure, partial success, timeout, or a changed external state?
- Can they recover without unnecessary re-entry or support?
- Does the interface help users reach the actual product outcome, or merely make an intermediate screen look clean?

A visually coherent screen can still be usability-uncertain when these questions are unresolved.

## 7. Separate hypotheses from evidence

Use evidence only for the claim it can support. [review.md](review.md) owns how static, rendered, measured, and assistive interface-review evidence is obtained and judged; this section owns only what those evidence types do or do not justify about usability confidence.

| Evidence type | What it can support | What it does not prove by itself |
|---|---|---|
| **Product facts** | accepted users/tasks/business rules/current behavior | that a proposed interaction is understandable or usable |
| **Design hypothesis** | a reasoned prediction about what should work | any observed user outcome |
| **Static source/design evidence** | intended structure, states, labels, implementation logic | rendered behavior or user task success |
| **Rendered/interaction evidence** | actual visual/state/interaction behavior in the exercised conditions | that representative users understand or complete the task |
| **Measured/accessibility evidence** | the specific automated/manual/assistive/performance properties actually measured | broad usability outside the measurement |
| **Behavioral/operational evidence** | observed funnels, errors, support tickets, abandonment, repeated actions | why users behaved that way without additional evidence |
| **User/task evidence** | what observed participants/users did, understood, failed, or recovered from for the tested tasks/context | untested populations, tasks, environments, or universal usability |

Never say an interface was user-tested, validated with users, or proven usable unless corresponding user/task evidence actually exists.

Do not treat preference polling as equivalent to observing task behavior when the decision is about task completion.

## 8. Handle usability uncertainty proportionally

### Match prototype fidelity to the question

Prototype fidelity is an evidence choice, not a quality score. Use the smallest fidelity that makes the decision-sensitive uncertainty observable.

- For information architecture, sequencing, labeling, or broad task-flow questions, a rough wireflow or minimally interactive prototype may provide stronger signal than polished visual detail.
- For hierarchy, density, typography, copy wrapping, brand expression, or reference-fidelity questions, include enough visual fidelity for those properties to be judged.
- For interaction timing, focus/keyboard behavior, motion, responsive/adaptive transitions, device/input behavior, or assistive-technology questions, use enough functional/platform fidelity to exercise the behavior rather than relying on a static mock.
- Add realistic content/state complexity when it can change the answer; do not add polish that cannot.
- Do not treat high visual fidelity as stronger usability evidence by itself. A polished prototype remains a hypothesis until the relevant task/user evidence exists.

Use this decision flow:

```text
Is the interaction conventional, low-consequence, reversible, and well-supported?
  ├─ yes -> use established patterns + proportional review; no research ceremony
  └─ no  -> identify the decision-sensitive usability hypothesis
            -> can stronger task evidence materially change the decision?
                 ├─ no -> proceed with the safer/conventional/reversible choice
                 └─ yes -> use the cheapest credible evidence that answers that question
                           (prototype/task observation, existing product behavior,
                            support/analytics evidence, or other suitable research)
```

When direct user-research capability is unavailable:

- do not fabricate user evidence or block ordinary work automatically;
- prefer familiar, reversible, clearly signposted interaction;
- reduce novelty and error cost where doing so preserves the product outcome;
- label the material usability assumption in the interface-decision packet;
- recommend the specific task/question that stronger evidence should test, not a generic request to “do user research.”

Escalate only when the unresolved usability assumption materially changes product risk, accepted behavior, or another owner's decision boundary.
