# TA01 — Prompt Manipulation

## Overview

**Prompt manipulation** is the most prevalent and well-documented vulnerability class in AI systems. It encompasses all techniques where an attacker crafts, modifies, or injects input to cause an AI system to deviate from its intended behaviour — bypassing safety controls, extracting confidential information, or executing unintended actions.

Prompt manipulation is to AI systems what SQL injection was to web applications in the early 2000s: a fundamental architectural vulnerability that arises from the inability to cleanly separate instructions from data. Unlike traditional injection attacks, prompt manipulation exploits the natural language understanding layer itself, making it exceptionally difficult to eliminate through conventional input validation.

**AAISAF is the first framework to comprehensively catalogue prompt manipulation techniques with severity scoring, detection methods, and compliance mapping tailored to Australian regulatory requirements.**

## Why This Matters

- **OWASP ranks Prompt Injection as LLM01** — the #1 vulnerability in Large Language Model applications
- **MITRE ATLAS catalogues this as AML.T0051** — a documented adversarial technique against ML systems
- **No production LLM has demonstrated complete immunity** to prompt injection as of 2026
- **Real-world exploitation is widespread**: Bing Chat data exfiltration (2023), ChatGPT plugin manipulation (2023), automated prompt injection in email processing systems (2024)
- **Regulatory exposure is direct**: Australian Privacy Act APP 11 requires reasonable security measures; unmitigated prompt injection in systems processing personal information constitutes a failure of this obligation
- **Financial impact ranges from data breach remediation ($4.45M average, IBM 2023) to complete system compromise** depending on the AI system's access scope

## Applicable System Types

- **Type A**: Standalone LLM Application (direct user interaction)
- **Type B**: RAG-Augmented System (indirect injection via knowledge base)
- **Type C**: Autonomous Agent (highest risk — can execute actions)
- **Type D**: Multi-Agent System (cascade risk across agents)
- **Type E**: API-Integrated System (injection via API data)
- **Type F**: MCP-Connected System (injection via tool descriptions and resources)
- **Type G**: Composite System (all vectors applicable)

All system types are vulnerable to at least one prompt manipulation technique. Types C, D, F, and G face the highest risk due to action execution capabilities.

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA01.001](../techniques/TA01/TA01.001-direct-prompt-injection.md) | Direct Prompt Injection | Critical | 8.5 |
| [TA01.002](../techniques/TA01/TA01.002-indirect-prompt-injection.md) | Indirect Prompt Injection | Critical | 8.8 |
| [TA01.003](../techniques/TA01/TA01.003-system-prompt-extraction.md) | System Prompt Extraction | High | 6.5 |
| [TA01.004](../techniques/TA01/TA01.004-jailbreaking-role-play.md) | Jailbreaking via Role Play | High | 7.0 |
| [TA01.005](../techniques/TA01/TA01.005-multi-turn-manipulation.md) | Multi-Turn Prompt Manipulation | High | 7.2 |
| [TA01.006](../techniques/TA01/TA01.006-encoded-payload-injection.md) | Encoded Payload Injection | Medium | 5.8 |
| [TA01.007](../techniques/TA01/TA01.007-prompt-leaking-output-analysis.md) | Prompt Leaking via Output Analysis | Medium | 5.5 |
| [TA01.008](../techniques/TA01/TA01.008-context-window-manipulation.md) | Context Window Manipulation | Medium | 5.0 |
| [TA01.009](../techniques/TA01/TA01.009-language-based-bypass.md) | Language-Based Bypass | Medium | 5.5 |
| [TA01.010](../techniques/TA01/TA01.010-instruction-hierarchy-confusion.md) | Instruction Hierarchy Confusion | High | 7.5 |
| [TA01.011](../techniques/TA01/TA01.011-delimiter-formatting-exploitation.md) | Delimiter and Formatting Exploitation | Medium | 5.0 |
| [TA01.012](../techniques/TA01/TA01.012-multimodal-prompt-injection.md) | Prompt Injection via Multimodal Input | High | 7.3 |

## Attack Tree

```
Prompt Manipulation
├── Direct Injection
│   ├── TA01.001 Direct Prompt Injection (override system prompt)
│   ├── TA01.004 Jailbreaking via Role Play (persona-based bypass)
│   ├── TA01.005 Multi-Turn Manipulation (gradual escalation)
│   └── TA01.006 Encoded Payload Injection (encoding-based bypass)
├── Indirect Injection
│   ├── TA01.002 Indirect Prompt Injection (via external data)
│   └── TA01.012 Multimodal Prompt Injection (via images/audio/video)
├── Information Extraction
│   ├── TA01.003 System Prompt Extraction (direct extraction)
│   └── TA01.007 Prompt Leaking via Output Analysis (inference-based)
├── Boundary Exploitation
│   ├── TA01.008 Context Window Manipulation (attention dilution)
│   ├── TA01.010 Instruction Hierarchy Confusion (priority exploitation)
│   └── TA01.011 Delimiter and Formatting Exploitation (boundary confusion)
└── Filter Evasion
    ├── TA01.006 Encoded Payload Injection (encoding bypass)
    └── TA01.009 Language-Based Bypass (multilingual evasion)
```

## Key References

- OWASP. (2025). "OWASP Top 10 for Large Language Model Applications." LLM01: Prompt Injection.
- MITRE ATLAS. (2024). "AML.T0051 — LLM Prompt Injection." https://atlas.mitre.org
- Perez, F. & Ribeiro, I. (2022). "Ignore This Title and HackAPrompt: Exposing Systemic Weaknesses of LLMs through a Global Scale Prompt Hacking Competition."
- Greshake, K., Abdelnabi, S., Mishra, S., Endres, C., Holz, T., & Fritz, M. (2023). "Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection."
- Zou, A., Wang, Z., Kolter, J.Z., & Fredrikson, M. (2023). "Universal and Transferable Adversarial Attacks on Aligned Language Models."
- Liu, N.F., Lin, K., Hewitt, J., Paranjape, A., Bevilacqua, M., Petroni, F., & Liang, P. (2024). "Lost in the Middle: How Language Models Use Long Contexts."
- Microsoft. (2024). "Red Teaming of Multi-Turn LLM Attacks: Crescendo Attack Research."
