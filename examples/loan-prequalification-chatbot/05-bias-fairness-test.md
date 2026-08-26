# Bias & Fairness Test — LoanAssist Scoring Layer (Completed Example)

*Filled-out version of [templates/bias-fairness-testing-guide.md](../../templates/bias-fairness-testing-guide.md). See the [scenario overview](README.md) for context.*

## 1. Applies?

Yes — the scoring layer influences a credit-adjacent decision and could differentially affect protected groups. Required before launch per the [Risk Assessment](02-risk-assessment.md) and the [Banking sector pack](../../sectors/banking-financial-services/README.md).

## 2. Groups tested

Race/ethnicity, sex, and age band, using Riverbend's existing HMDA-adjacent reporting fields (collected separately from the scoring model's own inputs, per standard fair-lending testing practice — collection here is for monitoring purposes under the applicable regulatory exception, not used as a model feature).

## 3. Metrics selected

- **Disparate impact ratio (four-fifths rule)** — chosen as the primary metric because it's the standard regulatory reference point for this sector, per the [Banking sector pack](../../sectors/banking-financial-services/README.md).
- **Predictive parity** — chosen as a secondary check, since the score is meant to predict actual approval likelihood consistently across groups.

## 4. Results — round 1 (initial model, before mitigation)

| Group | Selection rate (favorable pre-qualification) | Disparate impact ratio vs. highest group |
|---|---|---|
| Reference group (highest selection rate) | 61% | 1.00 |
| Group A | 52% | 0.85 |
| Group B | 46% | **0.75** ⚠️ below 0.8 threshold |
| Group C | 58% | 0.95 |

**Finding:** Group B fell below the four-fifths threshold. Investigation traced roughly half the gap to two features acting as likely proxies: **zip code** and **employer name** (employer name correlated with employer industry, which correlated with the tested groups in this portfolio).

## 5. Mitigation

- Zip code and employer name removed from the scoring model's feature set entirely (not just down-weighted — the [Risk Assessment](02-risk-assessment.md) proxy-discrimination control reflects this).
- Model retrained without those features.

## Results — round 2 (after mitigation)

| Group | Selection rate | Disparate impact ratio |
|---|---|---|
| Reference group | 60% | 1.00 |
| Group A | 53% | 0.88 |
| Group B | 50% | **0.83** ✅ passes threshold |
| Group C | 57% | 0.95 |

**Interpretation:** Removing the two proxy features closed most of the gap for Group B, at a small cost to overall model AUC (0.82 → 0.81, judged an acceptable tradeoff and documented as such — see [Model Card](04-model-card.md)). The remaining gap is smaller and judged consistent with legitimate credit-relevant factors, not residual proxy effects, but is flagged for continued monitoring rather than declared fully resolved.

## 6. Documentation

| Field | Value |
|---|---|
| System tested | LoanAssist-Score v1.0 |
| Date | 2026-02-22 |
| Metrics used and why | Disparate impact ratio (regulatory standard reference) + predictive parity (consistency check) |
| Results summary | Initial disparity in Group B traced to zip code/employer-name proxies; resolved by feature removal and retraining |
| Remediation taken | Zip code and employer name removed from feature set; model retrained |
| Reviewed/approved by | David Ochoa (Governance Lead), Fair Lending Officer (Compliance) |
| Next test date | 2026-06-08 (aligned to quarterly re-validation) |

---
**Next:** [Pre-Deployment Checklist](06-pre-deployment-checklist.md)
