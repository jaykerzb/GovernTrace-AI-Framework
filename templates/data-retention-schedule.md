# AI Data Retention Schedule

Defines how long data associated with AI systems is kept and when it's deleted. Complete one entry per system/tool — required for any Medium/High risk system per the [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md), and referenced in [Vendor Due Diligence](vendor-due-diligence.md) "data handling."

## Why this exists separately from a general records retention policy

AI systems create data types a standard retention policy often misses: prompts/inputs, model outputs, logs used for monitoring, and — critically — whether a vendor retains your data for their own model training. Each needs its own retention decision.

## Per-system schedule

| Data type | What it includes | Retention period | Deletion method | Owner |
|---|---|---|---|---|
| **Prompts / inputs** | User-submitted text, files, or queries sent to the AI system | | | |
| **Model outputs** | Generated content, predictions, scores | | | |
| **Usage logs** | Who used the system, when, what was queried (for audit/monitoring) | | | |
| **Human review records** | Reviewer decisions/overrides on AI output (for accountability) | | | |
| **Training/fine-tuning data** (if applicable) | Any internal data used to fine-tune a model | | | |
| **Incident records** | Records tied to an [AI Incident](incident-response-runbook.md) | | | See note below |

> **Incident records exception:** even if operational logs are short-retention, records tied to a filed incident should generally be retained longer (e.g., matching your legal hold or dispute-resolution timelines) — set this per your legal counsel's guidance, not the default operational period.

## Vendor-side retention (fill from Vendor Due Diligence)

| Question | Answer |
|---|---|
| Does the vendor retain your data after your account/session ends? | |
| Vendor's own retention period, if disclosed | |
| Can you request vendor-side deletion, and how? | |
| Does vendor retention differ for training vs. non-training use? | |

## Regulatory inputs to consider

- **GDPR / similar regimes:** data minimization and storage-limitation principles apply to AI-processed personal data same as any other personal data — don't keep prompts/outputs containing personal data longer than the stated purpose requires.
- **Sector-specific rules** (HIPAA, financial recordkeeping, etc.): may set a *minimum* retention that overrides a shorter default — check before deleting.
- **Litigation holds:** any system under legal hold suspends normal deletion — coordinate with Legal before auto-deleting logs for a system involved in a dispute or investigation.

## Review

| Field | Value |
|---|---|
| System/tool name | |
| Schedule set by | |
| Date | |
| Next review date | |

---
*Related: [Vendor Due Diligence](vendor-due-diligence.md) · [Acceptable Use Policy](../policies/acceptable-use-policy.md) · [Incident Response Runbook](incident-response-runbook.md)*
