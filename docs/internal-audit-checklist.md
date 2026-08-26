# AI Governance Internal Audit Checklist

Closes a gap flagged in the [ISO/IEC 42001 Crosswalk](standards/iso-42001-crosswalk.md) (Clause 9: performance evaluation/internal audit — previously marked as not addressed here) and the [NIST AI RMF Crosswalk](standards/nist-ai-rmf-crosswalk.md) (Govern 1.5: monitoring the risk management process itself). The difference between this and a [Risk Assessment](../templates/ai-risk-assessment.md) is scope: a Risk Assessment evaluates one AI system; this evaluates whether the *governance program itself* is functioning as designed.

Run this annually at minimum, or before any external audit/certification effort ([ISO/IEC 42001](standards/iso-42001-crosswalk.md) certification or a customer/regulator review). Whoever runs it should not be the [Governance Lead](roles-and-raci.md) being audited — use an internal audit function, a peer from another team, or an external reviewer for independence.

## 1. Coverage — is everything actually going through the process?

- [ ] Pull a sample of AI tools known to be in use (SSO logs, expense/procurement records, vendor invoices) and cross-check against the [AI Tool Inventory](../templates/ai-tool-inventory.md) — how many are missing? Any gap here is undocumented shadow AI.
- [ ] For each sampled tool that *is* in the inventory: does a completed [Use-Case Intake Form](../templates/ai-use-case-intake-form.md) exist?
- [ ] For each High/Medium-risk tool: does a completed, signed-off [Risk Assessment](../templates/ai-risk-assessment.md) exist, and is it current (not past its re-review date)?

## 2. Quality — are completed documents actually good, not just present?

- [ ] Sample 3-5 [Risk Assessments](../templates/ai-risk-assessment.md): are the risk ratings justified by what's written, or do they look rubber-stamped (e.g., every dimension marked "Low" with no explanation)?
- [ ] Sample 3-5 [Pre-Deployment Checklists](../checklists/pre-deployment-checklist.md): were "human review tested" and similar items actually verified, or just checked off? (Compare against the [worked example](../examples/loan-prequalification-chatbot/06-pre-deployment-checklist.md) for what "actually tested" documentation looks like.)
- [ ] Sample any [Bias & Fairness Tests](../templates/bias-fairness-testing-guide.md) on file: do the documented metrics match what the methodology called for, and were disparities followed up on or silently left unresolved?

## 3. Controls — do the safety mechanisms actually work?

- [ ] For at least one live High-risk system: attempt to trace its rollback/kill-switch procedure — does it work as documented, or is it theoretical?
- [ ] For at least one customer- or employee-facing AI system: verify the human review/escalation step actually exists in the live product, not just in the Risk Assessment's description of it.
- [ ] Check the [Incident Response Runbook](../templates/incident-response-runbook.md) log (if incidents occurred this period): were severity classifications, notification timeframes, and close-out documentation actually followed?

## 4. Governance structure — are the roles real?

- [ ] Confirm every role in [Roles & RACI](roles-and-raci.md) has a current, named person — not a stale name from a reorg ago
- [ ] Confirm the [Training & Awareness Plan](../templates/training-and-awareness-plan.md) cadence was actually followed (training delivered, completion tracked) — not just that a plan exists
- [ ] Confirm [Board Reporting](../templates/board-reporting-template.md) actually happened on schedule, and that leadership asks/received answered — not a report sent into silence

## 5. Findings and follow-up

| Finding | Severity | Owner | Remediation | Target date |
|---|---|---|---|---|
| | | | | |

**Severity guide:** Critical (a control believed to exist doesn't) · High (a required document is missing or badly out of date for a High-risk system) · Medium (process followed inconsistently) · Low (documentation/clarity gap, no real exposure)

## 6. Sign-off

| Field | Value |
|---|---|
| Audit conducted by (independent of Governance Lead) | |
| Period covered | |
| Date | |
| Overall assessment | [ ] Program operating as designed [ ] Operating with gaps (see findings) [ ] Not operating as designed |
| Reported to leadership | Y/N — feed into next [Board Reporting Template](../templates/board-reporting-template.md) |

---
*Related: [Maturity Model](maturity-model.md) · [Roles & RACI](roles-and-raci.md) · [ISO/IEC 42001 Crosswalk](standards/iso-42001-crosswalk.md)*
