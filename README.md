# GovernTrace AI Framework

A practical, ready-to-use AI governance framework for organizations that need to manage AI risk but don't have a dedicated compliance team. Fill in a few templates, adopt one policy, and you have a working governance program — crosswalked against [NIST AI RMF](docs/standards/nist-ai-rmf-crosswalk.md), [ISO/IEC 42001](docs/standards/iso-42001-crosswalk.md), the [EU AI Act's risk tiers](docs/standards/eu-ai-act-risk-tiers.md), and [OWASP AI security guidance](docs/standards/owasp-ai-mapping.md) so it holds up to outside scrutiny.

This is **not** a compliance product or legal advice — it's a starting point you adapt to your organization, industry, and jurisdiction.

> **Note:** the intake and risk-assessment templates here are intentionally lightweight (plain markdown, filled in by hand). For teams that outgrow that and want intake/assessment tracked as live, structured data with workflow automation, that's the direction of the companion [GovernTrace AI Platform](#) (in development) — this repo will remain the standalone, no-infrastructure-required version.

## Who this is for

Small and mid-sized organizations that are:
- Already using AI tools (ChatGPT, Copilot, custom LLM features) without a formal process around them
- Building AI-powered features and need lightweight gates before shipping
- Bringing in third-party AI vendors and need a due-diligence process
- Getting asked "how do you govern AI?" by a customer, board member, or regulator, and don't have a good answer yet

You don't need a compliance team to use this — the [Roles & RACI](docs/roles-and-raci.md) doc shows how to assign these responsibilities to roles you probably already have.

## What's covered

| Area | What it does |
|---|---|
| **Policy** | An acceptable-use policy governing how employees use AI tools day to day |
| **Risk management** | A structured way to classify and assess risk for any AI use case before it ships |
| **Development lifecycle gates** | Checklists that plug into your existing release process |
| **Vendor oversight** | Due-diligence questions specific to AI vendors (data use, model transparency, security) |

## Quick start

1. **Read and adapt** the [Acceptable Use Policy](policies/acceptable-use-policy.md) — fill in the brackets, run it through your normal policy approval process, publish it.
2. **Stand up intake**: point anyone requesting a new AI tool or building an AI feature at the [Use-Case Intake Form](templates/ai-use-case-intake-form.md).
3. **Assess what needs it**: use cases flagged as higher-risk during intake get a full [AI Risk Assessment](templates/ai-risk-assessment.md).
4. **Vet vendors**: any third-party AI tool goes through [Vendor Due Diligence](templates/vendor-due-diligence.md) before approval.
5. **Gate deployment**: every AI feature or tool goes through the [Pre-Deployment Checklist](checklists/pre-deployment-checklist.md) (low-risk or medium/high-risk track) before go-live.
6. **Assign ownership**: use [Roles & RACI](docs/roles-and-raci.md) to name who's accountable for each step — even if it's one person wearing four hats.

That's a working Level 2 governance program (see the [Maturity Model](docs/maturity-model.md)). Everything else in `docs/` is there for when you want to go deeper.

## Repository structure

```
├── policies/
│   └── acceptable-use-policy.md      # Org-wide AI usage policy
├── templates/
│   ├── ai-use-case-intake-form.md    # Front door for any new AI tool/use case
│   ├── ai-risk-assessment.md         # Full risk assessment (NIST-aligned)
│   └── vendor-due-diligence.md       # Third-party AI vendor vetting
├── checklists/
│   └── pre-deployment-checklist.md   # Go-live gate, low-risk and high-risk tracks
└── docs/
    ├── roles-and-raci.md             # Who owns what
    ├── maturity-model.md             # Self-assessment: where are you, what's next
    └── standards/
        ├── nist-ai-rmf-crosswalk.md      # Subcategory-level mapping to NIST AI RMF
        ├── iso-42001-crosswalk.md        # Clause/Annex A mapping to ISO/IEC 42001
        ├── eu-ai-act-risk-tiers.md       # Risk-tier triage against the EU AI Act
        └── owasp-ai-mapping.md           # LLM/ML Top 10 security checklist mapping
```

## How deep to go

- **Just need something today?** Adopt the policy, use the intake form and pre-deployment checklist. That alone puts a stop to ungoverned AI sprawl.
- **Shipping AI features regularly?** Add the risk assessment and vendor due-diligence templates into your existing PR/release process.
- **Need to show this to auditors, customers, or a board?** Use the [NIST AI RMF crosswalk](docs/standards/nist-ai-rmf-crosswalk.md) and [maturity model](docs/maturity-model.md) to frame what you've built in terms they recognize. If you're EU-exposed, also check [EU AI Act risk tiers](docs/standards/eu-ai-act-risk-tiers.md); if certification is on the table, see the [ISO/IEC 42001 crosswalk](docs/standards/iso-42001-crosswalk.md).

## Scope and limitations

- Templates are deliberately framework-agnostic markdown — no tooling lock-in, easy to drop into a wiki, Notion, or a `governance/` folder in your existing repo.
- This does not implement or certify compliance with any specific regulation (EU AI Act, NIST AI RMF, ISO/IEC 42001) — the [standards crosswalks](docs/standards/) show *directional* alignment and honest gaps, not certification. Involve legal/compliance for anything regulator-facing.
- Security guidance here is a checklist, not a penetration test — high-risk systems still need real security review.

## Contributing

Issues and PRs welcome — especially real-world feedback on where a template was too heavy, too light, or missing something for a specific industry.

## License

[MIT](LICENSE)
