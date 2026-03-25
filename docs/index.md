---
title: Home
layout: home
nav_order: 1
---

# AAISAF — AI Security Assessment Framework
{: .fs-9 }

The first comprehensive, open-source AI security assessment framework with technique-level depth for modern AI systems.
{: .fs-6 .fw-300 }

[Get Started](/aaisaf/framework/introduction){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[View on GitHub](https://github.com/Jbermingham1/aaisaf){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## What is AAISAF?

AAISAF provides **technique-level assessment methodology** for AI systems — bridging the gap between OWASP LLM Top 10 (vulnerability categories), MITRE ATLAS (adversary tactics), and NIST AI RMF (governance).

It covers attack surfaces that no other framework addresses: **MCP servers**, **voice AI**, **agentic orchestration**, and **RAG pipelines** at operational depth.

### Key Numbers

| Metric | Value |
|:-------|:------|
| Assessment Techniques | **87** |
| Tactic Categories | **10** |
| Compliance Mappings | **6** (OWASP, MITRE ATLAS, NIST AI RMF, ISO 42001, AU/APAC Regulatory, EU AI Act) |
| Assessment Checklists | **9** |
| Maturity Levels | **5** |

### Novel Coverage

AAISAF is the **first framework globally** to provide technique-level coverage for:

- **TA06 — Voice AI Exploitation** (9 techniques): Deepfake spoofing, voice prompt injection, STT pipeline attacks, credential harvesting via voice agents
- **TA10 — MCP Server & Tool Security** (12 techniques): Tool poisoning, rug pulls, cross-origin injection, transport exploitation, consent fatigue

### How It Complements Existing Frameworks

| Framework | What It Provides | Gap AAISAF Fills |
|:----------|:----------------|:-----------------|
| OWASP LLM Top 10 | Vulnerability categories | Assessment methodology + techniques |
| MITRE ATLAS | Adversary tactic mapping | Testing guidance + compliance mapping |
| NIST AI RMF | Governance structure | Technical assessment + regulatory context |
| ISO/IEC 42001 | Management system standard | Attack techniques + operational testing |

### Assessment Types

1. **Quick Self-Assessment** (30 min) — Checklist-based, SMB-friendly
2. **Standard Assessment** (1-2 days) — All applicable tactics covered
3. **Deep Assessment** (5-10 days) — Full technique-level active testing

### Severity Scoring: AISS

AAISAF uses the **AI Impact Severity Score (AISS)** — a CVSS-compatible 0.0–10.0 scale enhanced with 5 AI-specific metrics:

- Data Sensitivity Exposure
- Autonomy Impact
- Cascade Potential
- Persistence
- Financial Impact Potential

---

## Quick Start

1. **Identify your AI system type** → [Methodology](/aaisaf/framework/methodology)
2. **Run the Quick Assessment** → [Quick Assessment](/aaisaf/assessments/quick-assessment)
3. **Review applicable tactics** → [Taxonomy](/aaisaf/taxonomy/)
4. **Score findings with AISS** → [AISS Specification](/aaisaf/assessments/aiss)
5. **Map to compliance requirements** → [Compliance](/aaisaf/compliance/)
6. **Assess maturity level** → [Maturity Model](/aaisaf/framework/maturity)

---

## Global Applicability

AAISAF is designed for **global use**. The core taxonomy, techniques, and scoring system are jurisdiction-agnostic. Compliance mapping modules provide region-specific regulatory context:

- **OWASP LLM Top 10** — Global
- **MITRE ATLAS** — Global
- **NIST AI RMF** — US / International
- **ISO/IEC 42001** — International
- **EU AI Act** — European Union
- **AU/APAC Regulatory** — Australia, APAC region (VAISS, Privacy Act, Essential Eight, SOCI Act)

Organisations in any jurisdiction can use AAISAF's techniques and methodology, selecting the compliance modules relevant to their regulatory environment.

---

## License

AAISAF is released under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) by [Bifrost Labs](https://github.com/Jbermingham1).
