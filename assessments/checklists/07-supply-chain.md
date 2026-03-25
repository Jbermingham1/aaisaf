# Checklist 07 — Supply Chain Security

**Applicable System Types:** All

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 7.1 | Maintain inventory of all AI dependencies (models, libraries, data sources) | Q | X | X | TA05 |
| 7.2 | Scan AI libraries for known vulnerabilities | Q | X | X | TA05.002 |
| 7.3 | Verify model provenance (source, integrity, version) | | X | X | TA05.001 |
| 7.4 | Review model serialisation format (prefer SafeTensors over pickle) | | X | X | TA05.004 |
| 7.5 | Verify fine-tuning data provenance and integrity | | X | X | TA05.003 |
| 7.6 | Review prompt template sources (if using shared templates) | | X | X | TA05.005 |
| 7.7 | Verify embedding model integrity (if using RAG) | | X | X | TA05.006 |
| 7.8 | Review AI gateway/proxy security (if using litellm or similar) | | X | X | TA05.007 |
| 7.9 | Deep dependency audit with pip-audit/npm audit | | | X | TA05.002 |
| 7.10 | Model binary analysis for backdoors | | | X | TA05.001 |
| 7.11 | Fine-tuning data poisoning resilience test | | | X | TA05.003 |

## Evidence Requirements

- AI dependency inventory (SBOM)
- Vulnerability scan results
- Model provenance documentation
- Dependency update/patch policy
