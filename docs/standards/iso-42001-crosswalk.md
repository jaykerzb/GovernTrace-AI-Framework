# ISO/IEC 42001 Crosswalk

[ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html) is the first certifiable international standard for an AI Management System (AIMS) — structured like ISO 27001 (same Annex SL high-level structure), so if you're already ISO 27001-certified, this will feel familiar.

**This repo does not implement or certify ISO/IEC 42001.** The standard itself is paid/licensed and this framework doesn't reproduce its text. What follows is a crosswalk so you can see how far this repo gets you toward a real AIMS, and what's still missing if certification is a goal.

## Clause-by-clause

| ISO 42001 Clause | Requirement (summarized) | Mapped artifact | Status |
|---|---|---|---|
| **4. Context of the organization** | Determine internal/external issues, interested parties, and AIMS scope | [Acceptable Use Policy](../../policies/acceptable-use-policy.md) intro/scope section | 🟡 |
| **5. Leadership** | Top management commitment; AI policy established; roles/responsibilities assigned | [Roles & RACI](../roles-and-raci.md); Acceptable Use Policy owner field | ✅ |
| **6. Planning** | Risk and opportunity assessment; AI objectives set; change planning | [AI Risk Assessment](../../templates/ai-risk-assessment.md) | ✅ |
| **7. Support** | Resources, competence, awareness, communication, documented information control | [Training & Awareness Plan](../../templates/training-and-awareness-plan.md); [AI Tool Inventory](../../templates/ai-tool-inventory.md) (resources) | ✅ |
| **8. Operation** | Operational planning and control; AI system impact assessment; third-party/supplier management | [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md); [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | ✅ |
| **9. Performance evaluation** | Monitoring, measurement, internal audit, management review | [Internal Audit Checklist](../internal-audit-checklist.md); [Board Reporting Template](../../templates/board-reporting-template.md) (management review); [Maturity Model](../maturity-model.md) | ✅ |
| **10. Improvement** | Nonconformity and corrective action; continual improvement | Acceptable Use Policy §7 incident reporting | 🟡 |

## Annex A controls (selected, high-relevance)

ISO 42001's Annex A has 38 controls across 10 themes. The ones most directly covered by this repo:

| Annex A theme | Mapped artifact |
|---|---|
| A.4 — Resources for AI systems (documented data, tooling, third-party components) | [Vendor Due Diligence](../../templates/vendor-due-diligence.md); [AI Tool Inventory](../../templates/ai-tool-inventory.md) |
| A.5 — Impact assessment | [AI Risk Assessment](../../templates/ai-risk-assessment.md) |
| A.6 — AI system lifecycle (design, verification, deployment, operation, retirement) | [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) |
| A.7 — Data for AI systems | Acceptable Use Policy §3 (data rules); Risk Assessment data sensitivity dimension |
| A.9 — Use of AI systems (responsible use, transparency to affected parties) | Acceptable Use Policy §5–6 |
| A.10 — Third-party and customer relationships | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) |

Themes **not** covered here and worth building out if certification is the goal: A.1–A.3 (policy/objectives documentation formality), A.8 (system documentation depth), the remaining supplier/incident controls that require formal audit trails beyond a markdown template.

## Should you actually pursue certification?

Certification makes sense if customers or regulators are asking for it, or if AI is core to your product and a competitive differentiator. For most small/mid orgs, reaching a solid, evidenced **Level 2–3** on the [Maturity Model](../maturity-model.md) gets you the actual risk reduction; certification is a separate, resource-intensive decision layered on top — budget for an external auditor. The [Internal Audit Checklist](../internal-audit-checklist.md) gives you a starting internal-audit function, but a certification body will still require its own formal audit.

See also: [NIST AI RMF Crosswalk](nist-ai-rmf-crosswalk.md) · [EU AI Act Risk Tiers](eu-ai-act-risk-tiers.md) · [GDPR Mapping](gdpr-mapping.md)
