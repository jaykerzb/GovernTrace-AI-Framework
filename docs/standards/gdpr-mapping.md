# GDPR / Data Protection Mapping

The [GDPR](https://gdpr-info.eu/) (and similar comprehensive privacy regimes — UK GDPR, and US state laws like CCPA/CPRA that borrow its structure) governs personal data processing broadly, not AI specifically — but AI systems are disproportionately likely to trigger its higher-scrutiny provisions, since they often involve large-scale profiling, automated decision-making, and novel processing purposes. This page closes a gap: earlier drafts of this framework referenced GDPR concepts (data minimization, DPAs) without a dedicated crosswalk — this is that crosswalk, alongside [NIST AI RMF](nist-ai-rmf-crosswalk.md), [ISO/IEC 42001](iso-42001-crosswalk.md), [EU AI Act](eu-ai-act-risk-tiers.md), and [OWASP](owasp-ai-mapping.md).

**Not legal advice.** GDPR applies based on where your organization operates and whose data you process, not just where you're headquartered — confirm applicability with counsel.

## Core GDPR concepts most relevant to AI

| Concept | What it requires | Mapped artifact |
|---|---|---|
| **Lawful basis for processing** | Every use of personal data needs a legal basis (consent, legitimate interest, contract, etc.) — an AI system processing personal data needs this established *before* deployment, not retrofitted | [AI Risk Assessment](../../templates/ai-risk-assessment.md) §1 (data involved); confirm with Legal before completing |
| **Data minimization** | Collect/process only what's necessary for the stated purpose | [Data Retention Schedule](../../templates/data-retention-schedule.md); Acceptable Use Policy §3 |
| **Purpose limitation** | Data collected for one purpose shouldn't be repurposed for another (e.g., support-ticket data later used to train a model) without a new lawful basis | [Model Card](../../templates/model-card.md) training data section — document original purpose vs. AI use |
| **Data Protection Impact Assessment (DPIA)** | Required for processing "likely to result in high risk," which explicitly includes large-scale profiling and automated decision-making — most Medium/High risk AI systems in this framework will trigger this | [AI Risk Assessment](../../templates/ai-risk-assessment.md) — treat a completed Risk Assessment as your DPIA's foundation, but confirm with your Data Protection Officer whether a formal DPIA is separately required |
| **Article 22 — automated decision-making** | Individuals have the right not to be subject to a decision based solely on automated processing that produces legal or similarly significant effects, with exceptions (explicit consent, contract necessity, authorized by law) — and a right to human intervention where it applies | [AI Risk Assessment](../../templates/ai-risk-assessment.md) §1 "scope of autonomy" — a fully automated High-impact decision likely needs a human-in-the-loop redesign or a documented Article 22 exception |
| **Data Processing Agreement (DPA)** | Required with any processor (including AI vendors) handling personal data on your behalf | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) "data handling" section |
| **International data transfers** | Personal data leaving the EU/UK needs a valid transfer mechanism (adequacy decision, Standard Contractual Clauses, etc.) — relevant if your AI vendor processes data outside the EU/UK | [Vendor Due Diligence](../../templates/vendor-due-diligence.md) "data processing/storage region" |
| **Right to erasure / access / rectification** | Individuals can request their data be deleted, disclosed, or corrected — a real challenge if personal data has been used to train or fine-tune a model, since "deleting" it from a trained model isn't the same as deleting a database row | [Data Retention Schedule](../../templates/data-retention-schedule.md); flag training-data erasure as a known technical limitation in the [Model Card](../../templates/model-card.md) if applicable |

## The specific AI wrinkle: training data erasure

Standard GDPR deletion assumes deleting a record from a database. If personal data was used to train or fine-tune a model, the data's *influence* on the model may persist even after the source record is deleted — full "unlearning" is a hard, often impractical technical problem. Practical approaches:
- Avoid training/fine-tuning on personal data where a pre-trained or retrieval-augmented approach can substitute (RAG pulls from a live, deletable data store rather than baking data into weights)
- If training on personal data is unavoidable, document the erasure limitation explicitly in the [Model Card](../../templates/model-card.md) and confirm your lawful basis and retention approach account for it
- Consider whether your Data Protection Officer needs to sign off on this as an accepted, documented limitation rather than treating it as solved

## How this maps to the core framework

| Core artifact | GDPR-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add lawful basis confirmation and Article 22 applicability check to §1; treat as DPIA foundation for Medium/High risk systems |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Add DPA and international transfer mechanism confirmation as go/no-go items |
| [Data Retention Schedule](../../templates/data-retention-schedule.md) | Apply data minimization and purpose limitation explicitly per system |
| [Model Card](../../templates/model-card.md) | Document training-data erasure limitations where personal data was used in training |

See also: [EU AI Act Risk Tiers](eu-ai-act-risk-tiers.md) (the two regimes overlap but are legally distinct — an AI system can be low-risk under the AI Act and still trigger a full DPIA under GDPR) · [NIST AI RMF Crosswalk](nist-ai-rmf-crosswalk.md)
