# RIS Evaluation Report Template
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Report Metadata

**Report Title:**  
**System Name:**  
**System Version:**  
**Model(s) Evaluated:**  
**Model Version / Build:**  
**Organization:**  
**Evaluator Name:**  
**Evaluation Date:**  
**Evaluation Location / Environment:**  

**Requested RIS Level:**  
**Final RIS Level Assigned:**  

---

# 2. System Description

Provide a detailed description of the system evaluated.

**2.1 System Overview**  
(Architecture, components, agents, tools, RAG sources, orchestration frameworks)

**2.2 Primary Use Cases**  
(Decision-support, workflows, automation, analysis, etc.)

**2.3 Operational Context**  
(Environment, deployment type, integrations)

**2.4 Reasoning Mode**  
(single-turn, multi-turn, agentic, tool-augmented, retrieval-augmented)

---

# 3. Evaluation Environment

**3.1 Hardware and Software Environment**  
(servers, GPUs, cloud settings, OS, dependencies)

**3.2 Inference Parameters**  
(temperature, top-p, frequency penalty, system prompts, context size)

**3.3 Configuration Settings**  
(model config, agent settings, allowed tools, retrieval limits)

**3.4 Environmental Invariants**  
(parameters that remained constant as required by RIS Section 9)

---

# 4. Evaluation Methodology

**4.1 Evaluation Framework Used**  
(Refer to RIS Section 9)

**4.2 Prompt Sets Used**  
- Number of baseline prompts  
- Number of perturbation prompts  
- Domain(s) covered  
- Difficulty distribution  

**4.3 Sampling Methodology**  
- Number of repeated inference samples  
- Number of perturbation samples  
- Testing intervals (if temporal evaluation performed)

**4.4 Baseline Establishment**  
(Describe how the baseline was created and validated)

---

# 5. Metrics and Results

## 5.1 Chain Stability

- stability score (mean)  
- stability score (min/max)  
- deviation patterns  
- compliance with variance envelope  

## 5.2 Semantic Coherence

- coherence score (mean)  
- conflicting or inconsistent samples  
- semantic retention analysis  

## 5.3 Drift Sensitivity

- drift score (mean)  
- drift trend over iterations  
- drift triggered by perturbations  
- structural vs semantic drift  

## 5.4 Variance Envelope Compliance

- total samples  
- samples within envelope  
- samples outside envelope  
- compliance percentage  

## 5.5 Governance Boundary Adherence

- boundary violations observed  
- types of violations (semantic, contextual, tool-induced, agent-induced)  
- severity and frequency  

---

# 6. Drift and Variance Analysis

**6.1 Drift Characterization**  
(structural drift, semantic drift, temporal drift, interference drift)

**6.2 Drift Thresholds**  
(document thresholds used and whether exceeded)

**6.3 Drift Events**  
(list and describe any drift events detected)

**6.4 Longitudinal Trends (if applicable)**  
(temporal stability, degradation, cycle patterns)

**6.5 Variance Envelope Breakdown**  
(how envelope was determined, deviation statistics)

---

# 7. Boundary and Interference Analysis

**7.1 Governance Boundary Tests**  
(prompts, results, violations)

**7.2 Tool/Agent Interference Tests**  
(description of scenarios tested and outcomes)

**7.3 Retrieval/RAG Interference Tests**  
(if applicable)

**7.4 Multi-Agent Interaction Analysis**  
(if applicable)

---

# 8. Control Compliance Review

Provide compliance status for all applicable controls from RIS Section 6.

**Chain Stability Controls (RS)**  
- RS-1  
- RS-2  
- RS-3  

**Semantic Coherence Controls (SC)**  
- SC-1  
- SC-2  
- SC-3  

**Drift Resistance Controls (DR)**  
- DR-1  
- DR-2  
- DR-3  

**Variance Envelope Controls (VE)**  
- VE-1  
- VE-2  
- VE-3  

**Governance Boundary Controls (GB)**  
- GB-1  
- GB-2  
- GB-3  

**Operational Integrity Controls (OP)**  
- OP-1  
- OP-2  
- OP-3  
- OP-4  

Mark each as:  
Compliant / Non-Compliant / Not Applicable

---

# 9. Violations and Exceptions

**9.1 Violations Detected**  
(detail any control or requirement failures)

**9.2 Boundary Violations**  

**9.3 Drift or Variance Violations**  

**9.4 Exceptions to SHOULD or MAY Controls**  

**9.5 Severity and Risk Classification**  
(Refer to RIS Section 8)

---

# 10. Final Classification

**10.1 Composite Reasoning Integrity Score:**  
(weighted score)

**10.2 Score-Based Eligibility:**  
(level eligible for based on scoring)

**10.3 Control-Based Eligibility:**  
(level eligible for based on control compliance)

**10.4 Final RIS Level Assigned:**  

**10.5 Summary Justification:**  
(clear rationale for level assignment)

---

# 11. Recommendations and Corrective Actions

Provide evaluator recommendations regarding:

- improvements to drift controls  
- variance tightening  
- boundary enforcement  
- governance mode adjustments  
- sampling consistency improvements  
- agent or tool isolation  

Include remediation steps if requesting RIS-3 or RIS-4 upgrades.

---

# 12. Appendices

Append any relevant materials:

- raw inference samples  
- stability/coherence charts  
- drift graphs  
- variance analysis data  
- ledger or log excerpts  
- configuration snapshots  
- prompt sets used  
- evaluator notes  

---

# 13. Signatures

**Evaluator Name:**  
**Evaluator Title / Organization:**  
**Evaluator Signature:**  
**Date:**  

**System Owner Name:**  
**System Owner Signature:**  
**Date:**  

---

# 14. Legal Notice

Reasoning Integrity Standard (RIS) v1.0  
© 2025 Atom Labs. All Rights Reserved.

This report template is provided for use with RIS evaluations and may not be modified without attribution.

---
