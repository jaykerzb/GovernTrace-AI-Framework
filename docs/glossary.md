# AI Glossary & System Definitions

A shared vocabulary for your AI Governance group. Inconsistent terminology is one of the most common ways governance breaks down in practice — one team's "AI system" is another's "just a spreadsheet formula," and a Risk Assessment is only as good as everyone applying it having the same mental model. Adopt this glossary as-is or edit it, but keep it version-controlled and referenced by name in your [Acceptable Use Policy](../policies/acceptable-use-policy.md).

## Types of AI systems

Use these categories on the [Use-Case Intake Form](../templates/ai-use-case-intake-form.md) and [Risk Assessment](../templates/ai-risk-assessment.md) to describe *what kind* of system you're governing — different types carry different failure modes.

| Type | Definition | Examples | Typical risk drivers |
|---|---|---|---|
| **Generative AI** | Produces new content (text, image, audio, video, code) from a prompt or input | ChatGPT, Copilot, Midjourney, internal LLM chat tools | Hallucination, IP/copyright exposure, data leakage via prompts |
| **Predictive / classification AI** | Assigns a label, score, or category to an input based on learned patterns | Credit scoring models, spam filters, churn prediction, resume screening | Bias/disparate impact, opaque decision logic |
| **Recommendation systems** | Ranks or surfaces options based on user data and behavior | Product recommendations, content feeds, candidate matching | Filter bubbles, manipulation risk, data profiling |
| **Computer vision** | Interprets or classifies visual input | Facial recognition, quality inspection, medical imaging analysis | Bias across demographics, surveillance concerns, accuracy in edge cases |
| **Natural language processing (non-generative)** | Extracts structure or meaning from text/speech without generating new content | Sentiment analysis, entity extraction, transcription, translation | Misinterpretation, language/dialect bias |
| **Autonomous / agentic AI** | Plans and executes multi-step actions with limited human checkpoints, often using tools | AI agents that browse, call APIs, execute code, or make purchases | Excessive agency, cascading errors, harder-to-predict behavior |
| **Embedded / decision-support AI** | AI as a component inside a larger non-AI system, informing but not making the final call | Fraud-detection flags reviewed by an analyst, AI-assisted diagnosis shown to a clinician | Overreliance/automation bias, unclear accountability if the human "always agrees" |
| **Traditional statistical/rules-based systems** | Deterministic logic or classical statistics — **not** AI/ML, even if colloquially called "smart" | If/then business rules, linear regression built and validated by a human analyst | Generally out of scope for this framework unless embedded inside a broader AI system |

> **Governance tip:** the last row matters. Not everything called "AI" by a vendor or a team is actually AI/ML in the governance-relevant sense. If a "smart" tool is really deterministic rules with no learned/probabilistic component and no vendor black box, it likely doesn't need a full [Risk Assessment](../templates/ai-risk-assessment.md) — note that reasoning on the intake form rather than skipping the process silently.

## Core definitions

**AI system**
A system that, for a given set of human-defined objectives, generates outputs (predictions, recommendations, decisions, or content) influencing real or virtual environments, using machine learning and/or logic- and knowledge-based approaches. (Adapted from OECD/NIST usage.)

**Model**
The trained artifact (weights, parameters, or rules) that produces outputs from inputs. A single AI system may use one model or several in combination.

**Foundation model**
A large model trained on broad data, adaptable to many downstream tasks (e.g., GPT, Claude, Llama). Most organizations *use* foundation models via API rather than train their own.

**Fine-tuning**
Further training a pre-trained model on your own data to specialize its behavior. Introduces its own data governance obligations — see [Acceptable Use Policy §3](../policies/acceptable-use-policy.md).

**Training data / validation data / test data**
Training data teaches the model; validation data tunes it during development; test data evaluates final performance on unseen examples. Governance-relevant because bias and quality issues usually originate in training data.

**Inference**
Running a trained model on new input to produce an output (as opposed to training). Most day-to-day AI *use* in an organization is inference against a vendor's already-trained model.

**Prompt**
The input given to a generative AI system, including any system instructions, user input, and retrieved context. Prompts can carry sensitive data — see Acceptable Use Policy data rules.

**Hallucination**
A confident but factually incorrect or fabricated output from a generative AI system. Not a bug in the traditional sense — an inherent property of how these models generate text.

**Bias / disparate impact**
A pattern where a system's outputs differ systematically across groups (e.g., by race, gender, age) in ways not justified by the task, potentially causing unlawful or unfair outcomes.

**Human-in-the-loop (HITL)**
A human must review and approve an AI output *before* it takes effect. The strongest form of oversight in this framework's [Risk Assessment](../templates/ai-risk-assessment.md) autonomy scale.

**Human-on-the-loop**
A human monitors an AI system that acts autonomously and can intervene or override, but doesn't approve every action before it happens.

**Automation bias / overreliance**
The tendency of humans to defer to AI output even when their own judgment or evidence suggests otherwise. A named failure mode in the [Risk Assessment](../templates/ai-risk-assessment.md) §3.

**Explainability / interpretability**
The degree to which a human can understand *why* a system produced a given output. Lower for deep learning/foundation models, higher for simpler statistical models — factors directly into the Risk Assessment's explainability dimension.

**Model card**
A short, standardized document describing a model's intended use, training data, evaluated performance, and known limitations. See the [Model Card template](../templates/model-card.md).

**Shadow AI**
AI tools adopted and used within an organization without going through governance/procurement — the primary problem the [Use-Case Intake Form](../templates/ai-use-case-intake-form.md) is designed to surface and eliminate.

**AI incident**
Any event where an AI system produces a harmful, biased, non-compliant, or unexpectedly damaging output, or is used outside its approved scope. See the [Incident Response Runbook](../templates/incident-response-runbook.md).

## Risk and impact terms

**Risk tier (Low / Medium / High / Unacceptable)**
This framework's classification, assigned via the [Risk Assessment](../templates/ai-risk-assessment.md), based on data sensitivity, impact, autonomy, reversibility, scale, and explainability. Distinct from — but mapped to — the EU AI Act's own tiers; see [EU AI Act Risk Tiers](standards/eu-ai-act-risk-tiers.md).

**Material decision**
A decision meaningfully affecting a person's access to opportunity, resources, rights, or safety (employment, credit, housing, healthcare, legal outcomes). AI involvement in a material decision automatically warrants a full Risk Assessment.

**High-risk AI system** (EU AI Act usage)
A specific regulatory category — see [EU AI Act Risk Tiers](standards/eu-ai-act-risk-tiers.md) for the list. Not the same as this framework's generic "High" risk tier, though they often overlap.

## Keeping this current

Review this glossary alongside your annual [Acceptable Use Policy](../policies/acceptable-use-policy.md) review, and any time your AI Governance group finds itself arguing about what a term means — that argument is the signal this page needs an edit.
