# Assessment Methodology

## Assessment Types

AAISAF defines three assessment types, scaled by depth, duration, and organisational maturity.

### Quick Self-Assessment (30 minutes)

**Purpose:** Rapid baseline evaluation. Identifies obvious gaps and provides a starting maturity score.

**Best for:** SMBs deploying their first AI system, awareness exercises, initial risk triage.

**Method:**
1. Classify the AI system (Type A–G)
2. Complete the [Executive/CISO Checklist](../assessments/checklists/09-executive-ciso.md)
3. Complete applicable domain checklists at the "Quick" depth (marked items only)
4. Calculate a preliminary maturity level
5. Document top 5 findings and recommended next steps

**Output:** 1–2 page summary with maturity level, top risks, and remediation priorities.

### Standard Assessment (1–2 days)

**Purpose:** Comprehensive assessment covering all applicable tactics. Sufficient for most organisations.

**Best for:** Organisations preparing for compliance, deploying AI into production, or conducting annual security reviews.

**Method:**
1. Scope the engagement using the classification guide below
2. Conduct stakeholder interviews (system owner, developers, security team)
3. Review architecture documentation and data flow diagrams
4. Execute all applicable techniques at Standard depth
5. Score all findings using AISS
6. Map findings to compliance requirements
7. Determine maturity level with evidence
8. Produce assessment report

**Output:** Full assessment report with executive summary, findings by tactic, AISS scores, compliance gaps, maturity assessment, and prioritised remediation plan.

### Deep Assessment (5–10 days)

**Purpose:** Full technique-level active testing including adversarial simulation. For critical systems or regulatory requirements.

**Best for:** Critical infrastructure AI, financial services AI, healthcare AI, systems processing sensitive personal information, or systems with autonomous action capabilities.

**Method:**
1. All Standard Assessment activities, plus:
2. Active adversarial testing against each applicable technique
3. Source code review of AI integration points
4. Supply chain audit of all AI dependencies
5. Red team exercises simulating realistic attack scenarios
6. Continuous monitoring configuration review
7. Incident response procedure validation

**Output:** Comprehensive report with full technique results, attack narratives, exploitation evidence, strategic remediation roadmap, and maturity improvement plan.

---

## Scope Classification

Every AI system is classified into one or more types. Classification determines which tactics and techniques are applicable.

### AI System Types

| Type | Name | Description | Applicable Tactics |
|------|------|-------------|-------------------|
| **A** | LLM Chatbot/Assistant | Conversational AI with no external data retrieval or tool use | TA01, TA04, TA05, TA07, TA08, TA09 |
| **B** | RAG-Augmented System | LLM with retrieval-augmented generation from external knowledge bases | TA01, TA02, TA04, TA05, TA07, TA08, TA09 |
| **C** | Agentic AI | LLM with tool use, code execution, or autonomous action capabilities | TA01, TA02, TA03, TA04, TA05, TA07, TA08, TA09 |
| **D** | Multi-Agent Orchestration | Multiple AI agents collaborating, delegating, or competing | TA01, TA02, TA03, TA04, TA05, TA07, TA08, TA09 |
| **E** | Voice AI System | Speech-to-text, text-to-speech, or voice-based AI interaction | TA01, TA04, TA05, TA06, TA07, TA08, TA09 |
| **F** | MCP-Connected System | AI system using Model Context Protocol for tool and data access | TA01, TA03, TA04, TA05, TA08, TA09, TA10 |
| **G** | Composite | Combination of two or more types above | All applicable from constituent types |

### Scope Determination Procedure

1. **Identify all AI components** in the system under assessment
2. **Classify each component** into Type A–F
3. **If multiple types apply**, classify as Type G and union all applicable tactics
4. **Document the boundary** — what is in scope and what is explicitly out of scope
5. **Identify data flows** — what data enters the AI system, what exits, where is it stored
6. **Identify trust boundaries** — where does user input meet AI processing, where does AI output meet downstream systems

---

## Assessment Phases

Every AAISAF assessment follows five phases regardless of assessment type.

### Phase 1: Scoping & Classification

**Activities:**
- Identify all AI system components
- Classify system type (A–G)
- Determine applicable tactics and techniques
- Define assessment boundary
- Identify stakeholders and schedule interviews
- Gather architecture documentation

**Deliverable:** Scope document with system classification, applicable techniques, and assessment schedule.

### Phase 2: Information Gathering

**Activities:**
- Review architecture diagrams and data flow documentation
- Conduct stakeholder interviews
- Review existing security controls and policies
- Identify AI model providers, versions, and configurations
- Map the AI supply chain (models, libraries, data sources, APIs)
- Review previous assessment findings (if any)

**Deliverable:** Information gathering report with system context, identified attack surface, and preliminary risk areas.

### Phase 3: Assessment Execution

**Activities:**
- Execute applicable techniques from selected tactics
- For Quick Assessment: checklist-based evaluation only
- For Standard Assessment: structured testing against each technique
- For Deep Assessment: active adversarial testing and exploitation attempts
- Document all findings with evidence (screenshots, logs, reproduction steps)
- Score each finding using AISS

**Deliverable:** Raw findings with evidence and AISS scores.

### Phase 4: Analysis & Reporting

**Activities:**
- Analyse findings for systemic patterns and root causes
- Map findings to compliance requirements (OWASP, MITRE, NIST, ISO, AU regulatory)
- Determine maturity level based on evidence
- Prioritise remediation actions by risk (AISS score × business impact)
- Draft assessment report

**Deliverable:** Assessment report with executive summary, detailed findings, compliance mapping, maturity assessment, and remediation plan.

### Phase 5: Remediation Support

**Activities:**
- Present findings to stakeholders
- Clarify remediation guidance for development team
- Provide re-testing support after remediation (Deep Assessment only)
- Schedule follow-up assessment if needed

**Deliverable:** Remediation tracking document and re-test results (if applicable).

---

## Assessment Rules of Engagement

### General Rules

1. **Written authorisation** is required before any active testing begins
2. **Scope boundaries** must be respected — do not test systems outside the agreed scope
3. **Production systems** require additional safeguards — agree on testing windows, rollback procedures, and escalation contacts
4. **Data handling** — any sensitive data encountered during testing must be handled according to the organisation's data classification policy and the Privacy Act 1988
5. **Findings disclosure** — all findings are disclosed to the system owner. No findings are withheld or disclosed to third parties without written consent.

### Active Testing Guidelines

For Standard and Deep assessments involving active testing:

- **Prompt injection testing**: Use progressively escalating payloads. Start with benign test strings. Stop if unexpected system behaviour occurs.
- **RAG poisoning**: Only test with designated test documents in isolated environments. Never poison production knowledge bases.
- **Agent exploitation**: Test tool use boundaries with non-destructive operations first. Confirm rollback capability before testing destructive operations.
- **Voice AI testing**: Synthetic voice testing requires explicit consent. Never test voice cloning against real individuals without their written consent.
- **MCP server testing**: Enumerate exposed tools before testing. Confirm which tools are safe to invoke in the test environment.
- **Denial of service**: Cost-exhaustion and rate limit testing must have agreed spending caps and circuit breakers.

### Reporting Standards

All AAISAF assessment reports must include:

1. Executive summary (1 page maximum)
2. Scope and methodology
3. System classification and applicable tactics
4. Findings ordered by AISS score (highest first)
5. Compliance mapping summary
6. Maturity level assessment with evidence
7. Prioritised remediation plan
8. Appendix: detailed technique results
