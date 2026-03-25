# AI Threat Landscape 2026

## Global AI Adoption

AI adoption has accelerated significantly since 2024 across all major markets. The key dynamics shaping the 2026 threat landscape:

### Market Context

- **77% of organisations** globally run GenAI in production, only **37%** have formal AI security policy (WEF 2026)
- **97% of non-human identities** have excessive privileges in AI-integrated environments (Entro Security 2025)
- **40% of enterprise applications** will integrate AI agents by end 2026 (Gartner)
- **Voice AI** deployment in contact centres accelerating globally, driven by cost reduction and 24/7 expectations
- **RAG systems** are the dominant enterprise AI pattern — deployed across legal, financial services, healthcare, and government globally
- **Agentic AI** entered production in mid-2025. Multi-agent systems are in early adoption, primarily in software development and data analysis
- **MCP (Model Context Protocol)** was released by Anthropic in November 2024. By March 2026, it had become the de facto standard for AI tool integration, with 5,800+ servers in the ecosystem

### The Gap

AI adoption has outpaced security maturity globally. Most organisations deploying AI:

- Have not conducted any AI-specific security assessment
- Rely on model provider guardrails as their sole defence
- Do not have AI-specific incident response procedures
- Have not mapped their AI systems to existing compliance obligations
- Do not monitor AI system behaviour in production

---

## Regulatory Landscape

### Global Regulatory Environment (March 2026)

AI regulation is accelerating globally, with mandatory compliance requirements emerging across jurisdictions:

| Jurisdiction | Key Regulation | Status | Impact |
|-------------|---------------|--------|--------|
| **European Union** | AI Act | Mandatory conformity assessments from August 2, 2026 | High-risk AI systems require structured assessment |
| **United States** | NIST AI RMF + AI 600-1 | Voluntary, widely adopted | De facto standard for GenAI risk management |
| **International** | ISO/IEC 42001 | Published 2023, adoption growing | AI management system certification |
| **United Kingdom** | AI Safety Institute | Operational | Frontier model evaluations |

### AU/APAC Regulatory Context

Australia does not have AI-specific legislation. The regulatory environment consists of:

| Instrument | Status | AI Relevance |
|-----------|--------|-------------|
| **Voluntary AI Safety Standard (VAISS/AI6)** | Published September 2024 | 10 voluntary guardrails. High-level principles, not assessment methodology. |
| **Privacy Act 1988 + APPs** | In force, reform ongoing | APPs 6 (use/disclosure), 11 (security), and NDB scheme apply to AI processing personal information. |
| **ASD Essential Eight** | Mandatory for federal government | Application control and patching requirements apply to AI deployment infrastructure. |
| **SOCI Act 2018** | In force | AI systems in critical infrastructure (energy, finance, healthcare, transport) must meet security obligations. |
| **Consumer and Competition Act** | In force | ACCC has indicated AI-generated outputs may be subject to misleading conduct provisions. |
| **AI Safety Institute** | Being established | Has not yet published assessment methodology or technical standards. |

### Key Regulatory Risks

1. **Privacy Act exposure**: Any AI system processing personal information (including in prompts or training data) is subject to APPs. RAG systems ingesting customer data, voice AI recording calls, and agents accessing databases all create Privacy Act obligations.

2. **SOCI Act exposure**: AI systems deployed in SOCI-designated sectors (banking, energy, healthcare, transport, telecommunications) must be covered by the entity's Critical Infrastructure Risk Management Program. This explicitly includes cyber security risks.

3. **NDB reporting**: If an AI vulnerability leads to unauthorised access to personal information, the Notifiable Data Breach scheme is triggered. Time limit: 30 days from awareness of breach.

4. **VAISS non-compliance**: While voluntary, VAISS establishes a reasonable standard of care. Organisations that suffer AI security incidents without addressing VAISS guardrails may face increased regulatory and legal scrutiny.

### International Regulatory Spillover

- **EU AI Act**: Australian businesses serving EU customers or deploying AI systems that affect EU residents must comply. High-risk AI systems require conformity assessments.
- **US Executive Orders**: AI safety requirements in US executive orders affect Australian businesses using US-based model providers.
- **ISO/IEC 42001**: Emerging as the international standard for AI management systems. Australian organisations seeking ISO certification will need to demonstrate AI risk assessment processes.

---

## Threat Actor Landscape

### Threat Actors Targeting AI Systems

