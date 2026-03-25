# Contributing to AAISAF

Thank you for your interest in contributing to the Australian AI Security Assessment Framework.

## How to Contribute

### Reporting Issues

- **Inaccurate technique descriptions**: Open an issue with the technique ID and specific correction needed
- **Missing evidence**: If a technique claims real-world evidence but you cannot verify it, flag it
- **Broken compliance mappings**: If a mapping to OWASP/MITRE/NIST/ISO doesn't match the source standard, report it
- **New techniques**: Propose new techniques with evidence (CVE, documented incident, or peer-reviewed research)

### Submitting Changes

1. Fork the repository
2. Create a feature branch (`git checkout -b technique/TA06.005-new-voice-attack`)
3. Follow the technique template schema exactly (see `framework/techniques/TEMPLATE.md`)
4. Ensure every technique has at least one verified evidence source
5. Run the consistency checker: `scripts/validate.sh`
6. Submit a pull request with a clear description

### Technique Submission Requirements

Every new technique **must** include:

- [ ] Unique ID following the `TAXX.YYY` convention
- [ ] At least one evidence source (CVE, incident report, or peer-reviewed paper)
- [ ] If no real-world evidence exists, label as "Theoretical — no documented exploitation as of [date]"
- [ ] Severity rating using the AISS methodology
- [ ] At least one compliance mapping (OWASP, MITRE, NIST, ISO 42001, or AU regulatory)
- [ ] Detection guidance
- [ ] Remediation guidance

### Writing Style

- Use ISO/IEC 27000 terminology where applicable
- Define novel terms in the glossary
- Zero colloquial or ambiguous language in technique descriptions
- British English spelling (Australian standard)
- Present tense for descriptions, imperative mood for remediation steps

### Compliance Mapping Rules

- Verify every mapping against the actual standard text, not secondhand summaries
- OWASP: Verify against [genai.owasp.org](https://genai.owasp.org)
- MITRE ATLAS: Verify against [atlas.mitre.org](https://atlas.mitre.org)
- NIST: Verify against [nist.gov](https://nist.gov)
- Australian legislation: Verify against [legislation.gov.au](https://www.legislation.gov.au)

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/). Be respectful, constructive, and evidence-driven.

## License

By contributing, you agree that your contributions will be licensed under CC BY-SA 4.0.
