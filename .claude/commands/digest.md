---
description: Sweep recent daily notes and file everything new into the vault
argument-hint: "[date YYYY-MM-DD — omit to sweep the last ~7 days]"
---

You are running the digest for Jonathan's Texco knowledge vault. Your job is to do all
the heavy lifting so he only ever has to brain-dump. Read `CLAUDE.md` first for the current
structure and rules.

## Which notes to process
- If an argument was given (`$ARGUMENTS`), process just that day: `1-daily/$ARGUMENTS.md` (any age).
- Otherwise **sweep every daily note dated in the last ~7 days** (`1-daily/YYYY-MM-DD.md`).
- In each note, only process `## Log` / `## ⏳ Unfiled` bullets that do **NOT** already end in `✅`.
  A trailing `✅` means the line is already filed — skip it. This makes re-runs safe (no double-filing).

## Idempotency — the ✅ tick (important)
- `✅` at the end of a line is the source of truth for "already filed". Never re-file a `✅` line.
- After you file a line, **append ` ✅`** to that exact line in the daily note.
- If Jonathan **edited a line and wants it re-filed**, he removes its `✅`; treat un-ticked lines as new.
- So: new lines and edited (un-ticked) lines get filed; ticked lines are left alone.

## What to do (per un-ticked line)
1. Break the un-ticked Log / Unfiled bullets into atomic items.
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
5. **Append ` ✅` to each line once you've filed it** (see Idempotency above).
6. **Ambiguous items:** first try to resolve them by asking Jonathan directly in this session and
   file them per his answer (then tick them ✅). Only if unresolved, leave them un-ticked under the
   day's `## ⏳ Unfiled — needs a decision` section, and re-surface still-open Unfiled items from the
   swept days so they don't get lost.
7. Update each processed day's `## Processed` footer with a short human-readable summary (date + what
   went where). This is just an audit trail — the ` ✅` ticks are what actually prevent double-filing.

## Rules
- `5-private/` is confidential: you MAY file personal colleague details *into* `5-private/team.md`,
  but NEVER move content *out of* `5-private/` into shared notes, and never surface private content
  in summaries.
- Never invent facts. If something is unclear, ask Jonathan or leave it in `## ⏳ Unfiled` — never guess.
- Keep the structured notes clean and consistent; Jonathan should never need to hand-edit them.

## Report back
End with a concise summary: which days you swept, what you filed and where, what's still in
`## ⏳ Unfiled` awaiting his decision, and any new `[[system]]` notes you created.
