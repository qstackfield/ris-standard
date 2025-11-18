# 9. Evaluation Methodology

## 9.1 Overview

The RIS evaluation methodology defines the standardized procedures for performing a reasoning integrity assessment. These procedures ensure that measurements are:

- repeatable  
- objective  
- statistically meaningful  
- comparable across systems  
- suitable for audit and certification  

All evaluations MUST follow the methodology in this section to be considered valid for RIS classification.

---

# 9.2 Evaluation Objectives

The objectives of RIS evaluation are to:

1. quantify reasoning stability and coherence  
2. measure drift and variance across repeated evaluations  
3. detect boundary violations  
4. assess interference sensitivity  
5. validate compliance with required controls  
6. classify the system into an appropriate RIS level  

Evaluation SHALL NOT assess factual correctness or ethical outcomes. Only reasoning integrity is measured.

---

# 9.3 Evaluation Conditions

## 9.3.1 Environmental consistency

Evaluations SHALL be conducted under consistent conditions, including:

- model version  
- inference parameters (temperature, top-p, settings)  
- context and prompt format  
- agent or tool configurations  
- hardware or infrastructure environment  

Changes to any parameter invalidate comparisons.

## 9.3.2 Isolation

The evaluation environment SHOULD minimize:

- interference from concurrent workloads  
- environmental noise  
- model adaptation or memory building  
- caching effects  

## 9.3.3 Documentation

The evaluator SHALL document:

- all inference parameters  
- all environment variables  
- system settings used for assessment  
- test prompt sets  

---

# 9.4 Prompt Set Requirements

RIS evaluation uses two types of prompts:

1. Baseline prompts  
2. Perturbation prompts  

## 9.4.1 Baseline prompts

Baseline prompts SHOULD include:

- informational queries  
- reasoning tasks  
- multi-step tasks  
- conceptual analysis tasks  
- domain-neutral questions  

At least 50 prompts SHOULD be used for general-purpose systems.  
At least 20 prompts SHOULD be used for specialized systems.

## 9.4.2 Perturbation prompts

Perturbation prompts MUST maintain semantic equivalence with baseline prompts while varying:

- syntax  
- structure  
- ordering  
- minor phrasing  
- neutral substitutions  

A minimum of 10 perturbations SHALL be used per baseline prompt selected for perturbation testing.

---

# 9.5 Sampling Methodology

## 9.5.1 Repeated inference sampling

For each baseline prompt:

- at least 25 repeated inference samples SHALL be collected  
- sampling parameters SHALL remain identical across all repetitions  

Repeated inference sampling is used to compute:

- chain stability  
- semantic coherence  
- drift sensitivity  
- variance envelope compliance  

## 9.5.2 Controlled perturbation sampling

For each perturbation prompt:

- at least 10 inference samples SHALL be collected  

Perturbation sampling is used to measure:

- structural drift  
- semantic drift  
- robustness under variation  

---

# 9.6 Baseline Establishment

## 9.6.1 Creating a baseline

The evaluator SHALL establish a baseline by:

1. selecting representative baseline prompts  
2. executing repeated inference sampling  
3. computing structural and semantic similarity metrics  
4. determining drift sensitivity  
5. defining acceptable variance envelopes  

## 9.6.2 Baseline validity

A baseline is valid only if:

- all evaluation conditions are documented  
- system configuration remains unchanged  
- variance envelope is statistically meaningful  

Baseline MUST be refreshed when model parameters change or risk models trigger reassessment.

---

# 9.7 Drift Evaluation

## 9.7.1 Drift detection

Drift is detected by:

- comparing new samples to baseline  
- analyzing deviation trends  
- identifying abrupt or progressive divergence  
- checking for consistent out-of-envelope behavior  

## 9.7.2 Drift characterization

Drift SHALL be categorized as:

- structural  
- semantic  
- temporal  
- interference-based  

## 9.7.3 Drift thresholds

A drift event occurs when:

- deviation exceeds the envelope for more than 5 percent of samples  
- repeated deviations occur during perturbation sampling  
- temporal divergence increases across sequential windows  

## 9.7.4 Drift escalation

If drift is detected:

- the system’s RIS level MAY be lowered  
- additional testing SHALL be performed  
- drift controls MUST be verified  

---

# 9.8 Boundary Evaluation

Boundary adherence SHALL be tested by:

- introducing tasks with clear semantic boundaries  
- evaluating attempts to use disallowed context  
- testing reasoning behavior with restricted tool outputs  
- detecting cross-task or cross-context contamination  

Any violation SHALL be logged and considered in level classification.

---

# 9.9 Interference Evaluation

Interference evaluation includes:

- testing reasoning stability before and after tool calls  
- measuring agent-to-agent interaction effects  
- injecting controlled retrieval variability  
- observing structural or semantic disruptions  

Interference MUST not cause uncontrolled reasoning divergence for systems seeking RIS-3 or RIS-4 level classification.

---

# 9.10 Variance Envelope Evaluation

Variance envelope compliance SHALL be tested through:

- repeated inference sampling  
- perturbation sampling  
- load or stress conditions if applicable  
- periodic resampling across intervals  

A system MUST maintain compliance for:

- at least 95 percent of samples (RIS-3)  
- at least 98 percent of samples (RIS-4)  

---

# 9.11 Evaluation Report Requirements

A complete evaluation report SHALL include:

1. System description  
2. Evaluation environment details  
3. Prompt sets used  
4. Sampling methodology  
5. Baseline metrics  
6. Drift analysis  
7. Variance envelope results  
8. Boundary adherence results  
9. Interference results  
10. Composite score calculation  
11. Control compliance analysis  
12. RIS level assigned  
13. Validity period  
14. Evidence appendix  

The report SHALL be signed by the evaluator.

---

# 9.12 Evaluation Validity

An evaluation remains valid only if:

- the system configuration does not change  
- no drift events occur in production  
- no new tools, agents, or retrieval sources are introduced  
- governance boundaries remain constant  

If any condition changes, reassessment MAY be required immediately.

---

# 9.13 Re-Evaluation Requirements

Re-evaluation SHALL occur:

- at the end of the classification validity period  
- when major model updates occur  
- when drift or instability is observed  
- when new risk categories are triggered  
- when evidence suggests deviation from baseline behavior  

Systems in regulated or safety-critical environments MAY require more frequent reassessments.

---
