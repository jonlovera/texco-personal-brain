# System Inventory — Payroll

> Status legend: ⬜ not started · 🟡 in progress · ✅ done
> Distilled from the 2026-07-23 payroll-tool walkthrough (see `1-daily/2026-07-23.md` for the full
> transcript). Speaker roles: **Dev** = the developer who built it (Ryan/Brock); **Payroll** = the
> payroll lead directing requirements ([[people|Michel VO]] / Michelle runs the weekly).

## Snapshot
- **Purpose / who uses it:** In-house payroll-processing tool. Ingests weekly/fortnightly timesheets
  (from emailed PDF attachments), splits them per employee, pulls job/JobPac codes, lets payroll
  review hours + allowances, reconciles against the **pre-pro** report, then posts ("ingests")
  timesheets into **JobPac**. Aims to replace the manual spreadsheet-based payroll run.
- **Owner / who knows it:** Built by Ryan/Brock; payroll requirements owned by Michel VO (payroll lead)
  and Michelle (runs the weekly).
- **Business criticality:** critical (pays staff; lots of EBA/award nuance).
- **Maturity:** was in testing until very recently; **now live** (dev→live done). Weekly is still run
  manually; plan is to run the tool **in parallel** with the manual process next week.

## Discovery checklist
- [ ] **Repo** — where the code lives
- [ ] **Tech stack** — (uses AI to extract data from timesheet PDFs; prompts are tunable)
- [ ] **Hosting** — where it runs + environment URLs. The **pipeline** stage is a **separate** app from Texco Tools.
- [ ] **Domain & DNS**
- [ ] **Database** — draws from a **timesheet** DB and a **lines** DB
- [x] **Authentication / access** — permissions are **separate from JobPac** access. The permission
  data exists in the DB but there is **no admin UI page** to manage it yet → Jonathan needs admin
  access to see all screens ([[runbook]]).
- [x] **Integrations** — **JobPac** (posts/ingests timesheets; transaction definitions + payroll
  rates table are the source of allowances/rates), **HiBob/"Bob"** (leave draw-down, tax scale,
  salary sacrifice), **Email** (timesheet PDF ingest), **AI** (extracts timesheet data).
- [ ] **Deployment**
- [ ] **Backups** / **Recovery** / **Secrets**
- [ ] **Known issues / tech debt** — RDO time not read correctly yet; several checks are WIP (see roadmap)
- [ ] **Risks** — **institutional-knowledge risk**: payroll rules/nuances live largely in one person's
  head; flagged as a top risk → [[handover]]
- [ ] **Quick wins**

## Workflow (the tool, end to end)
1. **Timesheet entry** — email comes in → extract PDF → split multi-person PDFs → pull job/JobPac code
   (sometimes blank, enter manually) → check job numbers + hours → summary shows which employees are
   still missing a timesheet.
2. **Review** — check/adjust hours & allowances; some fields free-type/editable (orange = editable,
   red line = overwritten/customised and persists), bottom section to be fully locked/automated.
3. **Reconcile** — post ("ingest") timesheets into JobPac (reversible/rollback); validates the run
   against the pre-pro report and against the manual run.
4. **Salary** — salary pay-run review + checks; approve → validate ABA → "marked as approved" / done.
5. **Pipeline → File → ABA** — mostly upcoming/not built; "file" would output the month-end reports.

## Key concepts / glossary
- **RDO** (Rostered Day Off) — **RDO accrual = 10% of OT/OTE hours** (normal time, sick leave, training
  days, leave — anything with super/OTE ticked). RDO is paid at **7.2 hours, not 8** (confirmed).
- **OTE** — Ordinary Time Earnings (super basis). **Pre-pro** — pre-processing report payroll reconciles against.
- **Transaction definition** — the source of truth for allowances, linked to an employee's **group code**.
- **Payroll rates table** — effective-dated source of rates (rates shown elsewhere are validation-only).
- **Site allowance** — contract-sum based (small/med/large) via the **EBA** table; override for combined
  contract sums (e.g. China Hall). **Demo** allowance *replaces* site; **asbestos** is paid *on top*.
  **Productivity** allowance is a flat **$4** (always paid).
- **Column T** — the JobPac pivot payroll always checks. **Poke** — notification/nudge to chase approvers.
- **Incolink / Cbus** — construction industry entitlements / super funds (must be apportioned to the job).

## Decisions (from the walkthrough)
- RDO accrual = 10% of OT/OTE hours; RDO paid at 7.2h (not 8) — confirmed.
- Demo replaces site allowance; asbestos on top; **no allowances at all on RDOs**. Productivity = flat $4.
- All allowances must come from the **transaction definition** (via group code); all rates from the
  **payroll rates table** (effective-dated). Shown rates are validation-only.
- Review screen bottom section fully locked/automated (except adjustments); overwrites flagged red.
- Pay-run numbering: **don't auto-generate** (off-cycle payments + reversals break sequence) — surface
  a confirmation of the pay-run number at approval instead.
- Allowances & deductions stay **manual** for the interim.

## Roadmap / action items
Work items are tracked as tickets in [[backlog]] (source: [[2026-07-23-payroll]]). Open payroll tickets:
- **High:** [[payroll-leave-drawdown-check]] · [[payroll-rdo-accrual-check]] · [[payroll-tax-checks]] · [[payroll-salary-review]] · [[payroll-approver-poke]]
- **Med:** [[payroll-apportionment-column]] · [[payroll-leave-job-costing-check]] · [[payroll-prevpay-columnt]] · [[payroll-rdo-calendar]] · [[payroll-salary-sacrifice-bob]] · [[payroll-rdo-hours-formula]]
- **Low:** [[payroll-km-reimbursement-field]] · [[payroll-rollback-terminology]]

**Payroll-team tasks (not dev tickets)** → [[next-actions]]: send site-allowance bands to Dev; build the
master allowance import (all projects × allowances, incl. NSW site codes, confirm NTA in the transaction
table); run some site-allowance payments; run weekly **in parallel** with the tool next week.

## Open / to verify
- Public-holiday treatment on RDOs (Dev to check what it posts).
- Whether the salary "date" output should feed the period close.
- Bob vs JobPac vs timesheet three-way hours check — Dev to confirm current logic.
- What the folders/spreadsheets on the server are → [[open-questions]].

Related: [[audit]] · [[people]] · [[handover]] · [[open-questions]]
