# TA08 — Access Control Subversion

## Overview

**Access control subversion** targets the boundaries, permissions, and enforcement mechanisms that constrain AI system behaviour. Traditional access control assumes deterministic enforcement — a firewall either blocks or allows. AI systems introduce a fundamentally different challenge: the enforcement boundary is a probabilistic model that can be persuaded, confused, or bypassed through natural language.

Every AI system has some form of access control — content filters, role restrictions, authorisation checks, human approval gates. Attacks in this tactic systematically undermine each layer. The attacker's goal is not necessarily to break the AI itself but to use the AI as a vector to bypass controls that would stop a human attacker.

**The core problem is semantic enforcement.** When access control decisions depend on an AI's interpretation of natural language, every input is a potential bypass. Paraphrasing, metaphor, academic framing, fictional contexts, and gradual escalation can all shift the AI's interpretation of what is permitted.

## Why This Matters

- **Guardrail bypasses** are discovered and shared daily — every major LLM has been bypassed repeatedly through semantic manipulation
- **Privilege escalation via AI output** creates a new class of elevation attacks where the AI becomes an unwitting accomplice
- **Cross-session data leakage** violates tenant isolation — a fundamental security guarantee in multi-user systems
- **Human-in-the-loop bypass** undermines the last line of defence in high-stakes AI deployments
- **Indirect prompt injection** can silently override authorisation decisions without the user's knowledge

## Applicable System Types

- **Type A**: Standalone LLM (TA08.001, TA08.003, TA08.004)
- **Type B**: RAG-Augmented System (TA08.001, TA08.003, TA08.005, TA08.006)
- **Type C**: Agentic System (all techniques — primary target)
- **Type D**: Multi-Agent System (all techniques — expanded attack surface)
- **Type E**: Fine-Tuned/Custom Model (TA08.001, TA08.003, TA08.004)
- **Type F**: MCP-Connected System (TA08.002, TA08.006, TA08.007)
- **Type G**: Composite System (all techniques)

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA08.001](../techniques/TA08/TA08.001-guardrail-bypass.md) | Guardrail Bypass via Semantic Manipulation | High | 6.8 |
| [TA08.002](../techniques/TA08/TA08.002-privilege-escalation.md) | Privilege Escalation via AI Output | Critical | 8.0 |
| [TA08.003](../techniques/TA08/TA08.003-content-filter-evasion.md) | Content Filter Evasion | Medium | 5.5 |
| [TA08.004](../techniques/TA08/TA08.004-system-role-manipulation.md) | System Role Manipulation | High | 7.0 |
| [TA08.005](../techniques/TA08/TA08.005-cross-session-leakage.md) | Cross-Session Data Leakage | High | 7.2 |
| [TA08.006](../techniques/TA08/TA08.006-auth-bypass-indirect.md) | Authorisation Bypass via Indirect Prompt | Critical | 8.3 |
| [TA08.007](../techniques/TA08/TA08.007-human-loop-bypass.md) | Human-in-the-Loop Bypass | High | 7.5 |

## Attack Tree

```
Access Control Subversion
├── Content Boundary Layer
│   ├── TA08.001 Guardrail Bypass (semantic manipulation)
│   └── TA08.003 Content Filter Evasion (encoding/obfuscation)
├── Identity & Role Layer
│   ├── TA08.004 System Role Manipulation (role confusion)
│   └── TA08.005 Cross-Session Data Leakage (tenant isolation)
├── Authorisation Layer
│   ├── TA08.002 Privilege Escalation via AI Output (downstream systems)
│   └── TA08.006 Authorisation Bypass via Indirect Prompt (injection)
└── Human Oversight Layer
    └── TA08.007 Human-in-the-Loop Bypass (approval circumvention)
```

## Key References

- OWASP. (2025). "OWASP Top 10 for Large Language Model Applications." v2.0.
- Perez, E. & Ribeiro, M. (2022). "Red Teaming Language Models with Language Models." Anthropic.
- Greshake, K. et al. (2023). "Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection."
- Anthropic. (2024). "Many-Shot Jailbreaking." Research publication.
- Wei, A. et al. (2023). "Jailbroken: How Does LLM Safety Training Fail?"
