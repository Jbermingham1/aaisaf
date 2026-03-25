# Checklist 08 — Data Protection

**Applicable System Types:** All

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 8.1 | Verify PII detection in AI outputs | Q | X | X | TA07.007 |
| 8.2 | Test training data extraction via targeted prompts | | X | X | TA07.001 |
| 8.3 | Verify session isolation (no cross-session data leakage) | Q | X | X | TA08.005 |
| 8.4 | Review data retention policy for AI interactions | Q | X | X | Privacy Act APP 11 |
| 8.5 | Verify cross-border data transfer compliance (if AI APIs are overseas) | | X | X | Privacy Act APP 8 |
| 8.6 | Test membership inference attacks | | | X | TA07.002 |
| 8.7 | Test model inversion attacks | | | X | TA07.004 |
| 8.8 | Verify guardrail bypass resistance | | X | X | TA08.001 |
| 8.9 | Test content filter evasion | | X | X | TA08.003 |
| 8.10 | Verify system role integrity (role manipulation resistance) | | X | X | TA08.004 |
| 8.11 | Test authorisation bypass via indirect prompt injection | | X | X | TA08.006 |
| 8.12 | Test human-in-the-loop bypass | | X | X | TA08.007 |
| 8.13 | Review AI system logging for sensitive data handling | | X | X | TA07.007 |
| 8.14 | Verify encryption of AI data at rest and in transit | Q | X | X | Privacy Act APP 11 |

## Evidence Requirements

- PII detection configuration and test results
- Session isolation test results
- Data retention policy documentation
- Cross-border data transfer assessment
- Encryption configuration evidence
