# NIST AI RMF Crosswalk

A subcategory-level mapping from [NIST AI RMF 1.0](https://www.nist.gov/itl/ai-risk-management-framework) (and its companion [Playbook](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook)) to the concrete artifacts in this repo. This is the detailed version — for the one-page summary, see the [README](../../README.md#quick-start).

Status legend: **✅ Covered** — an artifact directly addresses this · **🟡 Partial** — touched on, needs org-specific work · **⬜ Gap** — not addressed here, your responsibility to build

## GOVERN — policies, accountability, and culture

| Subcategory | What NIST asks for | Mapped artifact | Status |
|---|---|---|---|
| Govern 1.1–1.4 | Legal/regulatory requirements understood; risk tolerance and org policies documented and communicated | [Acceptable Use Policy](../../policies/acceptable-use-policy.md) | ✅ |
| Govern 1.5 | Ongoing monitoring and periodic review of the risk management process itself | [Maturity Model](../maturity-model.md) cadence section | 🟡 |
| Govern 1.6–1.7 | Inventory of AI systems maintained; processes for third-party/decommissioned systems | Tool inventory (see [Vendor Due Diligence](../../templates/vendor-due-diligence.md) footer) | 🟡 — inventory format is your choice; not templated here |
| Govern 2.1–2.3 | Roles, responsibilities, and reporting structure for AI risk defined; org has capacity to carry them out | [Roles & RACI](../roles-and-raci.md) | ✅ |
| Govern 3.1–3.2 | Workforce diversity/training so teams can identify AI risks; decision-makers understand limitations | Not templated — recommend using [OWASP AI Mapping](owasp-ai-mapping.md) as team training material | ⬜ |
| Govern 4.1–4.3 | Organizational culture prioritizes risk management; risks documented and used to inform decisions | [AI Risk Assessment](../../templates/ai-risk-assessment.md) §5 sign-off | ✅ |
| Govern 5.1–5.2 | Mechanisms for external/internal stakeholder feedback | [AI Use-Case Intake Form](../../templates/ai-use-case-intake-form.md); Acceptable Use Policy §7 incident reporting | 🟡 |
| Govern 6.1–6.2 | Policies for third-party risks (vendors, open-source models, data) | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | ✅ |

## MAP — context and framing

| Subcategory | What NIST asks for | Mapped artifact | Status |
|---|---|---|---|
| Map 1.1–1.6 | Business context, intended purpose, deployment context documented | [AI Risk Assessment](../../templates/ai-risk-assessment.md) §1 | ✅ |
| Map 2.1–2.3 | System categorized by type/method; scientific integrity and capability limits characterized | Risk Assessment §1 "scope of autonomy"; Vendor Due Diligence "model transparency" | 🟡 |
| Map 3.1–3.5 | Benefits, costs, and impacted individuals/groups identified, including third parties | Risk Assessment §1 "affected parties"; §2 risk classification | ✅ |
| Map 4.1–4.2 | Risks/benefits mapped for third-party software, data, models | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | ✅ |
| Map 5.1–5.2 | Likelihood and magnitude of impacts characterized; risks prioritized | Risk Assessment §2 risk classification table | ✅ |

## MEASURE — analysis and testing

| Subcategory | What NIST asks for | Mapped artifact | Status |
|---|---|---|---|
| Measure 1.1–1.3 | Approaches for measuring risk identified and applied; metrics documented | Risk Assessment §3 (failure modes); [OWASP AI Mapping](owasp-ai-mapping.md) | 🟡 — this repo gives you the checklist, not the test suite |
| Measure 2.1–2.3 | Test sets representative of deployment context; evaluated for validity/reliability | Not templated — depends heavily on your system; see Pre-Deployment Checklist "bias/fairness check" as a minimum bar | ⬜ |
| Measure 2.4–2.6 | Fairness and bias evaluated across relevant groups; environmental/sustainability impact considered where material | [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — Medium/High track | 🟡 |
| Measure 2.7–2.9 | Security and resilience evaluated; privacy risk evaluated | [OWASP AI Mapping](owasp-ai-mapping.md); Vendor Due Diligence "security" section | ✅ |
| Measure 2.10–2.13 | Explainability/interpretability evaluated; human oversight effectiveness assessed | Risk Assessment §2 "explainability"; §4 "human review before output used" | 🟡 |
| Measure 3.1–3.3 | Mechanisms for tracking identified risks over time; feedback incorporated | Risk Assessment re-review cadence; [Maturity Model](../maturity-model.md) Level 3 | 🟡 |
| Measure 4.1–4.3 | Measurement approaches documented and reviewed for validity | Not templated | ⬜ |

## MANAGE — response and continuous improvement

| Subcategory | What NIST asks for | Mapped artifact | Status |
|---|---|---|---|
| Manage 1.1–1.4 | Risks prioritized and responded to (mitigate/transfer/avoid/accept) based on Map/Measure outputs | Risk Assessment §4 controls table | ✅ |
| Manage 2.1–2.4 | Mechanisms in place to sustain value and manage risk of deployed systems (monitoring, degradation response) | Pre-Deployment Checklist "post-launch" section; Risk Assessment §4 "rollback/kill-switch" | ✅ |
| Manage 3.1–3.2 | Third-party risks managed against policy | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) risk rating | ✅ |
| Manage 4.1–4.3 | Risk treatments documented and communicated; lessons learned incorporated into future assessments | Acceptable Use Policy §7 incident reporting; [Maturity Model](../maturity-model.md) Level 3 | 🟡 |

## Honest gaps

This framework gives you strong coverage of **Govern** and **Map**, decent coverage of **Manage**, and partial coverage of **Measure** — because Measure is largely about running actual technical evaluations (bias testing, adversarial robustness, statistical validity) that depend on your specific system and can't be templated as markdown. If you need full Measure coverage, plan to pair this framework with:
- A bias/fairness testing methodology suited to your system (e.g. disparate impact analysis)
- Adversarial/red-team testing for anything customer-facing or high-risk (see [OWASP AI Mapping](owasp-ai-mapping.md) as a starting checklist)
- A defined metrics dashboard tracked over time, not just point-in-time assessments

See also: [ISO/IEC 42001 Crosswalk](iso-42001-crosswalk.md) · [EU AI Act Risk Tiers](eu-ai-act-risk-tiers.md) · [OWASP AI Mapping](owasp-ai-mapping.md)
