# [textrack] Resolve role-capacity vs assignee-capacity model

**System:** textrack · **Priority:** Med · **Status:** todo
**Source:** [[2026-07-21-textrack]] · **Trello:** —

## 📋 Paste to Trello
```
[textrack] Resolve role-capacity vs assignee-capacity model
Roles carry an expected capacity (e.g. PM = 40%) and assignees carry their own capacity — confusing and
double-tracked. Likely commit to role capacity flowing to the assigned person, but work through the
historic-data flow-on effects first.
Acceptance: single clear capacity model; historic capacities don't get wrongly backfilled.
Context: vault 2026-07-21-textrack
```

## Detail
**Problem:** A role has an expected capacity (PM ~40%) and the assignee has their own; users find the
two numbers confusing. But overall per-person capacity across projects is currently derived from the
*assignment* capacity, so changing it has flow-on effects.
**Proposed:** Likely use the role capacity passed to the current assignee — but design for the edge
cases first (see below) before changing.
**Acceptance:**
- [ ] One clear capacity model chosen
- [ ] Cross-project per-person capacity still correct

## Notes / edge cases
- If Lara was 50% and Nick takes over at 100%, Lara's *historic* capacity must not backfill to 100%.
- Same going forward if a 30%-er later takes over from Nick. This is why role/assignee were split.

Related: [[textrack]] · [[backlog]]
