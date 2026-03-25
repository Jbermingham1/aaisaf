# TA02 — Knowledge Pipeline Exploitation

## Overview

**Retrieval-Augmented Generation (RAG)** is the dominant enterprise AI architecture pattern in 2026. RAG systems augment LLM responses with information retrieved from external knowledge bases — documents, databases, APIs, and vector stores. This creates a pipeline from data ingestion through embedding, storage, retrieval, and generation that introduces attack surfaces at every stage.

Existing frameworks treat RAG vulnerabilities superficially. OWASP LLM08 (Excessive Agency) touches on RAG risks but doesn't provide technique-level assessment. AAISAF goes deep — 9 techniques covering the full RAG pipeline from document ingestion to response generation.

## Why This Matters

- RAG is deployed across financial services, legal, healthcare, and government in Australia
- Knowledge base poisoning can cause an AI system to give consistently wrong answers with apparent confidence
- Cross-tenant data leakage in multi-tenant RAG systems creates Privacy Act exposure
- Document injection attacks achieve indirect prompt injection through the retrieval pipeline
- Embedding manipulation can alter which documents are retrieved, changing AI behaviour without modifying the model

## Applicable System Types

- **Type B**: RAG-Augmented System (primary)
- **Type D**: Multi-Agent Orchestration (when agents use RAG)
- **Type G**: Composite systems with RAG components

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA02.001](../techniques/TA02/TA02.001-knowledge-base-poisoning.md) | Knowledge Base Poisoning | Critical | 8.2 |
| [TA02.002](../techniques/TA02/TA02.002-retrieval-manipulation.md) | Retrieval Manipulation via Query Injection | High | 7.1 |
| [TA02.003](../techniques/TA02/TA02.003-document-injection.md) | Document Injection with Hidden Instructions | Critical | 8.4 |
| [TA02.004](../techniques/TA02/TA02.004-embedding-manipulation.md) | Embedding Space Manipulation | High | 7.0 |
| [TA02.005](../techniques/TA02/TA02.005-context-overflow.md) | Context Window Overflow via Retrieved Content | Medium | 5.5 |
| [TA02.006](../techniques/TA02/TA02.006-metadata-exploitation.md) | Metadata Exploitation in Document Retrieval | Medium | 5.8 |
| [TA02.007](../techniques/TA02/TA02.007-cross-tenant-leakage.md) | Cross-Tenant Data Leakage via RAG | Critical | 8.8 |
| [TA02.008](../techniques/TA02/TA02.008-chunking-exploitation.md) | Chunking Strategy Exploitation | Medium | 5.3 |
| [TA02.009](../techniques/TA02/TA02.009-vector-db-bypass.md) | Vector Database Access Control Bypass | High | 7.5 |

## Attack Tree

```
RAG Pipeline Attack Surface
├── Ingestion Layer
│   ├── TA02.001 Knowledge Base Poisoning
│   ├── TA02.003 Document Injection (hidden instructions)
│   └── TA02.006 Metadata Exploitation
├── Embedding Layer
│   ├── TA02.004 Embedding Space Manipulation
│   └── TA02.008 Chunking Strategy Exploitation
├── Storage Layer
│   ├── TA02.007 Cross-Tenant Data Leakage
│   └── TA02.009 Vector Database Access Control Bypass
└── Retrieval & Generation Layer
    ├── TA02.002 Retrieval Manipulation (query injection)
    └── TA02.005 Context Window Overflow
```

## Key References

- Greshake, K., et al. (2023). "Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection."
- Zeng, Y., et al. (2024). "Good News Is Not Enough: Towards RAG Robustness Against Adversarial Noise."
- Chaudhari, H., et al. (2024). "Phantom: General Trigger Attacks on Retrieval Augmented Language Generation."
- OWASP. (2025). LLM08 — Excessive Agency (partial RAG coverage).
