# 10. Audit Guidelines

## 10.1 Overview

This section defines the audit requirements, evidence standards, assessment procedures, and validation criteria necessary to verify compliance with the Reasoning Integrity Standard (RIS). These guidelines ensure that evaluations are reliable, reproducible, and suitable for internal review, third-party certification, or regulatory oversight.

An auditor MAY be an internal reviewer, an external assessor, or an automated system. All auditors SHALL adhere to the requirements outlined in this section.

---

# 10.2 Audit Objectives

The objectives of a RIS audit are to:

1. verify the correctness and completeness of evaluation procedures  
2. validate metric calculations and composite reasoning integrity scores  
3. confirm implementation of mandatory controls  
4. detect deficiencies, violations, or risks  
5. ensure evidence sufficiency and traceability  
6. determine whether assigned RIS levels are justified  
7. produce a formal audit report documenting findings  

Audits SHALL NOT evaluate ethical, factual, or domain-specific correctness.

---

# 10.3 Audit Scope

The audit SHALL cover:

- evaluation methodology adherence  
- system configuration and invariants  
- reasoning integrity metrics  
- drift and variance analysis  
- control compliance  
- governance boundary enforcement  
- operational integrity  
- logged events and ledger entries  
- deviation or violation reports  

The audit MAY include additional areas depending on organizational, regulatory, or contractual requirements.

---

# 10.4 Evidence Requirements

Auditors SHALL review the following types of evidence:

## 10.4.1 Raw inference samples

- repeated inference outputs  
- perturbation outputs  
- temporal sampling outputs  
- tool-integrated outputs (if applicable)  

## 10.4.2 Metric calculations

- chain stability similarity data  
- semantic coherence scores  
- drift sensitivity calculations  
- variance envelope compliance results  
- boundary adherence results  

## 10.4.3 Configuration data

- inference parameters (temperature, top-p, etc.)  
- system settings  
- agent or tool configurations  
- environment variables  
- software versions  

## 10.4.4 Control implementation evidence

- governance boundary definitions  
- drift envelope definitions  
- stability and coherence controls  
- interference detection controls  
- audit logging mechanisms  

## 10.4.5 Logs and ledger entries

- reasoning ledger (or equivalent)  
- boundary violation logs  
- drift events  
- anomaly detection entries  
- operational logs related to inference behavior  

Auditors SHALL verify the authenticity and integrity of evidence before drawing conclusions.

---

# 10.5 Audit Procedures

## 10.5.1 Preparation

The auditor SHALL:

- obtain system documentation  
- review evaluation methodology used  
- validate prompt sets and sampling plans  
- confirm frozen inference parameters  
- ensure environmental consistency  

## 10.5.2 Evidence examination

The auditor SHALL examine:

- raw samples for drift or instability  
- metrics for correctness and reproducibility  
- compliance with mandatory controls  
- documentation for completeness  

## 10.5.3 Reproduction testing

Auditors MAY reproduce:

- repeated inference sampling  
- perturbation sampling  
- drift and variance calculations  

Reproduction SHALL use identical parameters to those documented in the evaluation.

## 10.5.4 Violation detection

The auditor SHALL check for:

- drift beyond thresholds  
- variance envelope breaches  
- boundary violations  
- interference anomalies  
- control misconfigurations  
- unreported failures  

Any violation SHALL be documented in the final audit report.

---

# 10.6 Compliance Determination

Audit findings SHALL conclude one of the following:

- compliant  
- compliant with exceptions  
- non-compliant  
- inconclusive (insufficient evidence)  

If non-compliant, the auditor SHALL document which controls or evaluation procedures were violated.

A RIS level MAY only be confirmed if:

- composite score qualifies  
- mandatory controls are satisfied  
- evidence is complete  
- no unmitigated high-risk deviations are observed  

---

# 10.7 Audit Reporting Requirements

The audit report SHALL include:

1. System overview  
2. Evaluation conditions  
3. Summary of controls reviewed  
4. Evidence examined  
5. Metric verification results  
6. Observed violations or exceptions  
7. Assessment of drift, variance, and boundary adherence  
8. Conformance determination  
9. Confirmed RIS level  
10. Recommendations and corrective actions  
11. Validity period of assessment  
12. Appendices with supporting data  

Reports SHALL be retained for the duration of the classification validity period.

---

# 10.8 Corrective Action Requirements

If deficiencies or violations are identified:

- corrective actions SHALL be documented  
- the system owner SHALL remediate issues  
- the system SHALL undergo partial or full reassessment  
- major issues SHALL reset the RIS classification  

Corrective actions MAY include:

- adjusting inference parameters  
- redefining governance boundaries  
- improving drift or variance controls  
- updating tool or agent behavior  

---

# 10.9 Auditor Qualifications

RIS audits MAY be conducted by:

- internal governance teams  
- independent third-party evaluators  
- qualified researchers  
- automated auditing systems  

Auditors SHOULD possess expertise in:

- LLM inference behavior  
- statistical evaluation  
- reasoning-chain analysis  
- AI governance and risk frameworks  
- tool, agent, or RAG system integrations (if applicable)  

Organizations MAY impose additional requirements for auditor certification.

---

# 10.10 Continuous Audit Recommendations

Organizations SHOULD implement ongoing audit-aligned practices:

- periodic drift checks  
- rolling variance sampling  
- boundary adherence monitoring  
- interference detection and logging  
- longitudinal stability assessments  

Continuous monitoring SHALL supplement, not replace, formal RIS audits.

---

# 10.11 Audit Validity

An audit is valid for:

- 12 months for general systems  
- 6 months for agentic or tool-integrated systems  
- 3 months for safety-critical systems  

Audits SHALL be invalidated immediately if:

- the model or agent is updated  
- new tools, retrieval sources, or agents are introduced  
- significant drift is observed in production  
- boundary violations occur repeatedly  

---

# 10.12 Audit Transparency

Organizations MAY disclose:

- confirmed RIS level  
- summary of findings  
- audit date and validity period  

Organizations SHOULD NOT publicly disclose:

- raw inference samples  
- proprietary metrics  
- internal configurations  
- confidential logs  

Unless required by contract, regulation, or security review.

---
