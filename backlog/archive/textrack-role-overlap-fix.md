# [textrack] Prevent overlapping assignees on the same role (TT-3)

**System:** textrack · **Priority:** Med · **Status:** done
**Source:** [[2026-07-21-textrack]] · **Trello:** — · **Shipped:** 2026-07-22 (see [[texco-tools]] deploy log)

## 📋 Paste to Trello
```
[textrack] Prevent overlapping assignees on the same role (TT-3) — DONE
Two people could be assigned to the same role over the same dates (nonsensical data). Fixed so a role
can't have overlapping assignees; sequential hand-overs (one ends, next begins) remain allowed.
Context: vault 2026-07-21-textrack
```

## Detail
**Problem:** You could assign someone directly over the top of an existing assignee on the same role
with overlapping dates — producing nonsensical capacity data. Sequential hand-overs (e.g. maternity
cover: Lara ends 30 Apr, Nick starts 1 May) are legitimate and must stay allowed.
**Outcome:** Fixed as **TT-3**, deployed to prod 2026-07-22.
**Acceptance:**
- [x] Overlapping same-role assignments prevented
- [x] Sequential (non-overlapping) hand-overs still allowed

Related: [[textrack]] · [[backlog]]
