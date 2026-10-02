# Instruction Architecture and Skill Composition

Status: **AUTHORITATIVE AUTHORING DESIGN**

This document defines how Product Interface Designer instructions should be structured so another AI can discover, reason with, and compose the Skill reliably. It is a project-authoring specification, not part of the distributable runtime unless a rule is promoted into `SKILL.md` or a runtime reference.

## 1. Design objective

Optimize for **decision clarity per context token**.

The Skill should make the next correct decision easier for an AI by:

- exposing authority and conflict resolution early;
- loading only decision-relevant knowledge;
- separating distinct decision domains;
- making branches explicit when outcomes materially differ;
- avoiding duplicated rules and parallel owners;
- preserving professional judgment where rigid recipes would be worse;
- returning actionable interface intent to whichever Skill owns implementation/integration.

A longer instruction is justified only when it materially improves decision quality, reliability, or handoff.

## 2. Runtime topology

```text
metadata/description
      ↓ trigger
   SKILL.md
      ↓ route by task/conditions
 direct references
      ↓
interface decision / review output
      ↓
caller or platform specialist executes/integrates
```

Rules:

- Keep `SKILL.md` as the control plane, not a knowledge dump.
- Keep runtime references one level deep from `SKILL.md`.
- Give each durable concern one canonical runtime owner.
- Load conditional domains only when relevant.
- Do not create a new reference merely because a topic has many notes; create it when it represents a distinct recurring decision domain.

## 3. Choose representation by reasoning shape

| Reasoning need | Preferred representation | Avoid |
|---|---|---|
| authority/conflict resolution | short ordered precedence | prose that hides which rule wins |
| conditional routing | decision table or compact decision tree | long narrative branches |
| ownership/composition | table with one owner per concern | overlapping prose in several files |
| sequential workflow | compact arrow/state flow plus only necessary rules | giant checklist with no decision points |
| heuristics/principles | concise prose + bullets | fake algorithmic precision |
| evidence levels | ordered scale/table | mixing observed and assumed evidence |
| comparisons/trade-offs | table only when dimensions are stable and comparable | tables used merely for visual formatting |
| exceptions/edge conditions | local rule next to the parent decision | distant catch-all exceptions |
| examples | one or few minimal examples when ambiguity remains | catalogs of examples that become pseudo-rules |

### Decision-tree rule

Use a tree only when:

- the branch condition is observable;
- branches materially change behavior;
- the tree reduces ambiguity more than ordinary prose.

Do not encode subjective continuous design judgment into artificial yes/no trees.

## 4. Canonical ownership and duplication control

Before adding a rule:

1. identify the decision it changes;
2. identify the canonical owner reference;
3. check whether an existing rule already yields the same decision;
4. merge/refine the existing rule when possible;
5. create a new owner only when the concern has a distinct trigger, evidence model, or decision surface.

Other references may point to the owner but should not restate its rule set.

A useful test:

```text
Would removing this new sentence change a decision
that is not already determined elsewhere?
  ├─ no  → do not add it
  └─ yes → place it in the one canonical owner
```

## 5. Decision precedence

Runtime precedence must distinguish **desired outcome/preferences** from **non-negotiable applicable constraints**.

The control plane should make conflicts resolvable without forcing the AI to infer policy from paragraph order.

Target model:

```text
current authoritative constraints
  → accepted product/user outcome
  → product/design truth
  → platform/locale/user-context conventions
  → domain design principles
  → optional stylistic suggestions
```

Exact runtime wording is an implementation task, but the architecture must prevent an aesthetic/user preference from silently overriding an applicable legal, safety, accessibility, or platform requirement.

## 6. Specialist composition model

Product Interface Designer is a **consulted specialist**, not a nested project Master.

### Generic composed flow

```text
Parent/Master frames accepted work
        ↓
Does a material interface decision exist?
        ├─ no  → parent continues
        └─ yes
             ↓
       invoke Product Interface Designer
             ↓
       interface decision packet
             ↓
platform/implementation owner executes
             ↓
material rendered/interaction review needed?
        ├─ no  → parent continues integration
        └─ yes → Product Interface Designer reviews
                  ↓
                parent continues integration/release
```

