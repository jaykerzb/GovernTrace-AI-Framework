# AI Risk Assessment

Complete this for any AI use case flagged during [intake](ai-use-case-intake-form.md) as higher-risk. Structured around NIST AI RMF's four functions (Govern, Map, Measure, Manage) — see the [full mapping](../docs/nist-ai-rmf-mapping.md) for how this template lines up.

## System overview

| Field | Value |
|---|---|
| System/use case name | |
| Owner (accountable individual) | |
| Model/vendor | |
| Date | |
| Linked intake form | |

## 1. Map — context and purpose

- What problem does this system solve, and for whom?
- Who are the affected parties (users, customers, employees, third parties)?
- What is the system's scope of autonomy? [ ] Fully automated, no review [ ] Human-in-the-loop [ ] Human-on-the-loop (can override) [ ] Advisory only

## 2. Risk classification

Rate each dimension **Low / Medium / High**, then take the highest rating as the overall tier.

| Dimension | Rating | Notes |
|---|---|---|
| Data sensitivity (what data does it touch) | | |
| Impact on individuals if wrong (physical, financial, legal, reputational, access to opportunity) | | |
| Autonomy (how much human oversight before action) | | |
| Reversibility (can a bad output be caught/undone before harm) | | |
| Scale (how many people/records affected) | | |
| Explainability (can you explain a given output if challenged) | | |

**Overall risk tier:** [ ] Low [ ] Medium [ ] High [ ] Unacceptable

> Unacceptable-risk use cases (e.g. covert manipulation, social scoring, real-time biometric surveillance of the public) should be rejected outright, in line with EU AI Act prohibited-practice categories — even if you're not otherwise EU-regulated, treating these as hard no's is good practice.

## 3. Measure — known failure modes

Check any that apply and describe mitigation. Cross-reference [OWASP AI security mapping](../docs/owasp-ai-mapping.md) for the security-specific items.

- [ ] **Hallucination / factual error** — mitigation:
- [ ] **Bias / disparate impact** across protected groups — mitigation:
- [ ] **Prompt injection** (untrusted input steering the model) — mitigation:
- [ ] **Data leakage** (sensitive data exposed via output or training) — mitigation:
- [ ] **Model/output drift over time** — mitigation:
- [ ] **Over-reliance** (humans rubber-stamping AI output) — mitigation:
- [ ] **Insecure output handling** (AI output executed/rendered without validation) — mitigation:

## 4. Manage — controls and ownership

| Control | In place? | Owner |
|---|---|---|
| Human review before output is used/sent | | |
| Logging/audit trail of inputs and outputs | | |
| Escalation path for disputed/harmful outputs | | |
| Periodic re-evaluation schedule | | |
| Rollback/kill-switch if system misbehaves | | |
| User-facing disclosure that AI is involved | | |

## 5. Sign-off

| Role | Name | Approved? | Date |
|---|---|---|---|
| System owner | | | |
| Governance reviewer | | | |
| (High risk only) Executive sponsor | | | |

**Re-review date:** [set based on risk tier — e.g. Low: annually, Medium: every 6 months, High: quarterly]

---
*Next: [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md) before go-live.*
