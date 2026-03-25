# Australian Regulatory Compliance Mapping

## Overview

This document maps AAISAF techniques to Australian regulatory requirements. Australia does not have AI-specific legislation (as of March 2026), but existing laws create significant obligations for organisations deploying AI systems.

---

## Privacy Act 1988 & Australian Privacy Principles (APPs)

### APP 1 — Open and Transparent Management of Personal Information

| AAISAF Relevance | Requirement |
|-----------------|-------------|
| All tactics | Organisations must have a clear, up-to-date privacy policy that covers how AI systems collect, use, and disclose personal information |
| TA07.007 (PII Leakage) | Policy must address how AI outputs containing personal information are managed |
| TA06 (Voice AI) | Policy must cover voice recording, processing, and storage by AI systems |

### APP 6 — Use or Disclosure of Personal Information

| AAISAF Technique | Compliance Requirement |
|-----------------|----------------------|
| TA02.007 (Cross-Tenant Leakage) | Personal information must not be disclosed to other tenants — this constitutes an unauthorised disclosure |
| TA10.007 (Data Exfiltration via MCP) | Data exfiltrated via MCP tools constitutes unauthorised disclosure |
| TA07.001 (Training Data Extraction) | Extraction of personal information from model outputs may constitute disclosure |
| TA03.006 (Privilege Escalation) | Escalation that accesses personal information beyond authorised scope |

### APP 8 — Cross-Border Disclosure of Personal Information

| AAISAF Relevance | Requirement |
|-----------------|-------------|
| TA04 (Model API Exploitation) | If AI API calls send personal information to overseas providers, APP 8 applies |
| TA02 (Knowledge Pipeline) | RAG systems using cloud embedding services may transfer data offshore |
| TA06 (Voice AI) | Voice recordings processed by overseas AI providers trigger APP 8 |

### APP 11 — Security of Personal Information

| AAISAF Technique | Compliance Requirement |
|-----------------|----------------------|
| All techniques | Organisations must take reasonable steps to protect personal information from misuse, interference, loss, and unauthorised access |
| TA01 (Prompt Manipulation) | Input validation and output filtering are "reasonable steps" |
| TA10.008 (MCP Auth Bypass) | Authentication on all AI system endpoints is required |
| TA08.005 (Cross-Session Leakage) | Session isolation must prevent cross-user data access |
| TA02.009 (Vector DB Bypass) | Database access controls are security obligations |

### Part IIIC — Notifiable Data Breaches (NDB) Scheme

| AAISAF Technique | NDB Trigger |
|-----------------|-------------|
| TA02.007 (Cross-Tenant Leakage) | Likely eligible data breach — unauthorised access to personal information |
| TA10.007 (Data Exfiltration) | Likely eligible data breach if personal information is exfiltrated |
| TA07.007 (PII Leakage) | Possible eligible data breach depending on scale and sensitivity |
| TA10.008 (Auth Bypass) | Likely eligible data breach if personal information is accessible |
| TA06.005 (Credential Harvesting) | Eligible data breach if credentials are harvested |

**Notification timeline**: 30 days from when the entity is aware of reasonable grounds to believe an eligible data breach has occurred.

---

## Voluntary AI Safety Standard (VAISS / AI6)

Published September 2024. 10 voluntary guardrails.

| Guardrail | AAISAF Mapping |
|-----------|---------------|
| **1. Accountability** | Maturity Level 3+ requires documented AI security governance |
| **2. Transparency about AI use** | TA06 (Voice AI) — users must be informed when interacting with AI voice agents |
| **3. Responsible and reliable AI** | All TA01-TA10 — security assessment ensures reliability |
| **4. Human control** | TA03.007 (Autonomous Action Abuse), TA08.007 (HITL Bypass), TA10.012 (Consent Fatigue) |
| **5. Privacy protection** | TA02.007 (Cross-Tenant), TA07.007 (PII Leakage), TA06.005 (Credential Harvesting) |
| **6. Safety and security** | All AAISAF techniques — the framework operationalises this guardrail |
| **7. Transparency of AI systems** | TA01.003 (System Prompt Extraction) — system prompts should be designed for transparency |
| **8. Fairness** | Out of scope for AAISAF (bias assessment is not covered) |
| **9. Contestability** | Maturity Level 3+ requires documented incident response and user recourse |
| **10. Accountability for impacts** | Maturity Level 4+ requires metrics tracking and leadership reporting |

