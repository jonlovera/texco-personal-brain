---
description: Roll up the week's daily notes into a non-technical executive update + CEO/CFO messages
argument-hint: "[ISO week, e.g. 2026-W30 — defaults to the current week]"
---

You are producing Jonathan's weekly **executive** update for his Texco knowledge vault. Read
`CLAUDE.md` first. The audience is non-technical executives — write like a CTO explaining outcomes,
with **no technical jargon**. Copy `2-updates/1-weekly/_template.md` for the structure.

## Which week
- If an argument was given (`$ARGUMENTS`), target that ISO week (e.g. `2026-W30`).
- Otherwise target the current ISO week. Compute the Mon–Sun date range for the header.
- Output file: `2-updates/1-weekly/<YYYY-Www>.md`. If it already exists, update it rather than duplicating.

## Gather the inputs
1. **Daily notes** for that week (Mon–Sun): read each `1-daily/<date>.md` — its `## Log` and
   `## Processed` sections are the raw material.
2. **Discovery progress:** `3-systems/audit.md` — how many systems exist and their Docs status
   (⬜/🟡/✅) → "x of ~N documented".
3. **Delivery:** the `## Changes / deploy log` in each `3-systems/<app>.md` (fixes/features/deploys
   dated within the week); count issues resolved.
4. **Risk reduction:** `3-systems/handover.md` — what bus-factor knowledge got captured; backup/access status.
5. **Decisions:** `4-notes/decisions.md` — anything logged this week.
6. **Ideas shipped/moving:** `4-notes/ideas.md` — rows that reached ✅ shipped (→ Wins) or advanced status.
7. **Next actions:** `4-notes/next-actions.md` — what got done / what's still committed.
8. **Baseline:** `4-notes/baseline.md` — use to ground the Time & money numbers (before → after).

## Draft the update
- Fill the template in **plain business language, but name the actual tools/products** — e.g.
  "rolled out **Marker.io** for in-app feedback, posting to **Trello**". Name Marker.io, Trello,
  JobPac, ChatGPT/Claude, etc.; gloss each in a few plain words the first time. Don't be vague ("a tool").
- **Auto-fill only metrics you can derive** from the notes (systems documented, # shipped, # issues,
  feedback count). For anything you cannot compute (hours saved, £ saved/avoided), **leave the
  `[bracket]` placeholder** — never invent a number.
- Write both messages in their distinct voices, addressed by name:
  - **Jack Bull** (Director — the exec Jonathan reports to) — strategic, warm: headline outcome +
    why it matters + momentum, one risk being managed (reassuring), any ask (or none).
  - **Dee** (CFO) — numbers-first: efficiency/cost/continuity, any spend or savings, any ask (or none).
- **Discovery-phase framing (both messages):** while the audit is still early and metrics are mostly
  placeholders, be honest that we're mapping the systems — lead with leading indicators (systems
  mapped, momentum, risk reduced), and do NOT imply hard $ savings that don't exist yet.
- **CFO attention flag:** begin the CFO message with a one-line status. Plain language, ⚠️ **only**
  when an action/decision is genuinely needed (`> ⚠️ **This week: need a decision on [X].**`);
  otherwise `> **This week: no action needed.**` with no icon. No traffic light.

## Rules
- Never invent facts or numbers — unknowns stay bracketed placeholders.
- Never surface anything from `5-private/` in an exec update.
- Keep both messages short (a few sentences each) — they're meant to be sent as-is after Jonathan
  confirms the numbers.

## Report back
Give the draft's path and a bullet list of every `[placeholder]` that still needs a real number
before the messages can go out.
