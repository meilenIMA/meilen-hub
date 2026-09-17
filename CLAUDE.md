# meilen-hub — CLAUDE.md

**Repo:** meilen-hub — IMA AI's hub / records repo (the `<hub>` of `IMA-AIO-STD-01` / `IMA-AIO-STD-02`)
**Owner:** meilen (CEO) · personal GitHub account `meilenIMA`, not the `imaai-my` org — a legacy/personal-account exception (`IMA-INF-STD-01` 0.11-i)
**Created as CLAUDE.md:** 2026-09-17 · repo existed on GitHub empty since before this date; scaffolded from the hub KB pattern (`IMA-INF-STD-01` Part II.2)
**Cowork project:** meilen-hub (this repo is mount-edited — Cowork writes this folder directly; see the Mount-Edited exception in `IMA-ENG-STD-01`)

---

## What this project is

The hub. Per `IMA-AIO-STD-02`: discussion of anything strategic, cross-product, or standards-shaping happens here, because only here can it see everything it touches. Per `IMA-AIO-STD-01`: this is the ONE project that writes to `imaai-standards`' main tree — every other project only proposes into its `drafts/`. This repo holds the org's own KB (org context, product/brand index, client records) — the actual rules live in `imaai-standards`, cited by ID.

## Read First

- `00-index.md` — org index + load-by-task
- `01-group-overview.md` — IMA AI structure, ventures, repo map
- `99-pending.md` — org pending items

## Current State · ▶ Resume

- 2026-09-17 — Repo scaffolded (CLAUDE.md + 00-index + 01-group-overview + 99-pending). Confirmed by CEO as the hub repo (previously empty on GitHub since creation). Nothing else filled yet.
- ▶ **Next:** register this repo in `imaai-standards/00-register.md` and `IMA-ENG-STD-01`'s Repo Reference table (New Project Checklist step 2 — `IMA-AIO-STD-01`) — a separate stage, touches a second repo, needs its own go-ahead. Populate `04-xx` (products), `05-xxx` (brands we own), `06-xxx` (client records) as those are formalized with real facts — not invented ahead of time.

---

## Hard Rules (this repo)

1. **This is the hub — the one project that writes to `imaai-standards`.** Every other project's CEO instruction on a standard is a proposal, not a ratification (`IMA-GOV-STD-01` §7); this project is where those proposals get ratified and implemented.
2. **No commercial terms outside `06-xxx` client records** — and even there, only what the CEO directly supplies. Never invent or estimate a rate, quotation, or commercial figure.
3. **No end-customer PII** anywhere in this repo.
4. Index files (`00-*`) carry no Pending section; content files always do (`IMA-INF-STD-01` Part II.1).
5. **Mount-edited project** — Cowork writes this folder directly (not clone→`/tmp`→push). The guards below are mandatory on every push (`IMA-ENG-STD-01` Mount-Edited Projects section): read back after a substantial write, run the Truncation Guard on the mount copy before `cp` to a push clone, verify with `cmp` after, and treat any shrink as suspect.

## Write Permissions

This Cowork project writes all files in this repo. It is also the only project permitted to write `imaai-standards`' main tree (via that repo's own clone → `/tmp` → guards → push flow — `imaai-standards` is NOT mount-edited, only this repo is).

<!-- IMAAI-STD-START v1.4 · synced from imaai-standards IMA-AIO-STD-01 on 2026-09-11 · do NOT hand-edit this block -->
## IMA AI Standards — Mandatory (synced block)

### Session Start — DO THIS FIRST (IMA-AIO-RUN-01 v2.1)
Every new chat / resumed task / lost context — before ANY work: (1) **`git pull --ff-only`** (uncommitted work: commit or stash first, then pull; never force) — this repo included, no exceptions; (2) orient to the session's mount root; (3) read this `CLAUDE.md` IN FULL; (4) read `00-index.md`; (5) **load the standards from `imaai-standards` (by ID) + any `04/05/06` files for the task and READ EACH ONE'S FULL TEXT, top to bottom** — the title, index row or version header is NOT the standard; the binding rules live mid-file; (6) read the repo file index + `99-pending.md`; (7) **post a "Session Start" summary that PROVES the reading: for EVERY file loaded, one line quoting the rule inside it that most constrains today's task** — a summary of bare filenames = session start NOT done, redo it (also note any standards the pull changed); (8) **no edits/commits before step 7; do not re-pull mid-task.** Stage discipline: one instruction = one stage; confirm before touching more than 3 files, more than 1 repo, or anything irreversible; run long jobs in reported chunks. Trigger: "run session start".

**This project IS the hub.** It writes `imaai-standards`' main tree directly (via that repo's clone/edit/push flow + guards) when the CEO ratifies a change here. Every OTHER project only proposes into `imaai-standards/drafts/<subject>.md` and stops (`IMA-GOV-STD-01` §7 · `IMA-AIO-STD-02` KB Change Proposal) — a CEO instruction inside a non-hub project is a proposal, not a ratification.
**This repo must follow:** `IMA-ENG-STD-01` (repo editing + guards, incl. the Mount-Edited Projects exception) · `IMA-INF-POL-01` (secrets) · `IMA-INF-STD-01` Part II (KB numbering).

### Repo editing — this repo is Mount-Edited (`IMA-ENG-STD-01` exception)
This repo is edited on the mount directly, not via clone → `/tmp` → push. On every push:
1. After any substantial write to the mount, read the file back — confirm the tail is intact (trailing newline + complete final section).
2. Before `cp` mount → push clone, run the Truncation Guard on the **mount copy**.
3. After `cp`, verify: `cmp <mount-file> <clone-file>` — any mismatch = stop.
4. Shrink check: `git diff --numstat HEAD -- <file>` in the clone — a file that got shorter without an intended deletion means the mount copy is suspect; stop and re-read the mount file.
5. Run the whole-repo audit (below) at the start of any KB housekeeping session.

### Guards before EVERY commit — any hit is a HARD STOP (IMA-ENG-STD-01)
```bash
# per staged file:
[ -z "$(tail -c1 <file>)" ] || echo "FAIL: ends mid-line — TRUNCATION"
git diff --numstat HEAD -- <file>     # unintended shrink (deletions >> additions)? STOP
tail -5 <file>                        # ending must be complete (.md ends at a full section)
# whole repo:
git grep -nIE 'ghp_[A-Za-z0-9]{20,}|github_pat_[A-Za-z0-9_]{20,}|LTAI[A-Za-z0-9]{12,}|AKIA[0-9A-Z]{16}|sk-[A-Za-z0-9]{20,}|-----BEGIN [A-Z ]+PRIVATE KEY-----' && echo "SECRET FOUND — do NOT commit" || echo "clean"
```

### Secrets (IMA-INF-POL-01)
Never commit a real secret — tokens, API keys, passwords, `JWT_SECRET`. Placeholders only; live values exist ONLY in `meilen-reference/.env` (this repo's personal-account analog of `credentials.env`). A committed secret = leaked → rotate it, then scrub.
<!-- IMAAI-STD-END -->

## On milestone completion

Update `Current State` above and `99-pending.md` in the same session, then push via the mount-edited flow in the synced block.
