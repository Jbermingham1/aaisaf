# MITRE ATLAS Compliance Mapping

## Overview

This document maps MITRE ATLAS adversary techniques to AAISAF assessment techniques. ATLAS provides the threat intelligence; AAISAF provides the assessment methodology.

**Source**: [MITRE ATLAS](https://atlas.mitre.org) — including October 2025 agentic AI additions.

---

## ATLAS Technique Mapping

| ATLAS ID | ATLAS Technique | AAISAF Techniques | Assessment Coverage |
|----------|----------------|-------------------|-------------------|
| AML.T0010 | ML Supply Chain Compromise | TA05.001, TA05.002, TA05.004, TA05.006, TA05.007, TA07.005, TA10.009 | Comprehensive — models, libraries, serialisation, gateways, MCP servers |
| AML.T0020 | Poison Training Data | TA02.001, TA07.003, TA07.006, TA03.004 | Comprehensive — training data, fine-tuning, knowledge base, agent memory |
| AML.T0024 | Exfiltration via ML Inference API | TA07.001, TA07.007, TA10.007 | Full — training data extraction, PII leakage, MCP exfiltration |
| AML.T0024.001 | Membership Inference | TA07.002 | Direct mapping |
| AML.T0024.002 | Model Inversion | TA07.004 | Direct mapping |
| AML.T0025 | Exfiltrate ML Model | TA07.008, TA02.009 | Full — model weights, vector database access |
| AML.T0029 | Denial of ML Service | TA04.001, TA04.002 | Full — cost exhaustion, rate limit bypass |
| AML.T0043 | Craft Adversarial Data | TA02.004, TA06.004 | Full — embedding manipulation, audio adversarial |
| AML.T0044 | Full ML Model Access | TA04.003, TA04.004, TA04.005, TA07.008 | Full — endpoint enumeration, fingerprinting, key extraction, weight exfiltration |
| AML.T0051 | LLM Prompt Injection | TA01.001–TA01.012 | Comprehensive — 12 technique variants |
| AML.T0051.000 | Direct | TA01.001 | Direct mapping |
| AML.T0051.001 | Indirect | TA01.002, TA02.003, TA10.004 | Extended — document injection, MCP resource injection |
| AML.T0051.002 | System Prompt Extraction | TA01.003 | Direct mapping |
| AML.T0053 | Abuse of Access | TA03.001, TA03.006, TA03.007, TA03.008, TA10.005 | Comprehensive — tool invocation, delegation, autonomous action, MCP chains |
| AML.T0054 | LLM Jailbreak | TA01.004, TA08.001, TA08.003 | Full — role play, semantic manipulation, filter evasion |

---

## AAISAF Techniques Without ATLAS Mapping

The following AAISAF techniques address attack surfaces not yet covered by MITRE ATLAS:

| AAISAF Technique | Gap Description |
|-----------------|-----------------|
| **TA02.002** Retrieval Manipulation | RAG-specific query injection — ATLAS doesn't cover RAG pipelines |
| **TA02.005** Context Window Overflow | RAG-specific context manipulation |
| **TA02.006** Metadata Exploitation | Document metadata manipulation |
| **TA02.007** Cross-Tenant Leakage | Multi-tenant RAG isolation |
| **TA02.008** Chunking Exploitation | RAG chunking strategy attacks |
| **TA06.001–TA06.009** Voice AI (all) | Voice AI attack surface — not yet in ATLAS |
| **TA10.001–TA10.012** MCP (all except TA10.004) | MCP server attack surface — not yet in ATLAS |
| **TA03.004** Memory Poisoning | Persistent agent memory attacks |
| **TA03.005** Cascading Failure | Multi-agent cascade attacks |
| **TA03.009** Planning Phase Manipulation | Agent reasoning manipulation |
| **TA03.010** Feedback Loop Exploitation | Reward/feedback manipulation |

**31 AAISAF techniques** cover attack surfaces not yet addressed by MITRE ATLAS, representing AAISAF's novel contribution to AI threat intelligence.

---

## Recommendations for ATLAS Contributors

Based on the gaps identified above, AAISAF recommends MITRE ATLAS consider adding techniques for:
1. RAG pipeline attacks (retrieval manipulation, cross-tenant leakage, chunking exploitation)
2. MCP server and tool attacks (tool poisoning, rug pull, tool shadowing, transport exploitation)
3. Voice AI attacks (voice prompt injection, deepfake spoofing, vishing)
4. Agent memory and planning attacks (memory poisoning, planning manipulation)
