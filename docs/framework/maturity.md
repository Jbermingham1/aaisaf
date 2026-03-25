---
title: Maturity Model
layout: default
parent: Framework
nav_order: 5
---

# AI Security Maturity Model

## 5-Level Progression

| Level | Name | Description |
|:------|:-----|:------------|
| **1** | Initial | No formal AI security practices. Ad hoc responses to incidents. |
| **2** | Developing | Basic defences in place. Some input validation. Awareness of AI-specific risks. |
| **3** | Defined | Documented AI security policies. Regular testing against AAISAF. Compliance mapping started. |
| **4** | Managed | Continuous monitoring. Automated testing in CI/CD. Metrics-driven security decisions. |
| **5** | Optimised | Red team exercises. Proactive threat intelligence. Community contribution. Continuous improvement. |

## Level Details

### Level 1 — Initial
- No AI-specific security policies or procedures
- Security testing limited to traditional application security
- No awareness of AI-specific attack vectors (prompt injection, data poisoning, etc.)
- Incident response does not account for AI-specific failure modes

### Level 2 — Developing
- Basic input validation on LLM interfaces
- Some awareness training on AI security risks
- Ad hoc security reviews of AI deployments
- System prompts include basic safety instructions
- No automated testing or monitoring

### Level 3 — Defined
- Documented AI security policy covering all deployed systems
- Regular assessments using AAISAF methodology
- Compliance mappings maintained for relevant standards
- AI system inventory with classification (Types A–G)
- Incident response procedures include AI-specific scenarios
- Security requirements included in AI procurement

### Level 4 — Managed
- Automated AI security testing integrated into CI/CD pipelines
- Continuous monitoring of AI system behaviour and outputs
- Metrics tracked: vulnerability density, AISS scores, remediation velocity
- Regular threat modelling updates for AI systems
- Supply chain security scanning for AI dependencies
- Formal red team exercises at least annually

### Level 5 — Optimised
- Proactive threat intelligence on emerging AI attack techniques
- Contribution to community frameworks (AAISAF, OWASP, MITRE ATLAS)
- Advanced red team exercises with novel attack research
- AI security embedded in organisational culture
- Continuous improvement driven by metrics and lessons learned
- External validation through third-party assessments

## Assessment

Use the [Executive/CISO Checklist](https://github.com/Jbermingham1/aaisaf/blob/main/assessments/checklists/09-executive-ciso.md) to determine your organisation's current maturity level.

---

[View source on GitHub](https://github.com/Jbermingham1/aaisaf/blob/main/framework/maturity/maturity-model.md){: .btn }
