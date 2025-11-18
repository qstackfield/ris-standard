# RIS API Integration Guide
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This guide explains how organizations can integrate RIS evaluation into their systems using an API-based workflow.  
It is intended for teams who prefer to send samples to an evaluation endpoint and receive metrics, RIS levels, and compliance results.

RIS does not mandate a specific API implementation.  
The examples provided here illustrate a **generic RIS-compliant API format** that any organization may implement internally.

---

# 2. RIS API Overview

A RIS evaluation API follows this pattern:

1. System generates inference samples  
2. System sends samples to `/ris/evaluate`  
3. API computes RIS metrics  
4. API returns:
   - computed metrics  
   - composite score  
   - RIS level  
   - violations (if any)  
   - evaluation summary  

This API does not require storing prompts, context, or sensitive data.

---

# 3. API Endpoints (Reference Format)

Below are recommended endpoint patterns.

## 3.1 POST /ris/evaluate

Purpose: submit samples and retrieve RIS metrics + classification.

Request body format:

    {
      "samples": [
        { "prompt": "...", "output": "..." },
        { "prompt": "...", "output": "..." }
      ],
      "parameters": {
        "temperature": 0.7,
        "top_p": 1.0
      }
    }

Response example:

    {
      "metrics": {
        "chain_stability": 0.87,
        "semantic_coherence": 0.90,
        "drift_sensitivity": 0.14,
        "variance_compliance": 0.96,
        "boundary_violations": 0
      },
      "composite_score": 0.84,
      "ris_level": "RIS-3",
      "status": "PASS",
      "summary": "System meets RIS-3 requirements."
    }

---

## 3.2 GET /ris/metrics/schema

Returns the schema of all metrics.

Useful for validating fields or building dashboards.

Example response:

    {
      "required": [
        "chain_stability",
        "semantic_coherence",
        "drift_sensitivity",
        "variance_compliance",
        "boundary_violations"
      ],
      "version": "1.0"
    }

---

## 3.3 GET /ris/info

Returns metadata about the evaluator:

    {
      "version": "1.0",
      "ris_supported": true,
      "max_samples": 5000
    }

---

# 4. Sample Client Implementation

Below is a pseudo-code example for calling a RIS API.

Python example:

    import requests
    payload = {
        "samples": samples,
        "parameters": { "temperature": 0.7, "top_p": 1.0 }
    }
    r = requests.post("https://yourdomain.com/ris/evaluate", json=payload)
    print(r.json())

Node example:

    const response = await fetch("https://yourdomain.com/ris/evaluate", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(payload)
    });
    const data = await response.json();

---

# 5. Security and Privacy

Organizations SHOULD:

- redact sensitive information before sending
- avoid sending PII, PHI, or proprietary text
- enforce API authentication (tokens, OAuth, mTLS)
- limit retention of submitted samples
- optionally perform evaluation on-premise

RIS does not require external submission of data.

---

# 6. Best Practices

- Use batching for large datasets  
- Enforce max sample sizes  
- Perform envelope compliance checks internally  
- Log evaluation metadata  
- Store RIS output as audit evidence  

---

# 7. Summary

A RIS evaluation API allows:

- external LLMs  
- internal models  
- agents  
- multi-agent systems  
- pipelines  

to obtain RIS metrics in a standardized format.

Organizations may implement this API internally or expose it as a service for their teams.

---
