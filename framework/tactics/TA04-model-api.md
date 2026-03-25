# TA04 — Model API Exploitation

## Overview

**Model APIs** are the primary interface through which applications interact with AI systems. Every major AI provider (OpenAI, Anthropic, Google, Mistral, Cohere) exposes models via REST APIs with token-based billing, rate limiting, and streaming capabilities. As AI becomes infrastructure, these APIs become high-value targets.

API exploitation in the AI context differs fundamentally from traditional API abuse. The combination of pay-per-token billing, non-deterministic outputs, and the model's ability to process and act on instructions creates attack vectors that do not exist in conventional API architectures. An attacker can weaponise the model itself as an amplifier — a single crafted request can trigger disproportionate cost, leak sensitive configuration, or bypass controls designed for deterministic systems.

**Existing frameworks underestimate API-layer risks specific to AI.** AAISAF catalogues the distinct attack techniques that emerge when APIs serve probabilistic, instruction-following systems rather than deterministic code.

## Why This Matters

- **Token flooding attacks** have caused documented five-figure billing spikes in production AI deployments
- **API key leakage via AI output** has been confirmed in production chatbots where models were given access to environment variables or configuration
- **Rate limit bypasses** undermine the primary cost-control mechanism for AI API consumption
- **Streaming response exploits** bypass output safety filters that only process complete responses
- Every organisation using AI APIs faces direct financial exposure from exploitation of these vectors

## Applicable System Types

- **Type B**: API-Accessible AI System (primary)
- **Type C**: AI-Integrated Application
- **Type G**: Composite AI System

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA04.001](../techniques/TA04/TA04.001-cost-exhaustion.md) | Cost Exhaustion via Token Flooding | High | 6.8 |
| [TA04.002](../techniques/TA04/TA04.002-rate-limit-bypass.md) | Rate Limit Bypass | Medium | 5.0 |
| [TA04.003](../techniques/TA04/TA04.003-endpoint-enumeration.md) | Model Endpoint Enumeration | Medium | 4.5 |
| [TA04.004](../techniques/TA04/TA04.004-api-key-extraction.md) | API Key Extraction via AI Output | High | 7.0 |
| [TA04.005](../techniques/TA04/TA04.005-model-fingerprinting.md) | Model Version Fingerprinting | Low | 3.5 |
| [TA04.006](../techniques/TA04/TA04.006-batch-inference-abuse.md) | Batch Inference Abuse | Medium | 5.2 |
| [TA04.007](../techniques/TA04/TA04.007-streaming-exploitation.md) | Streaming Response Exploitation | Medium | 5.0 |

## Attack Tree

```
Model API Attack Surface
├── Financial Layer
│   ├── TA04.001 Cost Exhaustion (token flooding)
│   └── TA04.006 Batch Inference Abuse (amplified cost)
├── Access Control Layer
│   ├── TA04.002 Rate Limit Bypass (throttle evasion)
│   └── TA04.004 API Key Extraction (credential leakage via model)
├── Reconnaissance Layer
│   ├── TA04.003 Endpoint Enumeration (undocumented APIs)
│   └── TA04.005 Model Fingerprinting (version disclosure)
└── Output Layer
    └── TA04.007 Streaming Exploitation (filter bypass)
```

## Key References

- OWASP. (2025). "Top 10 for LLM Applications." LLM10 (Unbounded Consumption).
- Anthropic. (2025). "API Rate Limits and Usage Policies."
- OpenAI. (2025). "API Safety Best Practices."
- MITRE ATLAS. (2024). "ML Attack Techniques — API Abuse."
