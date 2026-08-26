# Sector Pack: Manufacturing / Critical Infrastructure

For manufacturers, utilities, and operators of industrial control systems (ICS) / operational technology (OT) using AI for predictive maintenance, quality inspection, process optimization, or safety systems. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md).

## Why this sector needs its own overlay

This is the one sector pack in this framework where a failure mode is primarily **physical, not informational or financial** — a bad AI output can mean an equipment failure, a safety incident, or a critical-infrastructure outage, not just a wrong decision on paper. Risk assessment here needs a physical-safety lens the other packs don't carry, and it intersects with existing OT/ICS safety and cybersecurity regimes that predate AI governance entirely.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **Sector-specific critical infrastructure regulation** (e.g., NERC CIP for electric utilities, TSA security directives for pipelines, similar sector regulators) | Existing OT/ICS security and reliability regulation generally already applies regardless of whether AI is involved — AI governance here supplements, doesn't replace, your existing regulatory compliance program. |
| **OSHA / workplace safety law** | AI-influenced changes to physical processes (robotics, automated quality control affecting worker safety) fall under standard workplace safety obligations. |
| **Product liability law** | If an AI-driven quality inspection system fails to catch a defect that later causes harm, standard product liability exposure applies — with the added wrinkle of explaining why an AI-based inspection missed it. |
| **NIST guidance on AI in OT/ICS contexts** | NIST and sector-specific bodies (e.g., CISA) have issued growing guidance on AI risk specifically in OT/ICS environments, distinct from the general NIST AI RMF — worth tracking alongside the [NIST AI RMF Crosswalk](../../docs/standards/nist-ai-rmf-crosswalk.md). |
| **EU AI Act — high-risk "critical infrastructure" category** | AI used as a safety component in critical infrastructure is explicitly named as High-risk under the Act — see [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md) if EU-exposed. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Physical safety impact** — could a wrong AI output directly or indirectly cause physical harm to a worker, the public, or the environment? If yes, this is not a standard "High" risk — treat it with the same rigor as a safety-critical system, involving your safety engineering function, not just governance.
- [ ] **OT/IT boundary security** — does this AI system create a new network path between IT systems (where the model runs/is managed) and OT systems (where it acts), and is that boundary secured per your existing ICS security standards?
- [ ] **Fail-safe behavior** — when the AI system is uncertain, unavailable, or wrong, does the underlying process fail to a safe state, or does it continue operating on bad input?
- [ ] **Latency/availability requirements** — for real-time process control, does the AI system's availability and response time meet the safety-critical requirements of the process it's part of?
- [ ] **Sensor/data quality dependency** — is the AI system's reliability dependent on sensor data quality that could degrade (miscalibration, environmental interference) in ways not obvious to operators?

## Additional Pre-Deployment Checklist items

- [ ] Safety engineering / process safety review completed, independent of and in addition to the standard AI governance review
- [ ] Fail-safe behavior tested under simulated AI failure/uncertainty conditions, not just normal operation
- [ ] OT/IT network boundary reviewed by ICS security function per existing standards (NERC CIP or equivalent)
- [ ] Operator training completed — staff who work alongside the AI system understand its limitations and know how to safely override or bypass it
- [ ] Incident response plan includes physical/safety incident escalation, not just data/decision incident handling

## Sector-specific terms

- **OT (Operational Technology)** — hardware and software that monitors or controls physical processes and equipment, distinct from IT systems; the OT/IT boundary is a specific, well-established security concern this pack extends into AI governance.
- **Fail-safe** — a design principle where system failure results in a safe state rather than a dangerous one; a critical design question for any AI system with physical-world effects, not addressed by the core framework's generic "rollback plan" language alone.
- **Safety-critical system** — a system whose failure could result in death, injury, or significant environmental/property damage — a categorization independent of, and generally more stringent than, this framework's "High" risk tier.

## How this maps to the core framework

| Core artifact | Manufacturing/critical infrastructure-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3; any system with physical safety impact needs safety engineering sign-off in addition to standard sign-off |
| [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) | Add fail-safe testing and OT/IT boundary review as hard gates for any system with physical-world effects |
| [Incident Response Runbook](../../templates/incident-response-runbook.md) | Add a physical/safety incident severity path, likely requiring faster notification timeframes than the standard Sev 1/2 table |
| [Model Card](../../templates/model-card.md) | Add fields for the physical process(es) the model affects and its fail-safe behavior |

See also: [EU AI Act Risk Tiers](../../docs/standards/eu-ai-act-risk-tiers.md) · [OWASP AI Mapping](../../docs/standards/owasp-ai-mapping.md) (for the AI/cybersecurity intersection at the OT/IT boundary)
