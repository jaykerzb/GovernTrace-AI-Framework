# EU AI Act Risk Tiers

The [EU AI Act](https://artificialintelligenceact.eu/) is the first comprehensive AI-specific regulation with binding legal force. Even if you're not EU-regulated, its risk-tiering structure is a useful lens — it's increasingly referenced by customers, boards, and other regulators as *the* AI risk taxonomy. This page maps its tiers to this framework's [Risk Assessment](../../templates/ai-risk-assessment.md) so you can flag likely-regulated use cases early.

**This is not legal advice.** If any of your AI use cases might fall under the EU AI Act (you operate in the EU, serve EU users, or your AI output affects people in the EU), involve legal counsel — this page is a triage aid, not a compliance determination.

## The four tiers

### 1. Unacceptable risk — prohibited outright

Practices banned regardless of safeguards: social scoring by public authorities, real-time remote biometric identification in public spaces (with narrow law-enforcement exceptions), covert manipulation causing harm, exploiting vulnerabilities of specific groups (age, disability), emotion inference in workplaces/schools (with limited exceptions), and untargeted scraping of facial images to build recognition databases.

**In this framework:** [Risk Assessment](../../templates/ai-risk-assessment.md) §2 has an explicit "Unacceptable" tier — treat a match against any of the above as an automatic reject, not something to mitigate.

### 2. High risk — heavily regulated, not prohibited

Covers AI used in: critical infrastructure, education/vocational training (e.g. exam scoring), employment (hiring, firing, task allocation, performance monitoring), essential services (credit scoring, insurance pricing), law enforcement, migration/asylum, and administration of justice — plus AI embedded in products already subject to EU safety certification (medical devices, machinery, toys).

**Obligations if you're in this tier** (high-level — confirm specifics with counsel):
- Risk management system maintained throughout the AI system's lifecycle
- Data governance: training/validation/testing data must meet quality criteria
- Technical documentation and automatic logging ("record-keeping")
- Transparency to users that they're interacting with / subject to an AI system
- Human oversight designed into the system
- Accuracy, robustness, and cybersecurity requirements
- Conformity assessment before market placement

**In this framework:** if a [Risk Assessment](../../templates/ai-risk-assessment.md) use case matches this tier, treat it as **High** risk minimum, and layer in: [Vendor Due Diligence](../../templates/vendor-due-diligence.md) (for documentation from your model/tooling supplier), the "human review before output used" and "user-facing disclosure" items in the [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md), and the logging/audit-trail control in Risk Assessment §4.

### 3. Limited risk — transparency obligations

Chatbots, deepfakes, and AI-generated content generally fall here. The core obligation is **disclosure**: users must be told they're interacting with AI, and AI-generated/manipulated content (audio, image, video) must be marked as such.

**In this framework:** Pre-Deployment Checklist's "user-facing disclosure drafted" item covers this directly.

### 4. Minimal risk — no specific obligations

Most everyday AI use (spam filters, AI-enabled video games, recommendation engines without the above characteristics) falls here — voluntary codes of conduct are encouraged but not mandated.

**In this framework:** this is typically your [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) low-risk track.

## Quick triage mapping

| This framework's Risk Assessment tier | Likely EU AI Act tier (if EU-exposed) |
|---|---|
| Unacceptable | Unacceptable (prohibited) |
| High | Likely High-risk — get legal confirmation |
| Medium | Likely Limited-risk (transparency) — confirm it doesn't cross into a High-risk use case listed above |
| Low | Likely Minimal-risk |

This mapping is directional, not authoritative — a "Medium" in this framework's generic risk model can still land in the EU AI Act's High-risk annex if it touches employment, credit, or essential services, regardless of how contained the blast radius feels internally. Always check the actual use case against the High-risk list above, not just the tier label.

See also: [NIST AI RMF Crosswalk](nist-ai-rmf-crosswalk.md) · [ISO/IEC 42001 Crosswalk](iso-42001-crosswalk.md) · [GDPR Mapping](gdpr-mapping.md) — note the AI Act and GDPR are legally distinct regimes that often both apply to the same system
