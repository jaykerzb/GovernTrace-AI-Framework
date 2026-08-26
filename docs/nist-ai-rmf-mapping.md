# Mapping to the NIST AI Risk Management Framework

This framework is a lightweight, practical implementation of [NIST AI RMF 1.0](https://www.nist.gov/itl/ai-risk-management-framework) — it doesn't reproduce NIST's text, just shows where each of its four core functions is covered by a concrete artifact in this repo, so you can point an auditor or exec sponsor at it.

| NIST AI RMF Function | What it means | Where it's covered here |
|---|---|---|
| **Govern** | Culture, accountability, and policy for managing AI risk across the org | [Acceptable Use Policy](../policies/acceptable-use-policy.md), [Roles & RACI](roles-and-raci.md) |
| **Map** | Understand context, purpose, and stakeholders of a specific AI system before assessing risk | Section 1 of the [AI Risk Assessment](../templates/ai-risk-assessment.md); [Use Case Intake Form](../templates/ai-use-case-intake-form.md) |
| **Measure** | Analyze, benchmark, and track identified risks (bias, robustness, security, reliability) | Sections 2–3 of the [AI Risk Assessment](../templates/ai-risk-assessment.md); [OWASP AI Mapping](owasp-ai-mapping.md) for security-specific measurement |
| **Manage** | Prioritize and act on risks — controls, monitoring, response, and continuous improvement | Section 4 of the [AI Risk Assessment](../templates/ai-risk-assessment.md); [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md); re-review cadence in both |

## Why this mapping matters

Most small/mid organizations don't need to "implement NIST AI RMF" as a formal program — they need to demonstrate they thought about AI risk in a structured, repeatable way. Mapping your templates to a recognized framework does two things:

1. Gives you a credible answer when a customer, auditor, or regulator asks "how do you govern AI use?"
2. Gives you a real structure to grow into if you later need a more formal program (e.g. pursuing ISO/IEC 42001 certification)

## What this is *not*

This is not a certified or audited implementation of NIST AI RMF, and completing these templates does not constitute compliance with any regulation. Treat it as a starting structure to adapt to your organization's actual risk tolerance and legal obligations — involve legal/compliance for anything regulator-facing.
