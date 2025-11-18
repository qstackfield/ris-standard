# RIS Certification Entry Schema
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

This document defines the JSON structure for a **RIS Certification Entry**, representing a single certified system in a public or internal registry (directory, leaderboard, portal).

A certification entry is a short, indexable record derived from a full RIS scorecard and associated evidence.

---

## 2. Top-Level Structure

    {
      "schema_version": "1.0",
      "id": "string",
      "system_name": "string",
      "system_version": "string",
      "organization": "string",
      "category": "string",
      "ris_level": "string",
      "composite_score": 0.0,
      "status": "string",
      "valid_from": "YYYY-MM-DD",
      "valid_until": "YYYY-MM-DD",
      "evaluation_id": "string",
      "links": { ... },
      "tags": [ "string" ],
      "last_updated": "YYYY-MM-DD"
    }

---

## 3. Field Definitions

- schema_version: schema version for compatibility
- id: unique certification entry ID
- system_name: human-readable system or model name
- system_version: version string for the certified system
- organization: legal entity that owns the system
- category: type of system (e.g., "LLM", "agent", "RAG", "multi-agent")
- ris_level: assigned RIS level (e.g., "RIS-3")
- composite_score: overall reasoning integrity score
- status: certification status ("Active", "Expired", "Revoked", "Pending")
- valid_from: date the certification became effective
- valid_until: expiry date per RIS rules
- evaluation_id: reference to a specific evaluation
- links: references to additional resources
- tags: free-form labels for filtering
- last_updated: last modification date of this entry

---

## 4. links Object

    "links": {
      "scorecard_uri": "string",
      "evaluation_report_uri": "string",
      "conformance_statement_uri": "string",
      "model_card_uri": "string",
      "public_portal_uri": "string"
    }

These are typically HTTPS URLs, but may be internal URIs.

---

## 5. Example Certification Entry

    {
      "schema_version": "1.0",
      "id": "CERT-2025-0001",
      "system_name": "Example Agent",
      "system_version": "1.2.3",
      "organization": "ExampleCorp",
      "category": "agent",
      "ris_level": "RIS-3",
      "composite_score": 0.84,
      "status": "Active",
      "valid_from": "2025-01-10",
      "valid_until": "2026-01-10",
      "evaluation_id": "EV-2025-0001",
      "links": {
        "scorecard_uri": "https://ris.example.com/scorecards/CERT-2025-0001",
        "evaluation_report_uri": "https://ris.example.com/reports/EV-2025-0001",
        "conformance_statement_uri": "https://ris.example.com/conformance/EV-2025-0001",
        "model_card_uri": "https://ml.example.com/models/example-agent",
        "public_portal_uri": "https://ris.example.com/directory/CERT-2025-0001"
      },
      "tags": [ "production", "internal", "analytics" ],
      "last_updated": "2025-01-12"
    }

---

## 6. Use in Public Directories

Certification entries are designed to be:

- lightweight
- indexable
- filterable
- cacheable

They power:

- RIS leaderboards
- certification registries
- query APIs
- search interfaces

---