The parent remains authoritative for scope, repository state, task coordination, implementation ownership, integration, release, and continuity unless another explicit owner is defined.

### Interface decision packet

When composed, Product Interface Designer should return only what the caller needs:

- **intent:** what user/task outcome the interface must support;
- **decision:** concrete hierarchy/interaction/visual/locale behavior;
- **constraints:** mandatory user-facing/platform/locale/accessibility/trust requirements;
- **implementation latitude:** what the platform owner may adapt without changing the experience;
- **evidence:** what would make the decision/review credible;
- **open assumption:** only unresolved material product/design facts.

Do not return a second project plan, repository workflow, release plan, or implementation mechanism owned by another Skill.

## 7. Composition with AChWorks Skills

| Active Skill | Product Interface Designer owns | Other Skill retains |
|---|---|---|
| GitHub Project Orchestrator | material UI/UX decision, design constraints, interface review | outcome/scope, repository/task coordination, implementation strategy ownership, integration, CI, release, continuity |
| WP Native Builder | user-facing hierarchy, interaction, visual/UX/accessibility/locale intent | WordPress/Gutenberg/theme/plugin/WooCommerce owner/mechanism, serialization/lifecycle safety, publication |
| ACh Idea Advisor | interface implications after product outcome is sufficiently defined | whether/why to build, product outcome, reuse/placement direction, evidence-backed idea maturation |

### Escalation back to the caller

Return control instead of guessing when the unresolved choice materially changes:

- product/business behavior rather than interface expression;
- project/repository scope or priority;
- platform architecture/mechanism ownership;
- security/privacy/data policy outside user-facing presentation;
- legal/compliance policy;
- another owner's durable contract.

Ordinary reversible interface decisions remain inside Product Interface Designer.

## 8. Evidence discipline

The Skill should distinguish at least:

- authoritative product/design facts;
- inferred design hypotheses;
- static implementation evidence;
- rendered interaction/visual evidence;
- measured/assistive evidence;
- actual user/task evidence when available.

Do not call a design “validated” merely because it renders correctly or passes an accessibility scan.

For material new interaction models, unusual navigation, complex workflows, or consequential redesigns, the Skill should know when user/task evidence may be needed while remaining useful when such evidence is unavailable.

## 9. Current-authority routing

Durable principles belong in the Skill. Exact version-sensitive requirements belong to the current authoritative source.

Runtime guidance should tell the AI to consult current official documentation when exact behavior materially depends on:

- accessibility standards/patterns;
- native platform conventions;
- browser/platform APIs;
- legal/regulatory requirements;
- another authoritative product/platform contract.

Do not vendor entire standards merely to avoid current retrieval.

## 10. Context-budget rules

- Prefer one high-signal rule over several synonyms.
- Keep routing/authority near the entrypoint.
- Move detailed domain knowledge out of `SKILL.md`.
- Do not load unrelated locale/platform/advanced references.
- Avoid catalog-style lists unless lookup itself is the capability.
- Avoid “always check everything” wording; activate concerns by materiality.
- Use tables only when scanning relationships is faster than prose.
- Use prose when nuance or professional judgment matters.
- Use examples sparingly and never let examples silently become mandatory templates.

## 11. Review standard for future Skill edits

Before integrating a Skill-content change, ask:

1. Does it close an evidenced decision gap?
2. Is this Product Interface Designer's responsibility?
3. Is the rule non-obvious enough to earn context?
4. Does it have one canonical owner?
5. Is the chosen representation appropriate for how an AI must reason with it?
6. Does it conflict with or duplicate another AChWorks Skill?
7. Does it preserve standalone usefulness?
8. Does it preserve composed usefulness?
9. Does it need current external authority instead of frozen local detail?
10. Can any existing instruction be removed or simplified because of this change?

Passing this review does not require behavioral multi-model/harness testing.
