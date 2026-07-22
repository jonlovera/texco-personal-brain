---
description: Roll up the quarter's monthly updates into a board-level quarterly review + CEO/CFO messages
argument-hint: "[quarter, e.g. 2026-Q3 — defaults to the current quarter]"
---

Produce Jonathan's **quarterly** executive review — the board-level view. Read `CLAUDE.md` first.
Non-technical, outcome-focused. Copy `2-updates/3-quarterly/_template.md`.

## Which quarter
- Argument (`$ARGUMENTS`) sets it (e.g. `2026-Q3`); otherwise use the current quarter.
- Output: `2-updates/3-quarterly/<YYYY-Q#>.md`. Update it if it already exists.

## Gather the inputs
1. **Monthly updates** for the quarter: `2-updates/2-monthly/*.md` (the 3 months). If a month wasn't
   rolled up, fall back to that month's weekly files in `2-updates/1-weekly/`.
2. **Roadmap:** the 24-month roadmap in `4-notes/technology-strategy-2026-2028.md` — compare what was
   planned for this quarter vs what was delivered.
3. **Discovery:** `3-systems/audit.md`. **Risks:** `3-systems/handover.md` + the strategy doc's risk register.
4. **Wins & opportunities:** `4-notes/ideas.md`. **Decisions:** `4-notes/decisions.md`. **ROI:** `4-notes/baseline.md`.

## Draft
- Fill the template in plain business language. Metrics show the quarter **and cumulative-to-date**.
- Lead the doc with **roadmap progress** (planned vs delivered vs slipped).
- Include **team & resourcing needs** — this is where the case for hiring/budget is made.
- Auto-fill derivable numbers; bracket the rest. Answer the Quarterly Review questions from the
  strategy doc (roadmap progress / savings delivered / time saved / new opportunities / team needs /
  exec priorities).
- Write both exec messages (CEO strategic; CFO cumulative-savings/ROI + any budget ask).

## Rules
- Never invent numbers — unknowns stay bracketed. Never surface anything from `5-private/`.

## Report back
Give the draft's path and a bullet list of every `[placeholder]` needing a real number.
