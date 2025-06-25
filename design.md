#  Design Document

## 1. Overview

This project applies Echo State Networks to forecast weather-like patterns using real-world time series data.
It builds on a previous Lorenz-96 experiment and extends it to evaluate model performance on real atmospheric measurements.

## 2. Goals

- Apply ESN to forecast weather-like patterns using real-world time series data


## 3. Project Structure

```
.github/workflows                # continuous integration (CI) with Github Actions
docs/                                     # docs managed with sphinx
notebooks/                           # jupyter notebooks are saved here -- these should sync with Google Colab
src/
    <project-package-name>/
        models/
         __init__.py
        <ibrary_code.py>
        ...
    train.py                            # the main train script
    eval.py                             # the main evaluation script
tests/
    __init__.py
    conftest.py                      # configures pytest setup
    test_<module>.py          # test for the correspding module in the library
    ...
CONTRIBUTING.md           # Who is welcome to contribute? How do they onboard to the project?
.pre-commit-config.yaml
.gitignore
README.md
LICENSE
pyproject.toml
uv.lock
```
## 4. Data

source: ERA5?
format: ??
preprocessing: ??

## 5. Architecture

Baseline: Echo State Network (ESN) for chaotic forecasting

## 6. Tools & Libraries

xarray, numpy, scipy, matplotlib

jax, uv, pre-commit

pytest for testing

## 7. Team Roles

Katie:

Evan:

Alex:
- Code Review
- Design guidance
- Model development

## 8. Timeline & Milestones

chatgpt says
**Week 1–3: Foundations**
- Read papers and docs on:
  - Echo State Networks (ESNs)
  - NeuralGCM and Dinosaur
  - ERA5 reanalysis dataset
  - Xarray and UV project setup
- Set up GitHub repo, virtual environment, and project structure
- Begin collecting notes and questions in the design doc

**Week 4-5: Reproduction & Exploration**
- Try to replicate simplified experiments from NeuralGCM or Dinosaur
- Load and explore weather datasets (e.g., ERA5 samples or toy data)

**Week 6-7: Code Migration & Baseline Evaluation**
- Migrate code from original Lorenz-96 or previous ESN project
- Build minimal PDE simulator (e.g., Lorenz-96) in a reusable module
- Create an evaluation script to test baseline models:
  - Constant predictor
  - Linear/persistence predictor
- Use these simple models to establish weak baselines
- Compare predictions to simulated trajectories using RMSE or MAE

**Week 7+: Modeling and Evaluation**
- Train and test ESN on simulated data
- Compare to baselines (GRU, etc.)
- Analyze long-term vs. short-term prediction accuracy
- Document results and insights
- Train and test ESN on real-world data (ERA5)

## 9. Open Questions

- Is it the size of the data or the size of the model that is the limiting factor for long-term predictions?
- Is it useful to have a model that can make short-term predictions more efficiently than what's currently used?
