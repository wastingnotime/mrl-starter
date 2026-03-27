# MRL Starter

## Purpose

This document defines the minimal portable shape for adopting the Model Refinement Lab in a new repository.

Use it when creating a fresh project that should follow the same refinement discipline without copying domain-specific content from this repository.

---

## Split the Repository Into Two Parts

### Framework-generic

These parts should be portable across domains:

- `readme.md`
- `architecture.md`
- `groundrules.md`
- `decisions.md`
- `AGENTS.md`
- `.agents/skills/`
- `docs/operating/`
- `docs/building/project_structure.md`
- evaluator pattern, scenario runner pattern, and test shape

### Project-specific

These parts should be rewritten for each new domain:

- `docs/semantics/model_hypothesis.md`
- `docs/semantics/domain_background_knowledge.md`
- `docs/slices/`
- code under `src/`
- tests under `tests/`
- local evaluation artifacts under `runs/`

---

## Minimal Starter Layout

```text
project_root/
  readme.md
  architecture.md
  groundrules.md
  decisions.md
  AGENTS.md
  .gitignore
  pyproject.toml

  .agents/
    skills/
      extract/
      refine/
      build/
      egd/
      release/
      expose/
      living/

  docs/
    operating/
      mrl_reference.md
      mrl_starter.md
      skills_workflow.md
    building/
      project_structure.md
    evaluation/
      scenario_evaluation.md
    semantics/
      model_hypothesis.md
      domain_background_knowledge.md
    slices/

  src/
    app/

  tests/
    unit/
    integration/
```

---

## First Bootstrap Sequence

A new repository should start with this order:

1. define root strategic docs and `docs/operating/`
2. install repo-local skills under `.agents/skills/`
3. create empty semantic docs under `docs/semantics/`
4. run `extract` to build the first model baseline
5. run `refine` to create the first slice
6. run `build` to implement the first executable vertical slice
7. run `egd` before deciding `release`

---

## Portability Test

MRL is portable only if a new domain can reuse the same loop and skills by changing semantic artifacts and slices rather than rewriting the workflow itself.

A practical test is:

- keep the operating docs and skills
- replace semantic docs and slice docs
- implement a new first slice
- run the same loop end to end

If that works, the starter is sufficiently portable.
