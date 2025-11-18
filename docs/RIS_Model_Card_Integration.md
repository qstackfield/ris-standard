# RIS Model Card Integration Template
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Model Identification

**Model Name:**  
**Version / Build:**  
**Release Date:**  
**Owner / Maintainer:**  
**Contact:**  

---

# 2. Model Overview

Provide a description of the model’s purpose, architecture, and intended use cases.

**2.1 Description**  
(General model capabilities)

**2.2 Intended Use Cases**  
(supported domains, acceptable applications)

**2.3 Out-of-Scope Use Cases**  
(applications explicitly not supported)

**2.4 System Dependencies**  
(agents, tools, retrieval systems, memory systems, orchestration frameworks)

---

# 3. RIS Classification Summary

This section presents the model’s current reasoning integrity classification.

**RIS Level Assigned:**  
(RIS-0, RIS-1, RIS-2, RIS-3, or RIS-4)

**Date of Last RIS Evaluation:**  
**Evaluation Performed By:**  
**Evaluation Valid Until:**  

**Composite Reasoning Integrity Score:**  
(weighted average based on RIS metrics)

**Conformance Statement Location:**  
(link or reference to the completed RIS Conformance Statement)

**Evaluation Report Location:**  
(link or reference to the RIS Evaluation Report)

---

# 4. RIS Metrics Summary

Summaries of required RIS metrics:

## 4.1 Chain Stability  
(mean score, variance, lowest/highest stability values)

## 4.2 Semantic Coherence  
(mean score, outliers, contradiction detection notes)

## 4.3 Drift Sensitivity  
(drift score, patterns over time)

## 4.4 Variance Envelope Compliance  
(percentage of samples within envelope)

## 4.5 Governance Boundary Adherence  
(boundary violations observed, if any)

---

# 5. RIS Risk Profile

A brief assessment aligned with RIS Section 8 risk models.

**5.1 Structural Drift Risk:**  
(Low / Moderate / High)

**5.2 Semantic Drift Risk:**  
(Low / Moderate / High)

**5.3 Temporal Stability Risk:**  
(Low / Moderate / High)

**5.4 Interference Risk:**  
(Low / Moderate / High)

**5.5 Boundary Violation Risk:**  
(Low / Moderate / High)

**5.6 Degradation Risk:**  
(Low / Moderate / High)

---

# 6. Evaluation Environment

Document evaluation conditions used to compute RIS metrics.

**6.1 Inference Parameters:**  
(temperature, top-p, penalties, context window, system prompts)

**6.2 Model Runtime Environment:**  
(hardware, GPUs, cloud environment, framework versions)

**6.3 Operational State:**  
(single-turn vs. multi-turn, memory usage, tools enabled/disabled)

---

# 7. Governance Integration

Document how RIS fits into governance processes.

**7.1 Deployment Requirements:**  
(e.g., “Model must be RIS-3 or higher for production use”)

**7.2 Monitoring Requirements:**  
(drift monitoring, variance checks, reevaluation frequency)

**7.3 Approval Workflow:**  
(model review board criteria, internal audit requirements)

**7.4 Retention of Evidence:**  
(location of drift logs, baseline datasets, ledger records)

---

# 8. Known Limitations

Document reasoning behavior limitations, such as:

- unstable reasoning under certain prompt patterns  
- sensitivity to specific perturbations  
- high drift in multi-turn workflows  
- boundary sensitivity when tool calls change  
- inconsistent RAG dependence  

Include mitigation strategies if applicable.

---

# 9. Reassessment and Update Schedule

Specify the organization’s planned evaluation cadence.

Examples:

- general models: every 12 months  
- agentic models: every 6 months  
- safety-critical systems: every 3 months  
- or upon model retraining or version change  

---

# 10. Version History

Document RIS classification changes over time.

Example:

- v1.0.0 — RIS-3 (initial evaluation)  
- v1.1.0 — RIS-3 (no significant drift)  
- v2.0.0 — RIS-4 (after retraining)  

---

# 11. Appendices (Optional)

Include:

- drift charts  
- stability graphs  
- raw metrics samples  
- evaluation dataset examples  
- additional disclosures  

---

# End of Model Card Integration Template
