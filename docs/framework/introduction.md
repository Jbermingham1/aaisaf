---
title: Introduction
layout: default
parent: Framework
nav_order: 1
---

# Introduction

## Purpose

The AI Security Assessment Framework (AAISAF) provides a structured, evidence-based methodology for assessing the security of artificial intelligence systems. It is the operational layer that bridges existing frameworks — OWASP LLM Top 10, MITRE ATLAS, and NIST AI RMF — into actionable assessment techniques with multi-jurisdiction compliance mapping.

AAISAF exists because:

1. **No framework provides technique-level AI assessment methodology.** OWASP lists vulnerability categories. MITRE maps adversary tactics. NIST defines governance. None tell a practitioner *how* to test an AI system step by step.

2. **Critical attack surfaces are uncovered.** MCP (Model Context Protocol) servers, voice AI systems, and agentic orchestration emerged as production technologies in 2025-2026. No existing framework covers their security assessment at operational depth.

3. **Most jurisdictions lack AI-specific security assessment guidance.** Standards like the EU AI Act, Australia's VAISS/AI6, and NIST AI RMF provide governance — not operational testing methodology. Practitioners need a concrete framework now.

## Scope

AAISAF covers the security assessment of:

- Large Language Model (LLM) applications and chatbots
- Retrieval-Augmented Generation (RAG) systems
- Agentic AI with tool use and autonomous action capabilities
- Multi-agent orchestration systems
- Voice AI systems (phone agents, voice assistants, STT/TTS pipelines)
- MCP (Model Context Protocol) server implementations
- Composite systems combining multiple AI capabilities

AAISAF does **not** cover:

- Traditional ML model security (image classifiers, recommendation systems) — see MITRE ATLAS
- AI ethics, fairness, or bias assessment — see NIST AI RMF MAP function
- AI governance programme design — see ISO/IEC 42001
- General application security without AI components — see OWASP ASVS

## Audience

| Audience | How to Use AAISAF |
|:---------|:-----------------|
| **AI Security Assessors** | Primary users. Follow the assessment methodology, apply techniques, use checklists. |
| **Security Engineers** | Use technique descriptions for threat modelling, secure design, and code review. |
| **CISOs / Security Leaders** | Use the maturity model and executive checklist to evaluate organisational readiness. |
| **Developers Building AI Systems** | Use remediation guidance to build secure AI applications from the start. |
| **Compliance Officers** | Use compliance mappings to demonstrate alignment with OWASP, NIST, ISO, and regional regulations. |
| **Regulators / Policy Makers** | Reference the taxonomy and threat landscape for evidence-based policy development. |

## Relationship to Existing Frameworks

```
┌─────────────────────────────────────────────────────────┐
│                  GOVERNANCE LAYER                        │
│  NIST AI RMF  ·  ISO/IEC 42001  ·  EU AI Act  ·  VAISS │
├─────────────────────────────────────────────────────────┤
│                  THREAT INTELLIGENCE                     │
│  MITRE ATLAS  ·  OWASP LLM Top 10                       │
├─────────────────────────────────────────────────────────┤
│           ╔══════════════════════════════╗                │
│           ║  AAISAF — OPERATIONAL LAYER  ║                │
│           ║  Technique-level assessment  ║                │
│           ║  Checklists · AISS Scoring   ║                │
│           ║  Multi-jurisdiction mapping   ║                │
│           ╚══════════════════════════════╝                │
├─────────────────────────────────────────────────────────┤
│                  IMPLEMENTATION                          │
│  Application Security Testing  ·  Penetration Testing    │
└─────────────────────────────────────────────────────────┘
```

## Global Applicability

AAISAF's core taxonomy, techniques, and scoring system are **jurisdiction-agnostic**. Compliance mapping modules provide region-specific regulatory context:

- **OWASP LLM Top 10** — Global
- **MITRE ATLAS** — Global
- **NIST AI RMF** — US / International
- **ISO/IEC 42001** — International
- **EU AI Act** — European Union
- **AU/APAC Regulatory** — Australia, APAC region

Organisations in any jurisdiction can use AAISAF's techniques and methodology, selecting the compliance modules relevant to their regulatory environment.

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/00-introduction.md){: .btn }
