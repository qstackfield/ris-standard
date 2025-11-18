# RIS Benchmark Guide
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

The RIS Benchmark Guide defines the procedures, datasets, tools, and statistical methods required to execute a complete reasoning integrity benchmark in alignment with the Reasoning Integrity Standard (RIS). This guide is operational and informative. It is intended for:

- evaluation teams  
- auditors  
- model developers  
- enterprise governance teams  

The goal is to ensure that RIS evaluations are reproducible, comparable, and conducted under controlled conditions.

---

# 2. Benchmark Objectives

Benchmarks are designed to:

- measure stability, coherence, drift, variance, and boundary adherence  
- classify systems according to RIS levels  
- detect sources of instability or interference  
- validate governance and operational controls  
- provide evidence for conformance statements  

Benchmarks SHALL follow RIS Section 9 evaluation methodology.

---

# 3. Benchmark Environment Setup

## 3.1 System Isolation

Benchmarking SHALL be conducted in an isolated environment where:

- model settings are fixed  
- external context is controlled  
- no adaptive memory persists across runs  
- agents or tools are restricted to defined boundaries  

## 3.2 Hardware and Infrastructure

Document:

- CPU or GPU model  
- memory  
- inference accelerator settings  
- cloud or local environment  

Hardware differences MUST be documented to avoid evaluation drift.

## 3.3 Inference Configuration

Inference parameters MUST be consistent across all samples:

- temperature  
- top-p  
- frequency penalty  
- system messages  
- prompt templates  
- context window size  

Any change invalidates comparisons.

---

# 4. Building the Benchmark Prompt Set

RIS benchmarking requires two prompt categories:

- baseline prompts  
- perturbation prompts  

## 4.1 Baseline Prompt Requirements

A baseline prompt set SHALL include:

- 50 or more prompts for general-purpose models  
- 20 or more for domain-specific systems  
- reasoning tasks  
- multi-step problems  
- conceptual reasoning  
- comparison tasks  
- structured decision problems  

Prompts SHOULD vary by domain difficulty.

## 4.2 Perturbation Prompt Requirements

Each selected baseline prompt MUST have at least 10 perturbations.

Perturbations MUST preserve meaning while varying:

- syntax  
- structure  
- neutral phrasings  
- synonyms  
- reordering of clauses  

Example:

Baseline:  
"Explain the impact of supply shocks on inflation."

Perturbations:  
"Describe how supply disruptions influence inflation."  
"How do supply-side constraints affect inflation rates?"  

---

# 5. Sampling Procedures

## 5.1 Repeated Inference Sampling

For each baseline prompt:

- collect at least 25 repeated samples  
- do not modify system prompt  
- do not modify settings  
- do not allow memory accumulation  

Repeated sampling is used for:

- chain stability  
- semantic coherence  
- drift sensitivity  
- variance envelope calculations  

## 5.2 Perturbation Sampling

For each perturbation prompt:

- collect at least 10 samples  
- keep all parameters identical  

This identifies:

- robustness  
- structural drift  
- semantic drift  

---

# 6. Computing Metrics

RIS requires metrics defined in Section 5.  
This guide details how to compute them.

## 6.1 Chain Stability

Compute pairwise similarity between reasoning-structure representations.

Example procedure:

1. Extract or infer reasoning structure.  
2. Compute similarity(Ri, Rj) for all pairs.  
3. Average across all pairs.  

Higher stability indicates stronger structural consistency.

## 6.2 Semantic Coherence

Compute embedding-based similarity using:

- cosine similarity  
- semantic clustering  
- conceptual topic overlap  

Steps:

1. Embed all outputs.  
2. Compute pairwise cosine similarity.  
3. Average results.  

## 6.3 Drift Sensitivity

Compute variance over time:

1. Partition samples into sequential windows.  
2. Compute mean stability and coherence per window.  
3. Compute change across windows:

    drift = variance(stability) + variance(coherence)

## 6.4 Variance Envelope Compliance

Define envelope thresholds using baseline:

- stability range  
- coherence range  
- drift upper bound  

Compliance = samples within envelope / total samples

## 6.5 Boundary Adherence

Evaluate:

- unauthorized semantic domain expansion  
- context leakage  
- tool or agent influence  
- retrieval contamination  
- multi-task interference  

Boundary evidence MUST be documented.

---

# 7. Drift Analysis Procedures

## 7.1 Structural Drift Analysis

Compare reasoning structure sequences for:

- reordering  
- step divergence  
- missing or added transitions  

## 7.2 Semantic Drift Analysis

Track conceptual shifts:

- topic changes  
- inconsistent meaning  
- unexpected contradictions  

## 7.3 Temporal Drift Analysis

Divide evaluation into intervals:

- interval 1  
- interval 2  
- interval 3  

Compute stability and coherence per interval.  
Monitor for downward trends.

## 7.4 Interference-Based Drift

Induce controlled interference:

- tool responses  
- retrieval variance  
- agent-to-agent interaction  

Check for abnormal reasoning changes.

---

# 8. Variance Envelope Construction

To construct a variance envelope:

1. Compute stability and coherence for baseline samples.  
2. Compute mean and standard deviation.  
3. Define envelope thresholds:

    lower = mean - k * stdev  
    upper = mean + k * stdev  

k typically ranges from 1.0 to 1.5 depending on domain risk.

For RIS-4, envelope MUST be narrow and stable.

---

# 9. Boundary and Interference Testing

Boundary-testing prompts SHOULD include:

- prohibited context  
- unrelated domains  
- out-of-scope tasks  
- external references  

Measure whether the system:

- leaks context  
- expands domain  
- uses information not supplied  
- depends improperly on previous prompts  

Interference testing SHOULD include:

- alternate tool responses  
- modified retrieval snippets  
- agent perturbations  

---

# 10. Producing Benchmark Artifacts

Required benchmark deliverables:

- raw repeated inference samples  
- perturbation sample sets  
- metrics tables  
- drift graphs  
- variance envelope charts  
- boundary violation logs  
- interference test outputs  

All artifacts MUST be preserved.

---

# 11. Recommended Tools and Methods

RIS does not mandate tools, but recommends:

- embedding models for similarity  
- statistical libraries for variance  
- deterministic sampling scripts  
- structured datasets for prompt sets  
- reasoning parsers (if available)  
- hashing for ledger integrity  

Scripts SHOULD be version-controlled.

---

# 12. Benchmark Execution Checklist

Evaluators SHOULD complete the following:

- environment prepared and documented  
- all inference parameters frozen  
- baseline prompts assembled  
- perturbation prompts constructed  
- sampling completed  
- metrics computed  
- drift analysis performed  
- boundary tests executed  
- interference tests executed  
- evidence archived  
- evaluation report drafted  
- conformance document prepared  

---

# 13. Final Notes

This benchmark guide is designed to ensure:

- reproducibility  
- transparency  
- comparability across models and organizations  

It is intended to support:

- RIS audits  
- internal governance  
- enterprise risk programs  
- research benchmarking  
- model evaluation frameworks  

RIS benchmarking provides organizations with a reliable foundation for evaluating the integrity of reasoning in AI systems.

---
