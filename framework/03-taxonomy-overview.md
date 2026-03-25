# Taxonomy Overview

## Structure

AAISAF uses a three-level taxonomy modelled on MITRE ATT&CK:

```
Tactic (TA01–TA10)
  └── Technique (TA01.001–TA01.012)
        └── Sub-technique (TA01.001.a — where applicable)
```

- **Tactic**: A category of adversary objective (e.g., "Prompt Manipulation")
- **Technique**: A specific method to achieve that objective (e.g., "Direct Prompt Injection")
- **Sub-technique**: A variant of a technique (used sparingly for closely related methods)

---

## Full Taxonomy

### TA01 — Prompt Manipulation

Techniques for manipulating LLM behaviour through crafted input.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA01.001 | Direct Prompt Injection | Critical | LLM01 | AML.T0051.000 | A,B,C,D,E,F,G |
| TA01.002 | Indirect Prompt Injection | Critical | LLM01 | AML.T0051.001 | B,C,D,F,G |
| TA01.003 | System Prompt Extraction | High | LLM01 | AML.T0051.002 | A,B,C,D,E,F,G |
| TA01.004 | Jailbreaking via Role Play | High | LLM01 | AML.T0054 | A,B,C,D,E,G |
| TA01.005 | Multi-Turn Prompt Manipulation | High | LLM01 | AML.T0051 | A,B,C,D,E,G |
| TA01.006 | Encoded Payload Injection | Medium | LLM01 | AML.T0051 | A,B,C,D,F,G |
| TA01.007 | Prompt Leaking via Output Analysis | Medium | LLM01 | AML.T0044 | A,B,C,D,E,F,G |
| TA01.008 | Context Window Manipulation | Medium | LLM01 | — | B,C,D,F,G |
| TA01.009 | Language-Based Bypass | Medium | LLM01 | — | A,B,C,D,E,G |
| TA01.010 | Instruction Hierarchy Confusion | High | LLM01 | AML.T0051 | C,D,F,G |
| TA01.011 | Delimiter and Formatting Exploitation | Medium | LLM01 | AML.T0051 | A,B,C,D,F,G |
| TA01.012 | Prompt Injection via Multimodal Input | High | LLM01 | AML.T0051 | A,B,C,D,G |

### TA02 — Knowledge Pipeline Exploitation

Techniques targeting RAG pipelines, knowledge bases, and retrieval systems.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA02.001 | Knowledge Base Poisoning | Critical | LLM08 | AML.T0020 | B,D,G |
| TA02.002 | Retrieval Manipulation via Query Injection | High | LLM01,LLM08 | — | B,D,G |
| TA02.003 | Document Injection with Hidden Instructions | Critical | LLM01,LLM08 | AML.T0051.001 | B,D,G |
| TA02.004 | Embedding Space Manipulation | High | LLM08 | AML.T0043 | B,D,G |
| TA02.005 | Context Window Overflow via Retrieved Content | Medium | LLM08 | — | B,D,G |
| TA02.006 | Metadata Exploitation in Document Retrieval | Medium | LLM08 | — | B,D,G |
| TA02.007 | Cross-Tenant Data Leakage via RAG | Critical | LLM06,LLM08 | — | B,D,G |
| TA02.008 | Chunking Strategy Exploitation | Medium | LLM08 | — | B,D,G |
| TA02.009 | Vector Database Access Control Bypass | High | LLM08 | AML.T0025 | B,D,G |

### TA03 — Agent & Orchestration Abuse

Techniques exploiting AI agents with tool use and multi-agent systems.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA03.001 | Unauthorised Tool Invocation | Critical | LLM07 | AML.T0053 | C,D,F,G |
| TA03.002 | Agent Goal Hijacking | Critical | LLM01,LLM07 | AML.T0051 | C,D,G |
| TA03.003 | Inter-Agent Trust Exploitation | High | LLM07 | AML.T0053 | D,G |
| TA03.004 | Memory Poisoning in Persistent Agents | High | LLM07 | AML.T0020 | C,D,G |
| TA03.005 | Cascading Failure via Agent Chain | High | LLM07 | — | D,G |
| TA03.006 | Privilege Escalation Through Agent Delegation | Critical | LLM07 | AML.T0053 | D,G |
| TA03.007 | Autonomous Action Abuse | Critical | LLM07 | AML.T0053 | C,D,G |
| TA03.008 | Agent Impersonation | High | LLM07 | AML.T0053 | D,G |
| TA03.009 | Planning Phase Manipulation | Medium | LLM01,LLM07 | — | C,D,G |
| TA03.010 | Feedback Loop Exploitation | Medium | LLM07 | — | C,D,G |

