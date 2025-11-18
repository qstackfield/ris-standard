# 13. Appendices

## 13.1 Overview

This section contains informative appendices supporting the implementation, evaluation, and audit of the Reasoning Integrity Standard (RIS). Appendices are not normative unless explicitly referenced by a control or requirement.

The materials in this section include:

- definitions and terminology  
- mathematical formulations  
- example baseline structures  
- sample drift and variance calculations  
- reference ledger entries  
- prompt set templates  
- evaluation dataset formats  
- implementation considerations  

---

# 13.2 Key Definitions

## 13.2.1 Reasoning chain
A sequence of internal conceptual steps used by an LLM or agent to derive an output from an input.

## 13.2.2 Structural drift
A deviation in the ordering, length, or internal transitions of a reasoning chain beyond acceptable variance thresholds.

## 13.2.3 Semantic drift
A deviation in meaning, conceptual structure, or topic alignment across samples.

## 13.2.4 Variance envelope
The statistical boundary within which repeated inference behavior must remain to be considered stable.

## 13.2.5 Boundary violation
A reasoning event in which the model exceeds defined contextual, semantic, or operational constraints.

## 13.2.6 Interference event
An alteration of reasoning behavior caused by a tool, agent, retrieval source, or external system.

---

# 13.3 Mathematical Formulations

## 13.3.1 Chain stability score

Chain stability S is calculated as:

S = mean(similarity(Ri, Rj))

Where:

- Ri and Rj are pairs of reasoning chain representations  
- similarity is structural similarity between 0.00 and 1.00  

## 13.3.2 Semantic coherence score

Semantic coherence C is calculated using embedding similarity:

C = mean(cosine(Ei, Ej))

Where:

- Ei and Ej are embeddings of reasoning outputs  
- cosine is cosine similarity  

## 13.3.3 Drift sensitivity

Drift sensitivity D is calculated as:

D = variance(S) + variance(C)

Higher values indicate greater drift.

## 13.3.4 Variance envelope compliance

Compliance V is calculated as:

V = (number of samples within envelope) / (total samples)

Values are expressed as percentages.

---

# 13.4 Example Variance Envelopes

Systems MAY use the following envelope templates:

## 13.4.1 General-purpose LLM envelope

- chain stability: 0.75 to 1.00  
- semantic coherence: 0.80 to 1.00  
- drift sensitivity: below 0.30  

## 13.4.2 High-integrity envelope

- chain stability: 0.90 to 1.00  
- semantic coherence: 0.90 to 1.00  
- drift sensitivity: below 0.10  

Evaluators SHALL adjust envelopes based on domain requirements.

---

# 13.5 Example Ledger Entry (Reference Implementation)

Below is a sample hash-linked ledger entry derived from the LCAC reference implementation.
