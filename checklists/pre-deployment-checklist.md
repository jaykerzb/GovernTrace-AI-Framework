# Pre-Deployment Checklist

Run through this before any AI feature or tool goes live — for internal rollout or customer-facing release. Pick the track that matches your [Risk Assessment](../templates/ai-risk-assessment.md) outcome.

## Low-risk track

For use cases with no regulated data, no material decision-making, and human review already in place.

- [ ] [Intake form](../templates/ai-use-case-intake-form.md) completed and approved
- [ ] Tool added to the AI tool inventory
- [ ] Users briefed on [Acceptable Use Policy](../policies/acceptable-use-policy.md)
- [ ] Basic logging of usage in place (who used it, roughly when)

## Medium/High-risk track

Everything in the low-risk track, plus:

- [ ] [AI Risk Assessment](../templates/ai-risk-assessment.md) completed and signed off
- [ ] If third-party: [Vendor Due Diligence](../templates/vendor-due-diligence.md) completed
- [ ] Security review completed (data flows, access controls, secrets handling)
- [ ] Human review/override step tested and confirmed working, not just documented
- [ ] Bias/fairness check run if the system affects people differentially (even a basic disparity check across known groups)
- [ ] Prompt injection / adversarial input testing done for anything accepting untrusted input — see [OWASP AI mapping](../docs/owasp-ai-mapping.md)
- [ ] Rollback plan documented — how do you turn this off fast if it misbehaves?
- [ ] Monitoring/alerting in place for anomalous outputs or usage spikes
- [ ] User-facing disclosure drafted, if users interact with the AI directly
- [ ] Incident response contact/process confirmed for this system
- [ ] Re-review date set and calendared (owner is not "figure it out later")

## Go-live sign-off

| Role | Name | Sign-off | Date |
|---|---|---|---|
| System owner | | | |
| Governance reviewer | | | |
| Security reviewer (Medium/High only) | | | |

## Post-launch (first 30 days)

- [ ] Spot-check a sample of real outputs against expected behavior
- [ ] Confirm logging/monitoring is actually producing usable data
- [ ] Revisit risk tier if usage or data exposure looks different from what was assessed
