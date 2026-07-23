# System Inventory — TexTrack

> Status legend: ⬜ not started · 🟡 in progress · ✅ done
> Lives *within* Texco Tools (sidebar → "Projects"). See [[texco-tools]].

## Snapshot
- **Purpose / who uses it:** Resource & capacity planning for construction projects — places people
  (project managers + their teams) onto projects, tracks each person's capacity/workload, and
  forecasts hiring needs 6–18 months out. Used by the project-delivery office.
- **Owner / who knows it:** Ryan & Brok (built in-house; "Johnny"/"Sonny" also referenced).
- **Business criticality:** critical
- **Origin:** replaced a paid product, **Bridgit Bench** (~$50k/yr). Built from ~Sep/Oct 2025 for a
  better fit — it was about functionality, not cost saving.

## Discovery checklist
- [x] **Repo / where it lives** — part of the **Texco Tools** app (not a separate deploy).
- [x] **Tech stack** — same as Texco Tools (Laravel + Vue). "100% vibe-coded" on early-2026 models,
  so quality is uneven — flagged room for improvement across the app.
- [x] **Database** — projects live in the Texco Tools DB. Financials are **not** stored here — pulled
  from **JobPac** and cached (hourly / ~30-min cron); some live pulls are slow.
- [x] **Integrations** — **JobPac** (ERP: contract values & project financials; a "field mismatch"
  page diffs JobPac vs TexTrack, mostly one-way JobPac→TexTrack); **HiBob/Bob** (HR: people, roles,
  home addresses for site-distance allowances; ~12h refresh); **Teams** (quick-contact links);
  **Mapbox** (project map + address geocoding).
- [x] **Known issues / tech debt:**
  - Overlap-assignment bug (two people on one role over the same dates) — **fixed (TT-3)**.
  - JobPac connection slow (old DB) — mitigated with caching.
  - Role-capacity vs assignee-capacity model is confusing; needs a rethink.
  - "Scenarios" (what-if planning) ~80% built, currently unused.
  - UI rough edges (filters don't collapse; unfriendly project form).
- [x] **Risks:** bus factor (Ryan/Brok resolve data mismatches from personal knowledge); no CI; vibe-coded.
- [ ] **Hosting / Auth / Backups / Recovery / Secrets / Access** — inherit from Texco Tools (confirm).
- [ ] **Quick wins** — UI tidy-ups; improve the assignment/scoring UX.

## ⚠️ Looming: project-number convention change
JobPac project numbers are running out — Vic = 12xx, NSW = 13xx, approaching **1299**. Moving to a
**5-digit** scheme (drop the leading 1, keep the region digit → e.g. 20100 for Vic) to stay
alphanumerically sortable. **TexTrack isn't designed for this yet** and it's coming soon → [[next-actions]].

## Key concepts
- **Two phases per project:** design (office/pre-site) and construction (site-based); some roles are
  construction-only; role capacities differ by phase.
- **LOI** = Letter of Intent — pre-contract milestone marking when a job is officially "ours".
- **Unsecured jobs** — planned for before they're won (Jack, new-business director, decides which).
- **Assignment scoring** — ranks people for a role by experience (project-months), state familiarity,
  and availability (from HiBob).

Related: [[texco-tools]] · [[audit]] · [[people]] · [[handover]]
