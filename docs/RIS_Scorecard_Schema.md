# RIS Scorecard JSON Schema
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

This document defines the canonical JSON structure for a RIS scorecard.

A RIS scorecard is a machine-readable summary of:

- the system evaluated
- RIS metrics
- composite reasoning integrity score
- RIS level
- evaluation metadata
- evidence references

This schema is intended for:

- internal registries
- public portals
- audit systems
- model cards that embed RIS data

---

## 2. Top-Level Structure

Scorecards SHALL follow this structure:

    {
      "schema_version": "1.0",
      "system": { ... },
      "evaluation": { ... },
      "metrics": { ... },
      "ris": { ... },
      "evidence": { ... },
      "signatures": { ... }
    }

All fields are described in the following sections.

---

## 3. system Object

Describes the evaluated system.

    "system": {
      "name": "string",
      "version": "string",
      "owner": "string",
      "organization": "string",
      "description": "string",
      "category": "string",
      "use_cases": [ "string" ],
      "environment": "string",
      "model_family": "string",
      "model_version": "string"
    }

Fields:

- name: system or model identifier
- version: system version string
- owner: internal team or business owner
- organization: legal entity responsible
- description: high-level summary
- category: e.g., "LLM", "agent", "RAG", "multi-agent"
- use_cases: primary supported usage
- environment: "production", "staging", "internal", etc.
- model_family: e.g., "GPT-4 class", "Llama 3", "internal"
- model_version: specific model build or release label

---

## 4. evaluation Object

Describes evaluation conditions.

    "evaluation": {
      "evaluation_id": "string",
      "requested_ris_level": "string",
      "date": "YYYY-MM-DD",
      "evaluator": {
        "name": "string",
        "organization": "string",
        "type": "string"
      },
      "config": {
        "temperature": 0.0,
        "top_p": 0.0,
        "context_window": "string",
        "system_prompt_hash": "string",
        "agent_orchestration": "string",
        "tools_enabled": [ "string" ],
        "rag_enabled": true
      }
    }

Fields:

- evaluation_id: unique identifier
- requested_ris_level: target level (e.g., "RIS-3")
- date: evaluation completion date
- evaluator: who performed evaluation (human or automated)
- config: high-level inference and environment configuration

---

## 5. metrics Object

This object records numeric metrics required by RIS.

    "metrics": {
      "chain_stability": 0.0,
      "semantic_coherence": 0.0,
      "drift_sensitivity": 0.0,
      "variance_compliance": 0.0,
      "boundary_violations": 0,
      "sample_size": {
        "baseline_prompts": 0,
        "perturbation_prompts": 0,
        "baseline_samples": 0,
        "perturbation_samples": 0
      }
    }

Fields:

- chain_stability: mean stability score (0.00–1.00)
- semantic_coherence: mean coherence score (0.00–1.00)
- drift_sensitivity: drift sensitivity value (lower is better)
- variance_compliance: proportion of samples within envelope (0.00–1.00)
- boundary_violations: count of boundary violation events observed
- sample_size: counts used to compute metrics

---

## 6. ris Object

This object captures RIS-specific outcome data.

    "ris": {
      "composite_score": 0.0,
      "level": "string",
      "status": "string",
      "risk_profile": {
        "structural_drift": "Low",
        "semantic_drift": "Low",
        "temporal_stability": "Low",
        "interference": "Low",
        "boundary": "Low",
        "degradation": "Low"
      },
      "valid_from": "YYYY-MM-DD",
      "valid_until": "YYYY-MM-DD"
    }

Fields:

- composite_score: weighted reasoning integrity score (0.00–1.00)
- level: RIS level assigned ("RIS-0" to "RIS-4")
- status: "PASS" or "FAIL" relative to requested_ris_level
- risk_profile: classification across RIS risk categories
- valid_from: effective date
- valid_until: expiration per RIS rules

---

## 7. evidence Object

References to supporting artifacts.

    "evidence": {
      "evaluation_report_uri": "string",
      "conformance_statement_uri": "string",
      "raw_samples_uri": "string",
      "metrics_dataset_uri": "string",
      "logs_uri": "string",
      "notes": "string"
    }

Fields are URIs or internal references to evaluation artifacts.

---

## 8. signatures Object

Describes who attested to this scorecard.

    "signatures": {
      "evaluator": {
        "name": "string",
        "role": "string",
        "organization": "string",
        "signed_at": "YYYY-MM-DD"
      },
      "system_owner": {
        "name": "string",
        "role": "string",
        "organization": "string",
        "signed_at": "YYYY-MM-DD"
      }
    }

---

## 9. Minimal Example

    {
      "schema_version": "1.0",
      "system": {
        "name": "Example Agent",
        "version": "1.2.3",
        "owner": "AI Systems Team",
        "organization": "ExampleCorp",
        "description": "Multi-agent reasoning system for internal analytics.",
        "category": "agent",
        "use_cases": [ "analytics", "decision support" ],
        "environment": "production",
        "model_family": "GPT-class",
        "model_version": "2025-01-01"
      },
      "evaluation": {
        "evaluation_id": "EV-2025-0001",
        "requested_ris_level": "RIS-3",
        "date": "2025-01-10",
        "evaluator": {
          "name": "Governance Team A",
          "organization": "ExampleCorp",
          "type": "internal"
        },
        "config": {
          "temperature": 0.3,
          "top_p": 0.9,
          "context_window": "32k",
          "system_prompt_hash": "abc123...",
          "agent_orchestration": "central-planner",
          "tools_enabled": [ "search", "retrieval" ],
          "rag_enabled": true
        }
      },
      "metrics": {
        "chain_stability": 0.88,
        "semantic_coherence": 0.91,
        "drift_sensitivity": 0.11,
        "variance_compliance": 0.97,
        "boundary_violations": 0,
        "sample_size": {
          "baseline_prompts": 50,
          "perturbation_prompts": 20,
          "baseline_samples": 1250,
          "perturbation_samples": 200
        }
      },
      "ris": {
        "composite_score": 0.84,
        "level": "RIS-3",
        "status": "PASS",
        "risk_profile": {
          "structural_drift": "Low",
          "semantic_drift": "Low",
          "temporal_stability": "Low",
          "interference": "Low",
          "boundary": "Low",
          "degradation": "Low"
        },
        "valid_from": "2025-01-10",
        "valid_until": "2026-01-10"
      },
      "evidence": {
        "evaluation_report_uri": "https://.../reports/EV-2025-0001",
        "conformance_statement_uri": "https://.../conformance/EV-2025-0001",
        "raw_samples_uri": "s3://.../samples/EV-2025-0001",
        "metrics_dataset_uri": "s3://.../metrics/EV-2025-0001",
        "logs_uri": "s3://.../logs/EV-2025-0001",
        "notes": "Initial production evaluation."
      },
      "signatures": {
        "evaluator": {
          "name": "Jane Doe",
          "role": "AI Governance Lead",
          "organization": "ExampleCorp",
          "signed_at": "2025-01-11"
        },
        "system_owner": {
          "name": "John Smith",
          "role": "Product Owner",
          "organization": "ExampleCorp",
          "signed_at": "2025-01-12"
        }
      }
    }

---
