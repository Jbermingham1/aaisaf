# Changelog

All notable changes to the AI Security Assessment Framework (AAISAF) will be documented in this file.

This project adheres to [Semantic Versioning](https://semver.org/).

## [1.1.0] — 2026-03-31

### Added
- **4 new techniques** (87 → 91 total) based on real-world assessment findings:
  - TA08.008 — Third-Party Tracker Exposure (session recording, analytics without consent)
  - TA08.009 — Cookie Consent Bypass or Absence (tracking active without consent mechanism)
  - TA09.007 — Security Header Misconfiguration (missing CSP, X-Frame-Options, etc.)
  - TA09.008 — Advertising Tracker Embedding on Government/Enterprise Portals
- **Passive Posture Assessment** — new 60–90 minute assessment type using only publicly accessible information (HTTP headers, page source, third-party script audit, cookie consent review). No active testing required. Added to methodology as the first assessment tier.
- New attack tree branches: Privacy & Consent Layer (TA08), Infrastructure Posture (TA09)

### Changed
- Assessment types expanded from 3 to 4 (Passive Posture + Quick + Standard + Deep)
- TA08 technique count: 7 → 9
- TA09 technique count: 6 → 8
- Total framework technique count: 87 → 91

### Notes
- New techniques derived from real-world passive assessment findings on a public-sector innovation-precinct portal
- Passive Posture Assessment methodology validated in practice — 5 of 6 findings confirmed in 90 minutes of passive OSINT
- All new techniques include AISS scoring, compliance mapping, and evidence references

## [1.0.0] — 2026-03-25

### Added
- Full Jekyll documentation site with Just the Docs theme
- GitHub Actions workflow for automated Pages deployment
- Expanded CVE & Incident Index (6 CVEs + 25 documented incidents)
- Global positioning (compliance modules for AU/APAC, EU, and international standards)

## [0.9.0] — 2026-03-24

### Added
- Initial framework structure and taxonomy (10 tactics, 87 techniques)
- AISS (AI Impact Severity Score) specification
- Three assessment types: Quick, Standard, Deep
- AI system scope classification (Types A-G)
- 5-level maturity model
- 6 compliance mapping documents (OWASP, MITRE, NIST, ISO 42001, AU regulatory, EU AI Act)
- 9 domain assessment checklists
- AI threat landscape analysis
- Glossary and bibliography
