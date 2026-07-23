# [payroll] Timesheet-approver field + poke + exclude-from-pay-run

**System:** payroll · **Priority:** High · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] Timesheet-approver field + poke + exclude-from-pay-run
Keep "line manager" but add a "timesheet approver" field with a poke (email + SMS, since people ignore
email/Teams), CC'd to the employee. Add a permission-gated "you're about to be pulled from the pay
run" SMS button.
Acceptance: approver poke fires via email+SMS, CCs employee; exclude-from-run SMS is permission-gated.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** The approver poke doesn't reliably work; email/Teams get ignored; no way to warn someone they'll be excluded.
**Proposed:** Add timesheet-approver as a first-class field, poke via email+SMS, CC the employee, and a gated "exclude from pay run" SMS.
**Acceptance:**
- [ ] "Timesheet approver" field (alongside line manager)
- [ ] Poke via email + SMS, CC employee
- [ ] Permission-gated "about to be pulled from pay run" SMS

Related: [[payroll]] · [[backlog]]
