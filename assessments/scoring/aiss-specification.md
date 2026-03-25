# AISS — AI Impact Severity Score

## Overview

The AI Impact Severity Score (AISS) is a 0.0–10.0 severity rating system that extends CVSS with five AI-specific impact metrics. AISS maintains CVSS familiarity while capturing the unique risk characteristics of AI system vulnerabilities.

## Score Ranges

| Score | Severity | Colour |
|-------|----------|--------|
| 0.0 | None | — |
| 0.1–3.9 | Low | Green |
| 4.0–6.9 | Medium | Yellow |
| 7.0–8.9 | High | Orange |
| 9.0–10.0 | Critical | Red |

---

## Calculation

AISS = (CVSS_Base × 0.4) + (AI_Impact × 0.6)

Where AI_Impact is the weighted average of five AI-specific metrics:

```
AI_Impact = (DS × 0.20) + (AI × 0.25) + (CP × 0.20) + (PE × 0.15) + (FI × 0.20)
```

### CVSS Base Score (Weight: 0.40)

Standard CVSS v3.1 or v4.0 base score. If CVSS is not directly applicable (e.g., for logic-level AI vulnerabilities), estimate using the standard CVSS attack vector, complexity, privileges, and impact dimensions.

### AI-Specific Metrics (Weight: 0.60)

#### 1. Data Sensitivity Exposure (DS) — Weight: 0.20

Measures the sensitivity of data that could be exposed through this technique.

| Score | Level | Description |
|-------|-------|-------------|
| 0–1 | None | No data exposure possible |
| 2–3 | Low | Public or non-sensitive data only |
| 4–5 | Medium | Internal business data, non-PII user data |
| 6–7 | High | PII, financial data, health records |
| 8–9 | Very High | Credentials, protected health information, classified data |
| 10 | Critical | Mass PII exfiltration, authentication material for critical systems |

**Australian context:** Score ≥7 if the data falls under Australian Privacy Principle (APP) 6 or 11 obligations. Score ≥9 if the data would trigger mandatory Notifiable Data Breach (NDB) reporting under Part IIIC of the Privacy Act 1988.

#### 2. Autonomy Impact (AI) — Weight: 0.25

Measures whether exploitation can cause the AI system to take autonomous harmful actions.

| Score | Level | Description |
|-------|-------|-------------|
| 0–1 | None | No autonomous action possible |
| 2–3 | Low | AI may generate harmful text but takes no action |
| 4–5 | Medium | AI may invoke tools with limited scope (read-only) |
| 6–7 | High | AI may invoke tools with write/modify capabilities |
| 8–9 | Very High | AI may take financial, operational, or infrastructure actions |
| 10 | Critical | AI may take irreversible actions affecting safety or human welfare |

**Scoring guidance:** This metric receives the highest weight because autonomous AI action represents a qualitatively different risk from information disclosure. An AI that can be tricked into deleting databases, sending payments, or modifying infrastructure is fundamentally more dangerous than one that can only leak information.

#### 3. Cascade Potential (CP) — Weight: 0.20

Measures whether exploitation in one AI component can propagate to other components or systems.

| Score | Level | Description |
|-------|-------|-------------|
| 0–1 | None | Isolated to single interaction |
| 2–3 | Low | May affect the current session |
| 4–5 | Medium | May affect other users of the same AI system |
| 6–7 | High | May propagate to connected AI agents |
| 8–9 | Very High | May propagate across multiple systems via agent chains |
| 10 | Critical | System-wide compromise via cascading agent trust relationships |

**Multi-agent context:** Score ≥7 for any technique that can propagate through agent delegation, shared memory, or inter-agent communication channels. The 2025-2026 emergence of multi-agent systems created cascade risks that did not exist in standalone LLM deployments.

#### 4. Persistence (PE) — Weight: 0.15

Measures how long the effects of exploitation persist.

| Score | Level | Description |
|-------|-------|-------------|
| 0–1 | Ephemeral | Single response only, no lasting effect |
| 2–3 | Session | Persists for the current conversation session |
| 4–5 | Cross-Session | Persists across sessions (e.g., memory, stored context) |
| 6–7 | Persistent | Modifies stored data, knowledge base, or configuration |
| 8–9 | Long-Term | Modifies training data, fine-tuning, or model weights |
| 10 | Permanent | Irreversible modification to production systems or data |

#### 5. Financial Impact Potential (FI) — Weight: 0.20

Measures the potential financial impact of exploitation.

| Score | Level | Description |
|-------|-------|-------------|
| 0–1 | None | No financial impact |
| 2–3 | Low | Minor operational cost increase (<$1,000 AUD) |
| 4–5 | Medium | Moderate cost ($1,000–$10,000 AUD) — API abuse, rework |
| 6–7 | High | Significant cost ($10,000–$100,000 AUD) — data breach response |
| 8–9 | Very High | Major cost ($100,000–$1M AUD) — regulatory fines, legal liability |
| 10 | Critical | Catastrophic (>$1M AUD) — SOCI Act penalties, class action, business failure |

**Australian context:** Consider OAIC enforcement action precedents. The 2024 Medibank penalty ($21.5M) set the benchmark for significant data breach penalties. SOCI Act civil penalties can reach $52,500 per contravention per day.

---

## Calculation Example

**Technique: TA10.001 — Tool Poisoning via Malicious MCP Description**

| Metric | Score | Justification |
|--------|-------|---------------|
| CVSS Base | 8.8 | Network/Low complexity/No privileges/Changed scope |
| Data Sensitivity (DS) | 8 | Can access any data the MCP server has permission to read |
| Autonomy Impact (AI) | 9 | Can cause tool invocation with full permissions |
| Cascade Potential (CP) | 7 | Can propagate to other tools in the MCP session |
| Persistence (PE) | 6 | Persists until the malicious tool description is corrected |
| Financial Impact (FI) | 7 | Data breach response costs, potential regulatory exposure |

```
AI_Impact = (8 × 0.20) + (9 × 0.25) + (7 × 0.20) + (6 × 0.15) + (7 × 0.20)
          = 1.60 + 2.25 + 1.40 + 0.90 + 1.40
          = 7.55

AISS = (8.8 × 0.4) + (7.55 × 0.6)
     = 3.52 + 4.53
     = 8.05 → High
```

---

## Aggregation

When an assessment produces multiple findings, aggregate AISS scores for reporting:

- **System-Level Score**: Highest individual AISS score across all findings (worst-case)
- **Average Score**: Mean of all finding AISS scores (indicates general posture)
- **Weighted Score**: Sum of (AISS × count per severity band) / total findings

Report all three. The System-Level Score drives the executive summary risk rating. The Average Score indicates overall maturity. The distribution across severity bands tells the remediation story.

---

## Limitations

1. AISS is designed for AI system vulnerabilities. It should not replace CVSS for traditional application vulnerabilities.
2. The AI-specific metrics involve professional judgment. Two assessors may score the same technique differently by 0.5–1.0 points. This is acceptable and expected.
3. Financial Impact scores are estimated. Actual financial impact depends on organisational context, data volumes, and regulatory exposure.
4. AISS does not account for threat actor capability or intent. It measures potential impact, not likelihood.
