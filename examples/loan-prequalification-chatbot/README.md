# Worked Example: Loan Pre-Qualification Chatbot

## Scenario

**Riverbend Community Bank** (fictional, ~$4B assets, regional bank) wants to launch **LoanAssist**, a customer-facing chatbot on their website that answers questions about personal loan products and gives applicants a preliminary eligibility estimate ("pre-qualification score") before they submit a full application. LoanAssist is built on a third-party vendor's fine-tuned LLM (vendor: **"Cortex AI"**, fictional) combined with a scoring layer trained on Riverbend's historical loan performance data.

If the chatbot's pre-qualification score is favorable, the applicant is invited to submit a full application, which a human underwriter reviews per Riverbend's existing process. The chatbot's score is *advisory only* — it does not itself approve or deny credit.

This example walks the full governance flow for this use case, showing where it lands on risk, what controls get attached, and why — cross-referencing the [Banking & Financial Services sector pack](../../sectors/banking-financial-services/README.md) throughout, since this is squarely a credit-adjacent AI use case.

## Files in this example

1. [Use-Case Intake Form](01-intake-form.md)
2. [AI Risk Assessment](02-risk-assessment.md)
3. [Vendor Due Diligence](03-vendor-due-diligence.md) (Cortex AI)
4. [Model Card](04-model-card.md) (LoanAssist scoring model)
5. [Bias & Fairness Test](05-bias-fairness-test.md)
6. [Pre-Deployment Checklist](06-pre-deployment-checklist.md)

## The one-sentence takeaway

A chatbot that merely *talks about* loan products is low-stakes; the moment it also *scores* an applicant's eligibility — even "advisory only" — it becomes a credit-adjacent decision system, and the entire fair-lending machinery in the [Banking sector pack](../../sectors/banking-financial-services/README.md) applies. The "advisory only" framing doesn't reduce risk on its own — it only counts as a real mitigation if the human review step is *tested*, not just documented. That distinction drives most of the decisions in this example.
