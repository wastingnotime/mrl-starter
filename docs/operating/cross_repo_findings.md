# Cross-Repository Findings

## Purpose

This note defines how this repository records findings that were discovered locally but belong to another repository's ownership boundary.

Use it when a test, runtime observation, deploy artifact, or integration check shows a contract mismatch or unexpected behavior that this repository can observe but should not fix itself.

---

## Core Rule

This repository may observe and report a finding, but only the owning repository should define and implement the fix.

The local repository may:

- record evidence
- classify impact
- identify the likely owning repository
- add temporary validation or diagnostics
- block local rollout when necessary

The local repository must not:

- implement foreign fixes
- assume another repository's internal design
- silently work around the issue as if ownership were local
- coordinate multi-repository changes inside the finding itself

---

## Finding Location

Create one folder per finding under:

```text
work/findings/<date>-<short-name>/finding.md
```

Example:

```text
work/findings/2026-04-29-candidate-image-dispatch/finding.md
```

Keep the folder name short, stable, and specific to the observation.

---

## Required Contents

Each `finding.md` should capture:

- context
- observed behavior
- expected behavior
- impact
- suspected source
- evidence
- owning repository
- local impact

Suggested structure:

```md
# Finding: <short name>

## Context

Where this was discovered:
- feature
- deploy
- runtime
- test

## Observed Behavior

What actually happened.

Include:
- payloads
- logs
- traces
- screenshots, if relevant

## Expected Behavior

What should have happened.

Reference:
- contracts
- docs
- assumptions

## Impact

What breaks because of this:
- deploy
- runtime
- user flow
- data integrity

## Suspected Source

Which repository likely owns the issue.

## Evidence

Concrete data:
- logs
- request/response samples
- event payloads

## Suggested Direction

High-level direction only.

Do not define implementation inside another repository.

## Owning Repository

The repository responsible for fixing the issue.

## Local Impact

What this repository must do, if anything:
- adapt temporarily
- block deploy
- add validation
```

---

## Escalation

If the finding crosses repository boundaries or needs coordination, escalate it through the owning repository's normal handoff path or the broader management process used by this project family.

Do not turn the finding document into a hidden implementation plan for another repository.

---

## Local Follow-Up

The discovering repository may:

- add validation to prevent silent failure
- improve diagnostics
- document the expected contract

The discovering repository should not:

- embed a permanent workaround without explicit decision
- redefine the foreign contract locally
- expand the local change into cross-repo scope

