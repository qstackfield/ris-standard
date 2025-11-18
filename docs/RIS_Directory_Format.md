# RIS Directory Format
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

The RIS Directory Format defines how collections of RIS certification entries SHOULD be represented for:

- public directories
- internal registries
- leaderboards
- discovery APIs

The directory is essentially a list of certification entries with optional pagination and filters.

---

## 2. Directory Structure

    {
      "schema_version": "1.0",
      "generated_at": "YYYY-MM-DDThh:mm:ssZ",
      "total_entries": 0,
      "page": 1,
      "page_size": 50,
      "filters": { ... },
      "entries": [ ... ]
    }

Fields:

- schema_version: directory format version
- generated_at: timestamp of directory generation
- total_entries: total number of entries matching current filters
- page: current page number
- page_size: number of entries per page
- filters: description of filters applied
- entries: array of RIS Certification Entries

---

## 3. filters Object

    "filters": {
      "organization": "string or null",
      "ris_level_min": "string or null",
      "ris_level_max": "string or null",
      "category": "string or null",
      "status": "string or null",
      "tag": "string or null",
      "search": "string or null"
    }

All filters MAY be null, indicating no filter applied.

---

## 4. entries Array

The entries array SHALL contain RIS Certification Entries as defined in the RIS Certification Entry Schema.

Example:

    "entries": [
      { ... certification_entry_1 ... },
      { ... certification_entry_2 ... }
    ]

---

## 5. Example Directory Document

    {
      "schema_version": "1.0",
      "generated_at": "2025-01-15T10:30:00Z",
      "total_entries": 245,
      "page": 1,
      "page_size": 50,
      "filters": {
        "organization": null,
        "ris_level_min": "RIS-3",
        "ris_level_max": null,
        "category": null,
        "status": "Active",
        "tag": null,
        "search": null
      },
      "entries": [
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
          "links": { ... },
          "tags": [ "production", "analytics" ],
          "last_updated": "2025-01-12"
        }
      ]
    }

---

## 6. Usage

Directories may be:

- generated on demand
- cached on a schedule
- returned by a REST API
- used as static JSON for portals

They provide the basis for:

- UI tables
- search interfaces
- filters and sorting
- public RIS directories

---
