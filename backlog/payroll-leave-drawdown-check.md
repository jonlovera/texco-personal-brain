# [payroll] Leave/sick draw-down check at entry

**System:** payroll · **Priority:** High · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] Leave/sick draw-down check at entry
Add a sick/annual-leave draw-down check at the START of the timesheet-entry workflow, before the pay
cycle closes, so leave is ascribed in-cycle and we avoid manual Bob adjustments (double handling).
Acceptance: entry/review screen flags missing/late leave before cycle close; no retrospective manual adjustment.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** In Bob, if leave isn't ascribed to the pay cycle before it ends, it doesn't draw down the
balance — even entered retrospectively — so payroll must do a manual adjustment *plus* the entry (double handling).
**Proposed:** Surface a leave check at the *start* of the entry/review flow so it's caught before cycle close.
**Acceptance:**
- [ ] Leave discrepancies flagged on the entry/review screen
- [ ] Prompt to notify the employee / Marcus at that point
- [ ] In-cycle leave needs no manual Bob adjustment

Related: [[payroll]] · [[backlog]]
