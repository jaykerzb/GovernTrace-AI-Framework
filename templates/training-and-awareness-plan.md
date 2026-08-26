# AI Training & Awareness Plan

Closes a gap flagged in the [NIST AI RMF Crosswalk](../docs/standards/nist-ai-rmf-crosswalk.md) (Govern 3.1–3.2: "workforce competence so teams can identify AI risks") and the [ISO/IEC 42001 Crosswalk](../docs/standards/iso-42001-crosswalk.md) (Clause 7: competence and awareness) — both previously marked as gaps this framework didn't address. A governance program that only exists as documents nobody reads isn't a governance program.

## Audience tiers

Not everyone needs the same training. Use three tiers:

| Tier | Who | What they need |
|---|---|---|
| **All staff** | Everyone with access to any AI tool | [Acceptable Use Policy](../policies/acceptable-use-policy.md) basics: what's approved, what data rules apply, how to report a concern |
| **System owners/builders** | Anyone requesting, building, or managing an AI system | Full framework: [intake](ai-use-case-intake-form.md), [Risk Assessment](ai-risk-assessment.md), [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md) — how to actually complete these, not just that they exist |
| **Governance/review roles** | [Governance Lead, Security Reviewer, Exec Sponsor](../docs/roles-and-raci.md) | Deeper training: reading a [Model Card](model-card.md) critically, interpreting [bias/fairness test](bias-fairness-testing-guide.md) results, running the [Incident Response Runbook](incident-response-runbook.md) |

## Minimum viable training plan

- [ ] **Onboarding**: AI Acceptable Use Policy included in standard new-hire onboarding, with a signed acknowledgment
- [ ] **Annual refresh**: All-staff refresher on policy changes, recent incidents (anonymized/aggregated), and any new approved/prohibited tools
- [ ] **Just-in-time training**: System owners get a walkthrough of the intake → risk assessment → deployment flow *the first time they use it*, not buried in a handbook they read once
- [ ] **Governance role training**: Anyone taking on a Governance Lead, Security Reviewer, or Exec Sponsor role gets a dedicated session on their RACI responsibilities and how to actually evaluate a Risk Assessment, not just approve it
- [ ] **Incident drill**: At least annually, walk a governance group through a simulated [AI incident](../docs/glossary.md#core-definitions) using the [Incident Response Runbook](incident-response-runbook.md) — a runbook nobody has practiced is a runbook that fails under pressure

## Suggested content outline (all-staff session, ~20-30 min)

1. What counts as "AI" here — quick pass through [AI system types](../docs/glossary.md#types-of-ai-systems), especially the point that not everything marketed as "AI" needs special handling, and not everything that *does* need it is obviously AI
2. What's approved vs. prohibited — live walk of the current [AI Tool Inventory](ai-tool-inventory.md)
3. Data rules — what can and can't go into an AI tool (Acceptable Use Policy §3)
4. How to request a new tool — the [intake form](ai-use-case-intake-form.md), and why "just try it first" creates shadow AI risk
5. How to report a problem — the incident reporting path (Acceptable Use Policy §7)
6. Real example, if available — a sanitized past incident or near-miss is more memorable than abstract policy

## Tracking

| Field | Value |
|---|---|
| Last all-staff training delivered | |
| Completion rate | |
| Next scheduled session | |
| System-owner training completion (for active tool owners in the [inventory](ai-tool-inventory.md)) | |
| Last incident response drill | |

Feed completion metrics into the [Board Reporting Template](board-reporting-template.md) — "everyone signed the policy" and "everyone can actually use the process" are different claims, and leadership should know which one you can back up.

---
*Related: [Acceptable Use Policy](../policies/acceptable-use-policy.md) · [Roles & RACI](../docs/roles-and-raci.md) · [Incident Response Runbook](incident-response-runbook.md)*
