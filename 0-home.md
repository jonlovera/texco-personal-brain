# 🏠 Texco — Home

> The front door to this vault: one place to see everything at a glance, then click through.
> The at-a-glance sections below are **derived views** — `/digest` refreshes them automatically, so
> don't hand-edit them; edit the source note instead. Keep capturing in today's `1-daily/` note.
> _Last refreshed: 2026-07-23_

## 🖥 Systems at a glance

Docs status: ⬜ not started · 🟡 in progress · ✅ documented — full detail in [[audit]].

| System | Criticality | Docs |
|---|---|---|
| [[texco-tools]] — central internal platform (Laravel/Vue) | important | 🟡 |
| [[textrack]] — resource/capacity planning (in Texco Tools) | critical | 🟡 |
| [[payroll]] — timesheet ingest → JobPac (award/EBA logic) | critical | 🟡 |
| [[taxisoft]] — AP / OCR ("Connection Jobpac") | ? | 🟡 |
| [[the-close]] — newly discovered, purpose TBC | ? | ⬜ |
| [[texco-learn]] — staff learning/onboarding platform | minor | ⬜ |
| jobpac (external ERP — financial source of truth) | critical | ⬜ |
| hibob "Bob" (external HR) | important | ⬜ |
| texco main website (external — marketing; being rebuilt) | minor | ⬜ |

Cross-cutting infra (Coolify · AWS/S3 backups · Cloudflare DNS · GitHub · Bitwarden · O365 · CI/CD ·
AI tooling) is tracked in [[audit]].

## 📌 This week / now

Latest exec update: [[2026-W30]] · commitments live in [[next-actions]].

**To do**
- [ ] **Fri 24 Jul, 1–2:30pm** — New Business / AI session (Jack Bull); form a view on the AI consultant
- [ ] **Mon 28 Jul** — follow up with Tom Bull & Bec on the Yamba Get Away design feedback
- [ ] Decide on **Marker.io** paid plan before the trial lapses (~13 days or 25 issues)
- [ ] Design the new **5-digit project-number** scheme → [[textrack-5digit-project-numbers]]
- [ ] Meet with all 13 departments
- [ ] Book an app walkthrough with Ryan & Brock
- [ ] Prepare for handover — capture Ryan & Brock's knowledge → [[handover]]
- [ ] Split DNS
- [ ] Documentation pass
- [ ] Get to know **JobPac** (weeks 2–3) — request access + learn how it works
- [ ] **Payroll tool** — get admin access; run in parallel with the manual process next week ([[payroll]])

**Waiting on**
- [ ] Tom Bull & Bec — Yamba Get Away design choice + wording (sent 2026-07-22)

## ⚠️ Risks & handover

- **Biggest risk — continuity:** Ryan & Brock hold most tribal knowledge and access-granting power.
  Systematically capture it → [[handover]] (nothing logged yet).
- **Open questions:** 24 unresolved → [[open-questions]] (infra, backups/DR, DNS, CI, AI spend/policy,
  de-risking Ryan/Brock, how JobPac works, Composio, payroll server files).
- **Key-person risk (payroll):** payroll rules/nuances live largely in Michel VO's head → capture in [[payroll]] / [[handover]].
- **Server/file access:** project access revoked company-wide (per-job requests); Brock is the de-facto contact → [[runbook]] / [[handover]].

## 🎫 Backlog

Committed work only — full board in [[backlog]]. Ideas & requests upstream in [[ideas]]. Conversations in [[meetings]].

- **19 open tickets** (📋 ready for Trello) · 2 archived (1 in-trello, 1 done). By system: **payroll** 13 · **textrack** 4 · **texco-tools** 2.
- In Trello / in progress: [[textrack-5digit-project-numbers]] (5-digit cutover, PR-1 merged).
- Top priority: [[payroll-leave-drawdown-check]] · [[payroll-rdo-accrual-check]] · [[payroll-salary-review]] · [[payroll-approver-poke]] · [[payroll-tax-checks]]
- **Recent meetings:** [[2026-07-23-payroll]] · [[2026-07-21-textrack]]

## 💡 Ideas & wins

Status: 💡 idea · 🔎 exploring · 🔨 building · ✅ shipped · 🗑 dropped — full list in [[ideas]].

| Idea | Impact | Status |
|---|---|---|
| In-app feedback (Marker.io) | Med | ✅ shipped 2026-07-22 |
| Internal ChatGPT / open-source LLM on credits | High | 💡 idea |
| Instrument how teams use AI tools | Med | 💡 idea |
| Internal CRM (people/family info for site teams) | Med | 💡 idea |
| AI that reads team emails for site crews | High | 💡 idea |
| Company Brain — AI-fed knowledge base | High | 💡 idea |
| Custom internal dev tools + AI task capture | Med | 💡 idea |
| AI onboarding videos on [[texco-learn]] | Med | 💡 idea |
| Texco Activity Monitor (user/access/IP logging) | High | 💡 idea |
| Texco Identity — unified SSO | Low | 💡 idea |

## 🗺 Everything (index)

- **Systems** — [[audit]] (index) · [[handover]] · [[texco-tools]] · [[textrack]] · [[payroll]] · [[taxisoft]] · [[the-close]] · [[texco-learn]]
- **Backlog & meetings** — [[backlog]] (board) · [[meetings]] (index)
- **Notes** — [[runbook]] · [[people]] · [[decisions]] · [[open-questions]] · [[next-actions]] · [[baseline]] · [[ideas]]
- **Conventions** — [[naming-conventions]]
- **Updates** — weekly [[2026-W30]] · monthly (none yet) · quarterly (none yet)
- **Daily** — [[2026-07-23]] · [[2026-07-22]] · [[2026-07-21]] · [[2026-07-20]]

## Legend

- **Systems docs:** ⬜ not started · 🟡 in progress · ✅ documented
- **Ideas:** 💡 idea · 🔎 exploring · 🔨 building · ✅ shipped · 🗑 dropped
- **Daily lines:** trailing ✅ = filed by `/digest`

Related: [[audit]] · [[next-actions]] · [[handover]]
