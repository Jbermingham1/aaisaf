# TA05 — AI Supply Chain Compromise

## Overview

**AI supply chains** are uniquely complex and uniquely vulnerable. A modern AI application depends on pre-trained models (downloaded from public hubs), embedding models, fine-tuning datasets, prompt template libraries, AI-specific Python packages, model serialisation formats, and AI gateway/proxy infrastructure. Each dependency is a potential insertion point for malicious code, backdoors, or data manipulation.

Unlike traditional software supply chain attacks that inject code, AI supply chain attacks can also inject *behaviour*. A trojaned model looks identical to its legitimate counterpart — same architecture, same benchmark performance — but contains hidden triggers that activate under specific conditions. A poisoned embedding model returns normal results for 99.9% of queries but manipulates retrieval for attacker-chosen topics. These attacks are fundamentally harder to detect than conventional supply chain compromises.

**The March 2025 litellm supply chain attack** demonstrated that AI-specific infrastructure is actively targeted. AAISAF is the first framework to systematically map the AI-specific supply chain attack surface.

## Why This Matters

- **CVE-2024-5480** (litellm SSRF) and the **March 2025 litellm supply chain compromise** proved that AI-specific packages are actively targeted
- **HuggingFace hosts 500,000+ models** — the hub introduced malware scanning after discovering trojaned uploads
- **Pickle deserialization attacks** are the #1 model loading vulnerability; SafeTensors was created specifically to address this
- **Sleeper agent research** (Anthropic, 2024) demonstrated that backdoors can survive safety fine-tuning
- A single compromised dependency in the AI stack can affect every downstream application with no visible indicator

## Applicable System Types

- **Type A**: Standalone AI Model (primary for model-level attacks)
- **Type C**: AI-Integrated Application
- **Type D**: AI Development Pipeline
- **Type G**: Composite AI System

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA05.001](../techniques/TA05/TA05.001-malicious-model-upload.md) | Malicious Model Upload | Critical | 9.0 |
| [TA05.002](../techniques/TA05/TA05.002-dependency-confusion.md) | Dependency Confusion in AI Libraries | Critical | 8.5 |
| [TA05.003](../techniques/TA05/TA05.003-compromised-finetuning.md) | Compromised Fine-Tuning Data | High | 7.5 |
| [TA05.004](../techniques/TA05/TA05.004-model-serialisation.md) | Model Serialisation Exploits | Critical | 8.8 |
| [TA05.005](../techniques/TA05/TA05.005-prompt-template-supply-chain.md) | Prompt Template Supply Chain | High | 6.5 |
| [TA05.006](../techniques/TA05/TA05.006-embedding-compromise.md) | Embedding Model Compromise | High | 7.0 |
| [TA05.007](../techniques/TA05/TA05.007-ai-gateway-compromise.md) | AI Gateway/Proxy Compromise | Critical | 9.0 |

## Attack Tree

```
AI Supply Chain Attack Surface
├── Model Layer
│   ├── TA05.001 Malicious Model Upload (trojaned models on hubs)
│   ├── TA05.003 Compromised Fine-Tuning Data (backdoor insertion)
│   ├── TA05.004 Model Serialisation Exploits (unsafe deserialization)
│   └── TA05.006 Embedding Model Compromise (retrieval manipulation)
├── Package Layer
│   ├── TA05.002 Dependency Confusion (typosquatting AI libraries)
│   └── TA05.005 Prompt Template Supply Chain (malicious templates)
└── Infrastructure Layer
    └── TA05.007 AI Gateway/Proxy Compromise (litellm, API routers)
```

## Key References

- Anthropic. (2024). "Sleeper Agents: Training Deceptive LLMs That Persist Through Safety Training."
- HuggingFace. (2025). "Model Security Scanning and SafeTensors."
- CVE-2024-5480. litellm Server-Side Request Forgery. CVSS 9.8.
- Checkmarx. (2025). "Supply Chain Attacks Targeting AI/ML Infrastructure."
- OWASP. (2025). "Top 10 for LLM Applications." LLM05 (Supply Chain Vulnerabilities).