### TA04 — Model API Exploitation

Techniques targeting LLM APIs, model endpoints, and inference infrastructure.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA04.001 | Cost Exhaustion via Token Flooding | High | LLM04 | AML.T0029 | A,B,C,D,E,F,G |
| TA04.002 | Rate Limit Bypass | Medium | LLM04 | — | A,B,C,D,E,F,G |
| TA04.003 | Model Endpoint Enumeration | Medium | LLM04 | AML.T0044 | A,B,C,D,E,F,G |
| TA04.004 | API Key Extraction via AI Output | High | LLM04,LLM06 | AML.T0044 | C,D,F,G |
| TA04.005 | Model Version Fingerprinting | Low | LLM04 | AML.T0044 | A,B,C,D,E,F,G |
| TA04.006 | Batch Inference Abuse | Medium | LLM04 | — | A,B,C,D,G |
| TA04.007 | Streaming Response Exploitation | Medium | LLM04 | — | A,B,C,D,E,G |

### TA05 — AI Supply Chain Compromise

Techniques targeting AI-specific dependencies, models, and data pipelines.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA05.001 | Malicious Model Upload | Critical | LLM03 | AML.T0010 | A,B,C,D,E,F,G |
| TA05.002 | Dependency Confusion in AI Libraries | Critical | LLM03 | AML.T0010 | A,B,C,D,E,F,G |
| TA05.003 | Compromised Fine-Tuning Data | High | LLM03 | AML.T0020 | A,B,C,D,E,G |
| TA05.004 | Model Serialisation Exploits | Critical | LLM03 | AML.T0010 | A,B,C,D,E,G |
| TA05.005 | Prompt Template Supply Chain | High | LLM03 | — | A,B,C,D,E,F,G |
| TA05.006 | Embedding Model Compromise | High | LLM03 | AML.T0010 | B,D,G |
| TA05.007 | AI Gateway/Proxy Compromise | Critical | LLM03 | AML.T0010 | A,B,C,D,E,F,G |

### TA06 — Voice AI Exploitation

**Novel — No existing framework covers this tactic.**

Techniques targeting voice AI systems, speech processing pipelines, and telephony AI.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA06.001 | Voice Prompt Injection via Speech | High | LLM01 | — | E,G |
| TA06.002 | Synthetic Voice Spoofing (Deepfake) | Critical | — | — | E,G |
| TA06.003 | Conversation Flow Bypass | Medium | — | — | E,G |
| TA06.004 | Audio Adversarial Examples | High | — | AML.T0043 | E,G |
| TA06.005 | Credential Harvesting via Voice Agent | Critical | LLM06 | — | E,G |
| TA06.006 | DTMF and Telephony Signal Injection | High | — | — | E,G |
| TA06.007 | Voice Agent Vishing (AI-Assisted Social Engineering) | Critical | — | — | E,G |
| TA06.008 | Speech-to-Text Pipeline Exploitation | Medium | — | — | E,G |
| TA06.009 | Real-Time Voice Cloning in Active Call | Critical | — | — | E,G |

### TA07 — Training Data & Model Integrity

Techniques targeting training data, model weights, and inference integrity.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA07.001 | Training Data Extraction | High | LLM06 | AML.T0024 | A,B,C,D,E,G |
| TA07.002 | Membership Inference Attack | Medium | LLM06 | AML.T0024.001 | A,B,C,D,E,G |
| TA07.003 | Data Poisoning via Public Sources | High | LLM03 | AML.T0020 | A,B,C,D,E,G |
| TA07.004 | Model Inversion Attack | High | LLM06 | AML.T0024.002 | A,B,C,D,E,G |
| TA07.005 | Backdoor Trigger Activation | Critical | LLM03 | AML.T0010 | A,B,C,D,E,G |
| TA07.006 | Fine-Tuning Data Poisoning | High | LLM03 | AML.T0020 | A,B,C,D,E,G |
| TA07.007 | PII Leakage via Model Output | High | LLM06 | AML.T0024 | A,B,C,D,E,F,G |
| TA07.008 | Model Weight Exfiltration | High | LLM10 | AML.T0044 | A,B,C,D,E,G |

### TA08 — Access Control Subversion

