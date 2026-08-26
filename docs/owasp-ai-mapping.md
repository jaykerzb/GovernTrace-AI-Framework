# Mapping to OWASP AI Security Guidance

This framework's security-relevant checks draw on the [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) and [OWASP Machine Learning Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/). Use this as a quick lookup when doing the security portion of a [Risk Assessment](../templates/ai-risk-assessment.md) or [Pre-Deployment Checklist](../checklists/pre-deployment-checklist.md).

## LLM-specific risks (OWASP LLM Top 10)

| Risk | What to check | Covered in |
|---|---|---|
| Prompt injection | Can untrusted input (user text, retrieved documents, tool output) override system instructions or exfiltrate data? | Risk Assessment §3; Checklist "prompt injection testing" |
| Insecure output handling | Is model output ever executed, rendered as HTML/SQL/code, or passed to another system without validation? | Risk Assessment §3 |
| Training data / sensitive information disclosure | Could the model leak training data or data from other users/tenants in its output? | Acceptable Use Policy §3; Vendor Due Diligence "data handling" |
| Model denial of service | Can crafted input cause excessive resource use or cost (token flooding, recursive prompts)? | Checklist "monitoring/alerting" |
| Supply chain vulnerabilities | Are you using third-party models, plugins, or fine-tunes with unclear provenance? | Vendor Due Diligence "model transparency" |
| Excessive agency | Does the system take actions (send emails, execute code, make purchases) with insufficient human checkpoints? | Risk Assessment §1 "scope of autonomy"; Checklist "human review step tested" |
| Overreliance | Are humans rubber-stamping AI output without real review? | Risk Assessment §3 "over-reliance" |

## ML/system-level risks (OWASP ML Top 10, selected)

| Risk | What to check |
|---|---|
| Input manipulation / adversarial examples | Has the system been tested with adversarial or edge-case inputs, not just happy-path data? |
| Data poisoning | If you fine-tune or retrain on user-submitted data, is that data validated/sanitized first? |
| Model theft / extraction | Are there rate limits and access controls preventing systematic querying to reconstruct the model? |
| Transfer learning attacks | If using a pre-trained base model, has it been evaluated for inherited vulnerabilities/biases? |

## How to use this in practice

1. During a [Risk Assessment](../templates/ai-risk-assessment.md), for any system that accepts untrusted input (user prompts, uploaded files, web content, retrieved documents), walk the LLM Top 10 table above and note mitigations.
2. For systems with fine-tuning, custom training, or model-hosting components, also walk the ML Top 10 selection.
3. Findings feed directly into Risk Assessment §3 (failure modes) and §4 (controls).

This is a working checklist, not a penetration test. High-risk or customer-facing systems should get an actual security review or pen test from someone qualified to do adversarial testing.
