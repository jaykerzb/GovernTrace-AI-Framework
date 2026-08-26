# Roles & RACI

Most organizations adopting this framework won't have a dedicated "AI Governance" team. The point of this page is to assign the responsibilities to *existing* roles rather than invent new headcount.

## Minimum viable roles

| Role | Typical owner in a small/mid org | Responsibility |
|---|---|---|
| **AI Governance Lead** | Head of IT, Legal/Compliance lead, or a designated senior individual | Owns this framework, reviews intake forms, keeps the tool inventory current, chairs periodic review |
| **System/Use-Case Owner** | Whoever requested or built the AI feature | Completes the Risk Assessment, is accountable for the system's ongoing behavior |
| **Security Reviewer** | IT/Security lead (or outsourced security contact) | Reviews Medium/High-risk systems for the security-specific items (see [OWASP mapping](owasp-ai-mapping.md)) |
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
| Incident response | R | A | R | I |

## Cadence

- **Tool inventory review:** quarterly — prune unused tools, confirm nothing is running unapproved.
- **Policy review:** annually, or immediately after a material AI regulation change or major incident.
- **Risk re-review:** per the schedule set in each system's [Risk Assessment](../templates/ai-risk-assessment.md) (Low: annual, Medium: 6-monthly, High: quarterly).

For where this fits in your maturity journey, see the [Maturity Model](maturity-model.md).
