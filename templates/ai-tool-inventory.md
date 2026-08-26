# AI Tool Inventory

The single source of truth for every AI tool/system in use across the organization. This closes a gap flagged repeatedly elsewhere in this repo — the [NIST AI RMF Crosswalk](../docs/standards/nist-ai-rmf-crosswalk.md) (Govern 1.6–1.7) and [ISO/IEC 42001 Crosswalk](../docs/standards/iso-42001-crosswalk.md) (Clause 8) both note that a tool inventory is assumed but wasn't previously templated. This is that template.

Maintain this as a living document — a spreadsheet or lightweight database works better than markdown at scale, but the columns below are the schema either way. The [Governance Lead](../docs/roles-and-raci.md) owns keeping it current.

## Inventory

| Tool/System name | Vendor (or "internal") | Type ([glossary](../docs/glossary.md#types-of-ai-systems)) | Risk tier | Owner | Linked Risk Assessment | Data classification touched | Approval date | Next re-review | Status |
|---|---|---|---|---|---|---|---|---|---|
| *example: LoanAssist-Score* | *Internal* | *Predictive/classification* | *High* | *Priya Nandakumar* | *[link]* | *Confidential* | *2026-03-10* | *2026-06-08* | *Active* |
| | | | | | | | | | |

**Status values:** Active · Pending Approval · Suspended · Decommissioned

## Quarterly review checklist

Run this every quarter (see [Roles & RACI](../docs/roles-and-raci.md) cadence):

- [ ] Every row has a current owner (people leave — orphaned entries are a governance gap)
- [ ] Every row's "next re-review" date is in the future — flag and chase down anything overdue
- [ ] Cross-check against actual usage/billing data where available (SSO logs, vendor invoices) to catch **shadow AI** — tools in use that never went through [intake](ai-use-case-intake-form.md) and aren't in this inventory at all
- [ ] Decommissioned tools confirmed actually decommissioned (access revoked, data deleted per [Data Retention Schedule](data-retention-schedule.md)), not just marked as such
- [ ] Summary counts (total tools, by risk tier, overdue re-reviews) pulled into the next [Board Reporting Template](board-reporting-template.md)

## Why a spreadsheet/database beats markdown here

This template defines the schema so every implementation stays consistent, but a real inventory needs sorting, filtering, and reminders for overdue reviews — capabilities markdown doesn't have. Common options: a shared spreadsheet with conditional formatting on overdue dates, a lightweight internal tool, or (for teams that outgrow manual tracking) a platform that manages this as structured, live data — see the note near the top of the [README](../README.md) on the direction the companion GovernTrace AI Platform is headed.

---
*Related: [Use-Case Intake Form](ai-use-case-intake-form.md) · [AI Risk Assessment](ai-risk-assessment.md) · [Roles & RACI](../docs/roles-and-raci.md)*
