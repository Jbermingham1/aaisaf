# ISO/IEC 42001 Compliance Mapping

## Overview

This document maps AAISAF assessment techniques to ISO/IEC 42001:2023 — the international standard for AI management systems. AAISAF supports ISO 42001 implementation by providing the technical security assessment methodology that the standard requires but does not define.

**Source**: [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html) — Artificial intelligence management system.

---

## Clause Mapping

### Clause 4 — Context of the Organisation

| Requirement | AAISAF Support |
|------------|----------------|
| 4.1 Understanding the organisation | [02-threat-landscape.md](../02-threat-landscape.md) provides Australian AI threat context |
| 4.2 Interested parties | AAISAF compliance mappings identify stakeholder requirements (regulators, standards bodies) |
| 4.3 Scope of AIMS | AAISAF Scope Classification (Types A–G) provides structured AI system scoping |

### Clause 5 — Leadership

| Requirement | AAISAF Support |
|------------|----------------|
| 5.1 Leadership commitment | Maturity Level 3+ requires leadership engagement with AI security |
| 5.2 AI policy | AAISAF maturity model defines what an AI security policy should contain |
| 5.3 Roles and responsibilities | Assessment methodology defines assessor, system owner, and security team roles |

### Clause 6 — Planning

| Requirement | AAISAF Support |
|------------|----------------|
| **6.1 Risk assessment** | **Core AAISAF contribution** — 87 techniques provide comprehensive AI risk identification. AISS scoring quantifies risk. |
| 6.1.2 AI risk treatment | Every technique includes remediation guidance. Assessment reports provide prioritised remediation plans. |
| 6.2 AI objectives | Maturity levels provide measurable AI security objectives |

### Clause 8 — Operation

| Requirement | AAISAF Support |
|------------|----------------|
| 8.2 AI risk assessment | AAISAF Standard and Deep Assessments fulfil this requirement |
| 8.3 AI risk treatment | Technique remediation guidance supports risk treatment implementation |
| 8.4 AI system impact assessment | AISS scoring methodology supports impact assessment |

### Clause 9 — Performance Evaluation

| Requirement | AAISAF Support |
|------------|----------------|
| 9.1 Monitoring, measurement | AISS scores provide measurable security metrics. Maturity Level 4+ requires continuous monitoring. |
| 9.2 Internal audit | AAISAF Standard Assessment serves as an AI security internal audit methodology |
| 9.3 Management review | Assessment reports with AISS scores and maturity levels support management review |

### Clause 10 — Improvement

| Requirement | AAISAF Support |
|------------|----------------|
| 10.1 Continual improvement | Maturity model (Levels 1–5) provides a structured improvement path |
| 10.2 Nonconformity and corrective action | Assessment findings with remediation guidance drive corrective actions |

---

## Annex A Controls Mapping

| ISO 42001 Control | AAISAF Techniques |
|-------------------|------------------|
| **A.5.2** AI policy | Maturity model Level 3+ — documented AI security policy |
| **A.5.4** AI system lifecycle | Assessment methodology covers development, deployment, and operation phases |
| **A.6.1.2** AI risk assessment | All 87 techniques — AAISAF IS the risk assessment methodology |
| **A.6.2.6** Third-party AI components | TA05 (Supply Chain), TA10 (MCP), TA02.009 (Vector DB) |
| **A.7.2** Data for AI development | TA07 (Data & Model Integrity, all 8 techniques) |
| **A.7.4** Data quality | TA02.001 (KB Poisoning), TA02.003 (Document Injection), TA02.004 (Embedding Manipulation), TA02.006 (Metadata Exploitation), TA02.008 (Chunking Exploitation) |
| **A.7.5** Data for AI system | TA02 (Knowledge Pipeline), TA07 (Data Integrity) |
| **A.8.2** Access control | TA08 (Access Control, all 7 techniques), TA10.005 (MCP Privilege Escalation), TA10.008 (Auth Bypass) |
| **A.8.3** Information security | All techniques — AAISAF provides comprehensive AI information security assessment |
| **A.8.4** Change management | TA10.002 (Rug Pull), TA05 (Supply Chain) — tool and dependency change risks |
| **A.9.3** Human oversight | TA03.007 (Autonomous Action), TA08.007 (HITL Bypass), TA10.012 (Consent Fatigue) |
| **A.10.2** Transparency | TA01.003 (System Prompt Extraction), TA06 (Voice AI transparency requirements) |
