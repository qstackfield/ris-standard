# 2. Normative References

## 2.1 Purpose of Normative References

This section identifies documents, standards, and terminology references that are considered authoritative for understanding and implementing the Reasoning Integrity Standard (RIS). Where conflicts arise, this specification takes precedence unless a referenced standard is explicitly designated as controlling for a specific requirement.

Normative references are essential for interpreting RIS controls, understanding terminology, and establishing consistent evaluation and audit methodologies across implementations.

## 2.2 Standards and Frameworks Referenced by RIS

The following documents and standards are integral to interpreting RIS v1.0. Implementers are expected to be familiar with these materials, as RIS incorporates concepts, terminology, and structural patterns from them.

### NIST Standards

- NIST Special Publication 800-53: Security and Privacy Controls for Information Systems and Organizations  
- NIST Artificial Intelligence Risk Management Framework (AI RMF)  
- NIST SP 1270: Trustworthy and Responsible AI  

### ISO Standards

- ISO/IEC 27001: Information Security Management Systems  
- ISO/IEC 23894: Artificial Intelligence Risk Management  
- ISO/IEC 29100: Privacy Framework  
- ISO/IEC 25010: System and Software Quality Models  

### SOC 2 and AICPA Guidance

- AICPA Trust Services Criteria (Security, Availability, Processing Integrity, Confidentiality, Privacy)  
- AICPA AT-C 205: Examination Engagements  

### OWASP and Application Security References

- OWASP Application Security Verification Standard (ASVS)  
- OWASP Top 10 (referenced in governance and boundary controls)  

### AI Safety, Governance, and Model Evaluation References

- EU AI Act (Draft and Final Texts)  
- MLPerf and related benchmark publications  
- Model evaluation methodologies from major AI labs  
- Academic publications on chain-of-thought, inference stability, and cognitive drift  

## 2.3 Terminology References

RIS uses terminology derived from established research and industry standards. Implementers should reference the following categories for precise interpretation.

### AI Systems Terminology

- large language model (LLM)  
- agent and multi-agent system  
- chain-of-thought (CoT)  
- semantic coherence  
- contextual drift  
- inference-time variability  
- deterministic vs. non-deterministic reasoning  

### Governance Terminology

- risk posture  
- control requirement  
- conformance  
- audit evidence  
- variance threshold  
- stability metric  

### LCAC Terminology (Reference Implementation Only)

LCAC terminology is **informative**, not normative. Terms include:

- least-context access control  
- governance mode  
- reasoning boundary  
- drift envelope  
- trust baseline  
- variance baseline  
- reasoning ledger  

Implementers are not required to adopt LCAC’s terminology or architecture, but LCAC terms appear in examples and appendices as part of the reference implementation.

## 2.4 Definitions Governed by RIS

RIS mandates the following definitions for consistent use across all conformant implementations.

### Reasoning Integrity

The measurable ability of a system to produce stable, predictable reasoning outputs that maintain structural coherence across similar prompts, repeated prompts, operational conditions, and controlled variations.

### Reasoning Drift

A deviation in reasoning behavior, structure, or output that exceeds defined variance thresholds when evaluated under repeatable or controlled conditions.

### Chain Stability

The degree to which the internal reasoning structure of a system maintains consistent logical steps, semantic transitions, and contextual boundaries across repeated inference cycles.

### Semantic Consistency

The alignment of meaning, intent, and conceptual structure across multiple reasoning instances or reasoning steps for equivalent prompts.

### Governance Boundary

A defined constraint controlling the informational, contextual, or semantic state accessible to a reasoning system at inference time.

## 2.5 Control of Normative References

Where RIS references external standards:

- External standards MUST be treated as supporting material.
- External standards SHALL NOT override RIS requirements unless explicitly designated as authoritative.
- RIS SHALL define the governing definitions for reasoning integrity and drift.
- External terminology MAY be used for interpretation but not for replacing RIS controls.

## 2.6 Informative vs. Normative Material

RIS distinguishes between:

- Normative material (mandatory for conformance)
- Informative material (supporting guidance)

Normative sections include:

- Controls  
- Requirements  
- Measurement Framework  
- Scoring and Conformance  
- Audit Guidelines  

Informative sections include:

- Reference Implementation  
- Mapping to Other Standards  
- Appendices  

This distinction is preserved throughout the remainder of the specification.

---
