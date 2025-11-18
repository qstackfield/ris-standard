# RIS Certification Program
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

This document defines the RIS Certification Program framework.

The program exists to:

- provide a formal mechanism for systems to be evaluated under RIS
- assign RIS levels based on evidence
- document reasoning integrity in a standardized way
- support internal and external assurance, including regulatory contexts

---

## 2. Certification Types

Recommended certification classifications:

- Internal RIS Assessment
- Third-Party RIS Assessment
- Joint Assessment (internal plus external)
- Self-Attested RIS Compliance
- Verified RIS Certification (optional future program)

Organizations MAY choose one or more models based on risk and regulatory needs.

---

## 3. Scope of Certification

Certification applies to:

- a specific system or model configuration
- a specific version
- a defined deployment environment

Changes in any of the above SHOULD trigger reassessment.

---

## 4. Certification Process

Core steps:

1. Define scope and target RIS level  
2. Prepare evaluation environment  
3. Build prompt sets and sampling plan  
4. Run RIS evaluation (per RIS Section 9)  
5. Compute metrics and composite score  
6. Verify control compliance (RIS Section 6)  
7. Assign RIS level  
8. Generate Evaluation Report  
9. Generate Conformance Statement  
10. Issue or update Certification Entry and Scorecard  

---

## 5. Roles and Responsibilities

- System Owner:
  - defines scope
  - supports evaluation
  - signs conformance statement

- Evaluator:
  - performs or oversees RIS evaluation
  - validates evidence
  - signs evaluation report

- Governance Function:
  - approves or rejects RIS classification
  - sets minimum required RIS levels
  - ensures reassessment occurs on schedule

---

## 6. Validity Period

Per RIS Section 7:

- general LLM systems: up to 12 months  
- agentic or tool-integrated systems: up to 6 months  
- safety-critical systems: up to 3 months  

Organizations MAY enforce stricter validity windows.

Certification expires at the end of the validity period or earlier if:

- major model changes occur
- drift or variance thresholds are violated in production
- boundary violations become material

---

## 7. Reassessment Triggers

Reassessment SHOULD be performed when:

- the model is retrained or heavily fine-tuned
- new tools or agents are added
- RAG or memory architecture changes significantly
- production monitoring detects drift
- regulatory requirements change
- exposure or risk profile changes

---

## 8. Evidence Requirements

Minimum evidence:

- RIS Evaluation Report
- RIS Conformance Statement
- metric datasets
- prompts and sampling methodology
- logs (drift, variance, boundary events)
- configuration documentation for evaluation

Additional evidence MAY be required for high-risk environments.

---

## 9. Public vs. Private Certification

- Private Certification:
  - used internally
  - not published
  - suitable for internal control and governance

- Public Certification:
  - published in a RIS directory or portal
  - may be shared with regulators or customers
  - subject to public review

Organizations MAY choose one or both models.

---

## 10. Program Levels (Optional Future Extensions)

Future program levels MAY include:

- RIS-Ready:
  - metrics collected, not fully compliant

- RIS-Certified:
  - full compliance and evaluation completed

- RIS-Gold (for example):
  - consistent RIS-4 performance over multiple cycles

These are not part of RIS v1.0 but may be introduced later as program enhancements.

---

## 11. Alignment With Other Frameworks

Organizations MAY integrate RIS certification with:

- model risk management programs
- SOC 2 programs
- ISO 27001 ISMS
- NIST AI RMF
- EU AI Act compliance efforts

RIS provides the technical reasoning integrity layer beneath these governance frameworks.

---

## 12. Contact and Governance

RIS Certification governance SHOULD designate:

- responsible contact or team
- approval authority
- escalation path for disputes or anomalies

Contact details MAY be published on the RIS portal.

---
