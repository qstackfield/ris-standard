# RIS SDK Guide
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This guide describes how organizations can build a simple Software Development Kit (SDK) for RIS evaluation.  
The SDK provides utilities for:

- loading samples  
- computing RIS metrics  
- evaluating composite scores  
- determining RIS levels  
- generating summary reports  

RIS does not mandate a specific SDK.  
The examples here represent a **reference design** that any enterprise can implement.

---

# 2. SDK Capabilities

A RIS SDK SHOULD provide:

- helper functions for computing metrics
- a composite scoring function
- a RIS level classification method
- IO helpers for loading/saving JSON samples
- optional integration with LCAC or an internal evaluator

---

# 3. Suggested SDK Functions

## 3.1 compute_metrics(samples)

Computes:

- chain stability  
- semantic coherence  
- drift sensitivity  
- variance compliance  
- boundary adherence signals  

## 3.2 compute_composite_score(metrics)

Weighted calculation:

- 30% chain stability  
- 25% semantic coherence  
- 20% drift sensitivity  
- 15% variance compliance  
- 10% boundary adherence  

## 3.3 determine_ris_level(score, metrics)

Logic:

    if boundary violations:
        return "RIS-0"
    elif score >= 0.90:
        return "RIS-4"
    elif score >= 0.76:
        return "RIS-3"
    elif score >= 0.61:
        return "RIS-2"
    elif score >= 0.41:
        return "RIS-1"
    else:
        return "RIS-0"

---

# 4. Example Python SDK

Pseudo-code implementation:

    class RIS:
        def compute_metrics(self, samples):
            # compute all RIS metrics
            return metrics

        def composite_score(self, metrics):
            score = (
                metrics["chain_stability"] * 0.30 +
                metrics["semantic_coherence"] * 0.25 +
                (1 - metrics["drift_sensitivity"]) * 0.20 +
                metrics["variance_compliance"] * 0.15 +
                (1 - metrics["boundary_violations"]) * 0.10
            )
            return score

        def ris_level(self, score, metrics):
            # apply RIS rules
            return level

        def evaluate(self, samples):
            metrics = self.compute_metrics(samples)
            score = self.composite_score(metrics)
            level = self.ris_level(score, metrics)
            return { "metrics": metrics, "score": score, "level": level }

---

# 5. Example Usage

    ris = RIS()
    results = ris.evaluate(samples)
    print("RIS Level:", results["level"])

---

# 6. Integration With Evaluators (Optional)

The SDK MAY optionally call:

- LCAC evaluation API  
- internal evaluation pipeline  
- on-premise RIS evaluator  

This is not required.

---

# 7. Summary

RIS SDKs accelerate evaluation by:

- abstracting metric logic  
- reducing code duplication  
- enabling reproducible assessments  
- integrating with CI/CD systems  

Organizations SHOULD provide internal SDKs to ensure consistent scoring across teams.

---
