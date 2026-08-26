# AI Governance Maturity Model

A rough self-assessment to figure out where your org is today and what "next" looks like. Don't aim for Level 4 on day one — most organizations get real risk reduction from reaching Level 2.

## Level 0 — Ungoverned

- No visibility into what AI tools employees are using
- No policy exists; AI use is ad hoc and undocumented
- **Risk:** data leakage and unmanaged liability with zero warning signs

## Level 1 — Aware

- An [Acceptable Use Policy](../policies/acceptable-use-policy.md) exists and has been communicated
- Leadership knows AI is being used somewhere, but there's no formal intake or inventory
- **Next step:** stand up the [Use-Case Intake Form](../templates/ai-use-case-intake-form.md) and start an [AI Tool Inventory](../templates/ai-tool-inventory.md)

## Level 2 — Managed (this framework's default target)

- All new AI tools/use cases go through [intake](../templates/ai-use-case-intake-form.md)
- Higher-risk use cases get a [Risk Assessment](../templates/ai-risk-assessment.md) before launch
- Third-party tools go through [vendor due diligence](../templates/vendor-due-diligence.md)
- A named [Governance Lead](roles-and-raci.md) exists and the [tool inventory](../templates/ai-tool-inventory.md) is kept current
- Basic [training](../templates/training-and-awareness-plan.md) has been delivered — at minimum, everyone knows the policy exists and where to report a concern
- **Next step:** start measuring — track how many assessments are completed on time, how many incidents occur, whether re-reviews actually happen

## Level 3 — Measured

- Re-review cadences are tracked and enforced, not just documented
- Bias/fairness and security testing (see [OWASP mapping](standards/owasp-ai-mapping.md)) are routine for relevant systems, with results logged
- Incidents are tracked and feed back into policy/process updates
- The [Internal Audit Checklist](internal-audit-checklist.md) has been run at least once, independent of the Governance Lead, and its findings acted on
- **Next step:** formalize metrics into leadership reporting; consider whether a certifiable standard (ISO/IEC 42001) is worth pursuing

## Level 4 — Optimized

- AI governance is integrated into standard change-management and procurement processes (not a side process)
- Metrics on AI risk and governance effectiveness are reported to leadership/board on a regular cadence
- The org can demonstrate compliance readiness for relevant regulation (e.g. EU AI Act risk tiers, sector-specific rules) on demand

## Using this model

Pick your current level honestly, then use the "next step" for that level as your actual roadmap — don't try to build everything at once. Most of what's in this repo targets getting a small/mid org cleanly to **Level 2**.
