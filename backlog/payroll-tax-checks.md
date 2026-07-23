# [payroll] PAYG / new-starter tax-scale + rate-code checks

**System:** payroll · **Priority:** High · **Status:** todo
**Source:** [[2026-07-23-payroll]] · **Trello:** —

## 📋 Paste to Trello
```
[payroll] PAYG / new-starter tax-scale + rate-code checks
Add a PAYG/tax-scale check for new starters (they often come in without tax/pay rate set) and a
rate-code mismatch check (the rate CODE, not the $ value).
Acceptance: flags new starters missing tax setup; flags rate-code mismatches.
Context: vault 2026-07-23-payroll
```

## Detail
**Problem:** New starters frequently lack tax scale / pay rate on first run; rate-code errors slip through.
**Proposed:** Validate PAYG/tax scale (using Bob's expected scale) and call out rate-code mismatches automatically.
**Acceptance:**
- [ ] New-starter PAYG/tax-scale gap flagged
- [ ] Rate-code (not $) mismatch flagged

Related: [[payroll]] · [[backlog]]
