# Decision Log

> Technical and process decisions and — crucially — the reasoning behind each, so
> future-me remembers *why*. One entry per decision, newest at the top.

<!-- ## YYYY-MM-DD — <decision title>
     **Decision:** what was decided
     **Context:** what prompted it
     **Reasoning:** why this over the alternatives
     **Status:** proposed / adopted / superseded -->

## 2026-07-23 — TexTrack: move to a 5-digit project-number scheme
**Decision:** Adopt a 5-digit job-number scheme — drop the leading `1`, keep the region digit, add a
digit (e.g. Vic `20100`, ~10k jobs of headroom). Must stay **alphanumerically sortable**.
**Context:** JobPac project numbers are nearly exhausted (Vic `12xx`, NSW `13xx`, approaching `1299`);
we can't simply continue to `12100` because JobPac sorts **purely alphabetically**.
**Reasoning:** Preserving alphabetic sort order in JobPac is the crux — `12100` would sort next to
`1210`. The new scheme keeps sort order intact while opening ~10k of headroom per region.
**Status:** adopted (final digit conventions pending from Ryan). Spec/ticket: [[textrack-5digit-project-numbers]]. Source: [[2026-07-21-textrack]].

## 2026-07-23 — Apparel: no dedicated "view apparel" permission (for now)
**Decision:** Leave the "view apparel" permission field empty so every user can see the **Apparel**
feature without needing a specific permission granted.
**Context:** Launching Apparel in [[texco-tools]]; deciding how tightly to gate visibility.
**Reasoning:** Simplest path to get everyone access; "if it works, don't break it." More granular
per-tab permissions can come later if needed.
**Status:** adopted (revisit if per-tab permissions become necessary)

## 2026-07-22 — Adopt Marker.io for in-app feedback
**Decision:** Roll out **Marker.io** for in-app feedback capture, posting issues to **Trello**.
**Context:** No lightweight way for staff to report bugs/requests from inside [[texco-tools]].
**Reasoning:** Fast to roll out and integrates with the existing Trello board — low effort, immediate
value while a custom tool is only an idea (see [[ideas]]).
**Status:** adopted (trial). Paid-plan decision pending before the trial lapses (~13 days / 25 issues) → [[next-actions]].

Related: [[people]] · [[open-questions]]
