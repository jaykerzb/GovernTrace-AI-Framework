# Pre-Deployment Checklist — LoanAssist (Completed Example)

*Filled-out version of [templates/pre-deployment-checklist.md](../../checklists/pre-deployment-checklist.md), Medium/High-risk track, with [Banking sector pack](../../sectors/banking-financial-services/README.md) additions. See the [scenario overview](README.md) for context.*

## Medium/High-risk track

- [x] [Intake form](01-intake-form.md) completed and approved
- [x] Tool added to the AI tool inventory (full entry, post-approval)
- [x] Users briefed on Acceptable Use Policy *(N/A for public-facing chatbot — applies to internal staff supporting/monitoring the tool)*
- [x] Basic logging of usage in place
- [x] [AI Risk Assessment](02-risk-assessment.md) completed and signed off
- [x] [Model Card](04-model-card.md) completed
- [x] [Vendor Due Diligence](03-vendor-due-diligence.md) completed (Cortex AI) — approved with conditions, both met
- [x] Data Retention Schedule set (30-day operational logs at Cortex AI; Riverbend-side logs retained 7 years per standard financial recordkeeping requirements)
- [x] Security review completed — Cortex AI SOC 2 report reviewed, Riverbend-side scoring layer reviewed by internal security team
- [x] Human review/override step tested and confirmed working — **specifically tested end-to-end**: negative-score escalation path verified in staging with 50 simulated sessions, confirmed a human loan officer contact is reliably offered
- [x] [Bias & Fairness Test](05-bias-fairness-test.md) run — disparity found and mitigated (see file)
- [x] Prompt injection / adversarial input testing done — 200 adversarial prompts tested against the chat interface; no successful extraction of system instructions or fabricated "guaranteed approval" claims
- [x] Rollback plan documented — scoring layer can be disabled independently, chatbot reverts to "apply for full review" only
- [x] Monitoring/alerting in place — score distribution drift and unusual session-volume alerts configured
- [x] User-facing disclosure drafted — "This is an informal estimate, not a credit decision" shown before and alongside every score
- [x] Incident response contact/process confirmed — tied to [Incident Response Runbook](../../templates/incident-response-runbook.md), Sev 1/2 escalation includes Fair Lending Officer for anything bias-related
- [x] Re-review date set and calendared — 2026-06-08

**Banking-specific additions:**
- [x] Model validated per SR 11-7 program, independent of the model's developer (validated by a Model Risk team member not involved in building LoanAssist-Score)
- [x] Adverse action notice process — confirmed not independently triggered given the human-escalation design, per Legal's determination in the [Risk Assessment](02-risk-assessment.md)
- [x] Fair lending review completed and documented — Fair Lending Officer sign-off obtained separately from the Governance Lead sign-off
- [x] Data used confirmed in scope under GLBA and Riverbend's data governance program
- [x] Regulatory exam readiness confirmed — Model Risk team confirmed documentation package (Risk Assessment, Model Card, Bias Test, validation results) is exam-ready

## Go-live sign-off

| Role | Name | Sign-off | Date |
|---|---|---|---|
| System owner | Priya Nandakumar | ✅ | 2026-03-10 |
| Governance reviewer | David Ochoa | ✅ | 2026-03-10 |
| Security reviewer | IT Security Lead | ✅ | 2026-03-09 |
| Fair Lending Officer | Compliance | ✅ | 2026-03-08 |
| Executive sponsor | Angela Fitch | ✅ | 2026-03-11 |

## Post-launch (first 30 days)

- [x] Spot-checked 200 real sessions against expected behavior — no material issues found
- [x] Confirmed logging/monitoring producing usable data — score distribution stable, no drift alerts triggered
- [x] Revisited risk tier — held at High; no change in usage pattern or data exposure from what was assessed

---
**Back to:** [Scenario overview](README.md)
