# Model Card

A short, standardized record of what a model is, how it was evaluated, and what its limits are. Complete one per model/version in production use — for a third-party model, pull as much of this as possible from the vendor's own published model card and note what they didn't disclose. See [glossary](../docs/glossary.md#core-definitions) for term definitions.

## Overview

| Field | Value |
|---|---|
| Model name / version | |
| Type (see [AI system types](../docs/glossary.md#types-of-ai-systems)) | |
| Provider (internal / vendor name) | |
| Date added to inventory | |
| Linked Risk Assessment | |

## Intended use

- **Intended use case(s):**
- **Intended users:**
- **Out-of-scope uses** (uses this model should *not* be applied to):

## Training data (as disclosed)

- **Data sources:** [or "not disclosed by vendor — foundation model"]
- **Training data cutoff/date range:**
- **Known data gaps or skews** (e.g., underrepresented languages, time periods, populations):
- **Fine-tuned on internal data?** Y/N — if yes, describe:

## Evaluated performance

*Filled in from a completed [Model Validation & Test Set Design Guide](model-validation-testing-guide.md) — don't fill this in without one behind it.*

| Metric | Result | Test set / method | Date evaluated |
|---|---|---|---|
| | | | |
| | | | |

- **Performance across subgroups** (if evaluated — see [Bias & Fairness Testing Guide](bias-fairness-testing-guide.md)):
- **Known failure modes observed in your own testing:**

## Limitations and risks

- **Documented limitations (from vendor or your own testing):**
- **Relevant OWASP risks** (see [OWASP AI Mapping](../docs/standards/owasp-ai-mapping.md)):
- **Explainability:** [ ] High (rules-based/simple model) [ ] Medium [ ] Low (deep learning/foundation model, outputs not individually explainable)

## Human oversight

- How is this model's output reviewed before use? (Reference the linked Risk Assessment §4)
- Who is accountable for output from this model?

## Maintenance

| Field | Value |
|---|---|
| Owner | |
| Last reviewed | |
| Next scheduled review | |
| Deprecation/retirement plan (if applicable) | |

---
*Related: [AI Risk Assessment](ai-risk-assessment.md) · [Model Validation & Test Set Design Guide](model-validation-testing-guide.md) · [Vendor Due Diligence](vendor-due-diligence.md) · [Glossary](../docs/glossary.md)*
