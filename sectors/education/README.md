# Sector Pack: Education

For K-12 districts, higher education institutions, and ed-tech vendors deploying AI for grading, admissions, proctoring, tutoring, or administrative decisions. Layer this on top of the core [Risk Assessment](../../templates/ai-risk-assessment.md) and [Pre-Deployment Checklist](../../checklists/pre-deployment-checklist.md) — see the [sector pack overview](../README.md).

## Why education needs its own overlay

Education AI overwhelmingly touches **minors' data** and decisions that shape a student's academic trajectory (grading, admissions, discipline, special-education identification) — a combination that triggers student-specific privacy law most general frameworks don't address, plus a much lower institutional tolerance for opaque, unappealable decisions.

## Key regulatory context

| Regime | Relevance |
|---|---|
| **FERPA** (Family Educational Rights and Privacy Act) | Governs student education records; AI tools processing grades, disciplinary records, or other education records generally need to operate under a "school official" exception with strict use limitations, not as an independent data controller. |
| **COPPA** (Children's Online Privacy Protection Act) | Applies if the AI tool collects personal information from students under 13 — parental consent requirements are triggered independent of FERPA. |
| **State student data privacy laws** | Many states have their own student-data laws (often stricter than FERPA) governing what ed-tech vendors can do with student data, including AI-specific provisions in newer legislation. |
| **IDEA / Section 504** (special education) | AI used in identifying or evaluating students for special education services must not create discriminatory barriers to legally required accommodations and evaluations. |
| **Title VI / Title IX** | Nondiscrimination law extends to AI-driven decisions (admissions, discipline, proctoring flags) that disproportionately affect protected groups. |

## Additional risk categories for the Risk Assessment

Add to [AI Risk Assessment](../../templates/ai-risk-assessment.md) §3:

- [ ] **Student record scope creep** — is the AI vendor accessing more student data than its "school official" function requires under FERPA?
- [ ] **Minor consent requirements** — does this tool trigger COPPA parental consent, and is that process actually implemented (not just assumed unnecessary)?
- [ ] **Academic-decision explainability** — can a grading, admissions, or disciplinary AI output be explained well enough to survive a parent or student appeal?
- [ ] **Proctoring/surveillance overreach** — does an AI proctoring tool's flagging behavior (eye movement, background noise, etc.) disproportionately flag students with disabilities, different home environments, or other non-cheating-related factors?
- [ ] **Special education identification bias** — could this system's use in early identification/screening create or reinforce disparities in special education referral rates?

## Additional Pre-Deployment Checklist items

- [ ] FERPA "school official" exception basis documented and vendor contract restricts use accordingly
- [ ] COPPA parental consent process implemented and tested if applicable
- [ ] Appeal/contest process for any AI-influenced academic or disciplinary decision clearly defined and communicated to students/parents
- [ ] Proctoring/surveillance tools tested for disparate flagging rates across disability status and other relevant factors, where feasible to assess
- [ ] Vendor contract confirms no resale or ad-tech use of student data — a common ed-tech-specific red flag

## Sector-specific terms

- **Education record** (FERPA usage) — records directly related to a student maintained by an educational institution; broader than the general [glossary](../../docs/glossary.md)'s "sensitive data" and triggers specific access/disclosure rules.
- **School official exception** — the FERPA mechanism allowing a vendor to access education records without separate parental consent, contingent on legitimate educational interest and use restrictions matching the school's own obligations.

## How this maps to the core framework

| Core artifact | Education-specific addition |
|---|---|
| [AI Risk Assessment](../../templates/ai-risk-assessment.md) | Add the risk categories above to §3; treat any grading/admissions/discipline system as High risk minimum |
| [Vendor Due Diligence](../../templates/vendor-due-diligence.md) | Add FERPA school-official-exception and COPPA consent questions to the data-handling section |
| [Data Retention Schedule](../../templates/data-retention-schedule.md) | Add student-record-specific retention limits, often shorter than general operational data |
| [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) | Add disability status and special-education referral rate as tested dimensions where applicable |

See also: [Bias & Fairness Testing Guide](../../templates/bias-fairness-testing-guide.md) · [Public Sector pack](../public-sector/README.md) (for public K-12/higher-ed institutions)
