# [payroll] "Costed to leave job incorrectly" check + force-back

**System:** payroll · **Priority:** Med · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] "Costed to leave job incorrectly" check + force-back to timesheet
Detect people costed to the leave job when they shouldn't be, and force it back to the timesheet.
Rule: if K-rate charge-out > 1 → flag; if pay rate = 0 it can go to the LB job.
Acceptance: mis-costed leave flagged red and correctable back to timesheet.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** Every payroll deals with people wrongly costed to the leave job (e.g. sick leave).
**Proposed:** A check that flags and force-corrects back to the timesheet; compare the leave entry in Bob vs JobPac.
**Acceptance:**
- [ ] Flag when K-rate charge-out > 1 (pay rate 0 → LB job)
- [ ] Force-back to timesheet available

Related: [[payroll]] · [[backlog]]
