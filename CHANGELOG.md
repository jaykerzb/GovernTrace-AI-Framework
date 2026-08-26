# Changelog

All notable changes to this project are documented here. Format loosely follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [Semantic Versioning](https://semver.org/) in spirit — a MAJOR bump for structural/breaking reorganizations, MINOR for new templates/sectors/docs, PATCH for corrections and wording fixes.

## [Unreleased]

Nothing yet.

## [1.2.0] — 2026-08-26

Closes the last remaining gap explicitly flagged in the NIST AI RMF crosswalk (Measure 2.1–2.3: test set representativeness/validity), which v1.1.0 didn't fully address.

### Added
- [Model Validation & Test Set Design Guide](templates/model-validation-testing-guide.md) — a general accuracy/reliability validation methodology (test set design, drift monitoring, re-validation cadence), distinct from the [Bias & Fairness Testing Guide](templates/bias-fairness-testing-guide.md), which only covers group fairness

### Changed
- [NIST AI RMF Crosswalk](docs/standards/nist-ai-rmf-crosswalk.md) Measure function now shows no remaining flagged gaps — the "Honest gaps" section now describes an inherent limit (a template can't substitute for a qualified analyst's judgment on statistical validity) rather than a missing artifact
- [Model Card](templates/model-card.md), [Pre-Deployment Checklist](checklists/pre-deployment-checklist.md), and [Bias & Fairness Testing Guide](templates/bias-fairness-testing-guide.md) now reference the new guide

## [1.1.0] — 2026-08-26

Closes gaps explicitly flagged as unaddressed in the v1.0.0 standards crosswalks — a self-directed audit of this repo's own "Honest gaps" sections.

### Added
- [AI Tool Inventory](templates/ai-tool-inventory.md) — closes the NIST AI RMF (Govern 1.6–1.7) and ISO/IEC 42001 (Clause 8/A.4) gap around a templated tool inventory
- [Training & Awareness Plan](templates/training-and-awareness-plan.md) — closes the NIST AI RMF (Govern 3.1–3.2) and ISO/IEC 42001 (Clause 7) competence/training gap
- [Internal Audit Checklist](docs/internal-audit-checklist.md) — closes the ISO/IEC 42001 (Clause 9) internal audit gap and the NIST AI RMF (Govern 1.5) ongoing-monitoring gap; audits whether the governance program itself is functioning, not just whether documents exist
- [GDPR Mapping](docs/standards/gdpr-mapping.md) — a fifth standards crosswalk, covering lawful basis, DPIAs, Article 22 automated decision-making, and the AI-specific training-data-erasure problem

### Changed
- Updated [NIST AI RMF](docs/standards/nist-ai-rmf-crosswalk.md) and [ISO/IEC 42001](docs/standards/iso-42001-crosswalk.md) crosswalks to reflect newly-closed gaps
- Wired the four new artifacts into the main README, Roles & RACI, Maturity Model, and relevant existing templates

## [1.0.0] — 2026-08-26

First tagged release. Establishes the full v1 scope: core governance workflow, standards crosswalks, expanded template library, sector packs, a worked example, and repo hygiene.

### Added
- Core workflow: [Acceptable Use Policy](policies/acceptable-use-policy.md), [Use-Case Intake Form](templates/ai-use-case-intake-form.md), [AI Risk Assessment](templates/ai-risk-assessment.md), [Vendor Due Diligence](templates/vendor-due-diligence.md), [Pre-Deployment Checklist](checklists/pre-deployment-checklist.md)
- Standards crosswalks: [NIST AI RMF](docs/standards/nist-ai-rmf-crosswalk.md) (subcategory-level), [ISO/IEC 42001](docs/standards/iso-42001-crosswalk.md), [EU AI Act risk tiers](docs/standards/eu-ai-act-risk-tiers.md), [OWASP AI mapping](docs/standards/owasp-ai-mapping.md)
- Shared vocabulary: [docs/glossary.md](docs/glossary.md) defining AI system types and core governance terms
- Template library: [Model Card](templates/model-card.md), [Bias & Fairness Testing Guide](templates/bias-fairness-testing-guide.md), [Data Retention Schedule](templates/data-retention-schedule.md), [Incident Response Runbook](templates/incident-response-runbook.md), [Board Reporting Template](templates/board-reporting-template.md)
- Eight [sector packs](sectors/README.md): Banking & Financial Services, Healthcare, Insurance, Public Sector, Retail/E-commerce, Education, Technology/SaaS, Manufacturing/Critical Infrastructure
- A fully filled-out [worked example](examples/loan-prequalification-chatbot/README.md) (banking loan pre-qualification chatbot) walking every core template end to end
- Governance structure docs: [Roles & RACI](docs/roles-and-raci.md), [Maturity Model](docs/maturity-model.md)
- Repository hygiene: CONTRIBUTING.md, CODE_OF_CONDUCT.md, issue/PR templates, .gitattributes

---
[Unreleased]: https://github.com/jaykerzb/GovernTrace-AI-Framework/compare/v1.2.0...HEAD
[1.2.0]: https://github.com/jaykerzb/GovernTrace-AI-Framework/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/jaykerzb/GovernTrace-AI-Framework/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/jaykerzb/GovernTrace-AI-Framework/releases/tag/v1.0.0
