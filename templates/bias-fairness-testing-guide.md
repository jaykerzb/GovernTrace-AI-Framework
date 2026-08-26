# Bias & Fairness Testing Guide

A practical starting methodology for evaluating whether an AI system's outputs differ unfairly across groups — the "Measure" gap flagged in the [NIST AI RMF crosswalk](../docs/standards/nist-ai-rmf-crosswalk.md). Required for any system rated Medium/High risk in the [Risk Assessment](ai-risk-assessment.md) where output could differentially affect people. This is a starting methodology, not a statistics textbook — bring in a qualified analyst for anything high-stakes (hiring, lending, healthcare).

## 1. Decide if this applies

Ask during the [Risk Assessment](ai-risk-assessment.md):

- Does this system's output affect different people differently based on characteristics correlated with protected classes (race, gender, age, disability, national origin)?
- Does it make or influence a [material decision](../docs/glossary.md#risk-and-impact-terms) (hiring, credit, pricing, access, moderation)?

If yes to either, this guide applies before go-live and on an ongoing basis after.

## 2. Define the groups to test

- Identify the relevant protected/comparison groups for your context and jurisdiction (consult Legal/HR — this varies by use case and location).
- If you don't have group-labeled data to test with, consider: synthetic/paired testing (submit matched inputs that differ only in a protected attribute or proxy, e.g. name), or a proxy analysis using available fields (zip code, school, etc.) with the same caveats about proxy discrimination.

## 3. Pick your metrics

You will not use all of these — pick what fits the decision type, and document why.

| Metric | What it measures | Best for |
|---|---|---|
| **Demographic parity** | Are positive outcomes (approval, selection, high score) proportionate across groups? | Screening/selection decisions |
| **Equal opportunity** | Among people who *should* get a positive outcome, is the true positive rate equal across groups? | Decisions with a clear ground truth (loan repayment, job performance) |
| **Predictive parity** | Among people who *received* a positive outcome, is the accuracy equal across groups? | Risk-scoring systems |
| **Disparate impact ratio** | Selection rate for one group ÷ selection rate for the highest-selected group — a common regulatory rule of thumb flags ratios below ~0.8 ("four-fifths rule") as worth investigating | Employment-adjacent decisions (US EEOC context) |
| **Output quality parity (generative AI)** | Is response quality, refusal rate, or tone consistent across how the same request is phrased/attributed to different groups? | Chatbots, generative assistants |

## 4. Run the test

- [ ] Test set assembled, representative of your actual deployment population (not just convenient data)
- [ ] Metrics calculated per group and compared
- [ ] Results reviewed by someone other than the system's builder (avoid rubber-stamping — ties to "overreliance" in the [Risk Assessment](ai-risk-assessment.md) §3)
- [ ] Disparities beyond your organization's defined tolerance flagged for remediation before launch

## 5. Interpret results carefully

- A disparity doesn't automatically mean illegal discrimination or a broken model — but it does mean you need a documented, defensible explanation, not silence.
- Small sample sizes for minority groups can produce noisy metrics — don't over-read a result from too few data points; say so explicitly rather than presenting it as settled.
- Fixing one metric can worsen another (these metrics are mathematically not all simultaneously satisfiable in most real cases) — document the tradeoff and who approved it.

## 6. Document and repeat

| Field | Value |
|---|---|
| System tested | |
| Date | |
| Metrics used and why | |
| Results summary | |
| Disparities found | |
| Remediation taken (if any) | |
| Reviewed/approved by | |
| Next test date | |

Feed results into the [Risk Assessment](ai-risk-assessment.md) §3 (bias/disparate impact row) and, for anything customer- or employment-facing, keep this documentation — it's your evidence of good-faith diligence if a decision is ever challenged.

---
*Related: [AI Risk Assessment](ai-risk-assessment.md) · [Model Card](model-card.md) · [NIST AI RMF Crosswalk](../docs/standards/nist-ai-rmf-crosswalk.md)*
