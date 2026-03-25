# Checklist 06 — API Security

**Applicable System Types:** All

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 6.1 | Verify API authentication is enforced (API keys, OAuth) | Q | X | X | TA04.004 |
| 6.2 | Verify rate limiting is implemented and effective | Q | X | X | TA04.002 |
| 6.3 | Test cost exhaustion via large prompt/response manipulation | | X | X | TA04.001 |
| 6.4 | Verify API keys are not exposed in client-side code | Q | X | X | TA04.004 |
| 6.5 | Test for model endpoint enumeration | | X | X | TA04.003 |
| 6.6 | Test model version fingerprinting | | X | X | TA04.005 |
| 6.7 | Verify usage monitoring and alerting | Q | X | X | TA04.001 |
| 6.8 | Test batch inference abuse | | X | X | TA04.006 |
| 6.9 | Test streaming response filter bypass | | X | X | TA04.007 |
| 6.10 | Verify API key rotation policy | | X | X | TA04.004 |
| 6.11 | Test rate limit bypass via multiple keys/IPs | | | X | TA04.002 |
| 6.12 | Verify cost caps and circuit breakers | | X | X | TA04.001 |

## Evidence Requirements

- API authentication configuration
- Rate limiting configuration and test results
- Usage monitoring dashboard/alerts
- Cost cap configuration
- API key storage mechanism documentation
