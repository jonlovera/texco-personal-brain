# Systems Audit — what we have

> The master tracker for discovering every internal system. One row per system; drill into each
> via its own note. This is the source of truth for what systems exist; risks/unknowns live in
> [[open-questions]] and [[handover]]. Start a new system note by copying [[_template]].
> Docs status: ⬜ not started · 🟡 in progress · ✅ documented

## Inventory tracker

| System | Owner | Criticality | Repo | Hosting | Docs |
|---|---|---|---|---|---|
| [[texco-tools]] | Ryan/Brock | important | ? | Coolify? | 🟡 |
| [[textrack]] | Ryan/Brock | critical | (within Texco Tools) | via Texco Tools | 🟡 |
| [[payroll]] | Ryan/Brock (Michel VO — payroll lead) | critical | ? | separate (pipeline app) | 🟡 |
| [[taxisoft]] | ? | ? | AccountsPayable | ? | 🟡 |
| [[texco-learn]] | ? | minor | ? | learn.texco.net.au | ⬜ |
| [[the-close]] | ? | ? | ? | theclose.internal.texco.net.au | ⬜ |
| jobpac (external) | Finance / vendor | critical | — vendor ERP | vendor | ⬜ |
| hibob "Bob" (external) | HR / vendor | important | — vendor HR | vendor | ⬜ |
| texco main website (external) | Marketing / external provider | minor | — external | external provider (being rebuilt) | ⬜ |
<!-- Add rows as you discover more: systems, scripts, cron jobs, integrations, one-off tools.
     JobPac = ERP / financial source of truth; HiBob = HR. Both are external systems our apps read from. -->

## Cross-cutting infrastructure (spans all systems)

Things that aren't one app but underpin everything — audit these once.

- [ ] **Hosting — Coolify:** how it's accessed, managed via terminal, and updated ([[open-questions]])
- [ ] **Backups — AWS/S3:** Coolify backs up to an S3 bucket — what's included, and the restore process
- [ ] **DNS — Cloudflare:** who manages it; the "split DNS" task
- [ ] **Source control — GitHub org:** full repo list, who has admin/owner
- [ ] **Secrets — Bitwarden:** vault structure, who's admin
- [ ] **Email / identity — Office 365:** admin, how apps use it (e.g. quote emails)
- [ ] **CI/CD:** none on dev today (manual pulls) — a gap to design a fix for
- [ ] **AI tooling (ChatGPT / Claude):** access policy (who gets which), current spend, and the right
  budget — only ~5 of ~220 staff have access; Dee (CFO) is cost-conscious ([[open-questions]], [[ideas]])

## How to use
1. For each system, copy [[_template]] → `systems/<app>.md` and work the checklist.
2. Update the row's **Docs** status here (⬜ → 🟡 → ✅) as it fills in.
3. Log every unknown in [[open-questions]] and every decision in [[decisions]].
4. In practice: just dump what you learn into your daily note and run `/digest` — it lands here.

Related: [[people]] · [[handover]]
