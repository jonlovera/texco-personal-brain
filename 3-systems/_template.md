# System Inventory — <NAME>

> Copy this file to `systems/<app>.md` and work the checklist. Goal: know *everything* about
> this system. Don't stress about filling it in by hand — dump what you learn into your daily
> note and `/digest` will expand it in here. Status legend: ⬜ not started · 🟡 in progress · ✅ done

## Snapshot
- **Purpose / who uses it:**
- **Owner / who knows it:**
- **Business criticality:** critical / important / minor

## Discovery checklist
- [ ] **Repo** — where the code lives (GitHub org, repo name)
- [ ] **Tech stack** — language, framework, notable libraries
- [ ] **Hosting** — where it runs (Coolify? a server?) + every environment URL (local / dev / qa / prod)
- [ ] **Domain & DNS** — domains it uses, managed where (Cloudflare?)
- [ ] **Database** — type, where it lives, rough size
- [ ] **Authentication** — how login works, SSO?
- [ ] **Integrations** — other Texco systems, Office 365, external APIs
- [ ] **Deployment** — how a change reaches prod (manual pull? CI?)
- [ ] **Backups** — what's backed up, where (AWS/S3?), how often
- [ ] **Recovery** — has a restore been tested? how long would it take?
- [ ] **Secrets / credentials** — where stored (Bitwarden?)
- [ ] **Access** — who has admin, who can grant it
- [ ] **Known issues / tech debt**
- [ ] **Risks** — bus factor, security gaps, single points of failure
- [ ] **Quick wins** — cheap improvements spotted

## Notes

Related: [[audit]] · [[people]] · [[handover]]
