---
description: Extract a day's brain-dump note and file everything into the vault
argument-hint: "[date, e.g. 2026-07-22 — defaults to today]"
---

You are running the daily digest for Jonathan's Texco knowledge vault. Your job is to do all
the heavy lifting so he only ever has to brain-dump. Read `CLAUDE.md` first for the current
structure and rules.

## Which note to process
- If an argument was given (`$ARGUMENTS`), process `1-daily/$ARGUMENTS.md`.
- Otherwise process today's note, `1-daily/<today>.md`. If it doesn't exist, say so and stop.
- Only process the `## Log` and `## ⏳ Unfiled` sections. Skip anything already summarised under
  the `## Processed` footer — that material is done.

## What to do
1. Read the daily note and break the Log (and any Unfiled items) into atomic items.
2. **Expand** each terse jotting into a proper, complete entry — full sentences, context filled
   in from what you know. Don't just copy-paste his shorthand; write it up well.
3. File each item into the right note per the CLAUDE.md routing table:
   - access / setup / friction → `4-notes/runbook.md`
   - a system's detail (incl. deploys, fixes, quirks) → `3-systems/<app>.md` (create from
     `3-systems/_template.md` if the app has no note yet) AND update the row + Docs status in `3-systems/audit.md`
   - cross-cutting infra (Coolify/DNS/backups/GitHub/Bitwarden/O365/CI) → `3-systems/audit.md`
   - who-owns-what / work contacts / roles → `4-notes/people.md`
   - questions / unknowns → `4-notes/open-questions.md`
   - decisions + reasoning → `4-notes/decisions.md`
   - ideas / opportunities / "we could…" → `4-notes/ideas.md`
   - tasks / commitments / "I need to…" / "waiting on…" → `4-notes/next-actions.md`
   - observations of current manual effort / how long a process takes → `4-notes/baseline.md`
   - continuity / access-granting / tribal knowledge → `3-systems/handover.md`
   - clearly-personal colleague details (likes, family, pets) → `5-private/team.md`
4. Preserve `[ ]`/`[x]` checkbox status where it exists; add cross-links (`[[wiki-links]]`) between
   related entries.
5. **Ambiguous items:** first try to resolve them by asking Jonathan directly in this session and
   file them per his answer. Only if unresolved, leave them under the day's `## ⏳ Unfiled — needs a
   decision` section (do NOT stamp those as processed). Also re-surface any still-open Unfiled items
   from recent daily notes so they don't get lost.
6. Stamp the daily note's `## Processed` footer: the date processed and a short list of what was
   filed where. This prevents double-filing on re-runs.

## Rules
- `5-private/` is confidential: you MAY file personal colleague details *into* `5-private/team.md`,
  but NEVER move content *out of* `5-private/` into shared notes, and never surface private content
  in summaries.
- Never invent facts. If something is unclear, ask Jonathan or leave it in `## ⏳ Unfiled` — never guess.
- Keep the structured notes clean and consistent; Jonathan should never need to hand-edit them.

## Report back
End with a concise summary: what you filed and where, what's still in `## ⏳ Unfiled` awaiting his
decision, and any new `[[system]]` notes you created.
