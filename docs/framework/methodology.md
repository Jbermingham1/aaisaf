---
title: Methodology
layout: default
parent: Framework
nav_order: 2
---

# Assessment Methodology

## Assessment Types

| Type | Duration | Best For | Output |
|:-----|:---------|:---------|:-------|
| **Quick Self-Assessment** | 30 min | SMBs, initial baseline, awareness | Risk summary + priority actions |
| **Standard Assessment** | 1–2 days | All organisations, compliance prep | Full findings report + AISS scores |
| **Deep Assessment** | 5–10 days | Critical systems, regulatory requirement | Technique-level testing report + remediation plan |

## AI System Scope Classification

Before assessment, classify the target system:

| Type | Description | Example | Applicable Tactics |
|:-----|:------------|:--------|:-------------------|
| **A** | LLM chatbot/assistant | Customer support bot | TA01, TA04, TA05, TA07, TA08, TA09 |
| **B** | RAG-augmented system | Internal knowledge base Q&A | TA01, TA02, TA04, TA05, TA07, TA08, TA09 |
| **C** | Agentic AI with tool use | Coding assistant, data analyst | TA01, TA03, TA04, TA05, TA07, TA08, TA09 |
| **D** | Multi-agent orchestration | Autonomous workflow systems | All |
| **E** | Voice AI system | AI phone agent, voice assistant | TA01, TA04, TA05, TA06, TA07, TA08 |
| **F** | MCP-connected system | IDE integration, tool-use via MCP | TA01, TA04, TA05, TA08, TA09, TA10 |
| **G** | Composite | Multiple types combined | All |

## Assessment Phases

### Phase 1: Scoping & Classification
- Identify AI system boundaries and components
- Classify system type (A–G)
- Determine applicable tactics and techniques
- Select assessment type (Quick / Standard / Deep)

### Phase 2: Technique-Level Testing
- Work through applicable techniques from the taxonomy
- Use domain checklists for structured coverage
- Document findings with evidence

### Phase 3: Scoring & Risk Assessment
- Score each finding using [AISS](/aaisaf/assessments/aiss)
- Categorise by severity: Critical / High / Medium / Low
- Prioritise remediation based on risk and exploitability

### Phase 4: Compliance Mapping
- Map findings to applicable compliance frameworks
- Identify gaps against regulatory requirements
- Document compliance status per standard

### Phase 5: Maturity Assessment
- Evaluate organisation against the [5-level maturity model](/aaisaf/framework/maturity)
- Identify progression targets
- Recommend capability improvements

### Phase 6: Reporting
- Executive summary with key risks
- Detailed findings with AISS scores
- Remediation priorities with effort estimates
- Compliance gap analysis
- Maturity assessment results

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/01-methodology.md){: .btn }
