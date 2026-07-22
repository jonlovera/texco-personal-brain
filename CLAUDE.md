# CLAUDE.md — vault conventions

Personal knowledge vault for Jonathan Lovera, Texco's first software developer (acting as a
de-facto CTO over internal tools, no dev team). Plain markdown, read in Obsidian.
**Keep everything lightweight** — Jonathan captures, Claude curates.

## Start here (if the vault feels empty or you're unsure what to do)

1. In today's `1-daily/` note, list every system / app / script you can name (one line each), then
   run `/digest` — it populates `3-systems/audit.md`.
2. Pick the most critical system, book a walkthrough with Ryan/Brok, dump what you learn → `/digest`
   fills that `3-systems/<app>.md` checklist.
3. Log access needs as they come up (they land in `4-notes/runbook.md`) and unknowns in
   `4-notes/open-questions.md`. Work `3-systems/handover.md` in parallel — it's the highest risk.

## Structure

Folders are **numbered** to force a deliberate order in Obsidian.

```
CLAUDE.md                   # this file
1-daily/                    # Jonathan's daily brain-dumps — the ONLY thing he writes by hand
  _template.md · YYYY-MM-DD.md
2-updates/                  # non-technical executive rollups (each rolls up the level below)
  1-weekly/    _template.md · YYYY-Www.md
  2-monthly/   _template.md · YYYY-MM.md
  3-quarterly/ _template.md · YYYY-Q#.md
3-systems/                  # everything about our software (audit like a CTO)
  audit.md                  #   THE systems index: inventory tracker + cross-cutting infra checklist
  _template.md              #   per-system inventory checklist — copy to 3-systems/<app>.md
  handover.md               #   continuity checklist: capture Ryan & Brok's tribal knowledge
  <app>.md                  #   one note per system (texco-tools.md, taxisoft.md, ...)
4-notes/                    # Jonathan's running logs + reference docs
  runbook.md                #   accounts, access requests, setup steps, "ask X for Y" friction
  open-questions.md         #   things to follow up on (checkbox list)
  decisions.md              #   decisions + the reasoning behind them
  people.md                 #   who's who / who owns what (work side)
  ideas.md                  #   ideas/opportunities backlog (→ Wins when shipped)
  next-actions.md           #   commitments to do + what I'm waiting on
  baseline.md               #   current manual effort / "before" metrics (ROI denominator)
  technology-strategy-2026-2028.md · naming-conventions.md   #   strategy blueprint + conventions
5-private/                  # personal/private notes — content NEVER leaves here (see Working rules)
  team.md · scratch.md
.claude/commands/           # project slash commands: /digest /weekly /monthly /quarterly
```

Five folders, one question each: `1-daily/` = *what I captured*; `2-updates/` = *what I tell execs*;
`3-systems/` = *what we have & how it works*; `4-notes/` = *my logs & reference*; `5-private/` =
*personal*. (Numbering is display-only — `[[wiki-links]]` resolve by note name, not path.)

## How files grow (no sprawl)

`/digest` writes into a **fixed** set of notes plus **one file per real system** (bounded — maybe
5–10 total). What grows over time is one file per day (`1-daily/`) and one per period (`2-updates/`) —
just your journal and your reports, stamped/dated and inert. Nothing multiplies uncontrollably.

## Daily workflow (the whole point)

Jonathan **captures, Claude curates.** He only ever hand-writes in `1-daily/`; Claude does all the
extracting, expanding, and filing. **Never expect him to hand-edit the structured notes.**

1. During the day he brain-dumps into `1-daily/<today>.md` (freeform, under `## Log`).
2. He runs **`/digest`**.
3. Claude expands each jotting into a proper entry, distributes it per the filing table, and stamps
   the note's `## Processed` footer.
4. Ambiguous items: Claude asks live and files per his answer; anything unresolved stays under
   `## ⏳ Unfiled — needs a decision` in the day's note and is re-surfaced next `/digest`.

There is no `inbox.md` — the daily note (with its `⏳ Unfiled` section) is the only capture surface.

## Update cadence (executive rollups)

Each command rolls up the level below it into a non-technical update in `2-updates/…`, with
ready-to-send **CEO** (strategic, warm) and **CFO** (numbers-first) messages. Metrics that can be
derived are filled; numbers only Jonathan knows (hours/£ saved) stay `[bracketed]` — **confirm
before sending**. All feed the Success Metrics + Monthly/Quarterly Reviews in
`4-notes/technology-strategy-2026-2028.md`.

- **`/weekly`** → `2-updates/1-weekly/<YYYY-Www>.md` — rolls up the week's daily notes.
- **`/monthly`** → `2-updates/2-monthly/<YYYY-MM>.md` — rolls up the month's weeklies.
- **`/quarterly`** → `2-updates/3-quarterly/<YYYY-Q#>.md` — rolls up the quarter's monthlies; adds
  roadmap progress + team/resourcing needs.

**Never surface `5-private/` content in any exec update.**

## Filing rules (used by `/digest`)

| Item | Goes to |
|---|---|
| Account / access request, setup step, friction, "ask X for Y" | `4-notes/runbook.md` |
| Who owns what / a work contact / a role | `4-notes/people.md` |
| An open question or thing to follow up | `4-notes/open-questions.md` |
| A decision + its reasoning | `4-notes/decisions.md` |
| An idea / opportunity / "we could…" | `4-notes/ideas.md` |
| A task / commitment / "waiting on…" | `4-notes/next-actions.md` |
| How long a manual process takes / current pain | `4-notes/baseline.md` |
| Detail about one app/system (incl. deploys, fixes, quirks, setup) | `3-systems/<app>.md` (copy `3-systems/_template.md`) + update `3-systems/audit.md` |
| Cross-cutting infra (Coolify, DNS, backups, GitHub, Bitwarden, O365, CI) | `3-systems/audit.md` |
| Continuity / who-can-grant-access / tribal knowledge | `3-systems/handover.md` |
| Personal detail about a colleague (likes, family, pets) | `5-private/team.md` |

## Conventions & working rules

- **Filenames:** lowercase-kebab `.md`; folders numbered + lowercase. Link notes with `[[wiki-links]]`
  (Obsidian resolves by note *name*, not path — so moving a note between folders is safe, but
  *renaming* it breaks links, which must then be updated).
- **`5-private/` is confidential.** You MAY file clearly-personal colleague details *into*
  `5-private/team.md`. NEVER move content *out of* `5-private/` into shared notes, and never surface
  private content in summaries or reports.
- **Never invent facts** — expand only from what Jonathan actually wrote; otherwise ask or leave
  it under `## ⏳ Unfiled`.
- **Don't invent new folders or top-level notes** without asking. (A new `3-systems/<app>.md` from
  the template is expected, not a new folder.)
