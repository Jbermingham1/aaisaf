# TA03 — Agent & Orchestration Abuse

## Overview

**Agentic AI** — systems that plan, reason, use tools, and take autonomous action — has exploded from research curiosity to production reality between 2025 and 2026. LangChain, CrewAI, AutoGen, OpenAI Assistants, Anthropic Claude with tool use, and dozens of enterprise orchestration frameworks now deploy agents that execute multi-step workflows with real-world consequences: writing code, managing infrastructure, processing financial transactions, and interacting with external services.

This explosion has created a fundamentally new attack surface. In October 2025, MITRE added 14 new techniques to the ATLAS framework specifically targeting agentic AI systems — the largest single update since ATLAS launched. The message was clear: agent security is not a future concern, it is a current gap.

Unlike traditional AI systems where the model produces text, agentic systems produce **actions**. A compromised agent does not just output wrong information — it takes wrong actions with real consequences. The attack surface compounds with every tool granted, every agent added to a multi-agent system, and every degree of autonomy permitted.

**AAISAF is the first framework to systematically assess agent and orchestration security as a distinct tactic with scored techniques.**

## Why This Matters

- **MITRE ATLAS added 14 agentic techniques** in October 2025, acknowledging agents as a distinct threat category
- **Ruan et al. (2024)** documented privilege escalation, goal hijacking, and cascading failures in LM agent systems
- **Production incidents** with coding agents (autonomous code execution, infrastructure modification) have caused real damage
- **Multi-agent systems** introduce trust relationships between agents that mirror — and inherit — the vulnerabilities of human trust networks
- **Every tool granted to an agent is an attack surface** — the blast radius scales linearly with capability
- **Autonomy amplifies impact** — an agent that can act without human approval converts every vulnerability into an immediate exploit

## Applicable System Types

- **Type C**: AI-Augmented Application (agents embedded in applications)
- **Type D**: Autonomous AI Agent (single-agent systems with tool use)
- **Type F**: MCP-Connected System (agents using MCP for tool integration)
- **Type G**: Composite AI System (multi-agent orchestration)

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA03.001](../techniques/TA03/TA03.001-unauthorised-tool-invocation.md) | Unauthorised Tool Invocation | Critical | 8.2 |
| [TA03.002](../techniques/TA03/TA03.002-agent-goal-hijacking.md) | Agent Goal Hijacking | Critical | 8.5 |
| [TA03.003](../techniques/TA03/TA03.003-inter-agent-trust-exploitation.md) | Inter-Agent Trust Exploitation | High | 7.5 |
| [TA03.004](../techniques/TA03/TA03.004-memory-poisoning.md) | Memory Poisoning in Persistent Agents | High | 7.3 |
| [TA03.005](../techniques/TA03/TA03.005-cascading-failure.md) | Cascading Failure via Agent Chain | High | 7.0 |
| [TA03.006](../techniques/TA03/TA03.006-privilege-escalation-delegation.md) | Privilege Escalation Through Agent Delegation | Critical | 8.8 |
| [TA03.007](../techniques/TA03/TA03.007-autonomous-action-abuse.md) | Autonomous Action Abuse | Critical | 9.0 |
| [TA03.008](../techniques/TA03/TA03.008-agent-impersonation.md) | Agent Impersonation | High | 7.2 |
| [TA03.009](../techniques/TA03/TA03.009-planning-phase-manipulation.md) | Planning Phase Manipulation | Medium | 6.0 |
| [TA03.010](../techniques/TA03/TA03.010-feedback-loop-exploitation.md) | Feedback Loop Exploitation | Medium | 5.5 |

## Attack Tree

```
Agent & Orchestration Attack Surface
├── Goal & Planning Layer
│   ├── TA03.002 Agent Goal Hijacking (redirect objectives)
│   └── TA03.009 Planning Phase Manipulation (corrupt reasoning)
├── Tool & Action Layer
│   ├── TA03.001 Unauthorised Tool Invocation (invoke forbidden tools)
│   ├── TA03.006 Privilege Escalation via Delegation (lower→higher privilege)
│   └── TA03.007 Autonomous Action Abuse (exploit autonomous capabilities)
├── Multi-Agent Layer
│   ├── TA03.003 Inter-Agent Trust Exploitation (compromise trust chains)
│   ├── TA03.005 Cascading Failure via Agent Chain (propagate through chain)
│   └── TA03.008 Agent Impersonation (impersonate trusted agents)
├── Memory & State Layer
│   └── TA03.004 Memory Poisoning (corrupt persistent memory)
└── Feedback Layer
    └── TA03.010 Feedback Loop Exploitation (manipulate learning signals)
```

## Key References

- MITRE ATLAS. (2025). "ATLAS Update: 14 New Techniques for Agentic AI Systems." October 2025.
- Ruan, Y., et al. (2024). "Identifying the Risks of LM Agents with an LM-Emulated Sandbox." arXiv:2309.15817.
- Greshake, K., et al. (2023). "Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection." arXiv:2302.12173.
- Xi, Z., et al. (2023). "The Rise and Potential of Large Language Model Based Agents: A Survey." arXiv:2309.07864.
- OWASP. (2025). "OWASP Top 10 for LLM Applications v2.0."
- Cohen, B., et al. (2024). "Here Comes The AI Worm: Unleashing Zero-click Worms that Target GenAI-Powered Applications." arXiv:2403.02817.
