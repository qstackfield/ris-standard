# 4. RIS Levels

## 4.1 Overview

The Reasoning Integrity Standard (RIS) defines five levels of reasoning integrity maturity, ranging from RIS-0 (uncontrolled reasoning) to RIS-4 (high-integrity, production-grade reasoning). These levels provide a structured framework for evaluating the stability, predictability, and reliability of reasoning produced by large language models (LLMs) and agentic systems.

RIS levels classify systems based on measurable reasoning behavior, not model size, architecture, vendor, or training methodology. A system's RIS level reflects its demonstrated ability to maintain reasoning integrity under controlled conditions, repeated evaluations, and operational scenarios.

## 4.2 Level Definitions

RIS defines the following reasoning integrity maturity levels:

- RIS-0: Uncontrolled Reasoning
- RIS-1: Drift-Sensitive Reasoning
- RIS-2: Semi-Stable Reasoning
- RIS-3: Controlled Reasoning
- RIS-4: High-Integrity Reasoning

Each level includes required properties, performance characteristics, and failure thresholds.

## 4.3 RIS-0: Uncontrolled Reasoning

### Description
RIS-0 systems exhibit unpredictable, highly variable, or unstable reasoning behavior. Reasoning chains diverge significantly across repeated prompts, and semantic coherence is inconsistent or unreliable.

### Characteristics

- High variance across repeated inferences
- Unstable or incoherent reasoning chains
- Susceptibility to minor input or environmental perturbations
- Unbounded or uncontrolled reasoning state transitions
- No enforceable variance envelope
- Reasoning behavior cannot be reliably reproduced

### Typical Use Cases

- exploratory research models
- early-stage prototypes
- unconstrained generative systems

### Conformance
RIS-0 indicates non-conformance with all RIS requirements.

## 4.4 RIS-1: Drift-Sensitive Reasoning

### Description
RIS-1 systems demonstrate partial reasoning stability but remain sensitive to drift, perturbations, and repeated evaluations. Structural or semantic divergence occurs frequently.

### Characteristics

- partially stable reasoning patterns under ideal conditions
- significant drift under repetition or minimal variation
- inconsistent semantic alignment
- no enforceable drift boundaries
- limited reproducibility of reasoning behavior

### Typical Use Cases

- non-safety-critical applications
- general-purpose conversational models
- agent prototypes

### Conformance
RIS-1 indicates minimal partial alignment with RIS controls but does not meet baseline conformance.

## 4.5 RIS-2: Semi-Stable Reasoning

### Description
RIS-2 systems achieve basic reasoning integrity. Reasoning chains show moderate consistency across repeated prompts and operate within a loosely defined variance range. Drift is detectable but bounded.

### Characteristics

- moderate chain stability
- acceptable semantic coherence under repetition
- drift remains within a broad variance envelope
- occasional reasoning divergence under perturbation
- reproducible reasoning behavior in controlled cases

### Typical Use Cases

- consumer-facing AI applications
- low-risk enterprise workflows
- model evaluation and benchmarking environments

### Conformance
RIS-2 meets some baseline RIS controls but does not satisfy the requirements for production-grade reasoning integrity.

## 4.6 RIS-3: Controlled Reasoning

### Description
RIS-3 systems demonstrate controlled reasoning behavior suitable for production environments. Reasoning chains are stable across repetitions, drift remains within defined boundaries, and semantic coherence is predictably maintained.

### Characteristics

- consistent chain stability across repeated prompts
- defined and enforceable variance envelope
- predictable reasoning under controlled perturbations
- bounded semantic drift and minimal divergence
- reproducible reasoning state transitions
- resistance to tool and agent interference within expected parameters

### Typical Use Cases

- enterprise-grade LLM applications
- internal decision-support systems
- workflow automation
- multi-agent orchestration with defined boundaries

### Conformance
RIS-3 satisfies the majority of RIS requirements and is considered the minimum level appropriate for regulated or production-grade environments.

## 4.7 RIS-4: High-Integrity Reasoning

### Description
RIS-4 represents the highest level of reasoning integrity. Systems at this level produce stable, predictable, and coherent reasoning patterns with minimal variance across repeated evaluations. Drift is tightly controlled, and reasoning chains maintain structural integrity under both controlled and adversarial conditions.

### Characteristics

- high stability and coherence across all evaluations
- tightly bounded variance envelope
- minimal drift under repetition or perturbation
- predictable reasoning structure even with minor input variations
- resilience to interference from tools, retrieval components, or agents
- strong governance boundary adherence
- reproducible reasoning consistent with defined expectations

### Typical Use Cases

- safety-critical systems
- regulated industries requiring auditability
- financial, medical, legal, and security reasoning workflows
- autonomous agent frameworks with strict stability demands
- enterprise systems requiring deterministic reasoning behavior

### Conformance
RIS-4 conforms to all RIS requirements and demonstrates the highest degree of reasoning integrity defined by the standard.

## 4.8 Level Assignment Requirements

A system's RIS level MUST be assigned based on:

- performance across the RIS measurement framework
- compliance with required RIS controls
- observed behavior during evaluation methodology test suites
- documented evidence demonstrating stability and drift characteristics

Level assignment SHALL be determined from empirical results, not vendor claims or model size.

## 4.9 Level Validation and Reassessment

Systems evaluated for RIS conformance MUST undergo periodic reassessment based on:

- operational changes
- model updates or retraining
- architectural changes
- new tool or agent integrations
- changes in governance boundaries
- drift trends observed in production

Reassessment MAY elevate or reduce a system's RIS level depending on observed results.

---
