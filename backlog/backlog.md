# 🎫 Backlog — features & work to build

> One file per ticket in this folder; this note is the **board** — and the **read surface**: read *this*
> for the whole backlog, open an individual ticket only when working it (never sweep every file).
> `/digest` maintains it **incrementally** (only rows for tickets it changed) and doesn't hand-edit it.
> Workflow: pick a ticket → copy its **📋 Paste to Trello** block into a new Trello card → set the
> ticket's **Status** to `in-trello` + drop the card link in → its file moves to `backlog/archive/` and
> it leaves the active board (kept for provenance, never deleted). Closed = `in-trello`/`done` → archived.
> Status: `todo`/`ready` → `in-trello` → `done`. Priority: High · Med · Low.
> **This board holds committed work only** — ideas & requests live in [[ideas]] until you promote them.

## 📋 Ready for Trello

### payroll → [[payroll]]
| Priority | Ticket |
|---|---|
| High | [[payroll-leave-drawdown-check]] — leave/sick draw-down check at entry |
| High | [[payroll-rdo-accrual-check]] — RDO accrual check vs pre-pro |
| High | [[payroll-tax-checks]] — PAYG/new-starter tax-scale + rate-code checks |
| High | [[payroll-salary-review]] — build salary review into the tool |
| High | [[payroll-approver-poke]] — timesheet-approver field + poke + exclude-from-run |
| Med | [[payroll-apportionment-column]] — Incolink/Cbus/RDO apportionment column |
| Med | [[payroll-leave-job-costing-check]] — costed-to-leave-job check + force-back |
| Med | [[payroll-prevpay-columnt]] — previous-pay comparison + Column T |
| Med | [[payroll-rdo-calendar]] — RDO calendar (VIC+NSW) |
| Med | [[payroll-salary-sacrifice-bob]] — link salary sacrifice to Bob |
| Med | [[payroll-rdo-hours-formula]] — RDO working-hours formula (7.2) |
| Low | [[payroll-km-reimbursement-field]] — dedicated km-reimbursement field |
| Low | [[payroll-rollback-terminology]] — match JobPac "reverse" wording |

### textrack → [[textrack]]
| Priority | Ticket |
|---|---|
| Med | [[textrack-capacity-model]] — resolve role vs assignee capacity |
| Low | [[textrack-scenarios]] — finish "Scenarios" what-if planning |
| Low | [[textrack-ui-tidyups]] — UI tidy-ups |
| Low | [[textrack-jobpac-unlink]] — allow unlinking a project from JobPac |

### texco-tools → [[texco-tools]]
| Priority | Ticket |
|---|---|
| Med | [[texco-tools-apparel-landing]] — default to "New order", hide Catalogue |
| Med | [[texco-tools-apparel-approval]] — Apparel order approval routing |

## ✅ In Trello
_(none yet — move tickets here once copied into a card, with the card link)_

| System | Ticket | Trello |
|---|---|---|

## ✅ Done / In Trello (archived)
Closed tickets move to `backlog/archive/` to keep the active folder small — this is a compact pointer, not the full list.
- [[textrack-5digit-project-numbers]] — in-trello (5-digit cutover; PR-1 of 4 merged 2026-07-23) · [Trello card](https://trello.com/c/wqrOomzh/12-feat-tt-5-digit-job-number-cutover)
- [[textrack-role-overlap-fix]] — done (TT-3, shipped 2026-07-22)

Related: [[0-home]] · [[meetings]] · [[audit]]
