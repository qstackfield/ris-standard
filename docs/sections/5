# 5. Measurement Framework

## 5.1 Overview

The RIS Measurement Framework defines the quantitative and qualitative methods used to evaluate reasoning integrity. It provides the metrics, data collection procedures, statistical thresholds, and evaluation structures necessary to determine a system's RIS level.

The framework applies to all systems subject to RIS evaluation and SHALL be used consistently across:

- baseline assessments
- production monitoring
- audit reviews
- comparative benchmarking

Measurement MUST be based on empirical evidence. Qualitative assessments may supplement measurements but SHALL NOT replace them.

## 5.2 Measurement Categories

RIS evaluates reasoning integrity using five primary measurement categories:

1. Chain Stability
2. Semantic Coherence
3. Drift Sensitivity
4. Variance Envelope Compliance
5. Governance Boundary Adherence

All categories MUST be assessed to determine RIS level.

## 5.3 Required Inputs

The following inputs are required for RIS-compliant measurement:

- repeated inference samples from identical prompts
- controlled perturbation samples (minimal input variations)
- environmental invariants (temperature, sampling parameters)
- contextual invariants (system instructions, agent state)
- tool or retrieval call responses (if applicable)
- logs or ledger entries representing reasoning behavior

Implementations SHOULD collect evaluation data under isolated and consistent conditions.

## 5.4 Sample Size Requirements

A compliant RIS evaluation MUST include:

- a minimum of 25 repeated inference samples per test prompt
- a minimum of 10 controlled perturbation samples per prompt
- at least 50 total prompts across diverse categories for generalized models
- at least 20 prompts for domain-specific or task-specific systems

Larger sample sizes MAY be used but SHALL be documented.

## 5.5 Chain Stability Metric

### 5.5.1 Definition

Chain stability measures the consistency of a system’s reasoning structure across repeated inference cycles.

### 5.5.2 Measurement Method

Stability is measured using:

- structural similarity metrics
- step-to-step coherence comparisons
- reasoning-length variance
- transition-alignment scoring

A system MUST maintain chain similarity within its defined variance envelope.

### 5.5.3 Scoring

Chain stability is scored from 0.00 to 1.00.

Example thresholds:

- 0.85–1.00: stable
- 0.65–0.84: semi-stable
- below 0.65: unstable

RIS-4 systems SHALL achieve stability above 0.90 for all core prompts.

## 5.6 Semantic Coherence Metric

### 5.6.1 Definition

Semantic coherence measures the consistency of meaning and conceptual alignment across repeated inferences.

### 5.6.2 Measurement Method

Coherence is evaluated based on:

- semantic similarity scoring
- topic retention
- conceptual transition consistency
- negation or contradiction detection

### 5.6.3 Scoring

Scoring follows the same 0.00–1.00 scale.

RIS-4 systems SHALL demonstrate coherence above 0.90.

## 5.7 Drift Sensitivity Metric

### 5.7.1 Definition

Drift sensitivity measures the degree to which a system deviates from baseline reasoning behavior under repeated evaluations or minimal perturbations.

### 5.7.2 Measurement Method

Drift is assessed by:

- analyzing variance outside baseline patterns
- measuring semantic or structural deviation trends
- quantifying divergence under perturbation conditions

### 5.7.3 Scoring

Drift sensitivity is scored inversely (lower is better):

- 0.00–0.10: low drift
- 0.11–0.25: moderate drift
- above 0.25: high drift

RIS-4 systems SHALL maintain drift sensitivity below 0.10.

## 5.8 Variance Envelope Compliance

### 5.8.1 Definition

The variance envelope represents the acceptable range of variation in reasoning behavior.

### 5.8.2 Measurement Method

Variance envelope compliance is determined by:

- repeated inference testing
- perturbation evaluations
- longitudinal measurement
- stability under load or repeated requests

### 5.8.3 Scoring

A system is considered compliant if:

- at least 95 percent of evaluations fall within its defined envelope

RIS-4 systems SHALL achieve at least 98 percent compliance.

## 5.9 Governance Boundary Adherence

### 5.9.1 Definition

Governance boundaries constrain the context, semantic scope, and operational state the model may use for reasoning.

### 5.9.2 Measurement Method

Boundary adherence is measured by observing:

- context window expansion attempts
- unauthorized semantic domain expansion
- tool or agent influence patterns
- cross-task contamination or memory leakage

### 5.9.3 Scoring

Boundary violations are scored as:

- 0: no violations
- 1: one minor violation
- 2: repeated or significant violations

RIS-4 systems SHALL record zero violations under all evaluation conditions.

## 5.10 Composite Reasoning Integrity Score

RIS defines an aggregate score calculated using weighted metrics:

- Chain Stability: 30 percent
- Semantic Coherence: 25 percent
- Drift Sensitivity: 20 percent
- Variance Envelope Compliance: 15 percent
- Governance Boundary Adherence: 10 percent

Composite scores determine candidate RIS levels but do not replace conformance requirements.

## 5.11 Interpretation of Scores

Composite score ranges:

- 0.00–0.40: RIS-0
- 0.41–0.60: RIS-1
- 0.61–0.75: RIS-2
- 0.76–0.89: RIS-3
- 0.90–1.00: RIS-4

A system MUST meet both:

- composite scoring thresholds
- all mandatory controls applicable to its level

to be classified at that RIS level.

---
