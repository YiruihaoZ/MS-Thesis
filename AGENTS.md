# AGENTS.md

## Project overview
This is an R-based biostatistics analysis repository with simulation code, statistical modeling, and Quarto/R Markdown reports.

Main goals:
- preserve reproducibility
- make minimal, high-confidence changes
- avoid silent changes to statistical logic
- keep outputs, file names, and report structure stable unless the task explicitly requires changes

## First read
Before editing, read:
- `README.md`
- `ARCHITECTURE.md`
- `TESTING.md`
- `SECURITY.md`

For larger or multi-step tasks, create or update `PLANS.md` first.

## How to work in this repo
- Prefer the smallest safe edit that solves the task.
- Preserve existing object names, paths, and output file names unless a change is necessary.
- Do not overwrite raw input data.
- Do not silently change model formulas, variable coding, simulation settings, priors, seeds, or benchmark definitions.
- If statistical logic changes, explain exactly what changed and why.
- Reuse existing helper functions if available.
- Keep code readable and modular.
- Match the existing style of the repo.

## R / analysis rules
- If the project uses `renv`, do not change `renv.lock` unless dependency changes are required.
- If randomness is used, set or preserve seeds where appropriate.
- Keep scripts reproducible in a fresh session.
- Avoid hidden dependence on interactive workspace objects.
- Prefer explicit file reads/writes over implicit assumptions.

## Quarto / R Markdown rules
- Keep chunk labels stable unless necessary.
- Do not rename figures, tables, or output files unless requested.
- If a report changes, make sure the narrative still matches the actual results.
- Preserve captions, section structure, and cross-references where possible.

## Simulation / modeling rules
- Preserve current simulation design unless the task asks to change it.
- Do not change sample sizes, burn-in, priors, tuning parameters, or truth definitions without documenting it.
- If posterior summaries are changed, clearly state whether they are posterior mean, posterior median, pointwise summaries, or summaries from precomputed outputs.
- If plots compare estimated vs true values, verify both are on the same scale and represent the same quantity.

## Review rules
Follow `REVIEW.md`.

## Completion rules
Before marking a task complete, follow `CHECK.md`.

## Final response format
When summarizing completed work, include:
1. What changed
2. Why it changed
3. How it was validated
4. Any warnings, limitations, or follow-up items
