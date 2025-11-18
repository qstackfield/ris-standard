# RIS Release Checklist
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Purpose

This checklist ensures that all required steps have been completed before publishing a new version of the Reasoning Integrity Standard (RIS).  
It applies to:

- initial releases  
- minor revisions  
- patch releases  
- major revisions  

---

# 2. Pre-Release Verification

## 2.1 Specification Completeness

Confirm the following files are present and finalized:

- All 14 specification sections (00–13)  
- Supporting documents  
- Schemas  
- Guides  
- Change Log  

Checklist:

- [ ] All spec sections validated  
- [ ] Glossary updated  
- [ ] Change Log updated  
- [ ] Version identifiers updated across all docs  

---

# 3. Technical Validation (Documentation Only)

(no server required)

- [ ] mkdocs.yml validated  
- [ ] mkdocs `nav:` references correct  
- [ ] Local build test: `mkdocs serve`  
- [ ] All docs render correctly  
- [ ] No dead internal links  
- [ ] No formatting breaks (lists, headers, code blocks)  
- [ ] All fenced code blocks compile correctly  
- [ ] No smart quotes or illegal Unicode characters  

---

# 4. Content Review

- [ ] Consistent terminology (matches glossary)  
- [ ] Control language aligns with normative definitions (MUST/SHALL/SHOULD/MAY)  
- [ ] Risk model descriptions consistent  
- [ ] Metrics definitions consistent  
- [ ] Evaluation methodology verified  
- [ ] Reference implementation notes updated  
- [ ] No section conflicts or circular references  
- [ ] All diagrams (if included later) match spec text  

---

# 5. Structural Integrity

- [ ] All files in `/docs` root are top-level supporting documents  
- [ ] All spec documents live in `/docs/sections/`  
- [ ] Directory format matches RIS Standard Index  
- [ ] Repository organized cleanly for public readers  

---

# 6. Versioning

- [ ] Change Log updated  
- [ ] Version string updated in all docs  
- [ ] Release manifest generated (RIS_Release_Manifest.md)  
- [ ] Tag created for release (e.g., `v1.0`)  

---

# 7. Publishing (GitHub Pages or custom domain)

(no server access required yet)

- [ ] Repo set to Public  
- [ ] GitHub Pages enabled  
- [ ] Build from `gh-pages` or `docs/`  
- [ ] Custom domain `ris.atomlabs.app` added  
- [ ] HTTPS enforced  
- [ ] Final site verified  

---

# 8. Post-Release Documentation

- [ ] RIS citation format added to homepage  
- [ ] RIS v1.0 PDF prepared (optional)  
- [ ] Announcement draft prepared (optional)  
- [ ] v1.1 roadmap created  

---

# 9. Approval

Sign-off steps before release:

- [ ] Technical review complete  
- [ ] Editorial review complete  
- [ ] Governance approval granted  
- [ ] Final publish authorization  

---

# 10. Version

Checklist applies to:

**RIS v1.0 - January 2025**

---
