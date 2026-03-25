---
title: AU/APAC Regulatory
layout: default
parent: Compliance
nav_order: 5
---

# AU/APAC Regulatory Mapping

Maps AAISAF techniques to Australian and APAC regulatory requirements.

## Applicable Regulations

| Regulation | Scope | Key Requirements |
|:-----------|:------|:----------------|
| **VAISS/AI6** | Voluntary AI Safety Standard | 10 guardrails for AI safety |
| **Privacy Act 1988** (APPs) | All organisations handling personal information | APP 11 (security), APP 6 (use/disclosure) |
| **Essential Eight** | Government + critical infrastructure | Baseline security controls |
| **SOCI Act 2018** | Critical infrastructure sectors | Risk management, incident reporting |

## Technique Mapping

| Regulation | Key AAISAF Techniques |
|:-----------|:---------------------|
| **VAISS Guardrail 3** (Contestability) | TA01 (prompt manipulation), TA06.001 (voice injection) |
| **VAISS Guardrail 7** (Transparency) | TA10.001 (tool poisoning), TA08.004 (role manipulation) |
| **VAISS Guardrail 8** (Privacy) | TA07.007 (PII leakage), TA02.007 (cross-tenant), TA08.005 (session leakage) |
| **Privacy Act APP 11** (Security) | All techniques (security of AI processing personal information) |
| **Privacy Act APP 6** (Use/Disclosure) | TA07.001 (data extraction), TA07.007 (PII leakage), TA10.007 (exfiltration) |
| **Essential Eight** | TA05 (supply chain — patching, application control), TA08 (access control) |
| **SOCI Act** | TA03.005 (cascading failure), TA04.001 (denial of service), TA05.007 (gateway compromise) |

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/compliance/australian-regulatory-mapping.md){: .btn }
