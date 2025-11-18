# RIS Example Prompt Dataset
Reasoning Integrity Standard (RIS)  
Version 1.0  
Published by Atom Labs

---

# 1. Introduction

This document provides an example dataset structure for RIS evaluation.  
It is intended to help organizations build their own baseline and perturbation prompt sets.

RIS does not mandate specific prompts.  
This dataset format demonstrates best practices.

---

# 2. Dataset Structure

A RIS dataset consists of:

- baseline prompts  
- perturbation prompts  
- metadata  

Recommended structure:

    {
      "prompts": [
        {
          "id": "P001",
          "baseline": "Explain the role of supply shocks in inflation.",
          "perturbations": [
            "Describe how supply disruptions affect inflation.",
            "How do supply-side constraints influence inflation?",
            "Explain how production bottlenecks relate to inflation."
          ],
          "metadata": {
            "domain": "economics",
            "difficulty": "medium"
          }
        }
      ]
    }

---

# 3. Example Baseline Prompts

Example prompts across categories:

### Reasoning
- Explain how signal-to-noise ratio affects information reliability.
- Describe the relationship between cause and effect in policy analysis.

### Analysis
- Compare two approaches for optimizing system performance.
- Analyze the implications of shifting economic trends.

### Multi-step reasoning
- Outline the steps required to evaluate the validity of an argument.
- Explain how to derive insights from incomplete information.

---

# 4. Example Perturbation Prompts

Perturbations MUST preserve meaning while altering structure or phrasing.

Examples:

    Baseline:
    "Explain the impact of market consolidation on competition."

    Perturbations:
    "Describe how consolidation affects competitive dynamics."
    "How does market concentration influence competition?"
    "Discuss the consequences of fewer firms in a market."

---

# 5. Metadata Examples

Metadata helps evaluators track:

- domain  
- complexity  
- reasoning type  
- intended test category  

Example metadata:

    {
      "domain": "economics",
      "difficulty": "medium",
      "task_type": "explanatory"
    }

---

# 6. Dataset Size Guidelines

Recommended:

- 50+ baseline prompts for general-purpose models  
- 20+ baseline prompts for domain-specific models  
- 10 perturbations per selected baseline prompt  

---

# 7. Customization

Organizations MAY:

- create domain-specific prompt sets  
- test scenario-specific reasoning stability  
- build templates for different industries  
- integrate datasets into automated test pipelines  

---

# 8. Summary

This example dataset demonstrates:

- how to structure RIS prompts  
- how to create baseline and perturbation sets  
- how to store metadata  
- how to prepare evaluation inputs  

Organizations SHOULD tailor their datasets to their risk profile, domain, and model type.

---