Techniques for bypassing AI-specific access controls, guardrails, and policies.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA08.001 | Guardrail Bypass via Semantic Manipulation | High | LLM07 | AML.T0054 | A,B,C,D,E,F,G |
| TA08.002 | Privilege Escalation via AI Output | Critical | LLM07 | AML.T0053 | C,D,F,G |
| TA08.003 | Content Filter Evasion | Medium | LLM07 | AML.T0054 | A,B,C,D,E,G |
| TA08.004 | System Role Manipulation | High | LLM01 | AML.T0051 | A,B,C,D,E,F,G |
| TA08.005 | Cross-Session Data Leakage | High | LLM06 | — | A,B,C,D,E,G |
| TA08.006 | Authorisation Bypass via Indirect Prompt | Critical | LLM01,LLM07 | AML.T0051 | B,C,D,F,G |
| TA08.007 | Human-in-the-Loop Bypass | High | LLM07 | — | C,D,G |

### TA09 — AI-Enhanced Application Attacks

Techniques using AI outputs as vectors for traditional application vulnerabilities.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA09.001 | Cross-Site Scripting via AI Output | High | LLM02 | — | A,B,C,D,G |
| TA09.002 | SQL Injection via AI-Generated Queries | Critical | LLM02 | — | B,C,D,G |
| TA09.003 | Server-Side Request Forgery via AI Tool Use | High | LLM02 | — | C,D,F,G |
| TA09.004 | Command Injection via AI Code Generation | Critical | LLM02 | — | C,D,F,G |
| TA09.005 | Path Traversal via AI File Operations | High | LLM02 | — | C,D,F,G |
| TA09.006 | Insecure Deserialisation via AI Output | High | LLM02 | — | C,D,G |

### TA10 — MCP Server & Tool Security

**Novel — No existing framework covers this tactic.**

Techniques targeting Model Context Protocol servers, tool definitions, and the MCP communication layer.

| ID | Technique | Severity | OWASP | MITRE ATLAS | System Types |
|----|-----------|----------|-------|-------------|-------------|
| TA10.001 | Tool Poisoning via Malicious Description | Critical | LLM07 | — | F,G |
| TA10.002 | Rug Pull Attack (Post-Approval Tool Modification) | Critical | LLM07 | — | F,G |
| TA10.003 | Tool Shadowing | Critical | LLM07 | — | F,G |
| TA10.004 | Cross-Origin Prompt Injection via MCP Resource | Critical | LLM01,LLM07 | — | F,G |
| TA10.005 | Privilege Escalation via MCP Tool Chain | Critical | LLM07 | — | F,G |
| TA10.006 | Server-Side Request Forgery via MCP Tool | High | LLM02,LLM07 | — | F,G |
| TA10.007 | Data Exfiltration via MCP Tool Output | High | LLM06,LLM07 | — | F,G |
| TA10.008 | MCP Server Authentication Bypass | Critical | LLM07 | — | F,G |
| TA10.009 | Malicious MCP Server Registration | Critical | LLM03,LLM07 | — | F,G |
| TA10.010 | Tool Argument Injection | High | LLM01,LLM07 | — | F,G |
| TA10.011 | MCP Transport Layer Exploitation | High | LLM07 | — | F,G |
| TA10.012 | Consent Fatigue Exploitation | Medium | LLM07 | — | F,G |

---

## Taxonomy Summary

| Tactic | Techniques | Critical | High | Medium | Low |
|--------|-----------|----------|------|--------|-----|
| TA01 Prompt Manipulation | 12 | 2 | 4 | 5 | 1 |
| TA02 Knowledge Pipeline | 9 | 3 | 3 | 3 | 0 |
| TA03 Agent & Orchestration | 10 | 3 | 4 | 2 | 1 |
| TA04 Model API | 7 | 0 | 2 | 3 | 2 |
| TA05 Supply Chain | 7 | 3 | 3 | 1 | 0 |
| TA06 Voice AI (**Novel**) | 9 | 3 | 3 | 2 | 1 |
| TA07 Data & Model Integrity | 8 | 1 | 5 | 1 | 1 |
| TA08 Access Control | 7 | 2 | 3 | 1 | 1 |
| TA09 AI Application | 6 | 2 | 3 | 1 | 0 |
| TA10 MCP & Tool Security (**Novel**) | 12 | 6 | 4 | 1 | 1 |
| **Total** | **87** | **25** | **34** | **20** | **8** |
