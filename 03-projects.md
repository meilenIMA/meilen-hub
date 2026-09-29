# 03 — meilen-hub: Project Register

**Register per `IMA-INF-STD-01` Part VIII.1.** One code per engagement/task, set when first tracked, never changed or reused.
**Version:** 0.3 · **Updated:** 2026-09-29

---

| Project code | Scope | Started | Status |
|---|---|---|---|
| `meilenhub-2609-scaffold` | Scaffold this repo as meilen's task register, following the `laundryhub-00` pattern | 2026-09-17 | Done — corrected same day after initially misbuilding this repo as the governance hub |
| `bzubzu-2609-master-consolidation` | Consolidate `bzubzu-data-screencap/captured-master*.xlsx` version sprawl (v50–v77) into one un-versioned master file; old versions archived, not deleted | 2026-09-17 | Done — daily workbook process on the other side may still need pointing at the new filename |
| `wht-2609-register` | Track meilen's monthly WHT (withholding tax) filing prep folder — `meilen-wht/IMA Withholding Tax_2026 - Reorganised.xlsx` + monthly vendor receipts (subscriptions to foreign digital vendors) | 2026-09-18 | Registered — file left in place, no content touched; two older copies under `meilen-wht/Old ref/` not yet reviewed |
| `bzubzu-2609-screencap-sync` | Push meilen's updated `meilen-bzubzu/captured-master.xlsx` (edited through 2026-09-28) to the `bzubzu-data-screencap` handoff folder, whose copy was stale since the 2026-09-17 consolidation | 2026-09-29 | Done — old copy backed up to `bzubzu-data-screencap/_backups/captured-master-pre-sync-20260929.xlsx`; the `bzubzu-data` git repo (raw Shopee CSV exports only) was deliberately left untouched — this file doesn't match its documented conventions |

## Pending

- [ ] Register more of meilen's existing tasks here as they're identified
- [ ] Decide whether to consolidate the `Old ref/` copies in `meilen-wht/` (same version-sprawl pattern as `captured-master.xlsx`) — flagged 2026-09-18, not actioned
- [ ] `meilen-wht`'s vendor list closely overlaps the `tax`/`wht` head in the draft `IMA-FIN-STD-01`/`IMA-FIN-PRO-01` financial-records system — worth checking with the CEO whether these should become the same record; not this project's call to decide (flagged 2026-09-18)
- [ ] User named "BZU BZU data" (a Cowork project) as the push target but wasn't sure which folder it's connected to; pushed to `bzubzu-data-screencap` on the evidence (stale file + matching format), not `bzubzu-data` (wrong file format for that repo) — confirm with meilen which one "BZU BZU data" actually is (flagged 2026-09-29)
