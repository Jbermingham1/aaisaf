# TA07 — Training Data & Model Integrity

## Overview

**Training data and model integrity** represent the foundation of any AI system's trustworthiness. Every model inherits the biases, secrets, and vulnerabilities of its training data. Attacks against this layer target the model itself — either extracting what it learned, poisoning what it will learn, or stealing the model wholesale.

These attacks are particularly dangerous because they can be invisible at inference time. A poisoned model may perform normally on standard benchmarks while containing backdoors, leaking PII, or producing subtly manipulated outputs when specific triggers are present. Unlike prompt-level attacks, data and model integrity attacks can persist across all sessions, all users, and all deployments of the affected model.

**The research base is mature.** Carlini et al. (2024) demonstrated verbatim training data extraction from production LLMs. Shokri et al. established membership inference as a practical privacy attack. BadNets and sleeper agent research proved that backdoors survive fine-tuning. These are not theoretical — they are demonstrated capabilities.

## Why This Matters

- **Carlini et al. (2024)** extracted verbatim training data from ChatGPT, including PII, code, and copyrighted text
- **Membership inference attacks** can determine whether specific individuals' data was used in training — a direct privacy violation under GDPR and Australia's Privacy Act
- **Data poisoning via public sources** (Wikipedia, Reddit, Common Crawl) has been demonstrated at scale with minimal resources
- **Model weight exfiltration** represents theft of potentially billions of dollars in training investment
- **Backdoor attacks** can create models that pass all safety evaluations while containing hidden malicious behaviours

## Applicable System Types

- **Type A**: Standalone LLM (all techniques)
- **Type B**: RAG-Augmented System (TA07.001, TA07.002, TA07.007)
- **Type C**: Agentic System (all techniques)
- **Type D**: Multi-Agent System (all techniques)
- **Type E**: Fine-Tuned/Custom Model (TA07.003, TA07.005, TA07.006 — primary targets)
- **Type F**: MCP-Connected System (TA07.007, TA07.008)
- **Type G**: Composite System (all techniques)

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA07.001](../techniques/TA07/TA07.001-training-data-extraction.md) | Training Data Extraction | High | 7.0 |
| [TA07.002](../techniques/TA07/TA07.002-membership-inference.md) | Membership Inference Attack | Medium | 5.5 |
| [TA07.003](../techniques/TA07/TA07.003-data-poisoning-public.md) | Data Poisoning via Public Sources | High | 7.2 |
| [TA07.004](../techniques/TA07/TA07.004-model-inversion.md) | Model Inversion Attack | High | 6.8 |
| [TA07.005](../techniques/TA07/TA07.005-backdoor-trigger.md) | Backdoor Trigger Activation | Critical | 8.5 |
| [TA07.006](../techniques/TA07/TA07.006-fine-tuning-poisoning.md) | Fine-Tuning Data Poisoning | High | 7.5 |
| [TA07.007](../techniques/TA07/TA07.007-pii-leakage.md) | PII Leakage via Model Output | High | 7.3 |
| [TA07.008](../techniques/TA07/TA07.008-model-weight-exfiltration.md) | Model Weight Exfiltration | High | 7.0 |

## Attack Tree

```
Training Data & Model Integrity
├── Data Extraction
│   ├── TA07.001 Training Data Extraction (verbatim memorisation)
│   ├── TA07.002 Membership Inference (presence detection)
│   ├── TA07.004 Model Inversion (feature reconstruction)
│   └── TA07.007 PII Leakage (targeted personal data)
├── Data Poisoning
│   ├── TA07.003 Public Source Poisoning (pre-training)
│   ├── TA07.005 Backdoor Trigger Activation (planted triggers)
│   └── TA07.006 Fine-Tuning Poisoning (RLHF/SFT stage)
└── Model Theft
    └── TA07.008 Model Weight Exfiltration (API/side-channel/access)
```

## Key References

- Carlini, N. et al. (2024). "Extracting Training Data from ChatGPT." arXiv:2311.17035.
- Shokri, R. et al. (2017). "Membership Inference Attacks Against Machine Learning Models." IEEE S&P.
- Gu, T. et al. (2019). "BadNets: Evaluating Backdooring Attacks on Deep Neural Networks."
- Fredrikson, M. et al. (2015). "Model Inversion Attacks that Exploit Confidence Information." CCS.
- Hubinger, E. et al. (2024). "Sleeper Agents: Training Deceptive LLMs That Persist Through Safety Training." Anthropic.
- MITRE ATLAS. "AML.T0044 — Full ML Model Access." https://atlas.mitre.org
