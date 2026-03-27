# MRL Starter

## Purpose

This repository is a starter template for the Model Refinement Lab.

Use it to begin a new repository that follows the MRL loop:

```text
extract -> refine -> build -> egd -> release -> expose -> living -> extract
```

The default starter shape is:

- Python
- DDD-inspired modular monolith
- repository-scoped skills under `.agents/skills/`
- artifact-driven refinement workflow

If you want to change those defaults, read `architecture.md`, `groundrules.md`, and `docs/operating/mrl_reference.md` first and record intentional deviations in `decisions.md`.

---

## Getting Started

Clone the starter into the new repository name you want:

```bash
git clone <starter-url> my-new-project
cd my-new-project
```

Then read these files first:

- `docs/operating/mrl_reference.md`
- `docs/operating/skills_workflow.md`
- `architecture.md`
- `groundrules.md`
- `docs/building/project_structure.md`

Then start the loop:

1. run `extract` to build the first semantic baseline in `docs/semantics/`
2. run `refine` to define the first slice in `docs/slices/`
3. run `build` to implement one vertical slice
4. run `egd` to review the built behavior

The semantic placeholders in `docs/semantics/` are intentionally empty. They are meant to be filled by the `extract` phase, not by copying domain content from this starter.

---

## Starter Layout

```text
.agents/skills/            # repo-local MRL skills
/docs/operating/           # MRL model and workflow docs
/docs/building/            # structure and bootstrap guidance
/docs/evaluation/          # expectation-gap evaluation guidance
/docs/semantics/           # domain-specific meaning created by extract
/docs/slices/              # one slice document per increment
/src/app/                  # implementation root
/tests/                    # executable specification
```

---

## Notes

- Treat this repository as a template, not as a finished application.
- Keep domain specifics out of the starter and in the adopting repository.
- Prefer one small slice over broad scaffolding.
