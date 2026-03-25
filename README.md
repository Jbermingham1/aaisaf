# AAISAF — AI Security Assessment Framework

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/Jbermingham1/aaisaf/releases)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Techniques](https://img.shields.io/badge/techniques-87-red.svg)](#taxonomy)
[![Tactics](https://img.shields.io/badge/tactics-10-orange.svg)](#taxonomy)

**The first comprehensive, open-source AI security assessment framework with technique-level depth for modern AI systems.**

AAISAF provides technique-level assessment methodology for AI systems — bridging the gap between OWASP LLM Top 10 (vulnerability categories), MITRE ATLAS (adversary tactics), and NIST AI RMF (governance). It covers attack surfaces that no other framework addresses: **MCP servers**, **voice AI**, **agentic orchestration**, and **RAG pipelines** at operational depth. Designed for global use with regional compliance modules including AU/APAC, EU AI Act, and international standards.

---

## Why AAISAF Exists

Existing frameworks tell you **what** to worry about. AAISAF tells you **how** to test for it.

| Framework | What It Provides | What's Missing |
|-----------|-----------------|----------------|
| OWASP LLM Top 10 | Vulnerability categories | No assessment methodology, no techniques |
| MITRE ATLAS | Adversary tactic mapping | No testing guidance, no compliance mapping |
| NIST AI RMF | Governance structure | No technical assessment, no regulatory context |
| ISO/IEC 42001 | Management system standard | No attack techniques, no operational testing |
| **AAISAF** | **All of the above + technique-level testing + multi-jurisdiction compliance** | — |

### What Makes AAISAF Different

- **87 assessment techniques** across 10 tactic categories — each with evidence, detection, and remediation
- **Novel coverage**: MCP server security (TA10) and Voice AI exploitation (TA06) — covered by no other framework
- **AISS severity scoring**: CVSS-compatible 0.0–10.0 scale with 5 AI-specific impact metrics
- **Multi-jurisdiction compliance mapping**: OWASP, MITRE ATLAS, NIST, ISO 42001, EU AI Act, AU/APAC regulatory
- **Three assessment types**: 30-minute self-assessment to 10-day deep assessment
- **5-level maturity model** with clear progression criteria
- **9 domain checklists** ready for immediate practitioner use

---

## Taxonomy

10 tactic categories covering the full AI attack surface:

| ID | Tactic | Techniques | Novel? |
|----|--------|-----------|--------|
| TA01 | [Prompt Manipulation](framework/tactics/TA01-prompt-manipulation.md) | 12 | Enhanced |
| TA02 | [Knowledge Pipeline Exploitation](framework/tactics/TA02-knowledge-pipeline.md) | 9 | Enhanced |
| TA03 | [Agent & Orchestration Abuse](framework/tactics/TA03-agent-orchestration.md) | 10 | Enhanced |
| TA04 | [Model API Exploitation](framework/tactics/TA04-model-api.md) | 7 | Enhanced |
| TA05 | [AI Supply Chain Compromise](framework/tactics/TA05-supply-chain.md) | 7 | Enhanced |
| TA06 | [Voice AI Exploitation](framework/tactics/TA06-voice-ai.md) | 9 | **First** |
| TA07 | [Training Data & Model Integrity](framework/tactics/TA07-data-integrity.md) | 8 | Enhanced |
| TA08 | [Access Control Subversion](framework/tactics/TA08-access-control.md) | 7 | Enhanced |
| TA09 | [AI-Enhanced Application Attacks](framework/tactics/TA09-ai-application.md) | 6 | Enhanced |
| TA10 | [MCP Server & Tool Security](framework/tactics/TA10-mcp-tool-security.md) | 12 | **First** |

→ [Full taxonomy overview](framework/03-taxonomy-overview.md)

---

## Quick Start

### 1. Identify Your AI System Type

| Type | Description | Example |
|------|-------------|---------|
| A | LLM chatbot/assistant | Customer support bot |
| B | RAG-augmented system | Internal knowledge base Q&A |
| C | Agentic AI with tool use | Coding assistant, data analyst agent |
| D | Multi-agent orchestration | Autonomous workflow systems |
| E | Voice AI system | AI phone agent, voice assistant |
| F | MCP-connected system | IDE integration, tool-use via MCP |
| G | Composite | Multiple types combined |

### 2. Choose Your Assessment Type

| Type | Duration | Best For |
|------|----------|----------|
| [Quick Self-Assessment](assessments/quick-assessment.md) | 30 min | SMBs, initial baseline, awareness |
| [Standard Assessment](assessments/standard-assessment.md) | 1–2 days | All organisations, compliance prep |
| [Deep Assessment](assessments/standard-assessment.md#deep-assessment) | 5–10 days | Critical systems, regulatory requirement |

### 3. Run the Assessment

1. Scope the system using the [classification guide](framework/01-methodology.md#scope-classification)
2. Select applicable tactics based on system type
3. Work through the relevant [checklists](assessments/checklists/)
4. Score findings using [AISS](assessments/scoring/aiss-specification.md)
5. Map to compliance requirements using the [compliance guides](framework/compliance/)
6. Determine maturity level using the [maturity model](framework/maturity/maturity-model.md)
7. Generate report with findings, risk ratings, and remediation priorities

---

## Assessment Checklists

| Checklist | Applicable System Types |
|-----------|------------------------|
| [Prompt Security](assessments/checklists/01-prompt-security.md) | A, B, C, D, E, F, G |
| [RAG & Knowledge Pipeline](assessments/checklists/02-rag-pipeline.md) | B, D, G |
| [Agent & Orchestration](assessments/checklists/03-agent-orchestration.md) | C, D, G |
| [MCP & Tool Security](assessments/checklists/04-mcp-tool-security.md) | C, F, G |
| [Voice AI](assessments/checklists/05-voice-ai.md) | E, G |
| [API Security](assessments/checklists/06-api-security.md) | All |
| [Supply Chain](assessments/checklists/07-supply-chain.md) | All |
| [Data Protection](assessments/checklists/08-data-protection.md) | All |
| [Executive / CISO](assessments/checklists/09-executive-ciso.md) | All (non-technical) |

---

## Compliance Mappings

AAISAF maps every technique to established standards:

- [OWASP LLM Top 10 (2025)](framework/compliance/owasp-llm-mapping.md)
- [MITRE ATLAS](framework/compliance/mitre-atlas-mapping.md)
- [NIST AI RMF + AI 600-1](framework/compliance/nist-ai-rmf-mapping.md)
- [ISO/IEC 42001](framework/compliance/iso-42001-mapping.md)
- [AU/APAC Regulatory](framework/compliance/australian-regulatory-mapping.md) — Privacy Act, VAISS/AI6, Essential Eight, SOCI Act
- [EU AI Act](framework/compliance/eu-ai-act-mapping.md) — For organisations with EU exposure

---

## Maturity Model

| Level | Name | Description |
|-------|------|-------------|
| 1 | Initial | No formal AI security practices |
| 2 | Developing | Basic defences, some input validation |
| 3 | Defined | Documented policies, regular AAISAF testing |
| 4 | Managed | Continuous monitoring, automated testing, metrics-driven |
| 5 | Optimised | Red team exercises, proactive threat intelligence, community contribution |

→ [Full maturity model](framework/maturity/maturity-model.md)

---

## Framework Structure

```
aaisaf/
├── framework/
│   ├── 00-introduction.md          # Purpose, scope, audience
│   ├── 01-methodology.md           # Assessment methodology
│   ├── 02-threat-landscape.md      # Australian AI threat landscape 2026
│   ├── 03-taxonomy-overview.md     # Full taxonomy with mappings
│   ├── tactics/                    # 10 tactic overview files
│   ├── techniques/                 # 87 individual technique files
│   ├── compliance/                 # 6 compliance mapping documents
│   └── maturity/                   # 5-level maturity model
├── assessments/
│   ├── quick-assessment.md         # 30-min self-assessment
│   ├── standard-assessment.md      # Full methodology
│   ├── checklists/                 # 9 domain checklists
│   └── scoring/                    # AISS specification
└── references/
    ├── glossary.md
    ├── cve-index.md
    └── bibliography.md
```

---

## About

AAISAF is developed and maintained by [Jarrad Bermingham](https://github.com/Jbermingham1) / Bifrost Labs — an AI security research lab based in Australia, building for global practitioners.

This framework is independent, open-source, and vendor-neutral. It does not promote any commercial product or service. Contributions are welcome from the global security community.

### Citation

```
Bermingham, J. (2026). AI Security Assessment Framework (AAISAF) v1.0.
https://github.com/Jbermingham1/aaisaf
```

### License

[CC BY-SA 4.0](LICENSE) — Share and adapt freely with attribution.
