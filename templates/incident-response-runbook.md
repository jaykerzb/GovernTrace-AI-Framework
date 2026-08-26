# AI Incident Response Runbook

A runbook for handling an [AI incident](../docs/glossary.md#core-definitions) — any event where an AI system produces harmful, biased, non-compliant, or unexpectedly damaging output, or is used outside its approved scope. Pair with your organization's general security incident response process if one exists; this covers what's specific to AI.

## 1. Recognize and report

Anyone who suspects an AI incident should report it immediately to [contact/channel] — do not wait to confirm it's "real." Common triggers:

- A user reports harmful, offensive, or clearly wrong AI output
- Sensitive/regulated data appears to have been entered into or leaked by an AI tool
- An AI-assisted decision is challenged as biased or incorrect (e.g., in hiring, lending, moderation)
- A model behaves in an unexpected or unsafe way (excessive agency, unauthorized actions)
- A vendor discloses a security issue or model behavior change affecting a tool you use

This maps to the reporting obligation in [Acceptable Use Policy §7](../policies/acceptable-use-policy.md).

## 2. Triage

| Question | Answer |
|---|---|
| Which system/model is involved? (link [Model Card](model-card.md) if available) | |
| What happened, in one sentence? | |
| Is this ongoing/repeatable, or a one-off? | |
| Who is potentially affected, and how many people? | |
| Is regulated data involved (PII, financial, health)? | |

**Severity:**
- [ ] **Sev 1 — Critical:** Active harm, regulated data exposed at scale, or a material decision affecting someone was made on bad output with no review
- [ ] **Sev 2 — High:** Contained harm or a single-person impact from a flawed decision; data exposure limited in scope
- [ ] **Sev 3 — Moderate:** Bad output caught before causing real-world impact; process/policy gap identified
- [ ] **Sev 4 — Low:** Near-miss, or output quality issue with no downstream consequence

## 3. Contain

- [ ] If the system is actively causing harm: pause/disable it (reference the rollback plan in the [Risk Assessment](ai-risk-assessment.md) §4 or [Model Card](model-card.md))
- [ ] If data was exposed: follow your standard data breach process; notify security/legal per Sev 1/2
- [ ] Preserve evidence — logs, the specific input/output pair, timestamps — before anything is cleaned up or a vendor's context resets

## 4. Notify

| Severity | Who to notify | Timeframe |
|---|---|---|
| Sev 1 | Governance Lead, Security, Legal, Exec Sponsor | Immediately |
| Sev 2 | Governance Lead, Security | Within [X hours] |
| Sev 3 | Governance Lead | Within [1 business day] |
| Sev 4 | Log only, review at next governance cadence | N/A |

If any affected individual has a legal right to notification (e.g., under applicable data breach or AI-specific disclosure law), Legal makes that determination and drives that process — don't assume it's covered by this runbook.

## 5. Investigate root cause

- Was this a known limitation that should have been caught in the [Risk Assessment](ai-risk-assessment.md) or [Model Card](model-card.md)?
- Was a required human review step skipped, bypassed, or ineffective?
- Was this a vendor-side model change/degradation outside your control?
- Was this a novel failure mode not previously documented?

## 6. Remediate

- [ ] Immediate fix applied (config change, prompt/guardrail update, human process fix)
- [ ] Linked Risk Assessment updated to reflect the new known failure mode
- [ ] If a control gap caused this, the relevant template ([Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md), [Acceptable Use Policy](../policies/acceptable-use-policy.md)) updated
- [ ] Affected individuals remediated where applicable (correction, apology, appeal process, compensation per policy/legal guidance)

## 7. Close out

| Field | Value |
|---|---|
| Incident owner | |
| Date opened / closed | |
| Final severity | |
| Root cause summary | |
| Follow-up actions and owners | |
| Reported to leadership? | Y/N |

Log closed incidents in your tool inventory or a simple incident log (date, system, severity, root cause, resolution) — patterns across incidents are early warning signs for the [Maturity Model](../docs/maturity-model.md) review.

---
*Related: [AI Risk Assessment](ai-risk-assessment.md) · [Model Card](model-card.md) · [Acceptable Use Policy](../policies/acceptable-use-policy.md) · [Glossary](../docs/glossary.md)*
