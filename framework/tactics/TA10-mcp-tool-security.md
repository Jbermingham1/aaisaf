# TA10 — MCP Server & Tool Security

## Overview

**Model Context Protocol (MCP)** is an open standard released by Anthropic in November 2024 for connecting AI systems to external tools and data sources. By 2026, MCP has become the de facto integration standard, with thousands of production servers deployed across IDE integrations, enterprise tools, and custom applications.

MCP introduces a fundamentally new attack surface. Unlike traditional APIs where the consumer is a deterministic application, MCP tools are consumed by AI models that interpret natural language descriptions to decide which tools to call and how to call them. This creates exploitation opportunities that do not exist in conventional software architectures.

**No existing security framework covers MCP-specific attack techniques.** AAISAF is the first to systematically catalogue and assess these risks.

## Why This Matters

- **CVE-2025-6514** (CVSS 9.6) demonstrated that MCP server vulnerabilities are critical and exploitable
- **Checkmarx identified 11 distinct attack surfaces** in MCP implementations (2025)
- **Invariant Labs documented active tool poisoning** in widely-used MCP servers (2025)
- **1,467 exposed MCP servers** were identified in internet-facing scans (Checkmarx, 2025)
- Every MCP server grants AI systems capabilities — a compromised server grants an attacker those same capabilities

## Applicable System Types

- **Type F**: MCP-Connected System (primary)
- **Type G**: Composite systems with MCP components

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA10.001](../techniques/TA10/TA10.001-tool-poisoning.md) | Tool Poisoning via Malicious Description | Critical | 8.1 |
| [TA10.002](../techniques/TA10/TA10.002-rug-pull.md) | Rug Pull Attack | Critical | 8.4 |
| [TA10.003](../techniques/TA10/TA10.003-tool-shadowing.md) | Tool Shadowing | Critical | 8.0 |
| [TA10.004](../techniques/TA10/TA10.004-cross-origin-injection.md) | Cross-Origin Prompt Injection via MCP Resource | Critical | 8.3 |
| [TA10.005](../techniques/TA10/TA10.005-privilege-escalation.md) | Privilege Escalation via MCP Tool Chain | Critical | 8.7 |
| [TA10.006](../techniques/TA10/TA10.006-ssrf-via-tool.md) | Server-Side Request Forgery via MCP Tool | High | 7.2 |
| [TA10.007](../techniques/TA10/TA10.007-data-exfiltration.md) | Data Exfiltration via MCP Tool Output | High | 7.5 |
| [TA10.008](../techniques/TA10/TA10.008-auth-bypass.md) | MCP Server Authentication Bypass | Critical | 9.1 |
| [TA10.009](../techniques/TA10/TA10.009-malicious-registration.md) | Malicious MCP Server Registration | Critical | 8.5 |
| [TA10.010](../techniques/TA10/TA10.010-argument-injection.md) | Tool Argument Injection | High | 7.0 |
| [TA10.011](../techniques/TA10/TA10.011-transport-exploitation.md) | MCP Transport Layer Exploitation | High | 7.3 |
| [TA10.012](../techniques/TA10/TA10.012-consent-fatigue.md) | Consent Fatigue Exploitation | Medium | 5.8 |

## Attack Tree

```
MCP Attack Surface
├── Tool Definition Layer
│   ├── TA10.001 Tool Poisoning (malicious descriptions)
│   ├── TA10.002 Rug Pull (post-approval modification)
│   └── TA10.003 Tool Shadowing (name collision)
├── Data Layer
│   ├── TA10.004 Cross-Origin Injection (via resources)
│   └── TA10.007 Data Exfiltration (via tool output)
├── Execution Layer
│   ├── TA10.005 Privilege Escalation (tool chain)
│   ├── TA10.006 SSRF (via tool parameters)
│   └── TA10.010 Argument Injection
├── Infrastructure Layer
│   ├── TA10.008 Authentication Bypass
│   ├── TA10.009 Malicious Server Registration
│   └── TA10.011 Transport Exploitation
└── Human Layer
    └── TA10.012 Consent Fatigue
```

## Key References

- Checkmarx. (2025). "MCP Security Research: 11 Attack Surfaces in Model Context Protocol."
- Invariant Labs. (2025). "MCP Security Notification: Tool Poisoning Attacks in Wide Use."
- CVE-2025-6514. MCP Server Authentication Bypass. CVSS 9.6.
- Anthropic. (2024). "Model Context Protocol Specification." https://modelcontextprotocol.io