| Actor Type | Motivation | Techniques | Australian Relevance |
|-----------|-----------|-----------|---------------------|
| **Cybercriminals** | Financial gain | Prompt injection for data exfiltration, voice deepfake fraud, credential harvesting | High — financial sector globally targeted |
| **Nation-State** | Espionage, disruption | Supply chain compromise, training data poisoning, persistent agent manipulation | High — first confirmed state-sponsored AI attack September 2025 (Microsoft) |
| **Hacktivists** | Ideology, disruption | Jailbreaking, guardrail bypass, public embarrassment via AI output manipulation | Medium |
| **Insiders** | Various | System prompt extraction, data exfiltration via AI, privilege escalation | High — AI systems often have broad data access |
| **Researchers/Bug Bounty** | Discovery, reputation | All techniques — constructive when coordinated, destructive when not | Medium — drives vulnerability discovery |
| **Competitors** | Commercial advantage | Model extraction, training data theft, API abuse for competitive intelligence | Medium |

### Notable AI Security Incidents (2024–2026)

| Date | Incident | Relevance |
|------|----------|-----------|
| March 2025 | **litellm supply chain compromise** — Malicious code in popular AI proxy library | Demonstrated AI-specific supply chain risk (TA05) |
| October 2025 | **MCP server vulnerabilities** — CVE-2025-6514 (CVSS 9.6), 1,467 exposed servers found by Checkmarx | First major MCP security incident (TA10) |
| 2025 | **MITRE ATLAS expands** — 14 new adversary techniques added for agentic AI | Validated agentic AI as a distinct attack surface (TA03) |
| 2024-2025 | **Voice deepfake fraud incidents** — Multiple reports of synthetic voice used in authorisation fraud | Validated voice AI exploitation (TA06) |
| 2024 | **RAG poisoning in production** — Multiple documented cases of knowledge base manipulation | Validated knowledge pipeline attacks (TA02) |
| 2024 | **Medibank penalty** — $21.5M OAIC fine set AU data breach penalty benchmark | Establishes financial risk context for AI data exposure |

---

## Regional Considerations

### Data Sovereignty (Global)

Organisations across all jurisdictions must consider where AI processing occurs:
- Many LLM APIs route data through infrastructure in different jurisdictions
- Voice AI systems may process audio recordings across borders
- RAG systems may send sensitive documents to cloud-based embedding services in other regions
- MCP servers may expose internal data to AI systems hosted externally

Cross-border data transfer regulations (GDPR Article 44-49, AU APP 8, CCPA) apply when personal information is sent to AI processing services in other jurisdictions.

### AU/APAC-Specific Considerations

### Industry-Specific Risks

| Industry | Primary AI Use Cases | Key Risks |
|----------|---------------------|-----------|
| **Financial Services** | Customer service bots, document processing, fraud detection | Data exposure, voice deepfake fraud, regulatory non-compliance |
| **Healthcare** | Clinical decision support, patient triage, documentation | Patient data leakage, incorrect clinical guidance, TGA/AHPRA liability |
| **Legal** | Document review, legal research, contract analysis | Privilege breach via RAG, hallucinated precedents, client data exposure |
| **Government** | Citizen services, policy analysis, document processing | Essential Eight compliance, SOCI obligations, data sovereignty |
| **Education** | Student support, content generation, assessment | Academic integrity, student data protection, age-appropriate AI |
| **Resources/Mining** | Operational AI, predictive maintenance, safety systems | SOCI Act obligations, safety-critical AI reliability, remote connectivity |

### Essential Eight Alignment

AI system deployments must be integrated into the organisation's Essential Eight maturity assessment:

1. **Application Control**: AI agents with code execution capability must be covered
2. **Patch Applications**: AI libraries and model dependencies require patching cycles
3. **Configure Microsoft Office Macros**: AI-generated documents may contain macro payloads
4. **User Application Hardening**: AI browser integrations must be hardened
5. **Restrict Administrative Privileges**: AI system service accounts require least-privilege
6. **Patch Operating Systems**: AI deployment infrastructure OS patching
7. **Multi-Factor Authentication**: AI system administrative interfaces require MFA
8. **Regular Backups**: AI training data, fine-tuning data, and configuration require backup

---

## Threat Forecast 2026–2027

Based on current trajectory:

1. **MCP server attacks will increase significantly** as MCP adoption grows. The October 2025 CVE was the first; more will follow. Enterprise standardisation in 2026 will expand the attack surface.
2. **Voice deepfake fraud will target global financial services** as voice AI becomes the default interaction channel for banking and customer service.
3. **AI supply chain attacks will escalate** — the litellm incident demonstrated the attack pattern; others will replicate it.
4. **Multi-agent system compromises** will emerge as organisations deploy production multi-agent workflows without adequate trust boundaries. Agentic AI market: $6.96B → $57.42B by 2031 (42% CAGR).
5. **Regulatory enforcement will begin globally** — EU AI Act conformity assessments mandatory from August 2026; national regulators will bring first AI-specific enforcement actions.
6. **AI-specific incident response gaps** will be exposed when organisations discover their existing IR plans do not cover AI system compromises.

This threat landscape provides the operational context for AAISAF assessments. Assessors should reference this document when scoping engagements and prioritising findings.
