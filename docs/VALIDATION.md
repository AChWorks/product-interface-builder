# v0.1 Validation and Packaging

This document defines the reproducible release gate. GitHub Issues/PRs own live work state and exact run evidence; this file owns the stable validation procedure.

## Canonical Skill payload

The distributable Skill contains:
- `SKILL.md`;
- `references/`;
- `agents/openai.yaml` as an optional ChatGPT UI/discovery adapter.

Repository governance/docs such as `docs/`, `evals/`, `achworks.yaml`, and `THIRD_PARTY_NOTICES.md` remain release/project evidence and are not required runtime Skill behavior.

## Skill validation

Use the current official `skill-creator` validator/packager against a staging directory containing only the canonical Skill payload.

Required result:
- frontmatter/schema validation passes;
- all direct reference paths resolve;
- package output is exactly `skill.zip`;
- packaged size remains within the platform limit;
- no placeholder/example scaffold files remain.

Do not maintain a copied validator in this repository merely to duplicate the official one.

## Provider adapter validation

`agents/openai.yaml` is metadata only. Validate it independently as YAML and confirm removing it does not change the canonical `SKILL.md` or reference behavior.

## Koinon descriptor validation

Validate root `achworks.yaml` against the current Koinon `schemas/descriptor.schema.json` (`achworks.dev/v1alpha1`).

The descriptor is stable discovery metadata only. Do not mirror Issue/PR/release status into it.

## Provenance/license validation

Before release:
- repository license remains MIT;
- `docs/SOURCE-STRATEGY.md` pins audited upstream evidence;
- `THIRD_PARTY_NOTICES.md` matches the actual import state;
- no direct third-party code/data/prose is present unless its exact source/license/notice obligations are recorded.

## Evaluation

Run the scenarios in [../evals/scenarios.md](../evals/scenarios.md).

At minimum, release evidence must include:
- targeted existing-UI modification and locale non-leakage;
- Persian/RTL conditional behavior;
- static-vs-rendered evidence discipline;
- platform routing;
- project/WordPress composition boundaries;
- graceful degradation;
- two independent compatible runtime/harness families.

## Release

Release only after all v0.1 criteria are evidenced at the exact candidate SHA.

Record the candidate SHA, validation/package result, runtime/harness evidence, and any CI/check state in the release PR/Issue. Release/tag identity must point to the integrated commit, not a stale branch candidate.
