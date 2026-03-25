# OWASP LLM Top 10 (2025) Compliance Mapping

## Overview

This document maps every OWASP LLM Top 10 (2025) vulnerability category to the AAISAF techniques that assess for it. Use this mapping to demonstrate assessment coverage of OWASP requirements.

**Source**: [OWASP Top 10 for LLM Applications](https://genai.owasp.org) — 2025 edition.

---

## LLM01 — Prompt Injection

**OWASP Description**: Manipulation of LLMs through crafted inputs, causing unintended actions or responses.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA01.001 | Direct Prompt Injection |
| TA01.002 | Indirect Prompt Injection |
| TA01.003 | System Prompt Extraction |
| TA01.004 | Jailbreaking via Role Play |
| TA01.005 | Multi-Turn Prompt Manipulation |
| TA01.006 | Encoded Payload Injection |
| TA01.007 | Prompt Leaking via Output Analysis |
| TA01.008 | Context Window Manipulation |
| TA01.009 | Language-Based Bypass |
| TA01.010 | Instruction Hierarchy Confusion |
| TA01.011 | Delimiter and Formatting Exploitation |
| TA01.012 | Prompt Injection via Multimodal Input |
| TA02.002 | Retrieval Manipulation via Query Injection |
| TA02.003 | Document Injection with Hidden Instructions |
| TA06.001 | Voice Prompt Injection via Speech |
| TA10.004 | Cross-Origin Prompt Injection via MCP Resource |
| TA10.010 | Tool Argument Injection |

**AAISAF Assessment**: 17 techniques across 4 tactics provide comprehensive prompt injection assessment.

---

## LLM02 — Insecure Output Handling

**OWASP Description**: Insufficient validation, sanitisation, and handling of LLM outputs.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA09.001 | Cross-Site Scripting via AI Output |
| TA09.002 | SQL Injection via AI-Generated Queries |
| TA09.003 | Server-Side Request Forgery via AI Tool Use |
| TA09.004 | Command Injection via AI Code Generation |
| TA09.005 | Path Traversal via AI File Operations |
| TA09.006 | Insecure Deserialisation via AI Output |
| TA10.006 | Server-Side Request Forgery via MCP Tool |

**AAISAF Assessment**: 7 techniques cover the full range of output-based vulnerabilities.

---

## LLM03 — Supply Chain Vulnerabilities

**OWASP Description**: Risks from third-party components, models, and data in the AI supply chain.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA05.001 | Malicious Model Upload |
| TA05.002 | Dependency Confusion in AI Libraries |
| TA05.003 | Compromised Fine-Tuning Data |
| TA05.004 | Model Serialisation Exploits |
| TA05.005 | Prompt Template Supply Chain |
| TA05.006 | Embedding Model Compromise |
| TA05.007 | AI Gateway/Proxy Compromise |
| TA07.003 | Data Poisoning via Public Sources |
| TA07.005 | Backdoor Trigger Activation |
| TA07.006 | Fine-Tuning Data Poisoning |
| TA10.009 | Malicious MCP Server Registration |

**AAISAF Assessment**: 11 techniques cover models, libraries, data, and integration supply chain risks.

---

## LLM04 — Denial of Service

**OWASP Description**: Attacks that degrade LLM performance or availability through resource exhaustion.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA04.001 | Cost Exhaustion via Token Flooding |
| TA04.002 | Rate Limit Bypass |
| TA04.003 | Model Endpoint Enumeration |
| TA04.005 | Model Version Fingerprinting |
| TA04.006 | Batch Inference Abuse |
| TA04.007 | Streaming Response Exploitation |

**AAISAF Assessment**: 6 techniques cover API-level denial of service and abuse.

---

## LLM06 — Sensitive Information Disclosure

**OWASP Description**: Exposure of sensitive data through LLM responses.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA07.001 | Training Data Extraction |
| TA07.002 | Membership Inference Attack |
| TA07.004 | Model Inversion Attack |
| TA07.007 | PII Leakage via Model Output |
| TA04.004 | API Key Extraction via AI Output |
| TA02.007 | Cross-Tenant Data Leakage via RAG |
| TA08.005 | Cross-Session Data Leakage |
| TA10.007 | Data Exfiltration via MCP Tool Output |
| TA06.005 | Credential Harvesting via Voice Agent |

**AAISAF Assessment**: 9 techniques cover data extraction from models, sessions, tenants, and tools.

---

## LLM07 — Insecure Plugin/Tool Design

**OWASP Description**: Vulnerabilities in tools, plugins, and extensions used by LLMs.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA03.001 | Unauthorised Tool Invocation |
| TA03.002 | Agent Goal Hijacking |
| TA03.003 | Inter-Agent Trust Exploitation |
| TA03.006 | Privilege Escalation Through Agent Delegation |
| TA03.007 | Autonomous Action Abuse |
| TA08.001 | Guardrail Bypass via Semantic Manipulation |
| TA08.002 | Privilege Escalation via AI Output |
| TA08.006 | Authorisation Bypass via Indirect Prompt |
| TA08.007 | Human-in-the-Loop Bypass |
| TA10.001 | Tool Poisoning via Malicious Description |
| TA10.002 | Rug Pull Attack |
| TA10.003 | Tool Shadowing |
| TA10.005 | Privilege Escalation via MCP Tool Chain |
| TA10.008 | MCP Server Authentication Bypass |
| TA10.009 | Malicious MCP Server Registration |
| TA10.010 | Tool Argument Injection |
| TA10.011 | MCP Transport Layer Exploitation |
| TA10.012 | Consent Fatigue Exploitation |

**AAISAF Assessment**: 18 techniques — the most comprehensively assessed OWASP category, reflecting the critical importance of tool/plugin security.

---

## LLM08 — Excessive Agency

**OWASP Description**: Granting LLMs excessive functionality, permissions, or autonomy.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA02.001 | Knowledge Base Poisoning |
| TA02.002 | Retrieval Manipulation via Query Injection |
| TA02.003 | Document Injection with Hidden Instructions |
| TA02.004 | Embedding Space Manipulation |
| TA02.005 | Context Window Overflow |
| TA02.006 | Metadata Exploitation |
| TA02.008 | Chunking Strategy Exploitation |
| TA02.009 | Vector Database Access Control Bypass |
| TA03.004 | Memory Poisoning in Persistent Agents |
| TA03.005 | Cascading Failure via Agent Chain |
| TA03.008 | Agent Impersonation |
| TA03.009 | Planning Phase Manipulation |
| TA03.010 | Feedback Loop Exploitation |

**AAISAF Assessment**: 13 techniques cover RAG pipeline and agent orchestration risks.

---

## LLM10 — Model Theft

**OWASP Description**: Unauthorised access, copying, or exfiltration of proprietary LLMs.

| AAISAF Technique | Coverage |
|-----------------|----------|
| TA07.008 | Model Weight Exfiltration |

**AAISAF Assessment**: 1 technique covers model theft directly. Model theft is primarily a traditional security concern (access control, network security) rather than an AI-specific vulnerability.

---

## Coverage Summary

| OWASP LLM Item | AAISAF Techniques | Coverage Level |
|----------------|-------------------|---------------|
| LLM01 Prompt Injection | 17 | Comprehensive |
| LLM02 Insecure Output | 7 | Comprehensive |
| LLM03 Supply Chain | 11 | Comprehensive |
| LLM04 Denial of Service | 6 | Full |
| LLM06 Sensitive Info | 9 | Comprehensive |
| LLM07 Insecure Plugin | 18 | Comprehensive |
| LLM08 Excessive Agency | 13 | Comprehensive |
| LLM10 Model Theft | 1 | Basic |

> Note: OWASP LLM05 (Improper Output Handling), LLM09 (Overreliance) are addressed through output validation techniques in TA09 and knowledge pipeline integrity in TA02 respectively.
