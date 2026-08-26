# Sector Pack: Insurance

For carriers, MGAs, and insurtechs using AI in underwriting, pricing, claims, or marketing. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md). Shares significant overlap with the [Banking & Financial Services pack](../banking-financial-services/README.md) on fairness/model-risk concepts — read that one too if you're an insurtech lender.

## Why insurance needs its own overlay

Insurance regulation is primarily **state-based** (in the US) and has moved unusually fast on AI-specific rules compared to most sectors — largely because underwriting and pricing AI directly determines who gets coverage and at what cost, a textbook "material decision" per the [glossary](../../docs/glossary.md#risk-and-impact-terms).

## Key regulatory context

| Regime | Relevance |
|---|---|
| **NAIC Model Bulletin on the Use of AI Systems** | Adopted by many state insurance departments — sets expectations for AI governance programs, third-party AI vendor oversight, and testing for unfair discrimination. The closest thing to a sector-wide standard; treat as your baseline. |
| **State unfair trade practices acts** | Most states prohibit unfair discrimination in underwriting/rating; increasingly interpreted to explicitly cover algorithmic decisions. |
| **State-specific AI insurance laws** (e.g., Colorado's algorithm/predictive model regulations for life insurance) | Some states have gone further than the NAIC bulletin with binding testing and reporting requirements — check every state you're licensed in. |
| **Unfair Claims Settlement Practices Acts** | Relevant if AI is used in claims triage, evaluation, or denial — delay or improper denial via automation can trigger bad-faith exposure. |
| **FCRA** (where credit-based insurance scores are used) | Same disclosure/adverse-action logic as banking applies to credit-based insurance scoring. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Unfair discrimination in rating/underwriting** — tested per [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) against protected classes and proxies (territory, credit-based scores, etc.) relevant to your state's rules?
- [ ] **Claims denial/delay risk** — could this system's use in claims handling improperly deny or delay a valid claim, and is there a fast human escalation path?
- [ ] **Data source appropriateness** — is external/alternative data used in underwriting actually predictive and permitted under your state's regulations, or is it a discrimination proxy?
- [ ] **Regulatory filing accuracy** — if this model affects rates, does its logic match what was filed with and approved by state regulators? (A model that drifts from its filed methodology is a compliance problem independent of fairness.)
- [ ] **Multi-state variance** — does the system need different treatment/constraints by state given varying AI-specific insurance rules?

## Additional Pre-Deployment Checklist items

- [ ] Testing for unfair discrimination completed and documented per NAIC Model Bulletin expectations (or your state's specific requirement)
- [ ] Confirmed the model's actual logic matches what's on file with regulators, if it affects rating
- [ ] Claims-handling systems have a tested, fast human escalation path before any denial is finalized
- [ ] Third-party AI vendor (e.g., a vendor-supplied underwriting model) governance extended per NAIC's third-party oversight expectations — cross-reference [Vendor Due Diligence](../../templates/vendor-due-diligence.md)
- [ ] State-by-state applicability review completed if operating in multiple states

## Sector-specific terms

- **Unfair discrimination** (insurance usage) — differing treatment in rates or coverage not justified by actual risk-related factors; the core prohibition most state AI bulletins are built around.
- **External/third-party/alternative data** — non-traditional data sources (social media, purchasing behavior, etc.) used in underwriting; a major current regulatory focus area for proxy discrimination.
- **Rate filing** — the regulatory approval process for insurance pricing methodology; AI models used in rating generally need their logic reflected accurately in what's filed.

## How this maps to the core framework

| Core artifact | Insurance-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3; underwriting/pricing/claims decisions are Medium/High risk minimum |
| [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) | Add unfair discrimination testing aligned to your state regulator's specific expectations |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Add NAIC-aligned third-party AI oversight questions for underwriting/pricing vendors |
| [Board Reporting Template](../../templates/board-reporting-template.md) | Add a state-regulatory-filings status line if AI affects rating |

See also: [Banking & Financial Services pack](../banking-financial-services/README.md) · [NIST AI RMF Crosswalk](../../docs/standards/nist-ai-rmf-crosswalk.md)
