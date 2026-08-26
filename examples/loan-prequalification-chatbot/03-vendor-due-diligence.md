# Vendor Due Diligence — Cortex AI (Completed Example)

*Filled-out version of [templates/vendor-due-diligence.md](../../templates/vendor-due-diligence.md). See the [scenario overview](README.md) for context.*

## Vendor overview

| Field | Value |
|---|---|
| Vendor/product name | Cortex AI Conversational Platform (fictional) |
| Model(s) used | Cortex-fine-tuned LLM (built on a licensed foundation model); Riverbend's own scoring layer runs separately, hosted internally |
| Business owner / requester | Priya Nandakumar |
| Linked intake form | [01-intake-form.md](01-intake-form.md) |

## Data handling

- **Trains on customer inputs/outputs?** No — contract includes an explicit no-training-on-customer-data clause, confirmed in writing.
- **Data processing/storage region:** US-only, contractually restricted (relevant given Riverbend's data residency requirements for financial data).
- **Retention period:** 30 days for operational logs, then automated deletion; customer deletion requests honored within 5 business days.
- **DPA in place?** Yes, executed alongside the master services agreement.
- **Sub-processors:** Cortex AI discloses one sub-processor (cloud hosting) — no further AI sub-processing of Riverbend data.

## Security

- **Certifications:** SOC 2 Type II (current), no ISO 27001 yet — flagged as a minor gap, accepted given SOC 2 coverage.
- **Encryption:** TLS 1.2+ in transit, AES-256 at rest — confirmed via security questionnaire.
- **Breach notification SLA:** 72 hours, per contract.
- **Access controls:** SSO/SAML supported, role-based access, full audit logging available to Riverbend admins.

## Model transparency

- **Model card/system card published?** Yes — Cortex AI publishes a system card describing training approach, intended use, and known limitations for the fine-tuned conversational model.
- **Bias evaluations disclosed?** Partial — Cortex AI discloses general-purpose fairness testing on their base model, but not specific to financial-services use cases. *Gap noted: Riverbend's own [Bias & Fairness Test](05-bias-fairness-test.md) covers the financial-services-specific gap, applied to the full LoanAssist system (chat + scoring layer combined), not just Cortex AI's component.*
- **Training data disclosure:** General description provided (public web text, licensed datasets, fine-tuning corpus description); full dataset not disclosed (standard for foundation model vendors).
- **Process for reporting bad outputs?** Yes — dedicated support channel with contractual response SLA.

## Commercial and legal

- **Liability terms:** Cortex AI liability is capped; Riverbench retains full responsibility for credit decisions (correctly, since the scoring layer is Riverbend's own) — reviewed and accepted by Legal.
- **Termination notice:** 90 days, sufficient for an orderly transition if needed.
- **IP:** Riverbend owns all output generated in its conversations; Cortex AI provides standard IP indemnification for their platform.

## Risk rating

| Dimension | Rating |
|---|---|
| Data handling risk | Low |
| Security posture | Low-Medium (SOC 2 present, ISO 27001 absent) |
| Vendor transparency | Medium (system card exists but financial-services-specific fairness testing gap) |
| Contractual/legal risk | Low |
| Vendor lock-in / concentration risk | Medium — no immediate alternative vendor evaluated; flagged for next annual review |

**Overall decision: ☒ Approve with conditions**

**Conditions:** Riverbend's own bias/fairness testing must independently cover the full LoanAssist system (not rely on Cortex AI's general-purpose testing alone) before launch. Re-evaluate ISO 27001 status and vendor concentration risk at next annual review.

**Reviewed by:** David Ochoa / **Date:** 2026-02-28

**Next scheduled review:** 2027-02-28 (annual, per contract renewal)

---
**Next:** [Model Card](04-model-card.md)
