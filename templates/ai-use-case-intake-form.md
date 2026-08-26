# AI Use Case Intake Form

Use this form to request approval for a new AI tool or AI-powered feature. Submit to [governance contact/channel]. This is the front door of the framework — nothing gets a [Risk Assessment](ai-risk-assessment.md) or goes to [Vendor Due Diligence](vendor-due-diligence.md) until it's logged here.

## 1. Requester info

| Field | Value |
|---|---|
| Name | |
| Team | |
| Date submitted | |

## 2. What is being requested

- **Tool/model name:**
- **Vendor (if third-party):**
- **Is this a new tool, or a new use case for an already-approved tool?**
- **One-sentence description of what it will do:**

## 3. Data involved

- What data will this tool see or process? (e.g., customer names, internal docs, source code, none/synthetic)
- Data classification level: [ ] Public [ ] Internal [ ] Confidential [ ] Restricted
- Will any regulated data be involved (PII, health, financial, biometric, children's data)? Y/N — if yes, specify:

## 4. Who is affected

- Internal use only, or does output reach customers/the public?
- Does this tool make or influence a decision about a person (hiring, credit, pricing, access, moderation)? Y/N

## 5. Initial risk triage

Answer yes/no — **any "yes" routes this to a full [AI Risk Assessment](ai-risk-assessment.md) before approval.**

- [ ] Processes regulated or confidential data
- [ ] Influences a decision materially affecting a person
- [ ] Customer-facing or public-facing output
- [ ] No human review step before output is used/sent
- [ ] Vendor is not already on the approved tool list

If **none** are checked, this may qualify for lightweight approval — see [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md), low-risk track.

## 6. Decision

| Field | Value |
|---|---|
| Reviewed by | |
| Date | |
| Outcome | [ ] Approved [ ] Approved with conditions [ ] Needs full risk assessment [ ] Rejected |
| Conditions / notes | |
| Added to tool inventory? | Y/N |

---
*Next steps: high-risk items → [AI Risk Assessment](ai-risk-assessment.md). Third-party tools → [Vendor Due Diligence](vendor-due-diligence.md). All approved tools ship with a completed [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md).*
