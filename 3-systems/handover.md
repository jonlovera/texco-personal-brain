# Continuity & Handover — capturing Ryan & Brock's knowledge

> Ryan and Brock hold most of the tribal context (they can grant Claude access, create/purchase
> domains, and know how every app really works). This checklist extracts that knowledge
> systematically before it's lost — the single biggest risk right now. Pair with [[audit]] for
> the systems detail and [[people]] for who-owns-what.

## Access & who-can-grant-what
<!-- For each: who can grant it, and how. The goal is that access no longer depends on one person. -->
- [ ] Claude access — who grants it, how
- [ ] Domains — who can create/purchase (which registrar? Cloudflare?)
- [ ] Server / Coolify admin — how access is granted
- [ ] GitHub org — owners, how to add members
- [ ] AWS account (backups) — how to get in
- [ ] Bitwarden — vault structure, who's admin
- [ ] Office 365 — admin
- [ ] **Server / project-file access** — job access is now per-job request (revoked company-wide). IT
  owns it, but **Brock** is the de-facto contact people go to → capture the proper process so it doesn't depend on him.

## Tribal knowledge to capture
<!-- Book sessions with Ryan/Brock and record them (Granola). One pass per app + the general stuff. -->
- [ ] Walkthrough of each app — recorded
- [ ] "Where the bodies are buried" — fragile things, manual steps, gotchas
- [ ] Undocumented cron jobs / scripts / scheduled tasks
- [ ] Vendor & support contacts per system
- [ ] Licences / renewals they track in their heads
- [ ] **Payroll rules & nuances** — largely in Michel VO's head (award/EBA edge cases, allowances, RDO
  logic). Flagged as a top risk: only one person knows it → get it documented in [[payroll]]

## Handover sessions log
<!-- Date · who · what was covered · what's still open -->

Related: [[audit]] · [[people]] · [[open-questions]]
