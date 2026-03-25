# Quick Self-Assessment (30 Minutes)

## Purpose

Rapid baseline evaluation of your AI system's security posture. Identifies obvious gaps and provides a starting maturity level. Designed for SMBs, initial risk triage, and awareness exercises.

## Instructions

1. Identify your AI system type (A–G) from the table below
2. Complete Section 1 (all systems)
3. Complete applicable sections based on your system type
4. Calculate your score
5. Determine your maturity level

---

## AI System Type

| Type | Description | Additional Sections |
|------|-------------|-------------------|
| A | LLM chatbot/assistant | Section 1 only |
| B | RAG-augmented system | Sections 1, 2 |
| C | Agentic AI with tool use | Sections 1, 3 |
| D | Multi-agent orchestration | Sections 1, 2, 3 |
| E | Voice AI system | Sections 1, 4 |
| F | MCP-connected system | Sections 1, 3, 5 |
| G | Composite | All applicable |

---

## Section 1 — Core AI Security (All Systems)

| # | Check | Y/N | Risk if No |
|---|-------|-----|-----------|
| 1.1 | Do you have an inventory of all AI systems deployed? | | You cannot secure what you don't know about |
| 1.2 | Is there input validation on user prompts (length limits, character filtering)? | | Open to prompt injection (TA01) |
| 1.3 | Is there output filtering (PII detection, content safety)? | | Sensitive data may leak in responses (TA07.007) |
| 1.4 | Are AI system API keys stored securely (not in code, environment variables, or client-side)? | | API key theft enables abuse (TA04.004) |
| 1.5 | Do you monitor AI system usage and costs? | | Cost exhaustion attacks go undetected (TA04.001) |
| 1.6 | Are AI model provider terms of service and data handling reviewed? | | Data may be processed in ways that violate Privacy Act |
| 1.7 | Is there an incident response plan that covers AI-specific scenarios? | | No prepared response to AI security incidents |
| 1.8 | Has anyone on the security team received AI security training? | | AI-specific threats are not understood |
| 1.9 | Are AI dependencies (libraries, models) tracked and patched? | | Supply chain vulnerabilities (TA05) |
| 1.10 | Is the AI system's behaviour logged for audit purposes? | | Cannot investigate incidents or detect anomalies |

## Section 2 — RAG / Knowledge Pipeline (Types B, D, G)

| # | Check | Y/N | Risk if No |
|---|-------|-----|-----------|
| 2.1 | Is access to the knowledge base restricted (who can add/modify documents)? | | Knowledge base poisoning (TA02.001) |
| 2.2 | Are documents sanitised before ingestion (stripping hidden content, metadata)? | | Document injection attacks (TA02.003) |
| 2.3 | Is there tenant isolation in the vector database (if multi-tenant)? | | Cross-tenant data leakage (TA02.007) |
| 2.4 | Does the AI show source documents in its responses? | | Users cannot verify accuracy |
| 2.5 | Is the vector database authenticated (not accessible without credentials)? | | Vector database bypass (TA02.009) |

## Section 3 — Agent & Tool Use (Types C, D, F, G)

| # | Check | Y/N | Risk if No |
|---|-------|-----|-----------|
| 3.1 | Are tool invocations restricted to an allowlist? | | Unauthorised tool invocation (TA03.001) |
| 3.2 | Do destructive or high-impact actions require human approval? | | Autonomous action abuse (TA03.007) |
| 3.3 | Is there a limit on what actions the AI can take autonomously? | | Unbounded autonomy risk |
| 3.4 | Are tool permissions scoped to least privilege? | | Privilege escalation (TA03.006, TA10.005) |
| 3.5 | Are agent-to-agent communications validated (if multi-agent)? | | Inter-agent trust exploitation (TA03.003) |

## Section 4 — Voice AI (Types E, G)

| # | Check | Y/N | Risk if No |
|---|-------|-----|-----------|
| 4.1 | Are callers informed they are speaking with an AI? | | VAISS Guardrail 2, EU AI Act Article 50 |
| 4.2 | Is there authentication before the voice AI shares sensitive information? | | Credential harvesting (TA06.005) |
| 4.3 | Are voice recordings stored securely with access controls? | | Privacy Act APP 11 exposure |
| 4.4 | Is there a mechanism to detect synthetic/deepfake voices? | | Voice spoofing (TA06.002) |
| 4.5 | Can the voice AI transfer to a human on request? | | VAISS Guardrail 4 (Human control) |

## Section 5 — MCP & Tool Integration (Types F, G)

| # | Check | Y/N | Risk if No |
|---|-------|-----|-----------|
| 5.1 | Is there an allowlist of approved MCP servers? | | Malicious server registration (TA10.009) |
| 5.2 | Are MCP tool descriptions reviewed before installation? | | Tool poisoning (TA10.001) |
| 5.3 | Are MCP servers bound to localhost or authenticated? | | Authentication bypass (TA10.008) |
| 5.4 | Do MCP tools have network access restrictions? | | SSRF via MCP tools (TA10.006) |
| 5.5 | Are tool descriptions locked after approval (version pinned)? | | Rug pull attacks (TA10.002) |

---

## Scoring

Count "Yes" responses in all applicable sections.

| Score | Maturity Level | Recommended Action |
|-------|---------------|-------------------|
| 0–3 | Level 1 (Initial) | Immediate action needed — address all "No" items |
| 4–8 | Level 2 (Developing) | Developing — prioritise Critical risk items |
| 9–15 | Level 3 (Defined) | Good baseline — consider Standard Assessment |
| 16–20 | Level 3+ | Strong — Standard Assessment for full validation |
| 21–25 | Level 4 potential | Excellent — Deep Assessment for certification readiness |

---

## Next Steps

1. Address all "No" items rated as Critical risk first
2. Schedule a Standard Assessment within 90 days
3. Document your AI systems and security controls
4. Share results with your security team and leadership