---

## ASD Essential Eight

| Mitigation Strategy | AAISAF Relevance |
|--------------------|-----------------|
| **Application Control** | TA05 (Supply Chain) — AI libraries must be approved; TA10.009 (Malicious MCP Registration) — MCP servers must be allowlisted; TA03.001 (Unauthorised Tool Invocation) |
| **Patch Applications** | TA05.002 (Dependency Confusion) — AI libraries must be patched; TA05.007 (Gateway Compromise) — AI gateways require patching |
| **Configure Microsoft Office Macros** | TA09.001 (XSS via AI Output) — AI-generated documents may contain macros |
| **User Application Hardening** | TA01 (Prompt Manipulation) — browser-based AI interfaces must be hardened |
| **Restrict Administrative Privileges** | TA10.005 (MCP Privilege Escalation), TA03.006 (Agent Delegation Escalation), TA08.002 (Privilege Escalation via AI Output) |
| **Patch Operating Systems** | AI deployment infrastructure OS patching |
| **Multi-Factor Authentication** | TA10.008 (MCP Auth Bypass) — MCP server admin interfaces require MFA; TA08.006 (Auth Bypass via Indirect Prompt) |
| **Regular Backups** | TA02.001 (Knowledge Base Poisoning) — knowledge base backups enable recovery |

---

## Security of Critical Infrastructure Act 2018 (SOCI)

Applies to AI systems deployed in the following sectors: communications, data storage/processing, financial services, water, energy, healthcare, higher education, food/grocery, transport, space, and defence.

| SOCI Obligation | AAISAF Mapping |
|----------------|---------------|
| **Critical Infrastructure Risk Management Program** | AAISAF assessment should be incorporated into the entity's CIRMP |
| **Cyber security obligations** | All AAISAF techniques are relevant — AI systems in SOCI sectors must be assessed |
| **Reporting obligations** | AI security incidents affecting critical infrastructure must be reported to the Australian Cyber Security Centre |
| **Government assistance** | In extreme cases, government may direct an entity to take actions regarding AI system security |

**Penalty context**: Civil penalties under SOCI can reach $52,500 per contravention per day for entities. AAISAF assessment demonstrates due diligence in meeting SOCI obligations.

---

## Consumer Law (Competition and Consumer Act 2010)

| AAISAF Relevance | Requirement |
|-----------------|-------------|
| TA02.001 (Knowledge Base Poisoning) | AI systems providing consumer information must not mislead — poisoned knowledge bases could generate misleading conduct |
| TA06.002 (Synthetic Voice Spoofing) | AI voice impersonation of businesses may constitute misleading conduct |
| TA01.004 (Jailbreaking) | Jailbroken AI providing financial or medical advice creates consumer law exposure |

---

## Mapping Summary

| AAISAF Tactic | Privacy Act | VAISS | Essential Eight | SOCI Act | Consumer Law |
|--------------|-------------|-------|-----------------|----------|--------------|
| TA01 Prompt Manipulation | APP 11 | G3, G6 | User App Hardening | CIRMP | Misleading conduct |
| TA02 Knowledge Pipeline | APP 6, 11; NDB | G3, G5, G6 | Backups | CIRMP | Misleading conduct |
| TA03 Agent & Orchestration | APP 6, 11 | G4, G6 | Restrict Privileges | CIRMP | — |
| TA04 Model API | APP 8, 11 | G6 | Patch Apps | CIRMP | — |
| TA05 Supply Chain | APP 11 | G6 | App Control, Patch | CIRMP | — |
| TA06 Voice AI | APP 1, 6, 8, 11; NDB | G2, G5, G6 | — | CIRMP | Misleading conduct |
| TA07 Data & Model Integrity | APP 6, 11; NDB | G3, G5 | — | CIRMP | — |
| TA08 Access Control | APP 6, 11; NDB | G4, G6 | Restrict Privileges, MFA | CIRMP | — |
| TA09 AI Application | APP 11 | G6 | App Hardening | CIRMP | — |
| TA10 MCP & Tool Security | APP 6, 11; NDB | G4, G6, G7 | App Control, MFA | CIRMP | — |
