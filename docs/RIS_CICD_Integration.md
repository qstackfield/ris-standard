# RIS CI/CD Integration Example
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This document provides a practical example of how to integrate the Reasoning Integrity Standard (RIS) into a CI/CD pipeline.

The goal is to ensure that changes to:

- models
- agents
- tools
- retrieval systems
- prompt templates

are evaluated for reasoning integrity before deployment.

RIS integration in CI/CD is similar to:

- unit tests
- security scans
- static analysis
- policy checks

If RIS checks fail, deployment is blocked.

---

# 2. Pipeline Overview

A RIS-aware pipeline typically performs:

1. Environment setup  
2. Baseline and perturbation sampling  
3. Metric computation  
4. Drift, variance, and boundary checks  
5. RIS level classification  
6. Pass/fail gating based on minimum level  
7. Artifact generation (reports, logs, metrics)

Organizations define a minimum acceptable level, such as:

- “Model must achieve RIS-3 or higher to deploy to production.”

---

# 3. Prerequisites

To integrate RIS into CI/CD, an organization needs:

- access to the model or agent under evaluation
- ability to run repeated inference non-interactively
- scripts or tools to:
  - generate samples
  - compute RIS metrics
  - decide RIS level
- the RIS Benchmark Guide
- a CI/CD system (GitHub Actions, GitLab CI, Jenkins, Azure DevOps, etc.)

LCAC or other tools may optionally be used, but RIS does not require them.

---

# 4. Example Directory Structure

A recommended layout in your repository:

    /ris-ci/
        run_sampling.py
        compute_metrics.py
        evaluate_ris_level.py
        config.yaml
        report/
            samples.json
            metrics.json
            ris_report.md

- `run_sampling.py`:
  - runs repeated and perturbation sampling
- `compute_metrics.py`:
  - computes stability, coherence, drift, variance metrics
- `evaluate_ris_level.py`:
  - reads metrics
  - computes composite score
  - maps to RIS level
  - writes a simple pass/fail flag for the pipeline

---

# 5. Example GitHub Actions Workflow (RIS Gate)

Below is an example of a GitHub Actions workflow that:

- runs RIS sampling
- computes metrics
- evaluates the RIS level
- blocks deployment if the system does not reach at least RIS-3

    name: RIS Evaluation

    on:
      push:
        branches: [ "main" ]
      pull_request:

    jobs:
      ris_check:
        runs-on: ubuntu-latest

        steps:
          - name: Checkout repository
            uses: actions/checkout@v3

          - name: Set up Python
            uses: actions/setup-python@v4
            with:
              python-version: "3.10"

          - name: Install dependencies
            run: |
              pip install -r requirements.txt

          - name: Run RIS sampling
            run: |
              python ris-ci/run_sampling.py \
                --config ris-ci/config.yaml \
                --output ris-ci/report/samples.json

          - name: Compute RIS metrics
            run: |
              python ris-ci/compute_metrics.py \
                --input ris-ci/report/samples.json \
                --output ris-ci/report/metrics.json

          - name: Evaluate RIS level
            run: |
              python ris-ci/evaluate_ris_level.py \
                --metrics ris-ci/report/metrics.json \
                --output ris-ci/report/ris_report.md \
                --min-level RIS-3

          - name: Upload RIS report artifact
            uses: actions/upload-artifact@v3
            with:
              name: ris-report
              path: ris-ci/report/

          - name: Enforce RIS level gate
            run: |
              if grep -q "RIS LEVEL: FAIL" ris-ci/report/ris_report.md; then
                echo "RIS evaluation failed. Deployment blocked."
                exit 1
              else
                echo "RIS evaluation passed."
              fi

---

# 6. Example Script Responsibilities

## 6.1 run_sampling.py

Responsibilities:

- load config (prompts, counts, parameters)
- run repeated inference for each baseline prompt
- run perturbation sampling
- save output samples to a file (for example, `samples.json`)

Example behavior (pseudo-code):

    - read config.yaml
    - for each baseline prompt:
        - run N repeated samples
    - for each perturbation prompt:
        - run M samples
    - write all results to samples.json

## 6.2 compute_metrics.py

Responsibilities:

- read samples
- compute:
  - chain stability
  - semantic coherence
  - drift sensitivity
  - variance envelope compliance
  - boundary adherence signals (if available)
- output metrics as JSON (for example, `metrics.json`)

Example fields:

    {
      "chain_stability": 0.88,
      "semantic_coherence": 0.90,
      "drift_sensitivity": 0.12,
      "variance_compliance": 0.96,
      "boundary_violations": 0
    }

## 6.3 evaluate_ris_level.py

Responsibilities:

- read `metrics.json`
- compute composite score using RIS weighting
- derive candidate RIS level based on score thresholds
- adjust based on control or boundary failures if modeled
- write a human-readable summary to `ris_report.md`

Example output:

    RIS EVALUATION REPORT
    ---------------------
    Composite Score: 0.82
    Candidate Level: RIS-3
    Boundary Violations: 0
    Final RIS Level: RIS-3
    RIS LEVEL: PASS

If the level is below `--min-level`, it MUST output:

    RIS LEVEL: FAIL

for the pipeline enforcement step to catch.

---

# 7. Gating Rules

Organizations SHOULD define:

- minimum RIS level to deploy (for example, RIS-3)
- environments where RIS is mandatory (for example, staging and production)
- exceptions process (for example, pre-production experiments)

Example policy:

- production deployment:
  - required RIS level: RIS-3 or RIS-4
- internal-only tools:
  - minimum RIS level: RIS-2
- research or prototype branches:
  - RIS optional

---

# 8. Integration With Other CI/CD Systems

The same pattern can be applied to:

- GitLab CI (`.gitlab-ci.yml`)
- Jenkins pipelines
- Azure DevOps pipelines
- CircleCI, etc.

Typical steps:

1. Add a job/stage for RIS evaluation  
2. Run sampling and metrics scripts  
3. Parse results for PASS/FAIL signal  
4. Fail the job if RIS criteria are not met  

---

# 9. Best Practices

- Run RIS checks on pull requests that alter:
  - model versions
  - prompts
  - agents
  - tools
  - RAG sources
- Keep evaluation configs version-controlled
- Store RIS reports as build artifacts
- Periodically review RIS metrics even for passing builds
- Use RIS together with other quality and safety checks

---

# 10. Summary

RIS CI/CD integration ensures that:

- reasoning integrity is evaluated continuously
- unstable models are blocked from deployment
- changes to AI systems trigger automated governance checks

By treating RIS evaluation as a first-class pipeline stage, organizations can align reasoning integrity with the same rigor applied to testing, security, and reliability.

---
