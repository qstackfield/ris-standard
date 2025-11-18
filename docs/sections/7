# 7. Scoring and Conformance

## 7.1 Overview

This section defines the scoring methodology and conformance criteria used to determine a system's RIS level. Scoring integrates quantitative metrics from the measurement framework with mandatory control requirements. A system's RIS classification is based on both:

1. composite reasoning integrity score, and  
2. demonstrated compliance with required RIS controls.

A system SHALL NOT be assigned a RIS level solely based on scoring metrics without meeting corresponding control requirements.

---

# 7.2 Composite Reasoning Integrity Score

The composite score is calculated using weighted metrics defined in Section 5:

- Chain Stability: 30 percent  
- Semantic Coherence: 25 percent  
- Drift Sensitivity: 20 percent  
- Variance Envelope Compliance: 15 percent  
- Governance Boundary Adherence: 10 percent  

Each metric yields a value between 0.00 and 1.00.  
The weighted sum produces the final composite reasoning integrity score.

The composite score is used to determine *eligibility* for a RIS level, but SHALL NOT be used to determine *final classification* without control verification.

---

# 7.3 Metric Weighting

The rationale for metric weighting is as follows:

- Chain Stability (30 percent): foundational indicator of structural reasoning reliability.  
- Semantic Coherence (25 percent): ensures reasoning maintains consistent meaning.  
- Drift Sensitivity (20 percent): predicts long-term stability under repetition.  
- Variance Envelope Compliance (15 percent): ensures bounded divergence.  
- Governance Boundary Adherence (10 percent): required for operational trust and safety.

These weights SHALL remain consistent across RIS versions unless updated in a future amendment.

---

# 7.4 Eligibility Thresholds for RIS Levels

Eligibility thresholds based on composite score:

- 0.00–0.40: RIS-0  
- 0.41–0.60: RIS-1  
- 0.61–0.75: RIS-2  
- 0.76–0.89: RIS-3  
- 0.90–1.00: RIS-4  

Meeting the scoring threshold does not guarantee assignment to that RIS level.  
The system SHALL also satisfy the control requirements designated for that level.

---

# 7.5 Control-Based Conformance Requirements

The following table defines minimum control conformance for each RIS level:

| RIS Level | Required Controls |
|----------|-------------------|
| RIS-0 | No controls required |
| RIS-1 | Optional controls only |
| RIS-2 | All RS-1, SC-1, DR-1, VE-1, GB-1 controls |
| RIS-3 | All RIS-2 controls plus RS-2, SC-2, DR-2, VE-2, GB-2, OP-2 |
| RIS-4 | All RIS-3 controls plus RS-3, SC-3, DR-3, VE-3, GB-3, OP-3, OP-4 |

A system SHALL NOT be classified above RIS-2 unless all mandatory controls for RIS-3 are satisfied.  
A system SHALL NOT be classified above RIS-3 unless all mandatory controls for RIS-4 are satisfied.

---

# 7.6 Evidence Requirements

To support a RIS classification, the following evidence MUST be produced:

1. Measurement Framework Results  
   - repeated inference sample outputs  
   - controlled perturbation outputs  
   - variance compliance reports  
   - drift sensitivity analyses  

2. Control Implementation Evidence  
   - documentation of stability, coherence, drift, variance, and boundary controls  
   - operational integrity documentation  
   - governance boundary definitions  

3. Audit Logs  
   - reasoning ledger entries or equivalent reports  
   - evaluation logs  
   - anomaly and boundary violation logs  

4. Configuration Snapshots  
   - inference parameters  
   - environmental settings  
   - prompt templates  
   - tool access or agent configuration  

The evaluator SHALL verify all evidence before assigning a RIS level.

---

# 7.7 Conformance Determination Process

A system SHALL undergo the following steps to determine conformance:

1. Preparation  
   - define evaluation conditions  
   - document configuration  
   - establish invariants  

2. Data Collection  
   - perform repeated inference sampling  
   - perform controlled perturbation sampling  
   - log reasoning behavior  

3. Metric Calculation  
   - compute each metric independently  
   - calculate composite reasoning integrity score  

4. Control Verification  
   - confirm implementation and operation of required controls  
   - identify gaps or violations  

5. Level Assignment  
   - determine eligible RIS level based on composite score  
   - determine achievable RIS level based on control compliance  
   - final level SHALL be the lower of the two  

6. Report Generation  
   - produce a formal evaluation report  
   - document findings, score, control status, and assignment  

7. Certification  
   - issue a RIS Conformance Statement  
   - assign classification validity period  

---

# 7.8 Handling of Violations and Exceptions

If a system violates a mandatory control during evaluation:

- it SHALL be classified at the highest RIS level for which all mandatory controls are satisfied  
- violations MUST be documented with supporting evidence  
- systems MAY undergo remediation and reassessment  

Exceptions for SHOULD and MAY controls SHALL NOT affect level assignment if mandatory controls are met.

---

# 7.9 Reassessment Requirements

RIS conformance SHALL be reassessed when:

- the underlying model is updated  
- training data or fine-tuning changes  
- new tools or agents are added  
- governance boundaries change  
- drift or instability trends are detected in production  
- a significant degradation in metrics occurs  
- system behavior changes under load  

Reassessment MAY be performed more frequently based on organizational or regulatory requirements.

---

# 7.10 Validity of RIS Classification

RIS classification is valid for a period of:

- 12 months for general LLM systems  
- 6 months for agentic or tool-integrated systems  
- 3 months for safety-critical systems  

After expiration, the system SHALL be reevaluated to maintain a RIS classification.

---

# 7.11 Publication and Reporting

Organizations MAY publish:

- their RIS level  
- their composite score  
- high-level findings  

However, detailed logs, inference samples, and proprietary evaluation data SHOULD only be disclosed under NDA or regulatory requirement.

RIS conformance SHALL NOT be claimed without formal assessment.

---
