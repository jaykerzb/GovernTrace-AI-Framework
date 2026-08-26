# Security Policy

This repository is documentation — markdown templates, policies, and checklists. There's no application code, no runtime, no dependencies to have a CVE. That said, a few things are still worth a real reporting process.

## What to report here

- **Content that could cause real harm if followed**: a template or checklist item that, if implemented as written, would create a security or privacy vulnerability (e.g., a data-handling recommendation that's actually unsafe, a control described as sufficient that isn't).
- **Supply-chain concerns**: if a future version of this repo ever adds tooling, scripts, or GitHub Actions, report any vulnerability in those the same way you would for application code.
- **Sensitive data accidentally committed**: if you spot what looks like a real credential, API key, or personal data in the repo history (as opposed to the placeholder/fictional data in the [worked example](examples/loan-prequalification-chatbot/README.md)), report it immediately — don't open a public issue.

## What NOT to report here

- Disagreements with a regulatory interpretation — use the [regulatory correction issue template](.github/ISSUE_TEMPLATE/regulatory-correction.md) instead, that's a content-accuracy process, not a security one.
- General template feedback — use the [template feedback issue template](.github/ISSUE_TEMPLATE/template-feedback.md).

## How to report

Do not open a public issue for anything involving accidentally committed secrets or a genuinely exploitable recommendation. Instead, report it privately via GitHub's [private vulnerability reporting](https://github.com/jaykerzb/GovernTrace-AI-Framework/security/advisories/new) on this repository, or contact the maintainer directly through their GitHub profile.

## Response

This is a side project maintained by one person — expect an acknowledgment within a few days, not an SLA. Anything involving exposed secrets will be prioritized and the offending content removed/rotated as fast as possible.
