# AI-Assisted Automatic Control Course Experiments

This repository contains coursework materials for automatic control experiments. It focuses on temperature step-response processing, first-order plus dead-time model identification, and PID tuning with intelligent optimization algorithms.

## Overview

- Fit a first-order plus dead-time model from experimental temperature data.
- Design and simulate PID control for the identified model.
- Optimize PID parameters with particle swarm optimization and genetic algorithms.
- Store assignment documents, reports, datasets, and result images.

## Repository Structure

```text
.
+-- code/        # MATLAB scripts
+-- data/        # Experimental datasets
+-- picture/     # Result and reference images
+-- coursework-documents/  # Course documents and reports
```

Main scripts:

- `code/fitting.m`: reads temperature data, smooths the response, and identifies a transfer function.
- `code/PID.m`: tunes PID parameters with particle swarm optimization.
- `code/PID_GA.m`: tunes PID parameters with a genetic algorithm.

## Requirements

Run the project with MATLAB. The scripts expect these toolboxes:

- Control System Toolbox
- Global Optimization Toolbox

## Usage

From the repository root, run:

```powershell
matlab -batch "cd('data'); addpath('../code'); fitting"
matlab -batch "cd('code'); PID"
matlab -batch "cd('code'); PID_GA"
```

Note: `fitting.m` reads `temperature.csv` from the current working directory. Run it from `data/`, or update the script to use an explicit data path.

## Data and Outputs

`data/temperature.csv` contains the temperature response dataset. The MATLAB scripts print model parameters, PID parameters, and dynamic performance metrics, then generate response plots. Screenshots or exported figures should be stored in `picture/`.

## Contributing

Before submitting changes, run the affected MATLAB scripts and record important outputs. See `AGENTS.md` for contributor guidelines.
