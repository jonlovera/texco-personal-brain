# [payroll] RDO-accrual check vs pre-pro

**System:** payroll · **Priority:** High · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] RDO-accrual check vs pre-pro
Flag when RDO accrual ≠ 10% of OT/OTE hours, checked against the pre-pro RDO accrual — catches
mis-configured transaction definitions.
Acceptance: mismatch between computed 10% and pre-pro RDO accrual raises a flag.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** If a new transaction definition isn't set up properly, RDO accrual breaks silently.
**Proposed:** Compute 10% of OT/OTE hours (OTE = normal time, sick, training, leave) and compare to the pre-pro RDO accrual; flag differences.
**Acceptance:**
- [ ] Accrual computed as 10% of OTE hours
- [ ] Flag when it differs from pre-pro RDO accrual
- [ ] Pro-rata handled for sub-8-hour days

Related: [[payroll]] · [[backlog]]
