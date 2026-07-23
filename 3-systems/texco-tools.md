# System Inventory — Texco Tools

> Status legend: ⬜ not started · 🟡 in progress · ✅ done

## Snapshot
- **Purpose / who uses it:** Central internal system — "knows everything". Widely used.
- **Owner / who knows it:** Ryan & Brok
- **Business criticality:** important
- **Known niggle:** some screens are slow (often the live JobPac pulls — see Integrations).
- **Contains [[textrack]]** — the project resource-planning module, under the sidebar "Projects".

## Discovery checklist
- [ ] **Repo** — where the code lives (GitHub org, repo name)
- [x] **Tech stack** — Laravel (PHP) + Vue/JS, Docker (`laravel.test` container). Sail-style setup.
- [ ] **Hosting** — where it runs (Coolify? a server?) + every environment URL (local / dev / qa / prod)
- [ ] **Domain & DNS** — domains it uses, managed where (Cloudflare?)
- [ ] **Database** — type, where it lives, rough size
- [ ] **Authentication** — how login works (note: has a local-only `/dev/login/<email>` route)
- [x] **Integrations** — **JobPac** (ERP: financials/contract values, cached hourly / ~30-min cron;
  live pulls slow), **HiBob/"Bob"** (HR: people, roles, addresses; ~12h refresh), **Teams**
  (quick-contact links), **Mapbox** (maps/geocoding). Marker.io reports post to **Trello**.
- [ ] **Deployment** — how a change reaches prod (manual pull? CI?)
- [ ] **Backups** — what's backed up, where (AWS/S3?), how often
- [ ] **Recovery** — has a restore been tested? how long would it take?
- [ ] **Secrets / credentials** — where stored (Bitwarden?)
- [ ] **Access** — who has admin, who can grant it
- [ ] **Known issues / tech debt** — slow screens (start here)
- [ ] **Risks** — bus factor, security gaps, single points of failure
- [ ] **Quick wins** — cheap improvements spotted

## Local setup
Full Docker recipe (from a clean `docker compose up`). After the containers are up, three steps:

```bash
# 1. Rebuild the schema + seed reference data (roles, permissions, etc.)
docker compose exec laravel.test php artisan migrate:fresh --seed

# 2. Create a user (seeders create roles but NOT accounts)
docker compose exec laravel.test php artisan tinker --execute="
  \$u = App\Models\User::firstOrCreate(['email'=>'jlovera@texco.net.au'],['name'=>'J Lovera']);
  \$u->assignRole('Super Admin');
"

# 3. Log in — visit this local-only route in your browser:
#    http://localhost/dev/login/jlovera@texco.net.au
```

After step 3 you land on the dashboard as a Super Admin. Frontend assets are pre-built
(`public/build` exists); if you change Vue/JS files, run `docker compose exec laravel.test npm run build`
(or `npm run dev`).

## Changes / deploy log
- **2026-07-22** — Deployed to prod: fix **TT-3** — multiple assignees to the same role with overlapping time periods are now prevented.
- **2026-07-22** — Deployed to prod: **Marker.io** integration + updated the **What's New** page.
  Staff can now report bugs/improvements to **Trello** directly from any page (steering people to the
  tool instead of DMing me). ⚠️ On a **trial — ends after 13 days or 25 reported issues** (decide on a
  paid plan before then → [[next-actions]]). Doesn't work with ad-blockers / the Helium browser's blocker.

## Notes
- Marker.io feedback flows to Trello; doesn't work behind an ad-blocker.

Related: [[audit]] · [[people]] · [[handover]]
