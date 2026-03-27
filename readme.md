# MRL Starter

## Purpose

This repository is a starter template for the Model Refinement Lab.

Use it to begin a new repository that follows the MRL loop:

```text
extract -> refine -> build -> egd -> release -> expose -> living -> extract
```

The repository is intentionally generic. Replace the semantic docs and slice docs with material from your target domain.

---

## Start Here

Read these files first:

- `docs/operating/mrl_reference.md`
- `docs/operating/skills_workflow.md`
- `architecture.md`
- `groundrules.md`
- `docs/building/project_structure.md`

Then:

1. fill `docs/semantics/model_hypothesis.md`
2. fill `docs/semantics/domain_background_knowledge.md`
3. define the first slice under `docs/slices/`
4. implement one vertical slice only
5. run deterministic tests and expectation review

---

## Starter Layout

```text
.agents/skills/            # repo-local MRL skills
/docs/operating/           # MRL model and workflow docs
/docs/building/            # structure and bootstrap guidance
/docs/evaluation/          # expectation-gap evaluation guidance
/docs/semantics/           # domain-specific meaning to replace per project
/docs/slices/              # one slice document per increment
/src/app/                  # implementation root
/tests/                    # executable specification
```

---

## Notes

- Treat this repository as a template, not as a finished application.
- Keep domain specifics out of the starter and in the adopting repository.
- Prefer one small slice over broad scaffolding.
