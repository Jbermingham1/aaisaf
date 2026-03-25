# Checklist 09 — Executive / CISO Assessment

**Applicable:** All organisations deploying AI systems. Non-technical.

## Purpose

This checklist is designed for CISOs, security leaders, and executives who need to assess their organisation's AI security posture without technical testing. It covers governance, policy, compliance, and risk management.

---

## Governance & Policy

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.1 | Does the organisation have a written AI security policy? | | Critical |
| 9.2 | Is there a complete inventory of all AI systems deployed? | | Critical |
| 9.3 | Is there an AI system owner identified for each deployment? | | High |
| 9.4 | Has the board or executive team been briefed on AI security risks? | | High |
| 9.5 | Is AI security included in the organisation's risk register? | | High |
| 9.6 | Is there budget allocated for AI security assessment and tooling? | | Medium |

## Compliance

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.7 | Has a Privacy Impact Assessment been completed for AI systems processing personal information? | | Critical |
| 9.8 | Are AI systems included in the organisation's Notifiable Data Breach response plan? | | Critical |
| 9.9 | For SOCI entities: are AI systems included in the Critical Infrastructure Risk Management Program? | | Critical |
| 9.10 | Has the organisation assessed VAISS/AI6 alignment? | | High |
| 9.11 | For EU exposure: has EU AI Act applicability been assessed? | | High |
| 9.12 | Are AI vendor contracts reviewed for data handling, security, and liability? | | High |

## People & Training

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.13 | Has the security team received AI-specific security training? | | High |
| 9.14 | Do developers building AI features receive secure AI development training? | | High |
| 9.15 | Is there a designated AI security lead or champion? | | Medium |
| 9.16 | Are employees trained on responsible AI use (prompt hygiene, data handling)? | | Medium |

## Technical Controls

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.17 | Is there input validation on AI systems (prompt filtering)? | | Critical |
| 9.18 | Is there output filtering (PII detection, content safety)? | | Critical |
| 9.19 | Are AI API keys and credentials managed securely? | | Critical |
| 9.20 | Is there monitoring and alerting on AI system behaviour? | | High |
| 9.21 | Are AI system dependencies tracked and patched? | | High |
| 9.22 | Is the AI supply chain documented (models, libraries, data sources, tools)? | | High |

## Incident Response

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.23 | Does the incident response plan include AI-specific scenarios? | | Critical |
| 9.24 | Has the AI incident response plan been tested (tabletop exercise)? | | High |
| 9.25 | Is there a process for emergency AI system shutdown? | | High |
| 9.26 | Is there a communication plan for AI security incidents? | | Medium |

## Assessment & Improvement

| # | Question | Y/N | Priority |
|---|----------|-----|----------|
| 9.27 | Has an AI security assessment (AAISAF or equivalent) been conducted? | | High |
| 9.28 | Is there a scheduled cadence for AI security reassessment? | | Medium |
| 9.29 | Are AI security findings tracked and remediated with timelines? | | High |
| 9.30 | Is AI security improvement progress reported to leadership? | | Medium |

---

## Scoring

| Critical "No" Count | Maturity Implication |
|---------------------|---------------------|
| 0 | Level 3+ baseline |
| 1–3 | Level 2 — developing, with critical gaps |
| 4–7 | Level 1 — initial, significant risk |
| 8+ | Level 0 — unmanaged AI risk |

**Recommendation**: Any Critical "No" should be remediated within 30 days. Schedule a Standard Assessment within 90 days regardless of score.
