# Standard Assessment Methodology

## Overview

The AAISAF Standard Assessment is a 1–2 day comprehensive evaluation covering all applicable tactics for the target AI system. It produces a full assessment report with findings, AISS scores, compliance mapping, and prioritised remediation.

---

## Pre-Assessment

### 1. Engagement Setup

- Obtain written authorisation from the system owner
- Confirm scope boundaries (what is in and out of scope)
- Identify stakeholders and schedule interviews
- Request architecture documentation, data flow diagrams, and previous assessment reports
- Confirm testing environment (production with safeguards or staging)
- Establish escalation contacts and testing windows

### 2. Scope Classification

Classify the AI system using the [Type A–G classification](../framework/01-methodology.md#ai-system-types). Document:

- [ ] System type(s) identified
- [ ] All AI components inventoried
- [ ] Data flows documented (ingress, processing, egress)
- [ ] Trust boundaries identified
- [ ] Applicable tactics determined

### 3. Applicable Tactics Matrix

Based on system type, determine which tactics apply:

| Tactic | A | B | C | D | E | F | G |
|--------|---|---|---|---|---|---|---|
| TA01 Prompt Manipulation | X | X | X | X | X | X | X |
| TA02 Knowledge Pipeline | | X | | X | | | * |
| TA03 Agent & Orchestration | | | X | X | | X | * |
| TA04 Model API | X | X | X | X | X | X | X |
| TA05 Supply Chain | X | X | X | X | X | X | X |
| TA06 Voice AI | | | | | X | | * |
| TA07 Data & Model Integrity | X | X | X | X | X | X | X |
| TA08 Access Control | X | X | X | X | X | X | X |
| TA09 AI Application | X | X | X | X | | X | X |
| TA10 MCP & Tool Security | | | | | | X | * |

*Type G: Apply all tactics from constituent types.

---

## Assessment Execution

### Day 1: Information Gathering + TA01/TA04/TA05/TA08

**Morning (4 hours)**

1. **Stakeholder Interview** (1 hour)
   - System architecture walkthrough
   - Security controls discussion
   - Known issues and previous findings
   - Compliance requirements

2. **Architecture Review** (1 hour)
   - Verify data flow documentation
   - Identify all external integrations
   - Map AI model providers and versions
   - Identify authentication and authorisation mechanisms

3. **TA01 — Prompt Manipulation Assessment** (2 hours)
   - Test techniques TA01.001–TA01.012 as applicable
   - Document all findings with evidence
   - Score findings using AISS

**Afternoon (4 hours)**

4. **TA04 — Model API Assessment** (1 hour)
   - Test API security controls, rate limiting, authentication

5. **TA05 — Supply Chain Assessment** (1 hour)
   - Review AI dependencies (models, libraries, data sources)
   - Check for known vulnerabilities in dependencies

6. **TA08 — Access Control Assessment** (1 hour)
   - Test guardrails, content filters, privilege boundaries

7. **Preliminary Findings Review** (1 hour)
   - Organise Day 1 findings
   - Identify any blockers for Day 2
   - Adjust Day 2 plan if needed

### Day 2: Applicable Tactics + Analysis + Reporting

**Morning (4 hours)**

8. **Applicable Tactic Assessments** (3 hours)
   - TA02 (if Type B/D/G) — Knowledge pipeline assessment
   - TA03 (if Type C/D/F/G) — Agent and orchestration assessment
   - TA06 (if Type E/G) — Voice AI assessment
   - TA07 — Data and model integrity assessment
   - TA09 — AI application attack assessment
   - TA10 (if Type F/G) — MCP and tool security assessment

9. **Stakeholder Debrief** (1 hour)
   - Discuss preliminary findings
   - Clarify any questions
   - Confirm remediation priorities

**Afternoon (4 hours)**

10. **Analysis and Reporting** (4 hours)
    - Score all findings using AISS
    - Map findings to compliance requirements
    - Determine maturity level
    - Write assessment report

---

## Report Template

### Executive Summary (1 page)

- System classification and scope
- Overall AISS system-level score
- Maturity level
- Critical and High findings count
- Top 3 recommendations

### Scope and Methodology

- System type classification
- Assessment type (Standard)
- Applicable tactics and techniques
- Testing environment
- Limitations and caveats

### Findings

For each finding, ordered by AISS score (highest first):

| Field | Content |
|-------|---------|
| Finding ID | F-001 |
| Title | [Descriptive title] |
| AAISAF Technique | [TA reference] |
| AISS Score | [0.0–10.0] |
| Severity | Critical/High/Medium/Low |
| Description | [What was found] |
| Evidence | [Screenshots, logs, reproduction steps] |
| Impact | [Business impact in context] |
| Remediation | [Specific, actionable remediation] |
| Compliance | [Which standards this affects] |

### Compliance Summary

| Standard | Status | Key Gaps |
|----------|--------|----------|
| OWASP LLM Top 10 | [Partial/Aligned/Non-compliant] | [Specific gaps] |
| MITRE ATLAS | [Coverage assessment] | [Unmapped risks] |
| NIST AI RMF | [Alignment assessment] | [MEASURE 2.6 gaps] |
| ISO 42001 | [Readiness assessment] | [Control gaps] |
| AU Regulatory | [Compliance status] | [Specific exposures] |

### Maturity Assessment

- Current level with evidence
- Gap analysis for next level
- Improvement roadmap

### Remediation Plan

| Priority | Finding | AISS | Effort | Timeline |
|----------|---------|------|--------|----------|
| 1 | [Finding title] | [Score] | [Low/Med/High] | [Recommended timeline] |
| ... | | | | |

---

## Deep Assessment Extension

For Deep Assessments (5–10 days), extend the Standard Assessment with:

1. **Active adversarial testing** (2–3 days) — Full technique-level exploitation attempts
2. **Source code review** (1–2 days) — Review AI integration code, prompt construction, tool handling
3. **Supply chain audit** (1 day) — Deep dependency analysis, model provenance verification
4. **Red team exercise** (1–2 days) — Realistic attack scenarios against the production system
5. **Monitoring review** (0.5 day) — Assess production monitoring, alerting, and incident response
6. **Re-testing** (0.5–1 day) — Verify critical remediations after fixes are applied
