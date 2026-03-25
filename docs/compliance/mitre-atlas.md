---
title: MITRE ATLAS
layout: default
parent: Compliance
nav_order: 2
---

# MITRE ATLAS Mapping

AAISAF extends ATLAS coverage to AI-specific attack surfaces (MCP, voice AI) and adds assessment methodology.

| ATLAS Technique | AAISAF Techniques |
|:---------------|:-----------------|
| AML.T0010 (ML Supply Chain Compromise) | TA05.001, TA05.004, TA05.006, TA05.007, TA07.005 |
| AML.T0020 (Poison Training Data) | TA02.001, TA03.004, TA05.003, TA07.003, TA07.006 |
| AML.T0024 (Exfiltration via ML Inference API) | TA07.001, TA07.002, TA07.004 |
| AML.T0025 (Exfiltration via Cyber Means) | TA02.009 |
| AML.T0029 (Denial of ML Service) | TA04.001 |
| AML.T0043 (Craft Adversarial Data) | TA02.004, TA06.004 |
| AML.T0044 (Full ML Model Access) | TA01.007, TA04.003–005, TA07.008 |
| AML.T0051 (LLM Prompt Injection) | TA01.001–002, TA01.005–006, TA01.010–012, TA03.002, TA08.004, TA08.006 |
| AML.T0053 (Command and Control via ML Task) | TA03.001, TA03.003, TA03.006–008 |
| AML.T0054 (LLM Jailbreak) | TA01.004, TA08.001, TA08.003 |

### Gaps in ATLAS Covered by AAISAF

AAISAF provides technique-level coverage for attack surfaces not yet in ATLAS:
- **Voice AI (TA06)** — 9 techniques with no ATLAS mapping
- **MCP Security (TA10)** — 12 techniques with no ATLAS mapping
- **RAG-specific attacks (TA02)** — 7 of 9 techniques have no direct ATLAS mapping

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/compliance/mitre-atlas-mapping.md){: .btn }
