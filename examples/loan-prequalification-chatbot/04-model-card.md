# Model Card — LoanAssist Scoring Layer (Completed Example)

*Filled-out version of [templates/model-card.md](../../templates/model-card.md). See the [scenario overview](README.md) for context. Covers the Riverbend-built scoring layer specifically — the Cortex AI conversational component is documented separately via its vendor system card, referenced in [Vendor Due Diligence](03-vendor-due-diligence.md).*

## Overview

| Field | Value |
|---|---|
| Model name / version | LoanAssist-Score v1.0 |
| Type | Predictive / classification AI (see [glossary](../../docs/glossary.md#types-of-ai-systems)) — gradient-boosted tree model |
| Provider | Internal (Riverbend Model Risk & Data Science team) |
| Date added to inventory | 2026-03-01 |
| Linked Risk Assessment | [02-risk-assessment.md](02-risk-assessment.md) |

## Intended use

- **Intended use case:** Produce an informal, non-binding pre-qualification score (0–100) shown to prospective loan applicants before they submit a full application, to help them gauge likely eligibility.
- **Intended users:** Prospective personal loan applicants interacting with the public LoanAssist chatbot.
- **Out-of-scope uses:** Not to be used as, or presented as, an actual credit decision. Not to be used for existing-customer account decisions, collections, or any purpose beyond pre-application guidance. Not to be repurposed for other loan products without re-validation.

## Training data

- **Data sources:** De-identified historical personal loan applications and outcomes from Riverbend's own portfolio, 2019–2025.
- **Training data cutoff/date range:** Through December 2025.
- **Known data gaps or skews:** Portfolio is regionally concentrated (upper Midwest); applicants from newly-entered markets (2025 expansion states) are underrepresented in training data — flagged as a monitoring priority.
- **Fine-tuned on internal data?** N/A — this is a from-scratch model trained on internal data, not a fine-tuned foundation model.

## Evaluated performance

| Metric | Result | Test set / method | Date evaluated |
|---|---|---|---|
| AUC-ROC (predicting actual approval outcome) | 0.81 | Held-out 20% test set, 2024–2025 applications | 2026-02-15 |
| Calibration (predicted vs. actual approval rate by score band) | Within 4 percentage points across bands | Same test set | 2026-02-15 |
| Four-fifths rule ratio across race/ethnicity | 0.83 (passes 0.8 threshold) after proxy feature removal | See [Bias & Fairness Test](05-bias-fairness-test.md) | 2026-02-22 |

- **Performance across subgroups:** See full breakdown in [Bias & Fairness Test](05-bias-fairness-test.md) — new-market applicants show wider calibration error (~9 points) due to the training data gap noted above; flagged as a known limitation, not yet resolved.
- **Known failure modes observed in testing:** Systematically less confident (wider score variance) for applicants with thin credit files — consistent with training data sparsity for that segment, not a bias finding per se, but a reliability limitation communicated to users via the "informal estimate" disclaimer.

## Limitations and risks

- **Documented limitations:** Reduced reliability for new-market applicants and thin-file applicants (see above). Model does not incorporate real-time economic indicators — accuracy assumed to degrade in a rapidly shifting rate environment until the next quarterly re-validation.
- **Relevant OWASP risks:** Adversarial input manipulation is a low concern for this specific model (structured numeric/categorical inputs, not free text) — see [OWASP AI Mapping](../../docs/standards/owasp-ai-mapping.md) for the conversational layer's exposure instead.
- **Explainability:** ☒ Medium — gradient-boosted model, not deep learning; SHAP-based feature importance available per-prediction, which materially supports both fair-lending review and any future adverse-action-style explanation if the "advisory only" framing ever changes.

## Human oversight

Any applicant shown a *negative* pre-qualification score is offered a one-click path to speak with a human loan officer before leaving the flow (see [Risk Assessment §4](02-risk-assessment.md)). The final credit decision on any submitted full application is made by a human underwriter, independent of this model's score.

## Maintenance

| Field | Value |
|---|---|
| Owner | Riverbend Model Risk & Data Science team |
| Last reviewed | 2026-02-22 |
| Next scheduled review | 2026-06-08 (aligned to Risk Assessment re-review) |
| Deprecation/retirement plan | Superseded by v2.0 once new-market data reaches sufficient volume for a full retrain, targeted Q1 2027 |

---
**Next:** [Bias & Fairness Test](05-bias-fairness-test.md)
