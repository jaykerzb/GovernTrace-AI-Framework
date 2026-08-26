# AI Risk Assessment — LoanAssist (Completed Example)

*Filled-out version of [templates/ai-risk-assessment.md](../../templates/ai-risk-assessment.md), with [Banking sector pack](../../sectors/banking-financial-services/README.md) additions applied. See the [scenario overview](README.md) for context.*

## System overview

| Field | Value |
|---|---|
| System/use case name | LoanAssist pre-qualification chatbot |
| Owner (accountable individual) | Priya Nandakumar, Digital Banking Product |
| Model/vendor | Cortex AI (chat interface) + Riverbend proprietary scoring layer |
| Date | 2026-02-20 |
| Linked intake form | [01-intake-form.md](01-intake-form.md) |

## 1. Map — context and purpose

- **Problem/purpose:** Reduce drop-off in the loan application funnel by giving applicants an early, informal read on eligibility before committing to a full application.
- **Affected parties:** Prospective loan applicants (the public); loan officers who receive applications flagged as "pre-qualified"; the bank's fair-lending compliance posture.
- **Scope of autonomy:** ☒ Human-in-the-loop for the *final* credit decision (underwriter reviews the full application) — but the *pre-qualification score itself* is shown directly to the applicant with no human review before that.

## 2. Risk classification

| Dimension | Rating | Notes |
|---|---|---|
| Data sensitivity | High | Self-reported income, credit range, loan purpose — confidential financial data |
| Impact on individuals if wrong | High | A falsely negative score could discourage a creditworthy applicant from ever applying — a real economic harm that leaves no formal record to contest |
| Autonomy | Medium-High | Pre-qualification score is shown with no human check; final decision is human-reviewed |
| Reversibility | Medium | An applicant discouraged from applying may simply never come back — the harm isn't "reversible" in practice even though no formal denial occurred |
| Scale | High | Public-facing, expected to process thousands of applicant interactions monthly |
| Explainability | Medium | Scoring layer is a Riverbend-built gradient-boosted model (not deep learning) with feature importances available — this materially helps vs. relying on the LLM itself for scoring |

**Overall risk tier: ☒ High**

*Rationale: even though the LLM doesn't make the credit decision, the pre-qualification score functions as a de facto adverse action for anyone it discourages — with no human review, no formal adverse action notice, and real drop-off consequences. Per the [Banking sector pack](../../sectors/banking-financial-services/README.md), this is treated as High risk, not Medium, precisely because the "advisory only" framing was not yet backed by a tested control.*

## 3. Measure — known failure modes

- [x] **Hallucination / factual error** — the chatbot's conversational layer (LLM) could state incorrect loan terms, rates, or eligibility criteria. *Mitigation: LLM is constrained to a retrieval-augmented answer set for product-fact questions; free-form eligibility claims are disabled — only the separate scoring layer produces the pre-qualification number.*
- [x] **Bias / disparate impact** — the scoring layer is trained on historical loan performance data, which can encode past discriminatory patterns. *Mitigation: see [Bias & Fairness Test](05-bias-fairness-test.md).*
- [x] **Prompt injection** — a user could attempt to manipulate the chatbot into misrepresenting eligibility or extracting system instructions. *Mitigation: input sanitization, system prompt isolated from user-modifiable context; see [OWASP AI Mapping](../../docs/standards/owasp-ai-mapping.md).*
- [ ] **Data leakage** — not applicable in the same way; Cortex AI is contracted with a no-training-on-customer-data clause (see [Vendor Due Diligence](03-vendor-due-diligence.md)).
- [x] **Model/output drift over time** — the scoring layer's accuracy could degrade as economic conditions shift from the training period. *Mitigation: quarterly re-validation, tied to Riverbend's existing SR 11-7 model risk program.*
- [x] **Over-reliance** — applicants may treat an informal score as a guarantee. *Mitigation: explicit, prominent disclaimer language; see [Pre-Deployment Checklist](06-pre-deployment-checklist.md).*
- [ ] **Insecure output handling** — not applicable; output is display-only text/score, not executed.

## 4. Manage — controls and ownership

| Control | In place? | Owner |
|---|---|---|
| Human review before output is used/sent | Partial — added as a new control: any applicant shown a *negative* pre-qualification score is offered a one-click path to speak with a human loan officer before leaving the flow | Priya Nandakumar |
| Logging/audit trail of inputs and outputs | Yes — every chatbot interaction and score logged with timestamp | IT/Data Platform |
| Escalation path for disputed/harmful outputs | Yes — routes to [Incident Response Runbook](../../templates/incident-response-runbook.md) | David Ochoa |
| Periodic re-evaluation schedule | Quarterly, tied to SR 11-7 model validation cadence | Model Risk team |
| Rollback/kill-switch if system misbehaves | Yes — scoring layer can be disabled independently of the chat interface, reverting to "apply for a full review" only | Digital Banking Product |
| User-facing disclosure that AI is involved | Yes — chatbot identifies itself as AI-assisted; score is labeled "informal estimate, not a credit decision" | Legal/Compliance |

**Banking-specific additions (per [sector pack](../../sectors/banking-financial-services/README.md)):**
- [x] Adverse action explainability — *addressed by design: because the score never independently denies anything (it only routes to human review either way), no formal adverse action notice is legally triggered — but Legal confirmed this only holds because the human-escalation-on-negative-score control above is real, not cosmetic.*
- [x] Fair lending / disparate impact tested — see [Bias & Fairness Test](05-bias-fairness-test.md)
- [x] Model stability/drift monitored — quarterly re-validation above
- [x] Proxy discrimination reviewed — zip code and employer name excluded from scoring features specifically because of proxy risk identified during fairness testing
- [x] Third-party model risk — Cortex AI's conversational layer brought into Riverbend's existing SR 11-7 program scope; see [Vendor Due Diligence](03-vendor-due-diligence.md)

## 5. Sign-off

| Role | Name | Approved? | Date |
|---|---|---|---|
| System owner | Priya Nandakumar | Yes, conditioned on human-escalation control being live before launch | 2026-03-05 |
| Governance reviewer | David Ochoa | Yes | 2026-03-06 |
| Executive sponsor | Angela Fitch, Chief Digital Officer | Yes | 2026-03-08 |

**Re-review date:** 2026-06-08 (quarterly, per High-risk cadence)

---
**Next:** [Vendor Due Diligence](03-vendor-due-diligence.md)
