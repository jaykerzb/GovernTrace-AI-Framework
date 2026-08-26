# Sector Pack: Public Sector / Government

For government agencies and vendors building AI systems for government use. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md).

## Why public sector needs its own overlay

Government AI use carries obligations most private-sector deployments don't face: constitutional due process constraints on automated decisions about individuals, public records/transparency laws that can force disclosure of how a system works, and procurement rules that shape what you can even buy or build. The bar for explainability and public accountability is categorically higher.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **State algorithmic accountability / AI procurement laws** | A growing number of states (and some cities) require impact assessments, public inventories of government AI systems, or vendor disclosures before an agency can procure or deploy AI. Check your state and local requirements specifically — this area is moving fast and unevenly. |
| **Due process (constitutional)** | Automated decisions materially affecting a person's rights, benefits, or liberty (denial of benefits, risk scoring in criminal justice, etc.) may need to satisfy due process — meaningful notice and an opportunity to contest, which a black-box model can undermine. |
| **Public records / FOIA-type laws** | Government AI systems, their vendor contracts, and sometimes their underlying logic may be subject to public records requests — assume anything you build could become public. |
| **Federal guidance (if applicable)** | US federal agencies operate under OMB AI guidance (e.g., OMB M-24-10) governing federal agency AI use, including risk management and use-case inventories — relevant if you're a federal vendor or agency. |
| **EU AI Act — public-sector-specific provisions** | The Act's prohibited-practices list (social scoring, certain biometric surveillance) is specifically aimed at government use — see [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md) if EU-exposed. |
| **Anti-discrimination / civil rights law** | Same fair-treatment obligations as private sector, often with a higher public scrutiny bar given the government's role. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Due process adequacy** — if this system affects an individual's rights, benefits, or liberty, is there meaningful notice and a real opportunity to contest an adverse outcome?
- [ ] **Public transparency exposure** — is the org prepared for this system, its vendor contract, and (potentially) its logic to become public via a records request?
- [ ] **Procurement compliance** — has this system gone through required AI-specific procurement review (impact assessment, public inventory listing) per applicable state/local/federal law?
- [ ] **Disparate impact on protected/vulnerable populations** — particularly acute in benefits eligibility, criminal justice risk scoring, and similar high-stakes public programs; test per [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md).
- [ ] **Vendor lock-in / public accountability gap** — can the agency actually explain and defend a vendor's proprietary model's decisions, or does dependency on a vendor undermine accountability?

## Additional Pre-Deployment Checklist items

- [ ] Required algorithmic/AI impact assessment completed per applicable state or local law
- [ ] System added to any required public AI-use inventory
- [ ] Due process review completed (notice + appeal mechanism) for any system affecting individual rights or benefits
- [ ] Records-retention and public-disclosure implications reviewed with legal/records management before deployment
- [ ] Procurement contract includes explainability and audit rights sufficient for the agency to meet its own transparency obligations — don't let vendor IP claims block your ability to explain a decision to an affected person

## Sector-specific terms

- **Automated decision system (ADS)** — a common statutory term (used in several state laws) for a system that makes or materially assists in a decision affecting an individual; broader than this framework's [material decision](../../docs/glossary.md#risk-and-impact-terms) definition in some jurisdictions — check your state's statutory definition.
- **Algorithmic impact assessment** — a formal, often legally required, pre-deployment analysis of an automated system's effects on individuals and groups — distinct from, but overlapping with, this framework's core [Risk Assessment](../../templates/ai-risk-assessment.md).

## How this maps to the core framework

| Core artifact | Public-sector-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3; treat any rights/benefits-affecting system as High risk minimum |
| [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) | Add required impact assessment and public inventory steps as hard gates, not optional items |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Add explainability/audit-rights requirements to the contractual section |
| [Board Reporting Template](../../templates/board-reporting-template.md) | Add a public-transparency/records-exposure line for leadership awareness |

See also: [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md) · [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md)
