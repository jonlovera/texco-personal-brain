# Runbook / Friction Log

> Every account, access request, setup step, and "you have to ask X for Y" thing hit
> while getting set up — written so the next hire can just follow it. When you hit
> friction, log it here with enough detail that someone else could resolve it without you.

## Access & Accounts
<!-- System · who to ask · how the request was made · status. One row per thing you needed access to. -->

- [ ] Admin on dev servers — https://qa.tools.internal.texco.net.au/login and https://dev.transfer.texco.net.au
- [ ] Access to https://dev.ap.internal.texco.net.au/
- [x] Bitwarden / Coolify
- [ ] AWS account (Coolify backups)
- [ ] GitHub Organization — admin access (currently Ryan has it)
- [ ] Cloudflare — DNS settings access (currently Ryan has it)
- [ ] Jobpac — (currently Ryan has it)
- [ ] Trello
- [ ] Access to current documentation – docs live in Github but they are very poor. most of the docs live in Ryan's and Brock's brains
- [ ] Access to the DEV server – Ryan gave me access to the Dev server
- [ ] Access to the PROD server – Ryan should eventually give me access
- [ ] **Payroll tool — admin access** — permissions exist in the DB but there's no UI page; need admin to see all screens (see [[payroll]])
- [ ] **Composio** — used at the company; I don't have access and don't know what's in it (see [[open-questions]])

## Setup Steps
<!-- Ordered steps to a working dev environment. Link the system's own note (e.g. [[texco-tools]]). -->

- [x] Copy dev DB into local mysql
- [x] Get a database backup
- [x] Laptop + the 3 core repos (Texco Tools, TexTrack, TaxiSoft) running locally

See [[texco-tools]] for the full local Docker setup recipe.

## Good-to-know tools (used at Texco)
- **Bluebeam** — PDF editor (good for architects)
- **Adobe** — PDF
- **Granola** — meeting recording / transcription

## Gotchas / "Ask X for Y"
<!-- Undocumented tribal knowledge: what wasn't obvious, who unblocked it, how it was resolved. -->

- **Server / project file access:** access to all projects has been **revoked company-wide** — everyone
  must now request access to **each job independently**. IT owns this in theory, but **Brock** is the
  one who communicates it to the team, so people go to him in practice (a key-person dependency → [[handover]]).

Related: [[people]] · [[open-questions]]
