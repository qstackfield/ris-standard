# RIS Reference Evaluator Guide
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This guide explains how to structure a RIS Reference Evaluator.  
A RIS Reference Evaluator is a system that:

- accepts inference samples  
- computes RIS metrics  
- determines RIS level  
- logs results  
- returns a standardized output format

LCAC is an example of a reference evaluator, but RIS is implementation-agnostic.

---

# 2. Evaluator Architecture

A reference evaluator typically includes:

- input ingestion (samples)
- metric computation engine
- variance envelope logic
- drift analysis module
- boundary violation checks
- composite scoring module
- evaluator output formatter
- optional ledger storage

These components MAY be implemented as:

- a Python library  
- a REST API  
- a CLI tool  
- a local script  
- a microservice  

---

# 3. Inputs

The evaluator MUST accept a list of samples:

    [
      { "prompt": "...", "output": "..." },
      { "prompt": "...", "output": "..." }
    ]

Optional fields:

- intermediate steps (if available)
- tool outputs (for agent systems)
- context metadata

---

# 4. Outputs

A RIS evaluator SHOULD return:

    {
      "metrics": {},
      "composite_score": <float>,
      "ris_level": "RIS-x",
      "violations": [],
      "summary": "text summary"
    }

---

# 5. Evaluator Execution Steps

A RIS evaluator follows this workflow:

## Step 1: Load samples  
## Step 2: Compute metrics  
## Step 3: Compute composite score  
## Step 4: Determine RIS level  
## Step 5: Generate summary  
## Step 6: Log results (optional)  
## Step 7: Return response  

---

# 6. Logging (Optional but Recommended)

Evaluators MAY log:

- metric values  
- drift events  
- variance envelope breaches  
- boundary violations  
- scores over time  

Logging improves:

- auditability  
- reproducibility  
- long-term monitoring  

---

# 7. Integration With LCAC (Optional)

LCAC provides:

- trust score  
- drift model  
- ledger  
- variance tracking  
- governance modes

Organizations may choose to use LCAC as:

- a full evaluator  
- a partial evaluator  
- an evaluation engine plugin  

RIS does not require LCAC.

---

# 8. Extensibility

Evaluators MAY support:

- plugin metric modules  
- domain-specific RIS profiles  
- multi-agent scoring  
- scenario-based testing  
- RAG stability analysis  

These features are optional but powerful.

---

# 9. Summary

A RIS Reference Evaluator enables:

- reproducible reasoning integrity assessments  
- consistent RIS scoring  
- integration with CI/CD pipelines  
- integration with governance frameworks  

LCAC is one example, but any evaluator that follows RIS rules is compliant.

---
