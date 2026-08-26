# AI Vendor / Third-Party Due Diligence

Complete before onboarding any third-party AI tool or model provider. Pair with your standard vendor security review if one exists — this covers AI-specific questions that generic vendor reviews usually miss.

## Vendor overview

| Field | Value |
|---|---|
| Vendor/product name | |
| Model(s) used (own model, or which foundation model provider) | |
| Business owner / requester | |
| Linked intake form | |

## Data handling

- Does the vendor use your inputs/outputs to train or fine-tune their models? [ ] Yes [ ] No [ ] Opt-out available
- Where is data processed and stored (region)? Relevant if you have data residency requirements.
- What is the data retention period, and can you request deletion?
- Does the contract include a Data Processing Agreement (DPA) if personal data is involved?
- Sub-processors: does the vendor rely on other AI providers downstream (e.g. a wrapper around a foundation model)? List them.

## Security

- Does the vendor have a recognized security certification (SOC 2 Type II, ISO 27001) or will they provide a security questionnaire response?
- Is data encrypted in transit and at rest?
- Does the vendor have a documented vulnerability disclosure / incident notification process, and what's the SLA for notifying you of a breach?
- Access controls: SSO/SAML support, role-based access, audit logging available?

## Model transparency

- Does the vendor publish a model card, system card, or acceptable-use policy for the model?
- Is there disclosure of known limitations, bias evaluations, or eval benchmarks?
- Can the vendor explain, at a general level, how the model was trained (data sources, cutoff date)?
- Is there a documented process for reporting and getting fixes for harmful/incorrect outputs?

## Commercial and legal

- Liability terms: what happens if the tool causes harm/loss from a bad output?
- Can the vendor terminate/change the service with insufficient notice for you to react?
- Pricing model and what happens to your data/access if you stop paying?
- IP: who owns output generated using the tool? Any indemnification for IP claims on generated content?

## Risk rating

| Dimension | Rating (Low/Med/High) |
|---|---|
| Data handling risk | |
| Security posture | |
| Vendor transparency | |
| Contractual/legal risk | |
| Vendor lock-in / concentration risk | |

**Overall decision:** [ ] Approve [ ] Approve with conditions [ ] Reject

**Conditions (if any):**

**Reviewed by / date:**

**Next scheduled review:** [recommend annually, or on contract renewal]

---
*Approved vendors should be added to your internal AI Tool Inventory (a simple running list — tool, vendor, risk tier, approval date, review date — is enough to start; a spreadsheet works fine).*
