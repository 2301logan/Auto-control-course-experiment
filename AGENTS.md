# Repository Guidelines

## Project Structure & Module Organization

This repository contains MATLAB coursework for automatic control experiments.

- `code/` holds MATLAB scripts: `fitting.m` for response fitting, `PID.m` for particle-swarm PID tuning, and `PID_GA.m` for genetic-algorithm PID tuning.
- `data/` stores input datasets, currently `temperature.csv`.
- `picture/` stores generated or referenced images and figures.
- The Chinese-named coursework folder contains assignment descriptions, reports, and source documents. Keep large binary report files there rather than mixing them into `code/`.

## Build, Test, and Development Commands

There is no package build step. Run scripts from MATLAB with paths set so data files resolve correctly:

```powershell
matlab -batch "cd('data'); addpath('../code'); fitting"
matlab -batch "cd('code'); PID"
matlab -batch "cd('code'); PID_GA"
```

`fitting.m` reads `temperature.csv` from the current directory, so run it from `data/` or update the script path deliberately. `PID.m` uses `particleswarm`; `PID_GA.m` uses `ga`, so the Global Optimization Toolbox is expected.

## Coding Style & Naming Conventions

Use MATLAB script style already present in `code/`: clear section headers with `%%`, lowercase descriptive variable names for scalar parameters, and concise inline comments for equations or control assumptions. Use 4-space indentation inside functions and control blocks. Prefer meaningful filenames such as `PID_GA.m` or `fitting.m`; avoid temporary names like `untitled.m` for committed work.

Keep text files in UTF-8 when editing non-English comments or report notes. Avoid committing MATLAB autosave files (`*.asv`) unless there is a specific recovery reason.

## Testing Guidelines

No automated tests are currently defined. Before submitting changes, smoke-test the affected script with `matlab -batch` and confirm it completes without errors, prints expected model or PID parameters, and produces figures where applicable. For algorithm changes, record key outputs such as `K`, `tau`, `T`, `Kp`, `Ki`, and `Kd` in the PR description.

## Commit & Pull Request Guidelines

Recent commits use short conventional-style prefixes, for example `docs: ...`, `refactor: ...`, and `docx: ...`. Follow that pattern with a concise summary, such as `code: tune PID search bounds`.

Pull requests should describe the experiment or report changed, list commands run, mention toolbox requirements, and include screenshots or exported figures when visual output changes.
