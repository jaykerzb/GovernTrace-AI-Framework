# Roles & RACI

Most organizations adopting this framework won't have a dedicated "AI Governance" team. The point of this page is to assign the responsibilities to *existing* roles rather than invent new headcount.

## Minimum viable roles

| Role | Typical owner in a small/mid org | Responsibility |
|---|---|---|
| **AI Governance Lead** | Head of IT, Legal/Compliance lead, or a designated senior individual | Owns this framework, reviews intake forms, keeps the [tool inventory](../templates/ai-tool-inventory.md) current, chairs periodic review, runs the [Training & Awareness Plan](../templates/training-and-awareness-plan.md) |
| **System/Use-Case Owner** | Whoever requested or built the AI feature | Completes the Risk Assessment, is accountable for the system's ongoing behavior |
| **Security Reviewer** | IT/Security lead (or outsourced security contact) | Reviews Medium/High-risk systems for the security-specific items (see [OWASP mapping](standards/owasp-ai-mapping.md)) |
| **Executive Sponsor** | Relevant department head or exec | Signs off on High-risk deployments; owns the "unacceptable risk = no" call |

One person can hold multiple roles in a small org — the point is that each responsibility has a named owner, not that you need four people.

## RACI for the core workflow

R = Responsible, A = Accountable, C = Consulted, I = Informed

| Activity | System Owner | Governance Lead | Security Reviewer | Exec Sponsor |
|---|---|---|---|---|
| Submit Use-Case Intake | R/A | I | | |
| Triage intake (low vs. full assessment) | C | R/A | | |
| Complete Risk Assessment | R | A | C (if flagged) | I |
| Vendor Due Diligence | R | A | C | |
| Security review (Med/High risk) | C | I | R/A | |
| Pre-deployment sign-off — low risk | R/A | I | | |
| Pre-deployment sign-off — high risk | R | C | C | A |
| Periodic re-review | R | A | C (if applicable) | I |
| Incident response ([runbook](../templates/incident-response-runbook.md)) | R | A | R | I |
| Board/leadership reporting ([template](../templates/board-reporting-template.md)) | I | R/A | C | I |
| Staff training ([plan](../templates/training-and-awareness-plan.md)) | I | R/A | C (for governance-role training) | I |
| Internal audit ([checklist](internal-audit-checklist.md)) | C | I (subject of the audit) | C | I |

Note the internal audit row: the Governance Lead is *Informed*, not *Accountable*, because they're the one being audited — see the independence note in the [Internal Audit Checklist](internal-audit-checklist.md).

## Cadence

- **Tool inventory review:** quarterly — prune unused tools, confirm nothing is running unapproved. See [AI Tool Inventory](../templates/ai-tool-inventory.md).
- **Policy review:** annually, or immediately after a material AI regulation change or major incident.
- **Risk re-review:** per the schedule set in each system's [Risk Assessment](../templates/ai-risk-assessment.md) (Low: annual, Medium: 6-monthly, High: quarterly).
- **Board reporting:** quarterly, using the [Board Reporting Template](../templates/board-reporting-template.md).
- **Training:** onboarding + annual refresh minimum, per the [Training & Awareness Plan](../templates/training-and-awareness-plan.md).
- **Internal audit:** annually, or before any external certification effort — see the [Internal Audit Checklist](internal-audit-checklist.md).

For where this fits in your maturity journey, see the [Maturity Model](maturity-model.md).
