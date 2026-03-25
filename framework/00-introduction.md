# AAISAF — Introduction

## Purpose

The Australian AI Security Assessment Framework (AAISAF) provides a structured, evidence-based methodology for assessing the security of artificial intelligence systems. It is the operational layer that bridges existing frameworks — OWASP LLM Top 10, MITRE ATLAS, and NIST AI RMF — into actionable assessment techniques with Australian regulatory context.

AAISAF exists because:

1. **No framework provides technique-level AI assessment methodology.** OWASP lists vulnerability categories. MITRE maps adversary tactics. NIST defines governance. None tell a practitioner *how* to test an AI system step by step.

2. **Critical attack surfaces are uncovered.** MCP (Model Context Protocol) servers, voice AI systems, and agentic orchestration emerged as production technologies in 2025-2026. No existing framework covers their security assessment at operational depth.

3. **Australia lacks AI-specific security guidance.** The Voluntary AI Safety Standard (VAISS/AI6) is high-level and non-binding. The AI Safety Institute has not published assessment methodology. Practitioners need a concrete framework now.

## Scope

AAISAF covers the security assessment of:

- Large Language Model (LLM) applications and chatbots
- Retrieval-Augmented Generation (RAG) systems
- Agentic AI with tool use and autonomous action capabilities
- Multi-agent orchestration systems
- Voice AI systems (phone agents, voice assistants, speech-to-text/text-to-speech pipelines)
- MCP (Model Context Protocol) server implementations
- Composite systems combining multiple AI capabilities

AAISAF does **not** cover:

- Traditional machine learning model security (image classifiers, recommendation systems) — see MITRE ATLAS
- AI ethics, fairness, or bias assessment — see NIST AI RMF MAP function
- AI governance programme design — see ISO/IEC 42001
- General application security without AI components — see OWASP ASVS

## Audience

| Audience | How to Use AAISAF |
|----------|-------------------|
| **AI Security Assessors** | Primary users. Follow the assessment methodology, apply techniques, use checklists. |
| **Security Engineers** | Use technique descriptions for threat modelling, secure design, and code review. |
| **CISOs / Security Leaders** | Use the maturity model and executive checklist to evaluate organisational readiness. |
| **Developers Building AI Systems** | Use remediation guidance to build secure AI applications from the start. |
| **Compliance Officers** | Use compliance mappings to demonstrate alignment with OWASP, NIST, ISO, and AU regulations. |
| **Regulators / Policy Makers** | Reference the taxonomy and threat landscape for evidence-based policy development. |

## Relationship to Existing Frameworks

AAISAF is designed to complement, not replace, existing frameworks:

```
┌─────────────────────────────────────────────────────────────────┐
│                     GOVERNANCE LAYER                            │
│  NIST AI RMF  ·  ISO/IEC 42001  ·  AU VAISS/AI6               │
├─────────────────────────────────────────────────────────────────┤
│                     THREAT INTELLIGENCE                         │
│  MITRE ATLAS  ·  OWASP LLM Top 10                              │
├─────────────────────────────────────────────────────────────────┤
│              ╔═══════════════════════════════╗                   │
│              ║  AAISAF — OPERATIONAL LAYER   ║                   │
│              ║  Technique-level assessment   ║                   │
│              ║  Checklists · Scoring · AU    ║                   │
│              ║  regulatory compliance        ║                   │
│              ╚═══════════════════════════════╝                   │
├─────────────────────────────────────────────────────────────────┤
│                     IMPLEMENTATION                              │
│  Application Security Testing  ·  Penetration Testing           │
└─────────────────────────────────────────────────────────────────┘
```

### Specific Relationships

- **OWASP LLM Top 10 (2025)**: AAISAF provides the assessment techniques that test for each OWASP vulnerability category. Every AAISAF technique maps back to the relevant OWASP item.
- **MITRE ATLAS**: AAISAF extends ATLAS coverage to AI-specific attack surfaces (MCP, voice AI) and adds assessment methodology that ATLAS does not provide.
- **NIST AI RMF**: AAISAF operationalises the MEASURE function by providing concrete measurement techniques. Maps to AI 600-1 (Generative AI Profile).
- **ISO/IEC 42001**: AAISAF supports the risk assessment requirements of Clause 6.1 with evidence-based technique identification.
- **Australian Regulatory**: AAISAF maps techniques to Privacy Act/APPs, VAISS/AI6, ASD Essential Eight, and SOCI Act obligations.

## How to Read This Framework

1. **Start with the [Methodology](01-methodology.md)** — understand assessment types, scope classification, and phases
2. **Review the [Taxonomy Overview](03-taxonomy-overview.md)** — see all 10 tactics and their technique counts
3. **Select applicable tactics** based on your AI system type (A through G)
4. **Work through techniques** in each applicable tactic, using the [checklists](../assessments/checklists/) for guidance
5. **Score findings** using the [AISS specification](../assessments/scoring/aiss-specification.md)
6. **Map to compliance** using the [compliance documents](compliance/)
7. **Assess maturity** using the [maturity model](maturity/maturity-model.md)

## Versioning

AAISAF follows [Semantic Versioning](https://semver.org/):

- **Major** (X.0.0): Taxonomy restructure, breaking changes to technique IDs
- **Minor** (1.X.0): New techniques added, compliance mappings updated
- **Patch** (1.0.X): Corrections, evidence updates, editorial changes

## License

CC BY-SA 4.0 — Share and adapt freely with attribution to Bifrost Labs.
