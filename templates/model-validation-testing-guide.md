# Model Validation & Test Set Design Guide

Closes the last gap explicitly flagged in the [NIST AI RMF Crosswalk](../docs/standards/nist-ai-rmf-crosswalk.md) (Measure 2.1–2.3: test sets representative of deployment context, evaluated for validity/reliability). This is about whether a model is *accurate and reliable*, independent of whether it's *fair* — that's the [Bias & Fairness Testing Guide](bias-fairness-testing-guide.md)'s job. Use both; they check different things and a model can pass one and fail the other.

## 1. Does this apply?

Any model with a [Model Card](model-card.md) needs baseline validation before its performance numbers go in that card. This is lighter for a vendor's foundation model (you're generally trusting their published evals, cross-referenced in [Vendor Due Diligence](vendor-due-diligence.md)) and heavier for anything you train or fine-tune yourself.

## 2. Test set design

- [ ] **Held out, not peeked at** — the test set was never used during model development/tuning decisions. If it was touched even once to pick a threshold or feature, it's no longer a valid test set.
- [ ] **Representative of deployment, not just training distribution** — pull test examples from the actual population/conditions the model will face in production, not just a random split of historical data (these can differ: e.g., historical data may underrepresent a new market, a new product line, or a seasonal pattern).
- [ ] **Sized for the claim being made** — a tiny test set can't support a precise accuracy claim; know your confidence interval, not just your point estimate.
- [ ] **Includes edge cases deliberately, not just by chance** — thin-file applicants, unusual inputs, boundary conditions. Random sampling alone under-represents rare-but-important cases.
- [ ] **Time-appropriate** — for anything where the world changes (credit risk, fraud patterns, content trends), test on data from *after* the training window, not a random split of the same period, to catch temporal leakage and give an honest read on how it'll perform going forward.

## 3. What to measure

| Question | Why it matters |
|---|---|
| What's the primary accuracy/performance metric, and why is it the right one for this decision? | Optimizing the wrong metric (e.g., overall accuracy on an imbalanced outcome) can hide serious failures on the cases that matter most |
| How does performance compare to the current baseline (existing process, prior model, or "no model")? | A model that's technically accurate but worse than what it's replacing isn't a win |
| What's the confidence interval / uncertainty around the headline number? | A single point estimate from a small test set can be misleadingly precise |
| Where does the model fail, specifically? | Aggregate accuracy hides concentrated failure in a subgroup or condition — this is where [Bias & Fairness Testing](bias-fairness-testing-guide.md) and this guide overlap; run both |

## 4. Reliability under drift

- [ ] Establish a **performance baseline** at launch — the numbers everything else gets compared to.
- [ ] Define what **drift** looks like for this specific model (input distribution shift, output distribution shift, or a drop against a ground-truth sample) and how it'll be detected.
- [ ] Set a **re-validation cadence** proportionate to risk (tie to the [Risk Assessment](ai-risk-assessment.md)'s re-review cadence — Low: annual, Medium: 6-monthly, High: quarterly).
- [ ] Confirm the [Model Card](model-card.md)'s "known limitations" section gets updated when a re-validation finds something new, not just at initial launch.

## 5. Documentation

| Field | Value |
|---|---|
| Model tested | |
| Test set description (source, size, date range, representativeness notes) | |
| Primary metric and result (with confidence interval if applicable) | |
| Baseline comparison | |
| Known failure conditions identified | |
| Reviewed/approved by (independent of the model's builder) | |
| Next validation date | |

Feed results into the [Model Card](model-card.md)'s "Evaluated performance" section — that section should never be filled in without a completed validation like this behind it.

---
*Related: [Model Card](model-card.md) · [Bias & Fairness Testing Guide](bias-fairness-testing-guide.md) · [AI Risk Assessment](ai-risk-assessment.md)*
