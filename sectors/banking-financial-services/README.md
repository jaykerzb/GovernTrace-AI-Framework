# Sector Pack: Banking & Financial Services

For banks, credit unions, fintechs, lenders, payment processors, and core banking/payments vendors (e.g., organizations integrating with providers like Fiserv, FIS, or Jack Henry). Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md) for how these fit together.

## Why banking needs its own overlay

Financial services AI carries two risk types most sectors don't stack together: **model risk** (the model itself being wrong, unstable, or poorly validated — a well-established discipline in banking long before "AI governance" existed) and **fair lending risk** (AI-driven decisions about credit, pricing, or account access triggering anti-discrimination law). Both have mature regulatory expectations you should map to before treating this as a green-field problem.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **SR 11-7** (Federal Reserve / OCC Model Risk Management guidance) | The baseline expectation for model risk management at regulated banks — covers model development, validation, and ongoing monitoring. Extend, don't replace, if you already have an SR 11-7 program. |
| **ECOA / Regulation B** (Equal Credit Opportunity Act) | Prohibits discrimination in credit decisions; requires adverse action notices with specific, accurate reasons — a real challenge for opaque models. |
| **Fair Housing Act** | Applies if AI touches mortgage/housing-related lending decisions. |
| **FCRA** (Fair Credit Reporting Act) | Governs use of consumer report data in automated decisions; disclosure obligations when adverse action is based on such data. |
| **GLBA** (Gramm-Leach-Bliley Act) | Data privacy/security obligations for nonpublic personal financial information — relevant to what data AI tools can touch. |
| **BSA/AML** | If AI is used for transaction monitoring or fraud detection, model validation and explainability expectations from AML regulators apply. |
| **CFPB guidance** | Has specifically addressed AI/algorithmic credit decisions and adverse action notice adequacy — a live enforcement area. |
| **State-level AI/insurance-adjacent laws** | Some states have added AI-specific requirements for financial products — check state regulator guidance where you're licensed. |

This is not exhaustive — payments-specific rules (Reg E, card network rules), broker-dealer AI use (FINRA), and investment adviser AI use (SEC) bring additional regimes if applicable to your business.

## Additional risk categories for the Risk Assessment

Add these to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3 for any system touching credit, account decisions, or financial risk scoring:

- [ ] **Adverse action explainability** — can you generate a specific, accurate reason code from this model's output, not just a score? (Required under ECOA/Reg B if used in credit decisions.)
- [ ] **Fair lending / disparate impact** — has this been tested per [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) against protected classes relevant to lending?
- [ ] **Model stability/drift** — does the model's behavior stay consistent over time, or could drift silently change credit outcomes? Tie to SR 11-7 ongoing monitoring expectations.
- [ ] **Proxy discrimination** — could input features (zip code, alternative data) act as proxies for protected characteristics even without using them directly?
- [ ] **Third-party model risk** — if using a vendor credit/fraud model, does your model risk management program extend to it per SR 11-7's third-party guidance?

## Additional Pre-Deployment Checklist items

- [ ] Model validated per your SR 11-7 (or equivalent) model risk management framework, independent of the model's developer
- [ ] Adverse action notice process tested end-to-end and produces accurate, specific reasons
- [ ] Fair lending review completed and documented (legal/compliance sign-off, not just engineering)
- [ ] Data used for the model confirmed in scope/out of scope per GLBA and your data governance program
- [ ] Regulatory exam readiness: can you produce model documentation, validation results, and monitoring evidence on request?

## Sector-specific terms

- **Model risk** — the risk of financial loss or bad decisions arising from errors in model design, implementation, or use (SR 11-7 usage) — broader than the generic AI risk categories in the [glossary](../../docs/glossary.md), worth keeping distinct in your documentation.
- **Adverse action** — a credit denial or unfavorable change in credit terms, triggering specific notice obligations under ECOA/FCRA.
- **Champion/challenger testing** — running a new model alongside the production model on live data before fully replacing it — a common financial-services practice worth adopting for any Medium/High risk model change.

## How this maps to the core framework

| Core artifact | Banking-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3 |
| [Model Card](../../templates/model-card.md) | Add a "Model risk validation" field referencing your SR 11-7 program |
| [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) | Use disparate impact ratio / four-fifths rule as your primary metric for lending decisions — it's the one regulators reference most |
| [Incident Response Runbook](../../templates/incident-response-runbook.md) | Add regulatory notification triggers (state/federal banking regulator, CFPB) to your Sev 1/2 notification table |

See also: [core Risk Assessment](../../templates/ai-risk-assessment.md) · [NIST AI RMF Crosswalk](../../docs/standards/nist-ai-rmf-crosswalk.md) · [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md)
