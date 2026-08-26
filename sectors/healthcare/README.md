# Sector Pack: Healthcare

For providers, payers, health tech vendors, and any organization deploying AI that touches patient data or clinical/coverage decisions. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md).

## Why healthcare needs its own overlay

Healthcare AI splits into two very different risk profiles: **clinical AI** (diagnosis support, triage, treatment recommendations — where errors can directly harm patients and may trigger medical device regulation) and **administrative/coverage AI** (prior authorization, claims, scheduling — where errors delay or deny care and trigger different oversight). Know which one you're building before applying this pack.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **HIPAA** | Governs protected health information (PHI) — a Business Associate Agreement (BAA) is required with any AI vendor that touches PHI. Standard consumer AI tools (ChatGPT free tier, etc.) generally do **not** have a BAA and must not receive PHI. |
| **FDA — Software as a Medical Device (SaMD) / AI-ML guidance** | If the AI performs or supports a diagnostic, treatment, or clinical decision-making function, it may qualify as a medical device requiring FDA clearance/approval. Confirm classification early — this determines your entire validation and change-control process. |
| **21st Century Cures Act — Information Blocking** | May restrict certain kinds of AI-driven access limitations on patient health information. |
| **State AI-in-healthcare laws** | A growing number of states require disclosure when AI is used in clinical communications or coverage decisions — check state-specific rules. |
| **CMS guidance (payers)** | For AI used in coverage/utilization management determinations (notably prior authorization), CMS has issued specific expectations about human review and clinical criteria basis. |
| **Nondiscrimination (Section 1557 of the ACA)** | Prohibits discrimination in health programs, extending to algorithmic tools used in care decisions. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Clinical validity** — has the tool been validated against clinical outcomes, not just technical accuracy metrics, for the specific population it will be used on?
- [ ] **Medical device classification** — has someone with regulatory expertise confirmed whether this qualifies as SaMD, and if so, what clearance pathway applies?
- [ ] **PHI exposure / BAA coverage** — does every vendor touching PHI in this system have a signed BAA? (Cross-reference [Vendor Due Diligence](../../templates/vendor-due-diligence.md).)
- [ ] **Clinical overreliance** — is there a real risk that clinicians defer to AI output under time pressure without exercising independent judgment? (Ties to "automation bias" in the [glossary](../../docs/glossary.md).)
- [ ] **Population generalizability** — was the model trained/validated on a population that reflects who it will actually be used on (age, ethnicity, comorbidities, care setting)?
- [ ] **Coverage-decision fairness** — for payer use cases, does the tool deny or delay care disproportionately for any group, and is there a fast human appeal path?

## Additional Pre-Deployment Checklist items

- [ ] BAA confirmed in place with every vendor in the data path, before any PHI is transmitted
- [ ] Medical device classification determination documented (even if the conclusion is "not a device")
- [ ] Clinical validation study or equivalent evidence reviewed by a qualified clinician, not just the technical team
- [ ] Human clinician review point clearly defined and tested for any diagnostic/treatment-adjacent output
- [ ] For coverage/UM tools: appeal and human review path tested end-to-end, not just documented

## Sector-specific terms

- **PHI (Protected Health Information)** — individually identifiable health information covered by HIPAA; broader than general "sensitive data" in the core [glossary](../../docs/glossary.md).
- **Clinical decision support (CDS)** — software that provides clinicians with recommendations at the point of care; specific FDA carve-outs and expectations apply depending on how much autonomy it has.
- **Prior authorization / utilization management (UM)** — payer processes determining whether a treatment is covered; increasingly AI-assisted and a current regulatory/legislative focus area.

## How this maps to the core framework

| Core artifact | Healthcare-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3; treat any clinical-decision system as High risk minimum |
| [Model Card](../../templates/model-card.md) | Add fields for clinical validation study reference and population(s) validated on |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Add explicit BAA confirmation as a go/no-go gate, not just a data-handling question |
| [Incident Response Runbook](../../templates/incident-response-runbook.md) | Add patient safety event escalation and, where applicable, FDA adverse event reporting triggers |

See also: [core Risk Assessment](../../templates/ai-risk-assessment.md) · [NIST AI RMF Crosswalk](../../docs/standards/nist-ai-rmf-crosswalk.md) · [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md)
