# Changelog

All notable changes to this project are documented here. Format loosely follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [Semantic Versioning](https://semver.org/) in spirit — a MAJOR bump for structural/breaking reorganizations, MINOR for new templates/sectors/docs, PATCH for corrections and wording fixes.

## [Unreleased]

Nothing yet.

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
[Unreleased]: https://github.com/jaykerzb/GovernTrace-AI-Framework/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/jaykerzb/GovernTrace-AI-Framework/releases/tag/v1.0.0
