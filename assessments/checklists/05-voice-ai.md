# Checklist 05 — Voice AI Security

**Applicable System Types:** E, G

## Quick Assessment Items (marked with Q)

| # | Check | Quick | Standard | Deep | Technique |
|---|-------|-------|----------|------|-----------|
| 5.1 | Verify callers are informed they are speaking with AI | Q | X | X | VAISS G2, EU AI Act Art 50 |
| 5.2 | Verify authentication before sharing sensitive information | Q | X | X | TA06.005 |
| 5.3 | Verify voice recordings are stored securely with access controls | Q | X | X | Privacy Act APP 11 |
| 5.4 | Test voice prompt injection via spoken payloads | | X | X | TA06.001 |
| 5.5 | Test conversation flow bypass (skipping authentication, reaching unintended branches) | | X | X | TA06.003 |
| 5.6 | Test DTMF/telephony signal injection during call | | X | X | TA06.006 |
| 5.7 | Review STT pipeline for known biases and failure modes | | X | X | TA06.008 |
| 5.8 | Assess deepfake voice detection capability | | X | X | TA06.002 |
| 5.9 | Test whether voice AI can be manipulated to request credentials | | X | X | TA06.005 |
| 5.10 | Review call transfer and escalation security | | X | X | TA06.003 |
| 5.11 | Test audio adversarial examples against STT | | | X | TA06.004 |
| 5.12 | Assess real-time voice cloning risk in the deployment context | | | X | TA06.009 |
| 5.13 | Full vishing scenario simulation | | | X | TA06.007 |
| 5.14 | Test synthetic voice spoofing against authentication | | | X | TA06.002 |

## Evidence Requirements

- Call recordings demonstrating injection or bypass
- Conversation flow diagram with bypass points identified
- Authentication mechanism documentation
- Voice recording storage and access control evidence
- STT error rate analysis for adversarial inputs
