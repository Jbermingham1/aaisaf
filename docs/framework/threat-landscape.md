---
title: Threat Landscape
layout: default
parent: Framework
nav_order: 3
---

# AI Threat Landscape 2026

## Key Statistics

- **77% of organisations** run GenAI in production, only **37%** have formal AI security policy (WEF 2026)
- **97% of non-human identities** have excessive privileges (Entro Security 2025)
- **40% of enterprise applications** will integrate AI agents by end 2026 (Gartner)
- First **state-sponsored AI attack** confirmed September 2025 (Microsoft)
- AI red teaming demand surging **35% by 2028** with "almost no supply" (Mindgard)

## Emerging Attack Surfaces

### MCP Servers
- 5,800+ MCP servers in the ecosystem, enterprise standardization in 2026
- CVE-2025-6514 (CVSS 9.6) — MCP server authentication bypass
- 1,467 exposed MCP servers identified
- 11 distinct attack surfaces documented (Checkmarx 2025)

### Voice AI
- Market growing from $2.4B to $47.5B by 2034
- AI-powered vishing attacks up 442% H2 2024 vs H1 (CrowdStrike)
- Deepfake voice attacks targeting financial institutions and verification systems

### Agentic AI
- Agentic AI market: $6.96B → $57.42B by 2031 (42% CAGR)
- Multi-agent systems in production with minimal security testing
- MITRE ATLAS added 14 new agent-specific techniques October 2025

### Supply Chain
- litellm supply chain compromise (March 2025) — CVE-2024-5480, CVSS 9.8
- AI-specific dependency confusion attacks on the rise
- Model serialisation exploits via pickle/joblib/safetensors

## Regulatory Landscape

| Jurisdiction | Key Regulation | Status |
|:-------------|:--------------|:-------|
| **EU** | AI Act — mandatory conformity assessments | August 2, 2026 enforcement |
| **US** | NIST AI RMF + AI 600-1 (GenAI Profile) | Voluntary, widely adopted |
| **Australia** | VAISS/AI6 (Voluntary AI Safety Standard) | Non-binding, under review |
| **International** | ISO/IEC 42001 (AI Management System) | Published 2023, adoption growing |

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/02-threat-landscape.md){: .btn }
