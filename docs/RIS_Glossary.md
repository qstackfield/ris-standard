# RIS Glossary
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## Introduction

This glossary defines key terminology used throughout the Reasoning Integrity Standard (RIS).  
All terms in this glossary are informative unless referenced as normative terminology in the RIS specification.

---

# A

### Agent
A system or module that uses an LLM to perform actions, reasoning steps, or tool interactions autonomously or semi-autonomously.

### Agent Interference
A phenomenon in which the reasoning of one agent is influenced or altered by another agent’s output, state, or actions.

---

# B

### Baseline
A set of reasoning samples used to define stability, coherence, variance envelopes, and drift thresholds.

### Baseline Prompt
A prompt used to generate repeated inference samples without variation to establish base reasoning behavior.

### Boundary Violation
A reasoning event where the system exceeds defined contextual, semantic, or operational constraints.

### Boundary Enforcement
A set of checks preventing a system from exceeding defined reasoning limits.

---

# C

### Chain Stability
The consistency of the structure, sequence, and transitions of reasoning chains across repeated evaluations.

### Cognitive Drift
A measurable deviation in reasoning behavior over time, across samples, or under perturbations.

### Composite Score
A weighted aggregate reasoning integrity score based on metrics defined in RIS Section 5.

### Conformance
The degree to which a system meets RIS scoring thresholds and mandatory controls.

### Context Leakage
Use of information not present in the prompt, environment, or defined boundaries.

---

# D

### Deterministic Reasoning Pattern
A reasoning structure that remains stable under fixed parameters, even if surface-level outputs vary.

### Drift Sensitivity
The degree to which a system exhibits instability or divergence when exposed to repeated or perturbed inference cycles.

### Drift Envelope
A defined set of acceptable drift boundaries used to determine permissible reasoning variation.

---

# E

### Evaluation Environment
The set of configuration, hardware, software, and inference parameters under which RIS assessments occur.

### Envelope Compliance
A measurement indicating how many reasoning samples fall within established variance or drift thresholds.

---

# G

### Governance Boundary
A defined constraint determining what context, domain, or information the system may use during reasoning.

### Governance Mode
A system state (hold, elevate, lockdown) used to manage reasoning behavior and enforce constraints.

---

# I

### Interference Event
An unintended alteration of reasoning behavior caused by external components such as tools, retrieval systems, agents, or environment variations.

### Inference Parameters
Settings that govern model behavior, such as temperature, top-p, context window, and system instructions.

---

# L

### Ledger (Reasoning Ledger)
A sequential, hash-linked record of reasoning evaluations, metrics, and verdicts used for auditability.

### Longitudinal Monitoring
Tracking reasoning behavior across time intervals to detect degradation or temporal drift.

---

# M

### Measurement Framework
The set of metrics, scoring rules, and evaluation processes defined in RIS Section 5.

### Model Configuration
The parameters and environmental conditions that determine how a model executes reasoning.

---

# P

### Perturbation Prompt
A semantically equivalent variation of a baseline prompt used to test robustness and drift.

### Prompt Set
A collection of baseline and perturbation prompts used in RIS evaluation.

---

# R

### Reasoning Boundary
A defined limit determining what the system may consider or incorporate during reasoning.

### Reasoning Chain
An internal conceptual pathway or structure the system follows to derive an output.

### Reasoning Integrity
The consistency, stability, and predictability of reasoning patterns under controlled evaluation.

### Reasoning Stability
The degree to which a system’s reasoning remains unchanged across repeated evaluations.

### Reference Implementation
An example implementation demonstrating RIS-aligned controls and metrics (e.g., LCAC).

### Repeated Inference Sampling
A method of obtaining multiple outputs for the same prompt to evaluate stability and variance.

---

# S

### Semantic Coherence
The degree to which reasoning outputs preserve meaning, alignment, and context across samples.

### Structural Drift
A deviation in the structure or sequence of reasoning steps beyond expected thresholds.

### System Configuration
A full description of parameters, environment, tools, agents, and constraints under evaluation.

---

# T

### Temporal Drift
Progressive degradation or change in reasoning behavior across time or inference windows.

### Trust Score
A scalar value representing the model’s measured reasoning stability (used in reference implementations).

---

# V

### Variance Envelope
A statistical boundary defining acceptable variance in stability or coherence.

### Variance Envelope Compliance
A measurement of how many samples fall within the variance envelope.

### Violations
Any deviations from required controls or thresholds that impact reasoning integrity.

---

# End of Glossary
