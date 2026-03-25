---
title: AISS Scoring
layout: default
parent: Assessments
nav_order: 3
---

# AI Impact Severity Score (AISS)

AISS is a CVSS-compatible 0.0–10.0 severity scoring system enhanced with 5 AI-specific impact metrics.

## Metrics

| Metric | Range | Description |
|:-------|:------|:------------|
| **CVSS Base** | 0.0–10.0 | Standard CVSS v4.0 base score |
| **Data Sensitivity** | 0–10 | Sensitivity of data accessible via the vulnerability |
| **Autonomy Impact** | 0–10 | Can the attack cause autonomous harmful action? |
| **Cascade Potential** | 0–10 | Single agent → multi-agent → system-wide propagation |
| **Persistence** | 0–10 | Ephemeral → session → persistent → permanent |
| **Financial Impact** | 0–10 | Direct and indirect financial exposure |

## Composite Calculation

```
AISS = weighted_average(CVSS_Base × 0.4, AI_Metrics_Average × 0.6)
```

Where `AI_Metrics_Average = mean(Data_Sensitivity, Autonomy_Impact, Cascade_Potential, Persistence, Financial_Impact)`

## Severity Bands

| Score | Severity | Recommended Response Time |
|:------|:---------|:-------------------------|
| 9.0–10.0 | Critical | Immediate (within 24 hours) |
| 7.0–8.9 | High | Within 1 week |
| 4.0–6.9 | Medium | Within 1 month |
| 0.1–3.9 | Low | Within next assessment cycle |

---

[View full specification on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/assessments/scoring/aiss-specification.md){: .btn .btn-primary }
