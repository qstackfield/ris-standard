# RIS Quickstart Guide
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This Quickstart Guide explains how to begin using the Reasoning Integrity Standard (RIS) in under 10 minutes.  
It is intended for organizations, researchers, and engineering teams who need a simple, high-level process for applying RIS to an LLM, agent, or AI system.

This guide does not replace the full standard.  
It provides a fast-path workflow for initial adoption.

---

# 2. Basic Requirements

To perform a RIS evaluation you will need:

- access to the LLM or agent system under evaluation  
- ability to run repeated inference with fixed parameters  
- ability to save output samples  
- basic scripting or data analysis tools (Python recommended)  
- the RIS evaluation templates (included in this repository)  

No special infrastructure is required.

---

# 3. Quickstart Workflow Summary

RIS evaluation involves the following steps:

1. Prepare evaluation environment  
2. Build prompt sets  
3. Run repeated sampling  
4. Run perturbation sampling  
5. Compute metrics  
6. Identify drift, variance, and boundary results  
7. Complete the Evaluation Report  
8. Complete the Conformance Statement  
9. Assign a RIS level  

Each step is described below.

---

# 4. Step-by-Step Instructions

## Step 1: Prepare Evaluation Environment

- Freeze inference parameters (temperature, top-p, etc.).  
- Disable adaptive memory or persistent state.  
- Fix system instructions or agent configuration.  
- Document all environment details.

All evaluations MUST be performed with identical settings.

---

## Step 2: Build Baseline Prompt Set

Select:

- at least 50 baseline prompts (general-purpose models)  
- at least 20 prompts (domain-specific models)

Prompts should cover:

- reasoning  
- multi-step tasks  
- analytical queries  
- comparative questions  
- conceptual understanding  

Example:

    "Explain the impact of market consolidation on competition."

---

## Step 3: Build Perturbation Prompt Set

For each baseline prompt selected for perturbation:

- create at least 10 semantically equivalent variations  

Variations may include:

- synonym substitutions  
- reordering clauses  
- minor phrasal changes  

Example:

    Baseline: "Explain how supply shocks affect inflation."
    Perturbation: "Describe how supply disruptions influence inflation."

---

## Step 4: Run Repeated Inference Sampling

For each baseline prompt:

- generate at least 25 repeated samples  
- keep all parameters identical  
- store outputs in structured format (JSON, CSV, etc.)

These samples support:

- chain stability measurement  
- semantic coherence  
- drift sensitivity  
- variance compliance  

---

## Step 5: Run Perturbation Sampling

For each perturbation prompt:

- generate at least 10 samples  
- use the same parameters as baseline sampling  

This evaluates robustness and drift under controlled variation.

---

## Step 6: Compute RIS Metrics

The following metrics MUST be calculated:

- Chain Stability  
- Semantic Coherence  
- Drift Sensitivity  
- Variance Envelope Compliance  
- Governance Boundary Adherence  

Metric definitions are located in RIS Section 5.  
You may compute metrics using:

- Python statistical analysis  
- embedding-based similarity  
- JSON-based analysis scripts  
- internal or external evaluation tools  

---

## Step 7: Analyze Drift, Variance, and Boundary Behavior

Inspect results for:

- structural or semantic divergence  
- temporal degradation  
- boundary violations (use of unauthorized context or domain)  
- interference-based instability (tool, RAG, or agent effects)

Document all findings for the final report.

---

## Step 8: Complete the RIS Evaluation Report

Use:

`RIS_Evaluation_Report_Template.md`

Document:

- metrics  
- drift and variance results  
- boundary adherence  
- violations  
- environment details  
- sampling methodology  

This becomes the official audit record.

---

## Step 9: Complete the RIS Conformance Statement

Use:

`RIS_Conformance_Statement.md`

Document:

- composite score  
- control compliance  
- evidence summary  
- final RIS level assigned  

This becomes the organization’s self-attestation or audit deliverable.

---

# 5. Assigning a RIS Level

Use the rules in RIS Section 7:

- composite score threshold  
- mandatory control compliance  
- absence of high-severity risks  
- documented evidence  

The final RIS level MUST be the lower of:

- level qualified by score  
- level qualified by control compliance  

---

# 6. Next Steps

After initial evaluation:

- schedule periodic reassessment  
- integrate RIS controls into development workflows  
- build internal governance procedures  
- optionally integrate LCAC or other tooling to simplify evaluation  

---

# 7. Additional Resources

Included in this repository:

- RIS Specification (full)  
- Benchmark Guide  
- Evaluation Report Template  
- Conformance Statement Template  
- Glossary  
- Change Log  

For questions or contributions:  
Atom Labs Standards Division  
qstackfield@seedcore.io

---
