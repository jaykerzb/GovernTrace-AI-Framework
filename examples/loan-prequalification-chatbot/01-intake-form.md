# AI Use Case Intake Form — LoanAssist (Completed Example)

*Filled-out version of [templates/ai-use-case-intake-form.md](../../templates/ai-use-case-intake-form.md). See the [scenario overview](README.md) for context.*

## 1. Requester info

| Field | Value |
|---|---|
| Name | Priya Nandakumar |
| Team | Digital Banking Product |
| Date submitted | 2026-02-10 |

## 2. What is being requested

- **Tool/model name:** LoanAssist chatbot (built on Cortex AI's fine-tuned LLM + Riverbend proprietary scoring layer)
- **Vendor:** Cortex AI, Inc. (fictional)
- **Is this a new tool, or a new use case for an already-approved tool?** New tool, new use case
- **One-sentence description:** A website chatbot that answers loan product questions and gives applicants a preliminary, non-binding eligibility score before they submit a full loan application.

## 3. Data involved

- **What data will this tool see or process?** Applicant-provided income, employment status, self-reported credit range, loan purpose, requested amount; scoring layer also references Riverbend's historical (de-identified) loan performance data for model training.
- **Data classification level:** ☒ Confidential
- **Regulated data involved?** Yes — this is financial/credit-adjacent personal data. Not health or biometric data.

## 4. Who is affected

- **Internal use only, or output reaches customers/public?** Customer-facing (public website)
- **Does this tool make or influence a decision about a person?** Yes — it produces a preliminary eligibility score that influences whether someone proceeds to a full application.

## 5. Initial risk triage

- [x] Processes regulated or confidential data
- [x] Influences a decision materially affecting a person
- [x] Customer-facing or public-facing output
- [ ] No human review step before output is used/sent *(a human underwriter reviews the final application; the pre-qualification score itself is not independently human-reviewed before being shown to the applicant — flagged for the Risk Assessment)*
- [x] Vendor is not already on the approved tool list

**4 of 5 triggers checked → routes to full [AI Risk Assessment](02-risk-assessment.md).**

## 6. Decision

| Field | Value |
|---|---|
| Reviewed by | David Ochoa, AI Governance Lead |
| Date | 2026-02-12 |
| Outcome | ☒ Needs full risk assessment |
| Conditions / notes | Fair lending and vendor due diligence are non-negotiable before this proceeds to a Risk Assessment sign-off. Flagging early that "advisory only" framing needs to be tested, not assumed. |
| Added to tool inventory? | Pending — added at "candidate" status, full entry after Risk Assessment sign-off |

---
**Next:** [AI Risk Assessment](02-risk-assessment.md)
