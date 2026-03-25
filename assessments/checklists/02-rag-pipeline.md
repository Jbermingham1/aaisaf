# Checklist 02 — RAG & Knowledge Pipeline Security

**Applicable System Types:** B, D, G

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 2.1 | Verify knowledge base access controls (who can add/modify documents) | Q | X | X | TA02.001 |
| 2.2 | Test for document injection with hidden instructions (HTML comments, white text) | | X | X | TA02.003 |
| 2.3 | Verify document sanitisation at ingestion (strip formatting, metadata, hidden content) | Q | X | X | TA02.003 |
| 2.4 | Test retrieval manipulation via crafted queries | | X | X | TA02.002 |
| 2.5 | Verify tenant isolation in vector database (if multi-tenant) | Q | X | X | TA02.007 |
| 2.6 | Test cross-tenant data retrieval | | X | X | TA02.007 |
| 2.7 | Verify vector database authentication (not default/open) | Q | X | X | TA02.009 |
| 2.8 | Review chunking strategy for context preservation | | X | X | TA02.008 |
| 2.9 | Test embedding space manipulation (adversarial document retrieval) | | | X | TA02.004 |
| 2.10 | Test context window overflow via retrieved content | | X | X | TA02.005 |
| 2.11 | Review metadata handling in retrieval pipeline | | X | X | TA02.006 |
| 2.12 | Verify source attribution in AI responses | Q | X | X | TA02.001 |
| 2.13 | Test vector database direct access from external network | | X | X | TA02.009 |
| 2.14 | Review document provenance and integrity tracking | | X | X | TA02.001 |

## Evidence Requirements

- Knowledge base access control configuration
- Document sanitisation pipeline documentation
- Tenant isolation test results (multi-tenant systems)
- Vector database authentication evidence
- Retrieved document content samples showing/not showing hidden content
