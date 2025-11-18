# RIS Dynamic Portal Layout Specification
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

## 1. Purpose

This document defines a recommended layout for a dynamic RIS portal hosted at:

    https://ris.atomlabs.app

The portal is intended to:

- present the Reasoning Integrity Standard
- showcase certified systems
- act as an authoritative reference for RIS levels and scorecards

---

## 2. High-Level Pages

Suggested primary pages:

- Home
- Directory
- Certification Detail
- Scorecard View
- About / Standard
- Resources (Guides, Templates)
- Governance / Program

---

## 3. Home Page

Elements:

- brief description of RIS
- current version (v1.0)
- call-to-action buttons:
  - View Standard
  - Browse Certified Systems
  - Download Templates
- high-level stats:
  - total certifications
  - distribution by RIS level
- selected featured systems (optional)

---

## 4. Directory Page

Purpose:

- display a searchable, filterable table of RIS Certification Entries

Key components:

- filters:
  - organization
  - RIS level
  - category
  - status
  - tags
- search bar:
  - free-text across system name, organization, tags
- table columns:
  - system name
  - organization
  - category
  - RIS level
  - composite score
  - status
  - valid until

Rows link to **Certification Detail** page.

---

## 5. Certification Detail Page

Purpose:

- human-readable view of a single certification entry

Sections:

- system overview
- RIS classification
- risk profile
- validity period
- links:
  - model card
  - scorecard JSON
  - conformance statement
  - evaluation report

Optional:

- mini-charts for metrics (stability, coherence, drift, variance)

---

## 6. Scorecard View

Purpose:

- present RIS Scorecard in structured, readable format

Sections:

- system details
- evaluation details
- metrics
- RIS outcomes
- risk profile
- evidence references

Offer:

- "Download JSON"
- "Download PDF" (optional)

---

## 7. About / Standard Page

Sections:

- what RIS is
- why it exists
- who maintains it
- link to:
  - full spec
  - overview
  - change log
  - glossary

This page SHOULD be static and updated only when RIS versions change.

---

## 8. Resources Page

Content:

- links to guides:
  - Quickstart
  - Benchmark Guide
  - Integration Guide
  - SDK Guide
  - Evaluation Report Template
  - Conformance Statement Template
- links to example datasets

---

## 9. Governance / Program Page

Content:

- description of RIS certification program
- levels and requirements
- assessment and reassessment cycles
- how to participate
- contact information

Over time, this may evolve into a full program description for enterprises and regulators.

---

## 10. UX Principles

Recommended design principles:

- clarity over marketing
- emphasize auditability and transparency
- minimize branding noise
- highlight RIS level and risk information
- accessible and responsive design

---

## 11. Integration With APIs

Dynamic content SHOULD be driven by:

- the RIS Directory API
- certification entry API
- scorecard retrieval API
- stats API

This separates presentation (UI) from data (backend).

---
