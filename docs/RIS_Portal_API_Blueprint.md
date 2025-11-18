# RIS Public Portal API Blueprint
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

This document defines a reference API blueprint for a RIS public portal.

The portal API is responsible for:

- listing RIS-certified systems
- returning certification entries
- returning scorecards
- exposing metadata for UI components

This blueprint is implementation-agnostic.  
Organizations MAY implement any subset of these endpoints.

---

## 2. Base URL

Examples:

- https://ris.atomlabs.app/api
- https://ris.example.com/api

---

## 3. Endpoints Overview

Recommended endpoints:

- GET /directory
- GET /certifications/{id}
- GET /scorecards/{id}
- GET /organizations
- GET /stats

Optional:

- GET /levels
- GET /tags
- GET /search

---

## 4. GET /directory

Returns a paginated RIS directory.

Query parameters:

- page (integer, default 1)
- page_size (integer, default 50)
- organization
- category
- ris_level_min
- ris_level_max
- status
- tag
- search

Response body follows the RIS Directory Format.

---

## 5. GET /certifications/{id}

Returns a RIS Certification Entry.

Path parameter:

- id: certification entry ID (e.g., "CERT-2025-0001")

Response:

- 200: certification entry JSON
- 404: not found

---

## 6. GET /scorecards/{id}

Returns the full RIS Scorecard for a given certification.

Path parameter:

- id: certification entry ID or evaluation ID

Response:

- 200: RIS Scorecard JSON
- 404: not found

---

## 7. GET /organizations

Returns a list of organizations participating in RIS.

Response example:

    {
      "organizations": [
        {
          "name": "ExampleCorp",
          "slug": "examplecorp",
          "total_certifications": 5,
          "highest_ris_level": "RIS-4"
        }
      ]
    }

---

## 8. GET /stats

Returns high-level portal statistics.

Example:

    {
      "total_certifications": 245,
      "by_ris_level": {
        "RIS-0": 4,
        "RIS-1": 21,
        "RIS-2": 80,
        "RIS-3": 110,
        "RIS-4": 30
      },
      "by_category": {
        "LLM": 90,
        "agent": 100,
        "RAG": 40,
        "multi-agent": 15
      }
    }

---

## 9. Optional: GET /search

Search endpoint using free-text query parameter.

- q: search string

Returns lightweight certification entries or directory-like responses.

---

## 10. Security Considerations

Public portal APIs SHOULD:

- be read-only
- avoid exposing sensitive details
- rate-limit abusive usage
- support HTTPS only

Write operations (e.g., submitting evaluations) SHOULD be handled by separate, authenticated APIs.

---
