# [payroll] RDO working-hours formula (consistent 7.2)

**System:** payroll · **Priority:** Med · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] RDO working-hours formula (consistent 7.2)
RDO is paid at 7.2 hours (not 8). Build the working-hours formula so it's consistent — currently it
shows a mix of 7.2 and 8. Also fix the RDO start date not pulling from JobPac.
Acceptance: RDO consistently paid at 7.2h; start date reads from JobPac.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** RDO hours are inconsistent (7.2 vs 8) and the start date isn't coming from JobPac.
**Proposed:** A formula that always resolves RDO to 7.2h; source the start date from JobPac.
**Acceptance:**
- [ ] RDO paid at 7.2h consistently
- [ ] RDO start date sourced from JobPac

Related: [[payroll]] · [[backlog]]
