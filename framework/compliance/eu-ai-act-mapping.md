# EU AI Act Compliance Mapping

## Overview

This document maps AAISAF techniques to EU AI Act requirements relevant to Australian organisations with EU exposure. Australian businesses serving EU customers, deploying AI affecting EU residents, or partnering with EU entities must comply.

**Source**: Regulation (EU) 2024/1689 — Artificial Intelligence Act.

---

## Applicability to Australian Organisations

The EU AI Act applies extraterritorially when:
1. AI system output is used in the EU (even if the system is deployed in Australia)
2. Australian business provides AI services to EU customers
3. AI system processes data of EU residents

### Risk Classification

| EU AI Act Category | AAISAF System Types | AAISAF Assessment |
|-------------------|--------------------|--------------------|
| **Unacceptable Risk** (banned) | Social scoring, real-time biometric (with exceptions) | Generally not applicable to AAISAF system types |
| **High Risk** (conformity required) | Type B/C/D in healthcare, finance, education, employment, law enforcement, critical infrastructure | Full AAISAF Deep Assessment recommended |
| **Limited Risk** (transparency) | Type A (chatbots), Type E (voice AI) | AAISAF Standard Assessment + transparency checks |
| **Minimal Risk** (voluntary) | Type A (simple chatbots) | AAISAF Quick Assessment sufficient |

---

## High-Risk AI System Requirements

### Article 9 — Risk Management System

| Requirement | AAISAF Mapping |
|------------|----------------|
| 9(2)(a) Identification of known and foreseeable risks | All 87 AAISAF techniques identify known AI risks |
| 9(2)(b) Estimation and evaluation of risks | AISS scoring provides quantitative risk evaluation |
| 9(2)(c) Management of identified risks | Every technique includes remediation guidance |
| 9(5) Testing against clearly defined metrics | AISS provides clearly defined, repeatable metrics |
| 9(8) Risk management through the lifecycle | Assessment methodology covers deployment and operation phases |

### Article 10 — Data and Data Governance

| Requirement | AAISAF Mapping |
|------------|----------------|
| 10(2) Data quality | TA02.001 (KB Poisoning), TA07.003 (Data Poisoning), TA07.006 (Fine-Tuning Poisoning) |
| 10(5) Personal data processing | TA07.007 (PII Leakage), TA02.007 (Cross-Tenant Leakage), TA06.005 (Credential Harvesting) |

### Article 12 — Record-Keeping

| Requirement | AAISAF Mapping |
|------------|----------------|
| 12(1) Automatic logging | Maturity Level 4+ requires comprehensive logging of AI system behaviour |
| 12(2) Traceability | AAISAF assessment reports document system configuration, findings, and evidence |

### Article 13 — Transparency and Provision of Information

| Requirement | AAISAF Mapping |
|------------|----------------|
| 13(1) Transparency | TA06 (Voice AI) — Article 50 specifically requires disclosure of AI interaction in voice systems |
| 13(3) Appropriate level of information | TA01.003 (System Prompt Extraction) — system design should balance transparency with security |

### Article 14 — Human Oversight

| Requirement | AAISAF Mapping |
|------------|----------------|
| 14(1) Human oversight measures | TA03.007 (Autonomous Action Abuse), TA08.007 (HITL Bypass), TA10.012 (Consent Fatigue) |
| 14(4) Ability to override AI | TA03 (Agent & Orchestration) — assess whether human can stop/override agent actions |

### Article 15 — Accuracy, Robustness, and Cybersecurity

| Requirement | AAISAF Mapping |
|------------|----------------|
| **15(1) Accuracy** | TA02 (Knowledge Pipeline) — RAG accuracy under adversarial conditions |
| **15(3) Robustness against errors** | TA01 (Prompt Manipulation), TA03.005 (Cascading Failure) |
| **15(4) Cybersecurity** | **All 87 AAISAF techniques** — Article 15(4) is the primary EU AI Act security requirement that AAISAF operationalises |
| 15(5) Against manipulation | TA01 (Prompt Manipulation), TA02.003 (Document Injection), TA10.001 (Tool Poisoning) |

---

## Article 50 — Transparency Obligations

Applicable to all AI systems, not just high-risk:

| Obligation | AAISAF Mapping |
|-----------|----------------|
| 50(1) AI-generated content marking | TA09 (AI Application) — AI outputs must be identifiable |
| 50(2) Chatbot disclosure | All Type A systems — users must be told they are interacting with AI |
| 50(3) Deepfake disclosure | TA06.002 (Synthetic Voice Spoofing), TA06.009 (Real-Time Voice Cloning) |

---

## Summary for Australian Organisations

Australian organisations should use AAISAF to demonstrate EU AI Act compliance when:

1. **Deploying AI for EU users**: Full AAISAF Standard Assessment covers Article 15(4) cybersecurity requirements
2. **Operating high-risk AI in regulated sectors**: AAISAF Deep Assessment + maturity model supports Articles 9, 10, 14, 15
3. **Providing AI services**: AAISAF assessment reports serve as evidence of due diligence for conformity assessment
4. **Voice AI with EU users**: TA06 assessment covers Article 50 transparency obligations
