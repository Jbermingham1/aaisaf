# AAISAF Maturity Model

## Overview

The AAISAF Maturity Model provides a 5-level framework for assessing an organisation's AI security posture. It measures not just what controls exist, but whether they are practised, measured, and continuously improved.

## Maturity Levels

### Level 1 — Initial

**Description:** No formal AI security practices. AI systems are deployed without security assessment. Security is reactive, addressed only after incidents.

**Characteristics:**
- No AI-specific security policies or procedures
- AI systems deployed without security review
- No awareness of AI-specific threats (prompt injection, RAG poisoning, etc.)
- Reliance on model provider guardrails as sole defence
- No AI-specific incident response procedures
- No inventory of deployed AI systems

**Assessment Criteria:**
- [ ] Organisation has no AI security policy
- [ ] No AI systems have been assessed for security
- [ ] No AI-specific training for security team
- [ ] No monitoring of AI system behaviour

### Level 2 — Developing

**Description:** Basic AI security defences are in place. Some input validation, output filtering, and awareness of AI risks. Ad hoc rather than systematic.

**Characteristics:**
- Basic input validation on AI inputs (length limits, character filtering)
- Some output filtering (toxicity, PII detection)
- Informal awareness of prompt injection risks
- AI security considered in some deployment decisions
- Some AI systems documented, but no complete inventory
- Incident response partially covers AI, but no specific AI procedures

**Assessment Criteria:**
- [ ] Basic input validation implemented on at least one AI system
- [ ] Output filtering for PII or sensitive content on at least one system
- [ ] At least one person in the security team has AI security awareness
- [ ] Some documentation of AI systems exists
- [ ] At least one AI system has had any form of security review

### Level 3 — Defined

**Description:** Documented AI security policies, regular assessment against AAISAF, and integration with existing security programmes.

**Characteristics:**
- Written AI security policy covering deployment, assessment, and incident response
- Regular AAISAF assessments (at least annually) for all production AI systems
- Complete inventory of all AI systems with classification (Type A–G)
- AI-specific threat modelling conducted during development
- Security team trained on AI-specific threats and assessment techniques
- AI security integrated into SDLC (secure development lifecycle)
- Compliance mapping maintained (OWASP, NIST, ISO, AU regulatory)

**Assessment Criteria:**
- [ ] Written AI security policy exists and is reviewed annually
- [ ] All production AI systems are inventoried and classified
- [ ] AAISAF Standard Assessment completed for all production AI systems in the last 12 months
- [ ] Security team has completed AI security training
- [ ] AI threat modelling is part of the development process
- [ ] Compliance mappings are documented and maintained
- [ ] AI-specific incident response procedures exist and have been tested

### Level 4 — Managed

**Description:** Continuous monitoring, automated security testing, metrics-driven improvement. AI security is quantified and tracked.

**Characteristics:**
- Continuous monitoring of AI system behaviour in production
- Automated AI security testing integrated into CI/CD pipelines
- Metrics tracked: AISS scores, time to remediate, assessment coverage
- Regular reporting to leadership on AI security posture
- Vendor risk assessments for AI model providers and tool integrations
- Supply chain security for all AI dependencies
- Automated detection of prompt injection, anomalous outputs, and data leakage
- Regular (quarterly) re-assessment against AAISAF

**Assessment Criteria:**
- [ ] Continuous monitoring implemented for all production AI systems
- [ ] Automated AI security tests run in CI/CD for all AI-related code changes
- [ ] AI security metrics reported to leadership at least quarterly
- [ ] AI supply chain audit conducted at least annually
- [ ] Vendor risk assessment completed for all AI model providers
- [ ] Mean time to remediate AI security findings is tracked and improving
- [ ] Automated prompt injection detection deployed in production

### Level 5 — Optimised

**Description:** Proactive AI security posture. Red team exercises, threat intelligence integration, community contribution, and continuous innovation.

**Characteristics:**
- Regular AI red team exercises (at least bi-annually)
- AI threat intelligence programme — tracking new attack techniques, CVEs, research
- Proactive contribution to AI security community (reporting vulnerabilities, sharing research, contributing to frameworks)
- AI security innovation — developing novel detection and defence techniques
- Cross-functional AI security programme (security, data science, legal, compliance)
- Board-level AI risk reporting
- External assessment or certification (ISO 42001, third-party audit)

**Assessment Criteria:**
- [ ] AI red team exercise conducted in the last 6 months
- [ ] AI threat intelligence feeds monitored and actioned
- [ ] Organisation contributes to AI security community (publications, bug reports, framework contributions)
- [ ] Board-level reporting on AI security risk exists
- [ ] External AI security assessment or ISO 42001 certification obtained or in progress
- [ ] Novel AI security defences developed and deployed
- [ ] Cross-functional AI security governance board established

---

## Maturity Assessment Process

### Step 1: Baseline

Complete the maturity checklist above. The highest level where all criteria are met is the current maturity level.

### Step 2: Gap Analysis

For the next target level, identify which criteria are not met. These become the improvement roadmap.

### Step 3: Improvement Plan

For each unmet criterion, define:
- **Action**: What needs to be done
- **Owner**: Who is responsible
- **Timeline**: When it will be completed
- **Evidence**: How completion will be demonstrated

### Step 4: Reassessment

Reassess maturity after implementing improvements. Recommended cadence:
- Initial baseline: Immediately
- First reassessment: 6 months after baseline
- Ongoing: Annually, or after significant AI system changes

---

## Maturity Level by Organisation Type

| Organisation Type | Minimum Recommended Level |
|-------------------|--------------------------|
| SMB with basic AI chatbot | Level 2 |
| Enterprise with production RAG/agent | Level 3 |
| Financial services / healthcare / government | Level 4 |
| Critical infrastructure (SOCI Act entities) | Level 4 |
| AI platform provider | Level 5 |

---

## Mapping to Compliance Requirements

| Level | VAISS/AI6 | Privacy Act | Essential Eight | ISO 42001 | SOCI Act |
|-------|-----------|-------------|-----------------|-----------|----------|
| 1 | Non-compliant | Risk of breach | Not aligned | Not applicable | Non-compliant |
| 2 | Partial alignment | Basic compliance | Maturity Level 1 | Not applicable | Partial |
| 3 | Aligned | Compliant with documentation | Maturity Level 2 | Certifiable | Compliant |
| 4 | Fully aligned | Proactively compliant | Maturity Level 3 | Certified | Fully compliant |
| 5 | Leader | Exemplary | Maturity Level 3+ | Certified + continuous improvement | Leader |
