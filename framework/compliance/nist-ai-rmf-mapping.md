# NIST AI RMF + AI 600-1 Compliance Mapping

## Overview

This document maps AAISAF assessment activities to the NIST AI Risk Management Framework (AI RMF 1.0, NIST AI 100-1) and the Generative AI Profile (NIST AI 600-1).

**Sources**:
- [NIST AI RMF 1.0](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework) (2023)
- [NIST AI 600-1 — GenAI Profile](https://doi.org/10.6028/NIST.AI.600-1) (2024)

---

## AI RMF Core Functions

### GOVERN — Establish AI risk management culture and processes

| GOVERN Subcategory | AAISAF Mapping |
|-------------------|---------------|
| GOVERN 1.1 — Legal and regulatory requirements | [Australian Regulatory Mapping](australian-regulatory-mapping.md) — full mapping to Privacy Act, VAISS, Essential Eight, SOCI Act |
| GOVERN 1.4 — Risk management processes | AAISAF assessment methodology (01-methodology.md) provides the structured risk assessment process |
| GOVERN 1.5 — Ongoing monitoring | Maturity Level 4+ requires continuous monitoring; techniques provide detection guidance |
| GOVERN 3.1 — Human oversight mechanisms | TA03.007 (Autonomous Action Abuse), TA08.007 (Human-in-the-Loop Bypass), TA10.012 (Consent Fatigue) assess human oversight effectiveness |

### MAP — Context and risk identification

| MAP Subcategory | AAISAF Mapping |
|----------------|---------------|
| MAP 1.1 — Intended purpose | Scope Classification (Types A–G) maps AI system purpose to applicable risks |
| MAP 1.5 — Third-party risks | TA05 (Supply Chain) assesses third-party model, library, and data risks; TA10 (MCP) assesses third-party tool risks |
| MAP 2.1 — Scientific integrity | TA07 (Data & Model Integrity) assesses training data and model integrity |
| MAP 3.4 — Measurement approaches | AISS scoring specification provides quantitative risk measurement |

### MEASURE — Assess, analyse, and track AI risks

| MEASURE Subcategory | AAISAF Mapping |
|--------------------|---------------|
| MEASURE 1.1 — Appropriate methods | AAISAF assessment types (Quick/Standard/Deep) provide scaled assessment methods |
| MEASURE 2.3 — AI system performance | TA01 (Prompt Manipulation) measures safety control effectiveness under adversarial conditions |
| MEASURE 2.5 — Bias and fairness | Out of scope for AAISAF — see NIST AI RMF directly |
| MEASURE 2.6 — AI system security | **All 87 AAISAF techniques** — this is the primary mapping. AAISAF operationalises MEASURE 2.6 |
| MEASURE 2.7 — System security controls | TA04 (API Security), TA08 (Access Control), TA10 (MCP Security) assess system-level security controls |
| MEASURE 3.3 — Human oversight feedback | TA10.012 (Consent Fatigue) assesses human oversight effectiveness |

### MANAGE — Prioritise and act on AI risks

| MANAGE Subcategory | AAISAF Mapping |
|-------------------|---------------|
| MANAGE 1.1 — Risk prioritisation | AISS scoring provides risk prioritisation methodology |
| MANAGE 1.3 — Risk response | Every AAISAF technique includes remediation guidance |
| MANAGE 2.1 — Risk monitoring | Maturity Level 4+ requires continuous risk monitoring |
| MANAGE 4.1 — Incident management | AAISAF assessment identifies risks before incidents; maturity model requires incident response |

---

## NIST AI 600-1 — Generative AI Profile

The GenAI Profile identifies 12 risks specific to generative AI. AAISAF mapping:

| GenAI Risk | AAISAF Techniques |
|-----------|------------------|
| **CBRN Information** | TA01.004 (Jailbreaking), TA08.001 (Guardrail Bypass) |
| **Confabulation** | TA02.001 (Knowledge Base Poisoning) — poisoned RAG increases confabulation with false data |
| **Data Privacy** | TA07.001 (Training Data Extraction), TA07.002 (Membership Inference), TA07.007 (PII Leakage), TA02.007 (Cross-Tenant Leakage) |
| **Environmental** | TA04.001 (Cost Exhaustion) — resource abuse has environmental cost |
| **Human-AI Configuration** | TA08.007 (Human-in-the-Loop Bypass), TA10.012 (Consent Fatigue) |
| **Information Integrity** | TA02.001 (KB Poisoning), TA02.003 (Document Injection), TA07.003 (Data Poisoning) |
| **Information Security** | All TA01-TA10 techniques — AAISAF comprehensively covers this risk |
| **Intellectual Property** | TA07.001 (Training Data Extraction), TA07.008 (Model Weight Exfiltration) |
| **Obscene/Degrading** | TA01.004 (Jailbreaking), TA08.003 (Content Filter Evasion) |
| **Toxicity/Bias/Homogenisation** | Out of scope for AAISAF — bias/fairness assessment is separate |
| **Value Chain/Component** | TA05 (Supply Chain, all 7 techniques), TA10.009 (Malicious MCP Registration) |
| **Dangerous/Violent** | TA01.004 (Jailbreaking), TA08.001 (Guardrail Bypass), TA06.007 (Vishing) |
