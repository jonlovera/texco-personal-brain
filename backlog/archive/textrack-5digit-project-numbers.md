
# [textrack] Design for the new 5-digit project-number scheme

**System:** textrack · **Priority:** High · **Status:** in-trello
**Source:** [[2026-07-21-textrack]] · **Trello:** https://trello.com/c/wqrOomzh/12-feat-tt-5-digit-job-number-cutover
**Progress:** built as 4 PRs; **PR-1 merged** 2026-07-23 (https://github.com/TexcoAU/tools/pull/468).

## 📋 Paste to Trello
```
[textrack] Design for the new 5-digit project-number scheme
JobPac project numbers are running out (Vic 12xx, NSW 13xx, approaching 1299). Moving to a 5-digit
scheme: drop the leading 1, keep the region digit, add a digit → e.g. Vic 20100 (room for ~10k jobs).
Must stay alphanumerically sortable (JobPac sorts purely alphabetically). TexTrack isn't designed for
this yet and it's coming soon. Handle storage/parsing/sorting + the "Link to JobPac" upcoming-job flow.
Acceptance: TexTrack stores/links/sorts 5-digit numbers correctly; existing 4-digit jobs unaffected.
Context: vault 2026-07-21-textrack
```

## Detail
**Problem / why:** JobPac numbers are nearly exhausted — Victorian jobs are `12xx`, NSW `13xx`, and
we're approaching **1299**. We can't just continue to `12100`, because JobPac sorts **purely
alphabetically**, so `12100` would file next to `1210` — making reports look wrong and jobs hard to
find. TexTrack has **not been designed for this** and it's going to arrive quickly (once we pass 1299).

**The new scheme:** keep the region digit (`2` = Victoria), **drop the leading `1`**, and add digits →
e.g. Vic `20100`. Gives ~10,000 job numbers and stays sequential/alphanumerically sortable. Ryan to
send the finalised conventions.

**Proposed work:**
- Store/parse/sort project numbers under the 5-digit scheme without breaking existing 4-digit jobs.
- Update the **"Link to JobPac"** upcoming-job workflow (enter number → pull JobPac fields) for 5 digits.
- Confirm the field-mismatch diff and any sort/report views handle the new format.

**Acceptance:**
- [ ] 5-digit numbers stored, linked and sorted correctly (alphanumeric order preserved)
- [ ] Existing 4-digit jobs unaffected
- [ ] "Link to JobPac" flow accepts the new format
- [ ] Confirmed against the finalised conventions from Ryan

## Notes / edge cases
- NSW is `13xx` today — confirm its target region digit under the new scheme.
- Sorting is the crux: the whole reason for the scheme is to preserve alphabetic sort order in JobPac.

Related: [[textrack]] · [[backlog]]
