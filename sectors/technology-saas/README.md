# Sector Pack: Technology / SaaS / AI-Native Companies

For companies building AI-powered products or platforms used by other businesses or consumers — including SaaS companies embedding third-party foundation models, and AI-native startups whose core product *is* the model. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md).

## Why this sector needs its own overlay

The rest of this framework is written for organizations *using* AI internally. A tech/SaaS company building AI *into a product* has a second, distinct governance surface: you're not just managing your own AI risk, you're the upstream link in every one of your customers' AI governance chains. Your [Model Card](../../templates/model-card.md) and disclosures become *their* vendor due-diligence input.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **FTC Act (Section 5)** | Same deceptive-practices exposure as [Retail](../retail-ecommerce/README.md) — "AI-washing" claims about your own product are a live enforcement area. |
| **EU AI Act — provider obligations** | If you're a "provider" (not just a "deployer") of an AI system under the Act, you carry the heavier obligation set — conformity assessment, technical documentation, post-market monitoring — especially if your product falls into a High-risk category your customers use it for. See [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md). |
| **State AI transparency laws** | A growing number of states require disclosure when a product uses AI in ways that affect consumers, sometimes with specific obligations on the *platform* rather than the end-user business. |
| **Sector-specific pass-through obligations** | If your customers are in banking, healthcare, or another regulated sector, your contract terms and technical capabilities (auditability, explainability, data handling) directly determine whether *they* can meet their own obligations — see [Banking](../banking-financial-services/README.md), [Healthcare](../healthcare/README.md), etc. |
| **API/foundation model terms of service** | If you build on a foundation model provider's API, their acceptable use policy and rate/output restrictions flow down to you and, transitively, to your customers. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Downstream regulatory pass-through** — could your customers be in a regulated sector (banking, healthcare, insurance) that needs specific contractual or technical capabilities from you (audit logs, explainability, BAA-equivalent terms) to meet *their* obligations?
- [ ] **Provider vs. deployer status (EU AI Act)** — have you determined whether you're a "provider" under the Act for any High-risk use case your product enables? This changes your obligation set substantially.
- [ ] **Foundation model dependency risk** — what happens to your product and your customers if your underlying model provider changes pricing, deprecates a model, or changes its acceptable use policy?
- [ ] **Multi-tenant data isolation** — for any AI feature using customer data (fine-tuning, RAG, context), is there a hard guarantee against cross-customer data leakage?
- [ ] **Marketing claim accuracy** — do your own "AI-powered" claims match what the product actually does? (See [Retail pack](../retail-ecommerce/README.md) for the FTC angle.)

## Additional Pre-Deployment Checklist items

- [ ] Provider/deployer status under EU AI Act determined for any customer-facing High-risk use case
- [ ] Customer-facing documentation (your own equivalent of a [Model Card](../../templates/model-card.md)) published so customers can complete their own vendor due diligence on you
- [ ] Multi-tenant data isolation tested and verifiable, not just architecturally assumed
- [ ] Contractual terms reviewed against what regulated-sector customers will need (audit rights, explainability commitments, data processing terms)
- [ ] Marketing/legal review of AI-related product claims before launch

## Sector-specific terms

- **Provider** (EU AI Act usage) — the entity that develops an AI system or has it developed and places it on the market; carries the heaviest compliance burden under the Act.
- **Deployer** (EU AI Act usage) — the entity using an AI system under its authority; lighter obligations than a provider, but your customers may be deployers relying on *you* as the provider.
- **Multi-tenancy** — an architecture serving multiple customers from shared infrastructure; the core technical risk this pack calls out because AI features (fine-tuning, embeddings, RAG context) can create novel cross-tenant leakage paths beyond standard SaaS data isolation.

## How this maps to the core framework

| Core artifact | Tech/SaaS-specific addition |
|---|---|
| [Model Card](../../templates/model-card.md) | Treat as a dual-purpose document — internal governance record *and* your customers' due-diligence input; write it assuming an external audience |
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3, with explicit EU AI Act provider/deployer determination |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Apply this to your own foundation-model/API dependencies, not just to tools you buy for internal use |
| [Incident Response Runbook](../../templates/incident-response-runbook.md) | Add a customer-notification track — your incident may be your customers' incident too |

See also: [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md) · relevant customer-facing sector packs ([Banking](../banking-financial-services/README.md), [Healthcare](../healthcare/README.md), [Insurance](../insurance/README.md))
