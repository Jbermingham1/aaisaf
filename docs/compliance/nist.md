---
title: NIST AI RMF
layout: default
parent: Compliance
nav_order: 3
---

# NIST AI RMF Mapping

Maps AAISAF techniques to the NIST AI Risk Management Framework and AI 600-1 (Generative AI Profile).

AAISAF operationalises the MEASURE function by providing concrete measurement techniques for AI-specific risks.

| NIST AI RMF Function | Relevant AAISAF Tactics | Key Techniques |
|:---------------------|:-----------------------|:---------------|
| **GOVERN** — Policies and accountability | All (governance overlay) | Maturity model, executive checklist |
| **MAP** — Context and risk identification | TA01–TA10 (taxonomy) | System classification (Types A–G) |
| **MEASURE** — Risk assessment | All techniques | AISS scoring, 9 checklists |
| **MANAGE** — Risk treatment | All remediations | Technique-level remediation guidance |

### AI 600-1 (GenAI Profile) Mapping

| GenAI Risk | AAISAF Techniques |
|:-----------|:-----------------|
| Confabulation | TA01 (prompt manipulation inducing hallucination) |
| Data Privacy | TA07.001, TA07.002, TA07.004, TA07.007, TA08.005 |
| Environmental | TA04.001 (cost/resource exhaustion) |
| Information Integrity | TA02.001, TA02.003, TA07.003, TA07.005 |
| Information Security | TA01–TA10 (full taxonomy) |
| Intellectual Property | TA07.001, TA07.008 |
| Obscene/Abusive Content | TA08.001, TA08.003 (guardrail/filter bypass) |
| Value Chain | TA05.001–007 (supply chain) |

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/compliance/nist-ai-rmf-mapping.md){: .btn }
