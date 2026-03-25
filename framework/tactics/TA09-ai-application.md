# TA09 — AI-Enhanced Application Attacks

## Overview

**AI-enhanced application attacks** exploit the intersection of AI systems and traditional web/application security. When an AI system generates code, queries, commands, or markup that is executed by downstream systems, every classic application vulnerability becomes reachable through the AI layer. The AI becomes an unwitting attack proxy — translating natural language into exploitable payloads.

This tactic is distinct from traditional application security because the attack path runs through the AI. An attacker does not need direct access to the vulnerable application — they need only to manipulate the AI's output. This makes input validation fundamentally harder: the "input" is a natural language conversation, and the "output" is executable code.

**The severity is amplified by trust assumptions.** Many applications implicitly trust AI-generated output because it originates from an internal system rather than an external user. This bypasses existing input validation, WAF rules, and sanitisation layers that would catch identical payloads from a human attacker.

## Why This Matters

- **CVE-2024-3402** demonstrated XSS via AI-generated HTML in a production application
- **AI-generated SQL** is deployed in thousands of natural-language-to-SQL applications with insufficient parameterisation
- **Code generation tools** (Copilot, Cursor, Claude Code) produce shell commands that users execute with elevated privileges
- **CVE-2023-50164** (Apache Struts path traversal) demonstrated the class of vulnerabilities that AI file operations can trigger
- **Every OWASP Top 10 vulnerability** can be triggered through AI output if the output is consumed by a downstream application without sanitisation

## Applicable System Types

- **Type B**: RAG-Augmented System (TA09.001, TA09.002 — query generation)
- **Type C**: Agentic System (all techniques — primary target)
- **Type D**: Multi-Agent System (all techniques — expanded blast radius)
- **Type F**: MCP-Connected System (TA09.003, TA09.004, TA09.005)
- **Type G**: Composite System (all techniques)

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA09.001](../techniques/TA09/TA09.001-xss-via-ai.md) | Cross-Site Scripting via AI Output | High | 7.0 |
| [TA09.002](../techniques/TA09/TA09.002-sql-injection-ai.md) | SQL Injection via AI-Generated Queries | Critical | 8.5 |
| [TA09.003](../techniques/TA09/TA09.003-ssrf-via-tool.md) | Server-Side Request Forgery via AI Tool Use | High | 7.2 |
| [TA09.004](../techniques/TA09/TA09.004-command-injection.md) | Command Injection via AI Code Generation | Critical | 8.8 |
| [TA09.005](../techniques/TA09/TA09.005-path-traversal.md) | Path Traversal via AI File Operations | High | 7.0 |
| [TA09.006](../techniques/TA09/TA09.006-insecure-deserialisation.md) | Insecure Deserialisation via AI Output | High | 6.5 |

## Attack Tree

```
AI-Enhanced Application Attacks
├── Output Rendering
│   └── TA09.001 XSS via AI Output (HTML/JS generation)
├── Data Layer
│   ├── TA09.002 SQL Injection via AI Queries (NL-to-SQL)
│   └── TA09.006 Insecure Deserialisation (serialised output)
├── System Access
│   ├── TA09.003 SSRF via AI Tool Use (internal network)
│   ├── TA09.004 Command Injection via Code Generation (OS access)
│   └── TA09.005 Path Traversal via File Operations (filesystem)
```

## Key References

- OWASP. (2025). "OWASP Top 10 for Large Language Model Applications." v2.0. LLM07 (Insecure Plugin Design).
- CVE-2024-3402. Cross-Site Scripting via AI-generated output.
- CVE-2023-50164. Apache Struts Path Traversal.
- MITRE ATLAS. "AML.T0048 — Command and Control via AI."
- Greshake, K. et al. (2023). "Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection."
