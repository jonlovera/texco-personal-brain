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

## Meetings (transcripts in a daily note)
If a daily note contains a **meeting/walkthrough transcript** (typically a second `#`-level heading, or
a clearly-verbatim conversation):
- Create/update a meeting note `6-meetings/YYYY-MM-DD-<topic>.md` with sections: **Attendees ·
  Summary · Topics discussed · Decisions (with reasoning) · Action items (→ tickets) · Transcript**.
- **Move** the transcript out of the daily note into the meeting note's `## Transcript` section, and
  replace it in the daily note with a one-line link (`> 📋 Distilled → [[YYYY-MM-DD-topic]]`). *Exception:*
  don't hand-retype a long verbatim record if there's any risk of corrupting it — instead keep it in the
  daily note and link to it from the meeting note (as done for the 07-21 / 07-23 retro-fill).
- Add a row to `6-meetings/meetings.md` (newest first).
- Turn the meeting's action items into **backlog tickets** (see below), each back-linking to the meeting note.

## What to do (per un-ticked line)
1. Break the un-ticked Log / Unfiled bullets into atomic items.
2. **Expand** each terse jotting into a proper, complete entry — full sentences, context filled
   in from what you know. Don't just copy-paste his shorthand; write it up well.
3. File each item into the right note per the CLAUDE.md routing table:
   - access / setup / friction → `4-notes/runbook.md`
   - a system's detail (incl. deploys, fixes, quirks) → `3-systems/<app>.md` (create from
     `3-systems/_template.md` if the app has no note yet) AND update the row + Docs status in `3-systems/audit.md`
   - **committed work to build** (an agreed action item, "we're doing X", a clear decision to build) →
     a **backlog ticket** (see "Backlog tickets" below), NOT a checklist inside the system note. The
     system note links to its tickets. **Only committed work** — see the ideas/requests rule below.
   - **an idea / opportunity / "we could…" / something someone *asked* for but isn't yet committed** →
     `4-notes/ideas.md` (with a Source + status: `💡 idea` / `🙋 requested`). **Do NOT make it a ticket.**
     It becomes a ticket only when Jonathan explicitly says to build it (see "Promotion" below).
   - cross-cutting infra (Coolify/DNS/backups/GitHub/Bitwarden/O365/CI) → `3-systems/audit.md`
   - who-owns-what / work contacts / roles → `4-notes/people.md`
   - questions / unknowns → `4-notes/open-questions.md`
   - decisions + reasoning → `4-notes/decisions.md`
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
8. **Update the indexes incrementally** (derived views, but do NOT sweep every file):
   - `backlog/backlog.md` — **only** add/update the rows for tickets you created or changed this run.
     Discover existing tickets by **filename** (`ls backlog/*.md` / glob) — never by reading their bodies;
     the `<system>-<slug>` filename is the dedup key. **Do not read the whole backlog** to rebuild it —
     the index is the read surface; ticket bodies are opened only when working a specific ticket. When a
     ticket's Status becomes `in-trello`/`done`, **move its file to `backlog/archive/`** and move its
     board row to the compact archived-pointer list (it leaves the active board).
   - `6-meetings/meetings.md` — add/update the row for any meeting note touched this run (newest first).
9. **Refresh `0-home.md`** (the vault's front-door dashboard). After filing, re-derive its at-a-glance
   sections from their source notes and update the `_Last refreshed:_` stamp to the latest day swept:
   - `## 🖥 Systems at a glance` ← the inventory rows + Docs status in `3-systems/audit.md`
   - `## 📌 This week / now` ← `4-notes/next-actions.md` (To do + Waiting on) + the latest `2-updates/1-weekly/` note
   - `## ⚠️ Risks & handover` ← `3-systems/handover.md` state + the open-question count in `4-notes/open-questions.md`
   - `## 🎫 Backlog` ← counts from `backlog/backlog.md` (# ready / # in Trello / # done) + recent meetings from `6-meetings/meetings.md`
   - `## 💡 Ideas & wins` ← the table in `4-notes/ideas.md`
   These are **derived views** — regenerate them from the sources; don't treat `0-home.md` as a source of
   truth. Leave the static `## 🗺 Everything (index)` and `## Legend` sections alone (only add a link if
   you created a brand-new note this run). **Never link or surface `5-private/` content in `0-home.md`.**
   The refresh is a pure regeneration, so it's safe on every re-run.

## Backlog tickets (committed work to build)
Each work item is **one file** `backlog/<system>-<slug>.md` (the durable spec), never a checklist inside
a system note. Vault = the spec + context; **Trello = the live tracker**. **Only committed work becomes a
ticket** — ideas/requests stay in `4-notes/ideas.md` until promoted.
- **Structure:** `# [<system>] <Title>`; a header line with **System · Priority (High/Med/Low) · Status
  (todo/ready/in-trello/done) · Source (meeting/day link) · Trello (link once copied)**; a fenced
  **`## 📋 Paste to Trello`** block (title + summary + acceptance + `Context: <source>` — so the card is
  self-contained); then `## Detail` (Problem · Proposed · Acceptance criteria · Notes/edge cases).
- **Expand richly** — pull the reasoning and specifics from the meeting/day so the ticket stands alone.
- **Keying / idempotency:** the `<system>-<slug>` filename is the key. If a ticket already exists, update
  it; never create a duplicate. **Respect status:** never recreate or downgrade an `in-trello`/`done` ticket
  (Jonathan flips a ticket to `in-trello` + adds the card link when he copies it to Trello; `done`/`in-trello`
  files may live in `backlog/archive/`).
- Link each ticket back to its source ([[meeting]] or [[day]]) and its system note; the system note links to its open tickets.
- **Archive on close:** when a ticket is `in-trello` or `done`, move the file to `backlog/archive/` so
  the active `backlog/` folder holds open work only (kept for provenance, never deleted).

## Promotion — idea/request → ticket (deliberate only)
- **Never auto-promote.** A row in `4-notes/ideas.md` (idea or `🙋 requested`) becomes a ticket **only
  when Jonathan explicitly says to build it** (e.g. "make X a ticket", "let's build the invoice-export
  speedup"). Speculative "we could…" items and things people merely asked about stay in `ideas.md`.
- On promotion: create the `backlog/` ticket (expanded from the idea's context), set the idea's Status
  to `🎫 ticketed → [[<ticket>]]`, and link both ways. This keeps the backlog = committed work only.

## Decisions — capture the *why*
When filing a decision to `4-notes/decisions.md`, always include **Decision · Context · Reasoning ·
Status** *and a source link* to the meeting/day. When filing a task to `4-notes/next-actions.md`, carry
its **concrete spec inline** (not just a title) and link the ticket if one exists.

## Rules
- `5-private/` is confidential: you MAY file personal colleague details *into* `5-private/team.md`,
  but NEVER move content *out of* `5-private/` into shared notes, and never surface private content
  in summaries.
- Never invent facts. If something is unclear, ask Jonathan or leave it in `## ⏳ Unfiled` — never guess.
- Keep the structured notes clean and consistent; Jonathan should never need to hand-edit them.

## Report back
End with a concise summary: which days you swept, what you filed and where, any **meeting notes** and
**backlog tickets** created (with counts), what's still in `## ⏳ Unfiled` awaiting his decision, any new
`[[system]]` notes you created, and confirm you regenerated the indexes and refreshed `0-home.md`.
