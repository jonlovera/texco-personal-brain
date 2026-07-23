---
description: Roll up the month's weekly updates into a non-technical monthly exec update + CEO/CFO messages
argument-hint: "[month, e.g. 2026-07 — defaults to the current month]"
---

Produce Jonathan's **monthly** executive update. Read `CLAUDE.md` first. Audience is non-technical
executives — write like a CTO explaining outcomes, no jargon. Copy `2-updates/2-monthly/_template.md`.

## Which month
- Argument (`$ARGUMENTS`) sets the month (e.g. `2026-07`); otherwise use the current month.
- Output: `2-updates/2-monthly/<YYYY-MM>.md`. Update it if it already exists.

## Gather the inputs
1. **Weekly updates** for that month: `2-updates/1-weekly/*.md` whose week falls in the month — these
   are the primary source. If a week wasn't rolled up, fall back to that week's `1-daily/` notes.
2. **Discovery:** `3-systems/audit.md` (systems + statuses, month-end position).
3. **Wins & opportunities:** `4-notes/ideas.md` (status ✅ this month) and shipped items in each
   `3-systems/<app>.md` deploy log.
4. **Decisions:** `4-notes/decisions.md`. **ROI baseline:** `4-notes/baseline.md`.

## Draft
- Fill the template in plain business language. Show metrics **with the trend vs last month**.
- Auto-fill only derivable numbers; leave `[brackets]` for what you can't compute (hours/£ saved).
- Answer the Monthly Review questions from `4-notes/technology-strategy-2026-2028.md` (improved /
  learned / biggest saving / risks / opportunities / next month).
- Write both messages addressed by name: **Jack Bull** (Director — who Jonathan reports to; strategic
  & warm) and **Dee** (CFO; numbers-first). **Name the actual tools** (Marker.io, JobPac, etc.), never vague.

## Rules
- Never invent numbers — unknowns stay bracketed. Never surface anything from `5-private/`.
- Keep the messages short and send-ready after Jonathan confirms the numbers.

## Report back
Give the draft's path and a bullet list of every `[placeholder]` needing a real number.
