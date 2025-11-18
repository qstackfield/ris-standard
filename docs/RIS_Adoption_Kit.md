# RIS Adoption Kit
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

The RIS Adoption Kit provides organizations with a practical, structured approach to adopting the Reasoning Integrity Standard (RIS) internally.  
It is intended for:

- enterprise AI teams  
- governance and risk offices  
- safety and compliance functions  
- engineering and ML platform teams  
- research labs  
- regulators and auditors  

This kit outlines what organizations need to do to successfully implement RIS.

---

# 2. Adoption Overview

RIS adoption consists of four phases:

1. **Awareness** — learn what RIS is and why it matters  
2. **Preparation** — gather assets, define scope, assign roles  
3. **Evaluation & Controls** — run benchmarks and apply controls  
4. **Certification & Governance** — assign RIS level and maintain it  

These can be implemented gradually or all at once.

---

# 3. Phase 1: Awareness

Organizations SHOULD begin by understanding:

- the risks associated with reasoning instability  
- the role of RIS as a measurement standard  
- the meaning of RIS levels (RIS-0 to RIS-4)  
- industry alignment (NIST, ISO, SOC2 parallels)  
- how RIS fits into existing governance frameworks  

Recommended materials:

- RIS Overview  
- RIS Specification  
- RIS Glossary  

---

# 4. Phase 2: Preparation

### 4.1 Define System Scope
Identify which systems require RIS classification:

- LLMs  
- agents  
- multi-agent systems  
- RAG pipelines  
- decision-support systems  
- workflows involving reasoning  

### 4.2 Assign Roles
Minimum roles:

- **System Owner**  
- **Evaluator**  
- **Governance Reviewer**  
- **Risk/Compliance Stakeholder**  

### 4.3 Gather Required Inputs
Organizations should prepare:

- inference parameters  
- model versions  
- prompt templates  
- sample generation scripts  
- evaluation environment documentation  

### 4.4 Prepare Evidence Collection
Prepare folders or storage locations for:

- raw samples  
- metrics  
- logs  
- evaluation reports  
- conformance statements  

---

# 5. Phase 3: Evaluation & Controls

### 5.1 Run RIS Benchmark
Using the RIS Benchmark Guide:

- generate baseline prompts  
- generate perturbation prompts  
- run repeated sampling  
- compute metrics  
- run drift and boundary tests  

### 5.2 Apply RIS Controls
Reference:

- RS — Chain Stability  
- SC — Semantic Coherence  
- DR — Drift Resistance  
- VE — Variance Envelope  
- GB — Governance Boundaries  
- OP — Operational Integrity  

Organizations should document:

- which controls are implemented  
- which controls require remediation  
- control exceptions  

### 5.3 Compile Evaluation Artifacts
Complete:

- RIS Evaluation Report  
- RIS Conformance Statement  
- RIS Scorecard (JSON format)  

---

# 6. Phase 4: Certification & Governance

### 6.1 Assign RIS Level
Using RIS Section 7 rules:

- determine score-based level  
- determine control-compliance-based level  
- assign the lower of the two  

### 6.2 Publish Internal Certification
Store internally:

- scorecard  
- conformance statement  
- evaluation report  
- logs and metrics  

### 6.3 Add to Internal Registry
Organizations SHOULD maintain:

- internal RIS-certified system registry  
- version history  
- drift/degradation monitoring  

### 6.4 Optional Public Certification
If desired:

- publish scorecard  
- publish certification directory entry  
- provide model card linkage  

---

# 7. RIS Adoption Framework (Checklist)

Organizations SHOULD:

- understand RIS requirements  
- define evaluation scope  
- prepare prompts and sampling procedures  
- run benchmark tests  
- generate metrics  
- apply controls  
- produce evaluation artifacts  
- assign RIS level  
- maintain ongoing governance  

This checklist can be integrated into:

- MLOps pipelines  
- CI/CD  
- AI governance procedures  

---

# 8. Integration With Enterprise Governance

RIS integrates with:

- SOC 2 Processing Integrity  
- ISO 27001 operational controls  
- NIST AI RMF measurement framework  
- internal AI safety programs  
- regulatory audit requirements  

Organizations MAY adopt RIS as:

- a required deployment gate  
- a model lifecycle checkpoint  
- an audit and verification artifact  
- a procurement requirement  

---

# 9. Long-Term Adoption

As the RIS ecosystem grows, organizations will benefit from:

- RIS v1.1+ enhancements  
- RIS portal listing  
- drift-monitoring integrations  
- RIS evaluator automation  
- multi-agent certification profiles  

---

# 10. Summary

This adoption kit provides the foundational guidance necessary for enterprises and organizations to adopt RIS effectively.

By following this framework, organizations can:

- classify reasoning integrity  
- improve AI safety  
- reduce operational risk  
- meet governance requirements  
- align with industry best practices  

---

# End of Document
