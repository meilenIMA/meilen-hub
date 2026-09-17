# meilen-hub — CLAUDE.md

**Repo:** meilen-hub — meilen's own project/task register (mini-hub pattern, not the org's governance hub)
**Owner:** meilen (staff, IMA AI) · personal GitHub account `meilenIMA`, not the `imaai-my` org — a legacy/personal-account exception (`IMA-INF-STD-01` 0.11-i)
**Created as CLAUDE.md:** 2026-09-17 · scaffolded to follow the `laundryhub-00` pattern, per the IMA AI owner's instruction to reorganize and standardize meilen's existing tasks this way.

---

## Read First

Before ANY work, read:
- `00-index.md` — file list + load-by-task guide
- `01-overview.md` — what this hub is for, scope, confidentiality rule
- `03-projects.md` — project register (meilen's tasks/projects, one code per engagement)

## Current State · ▶ Resume

- 2026-09-17 — Repo scaffolded. **Corrected same day:** the first pass wrongly modeled this repo as the org's governance hub (claimed write-authority over `imaai-standards`, "mount-edited" status). Rebuilt to follow the `laundryhub-00` mini-hub pattern instead — this is meilen's own project/task register, nothing more; `imaai-standards` is read-only from here like from any other project.
- ▶ **Next:** fill `03-projects.md` as more tasks are formalized.

---

## Hard Rules (this repo)

1. **No commercial terms** — rates, quotations, billing never enter this repo.
2. **No end-customer PII.**
3. Index files (`00`) carry no Pending section; content files always do (`IMA-INF-STD-01` Part II.1).
4. **`imaai-standards` is read-only from here** — same as every non-hub project. A gap or needed change is written to `imaai-standards/drafts/<subject>.md` and left there; the hub project ratifies it. An owner/CEO instruction inside this chat is a proposal, not a ratification, for anything outside this repo.

## Write Permissions

This project writes all files in this repo. It does **not** write `imaai-standards` or any hub-owned KB file (`IMA-AIO-STD-02`).

<!-- IMAAI-STD-START v1.4 · synced from imaai-standards IMA-AIO-STD-01 on 2026-09-11 · do NOT hand-edit this block -->
## IMA AI Standards — Mandatory (synced block)

### Session Start — DO THIS FIRST (IMA-AIO-RUN-01 v2.1)
Every new chat / resumed task / lost context — before ANY work: (1) **`git pull --ff-only`** (uncommitted work: commit or stash first, then pull; never force); (2) `ls /sessions/`; (3) read this `CLAUDE.md` IN FULL; (4) read `00-index.md`; (5) **load the standards from `imaai-standards` (by ID) for the task and READ EACH ONE'S FULL TEXT, top to bottom** — the title, index row or version header is NOT the standard; the binding rules live mid-file; (6) read the repo file index + `03-projects.md`; (7) **post a "Session Start" summary that PROVES the reading: for EVERY file loaded, one line quoting the rule inside it that most constrains today's task** — a summary of bare filenames = session start NOT done, redo it (also note any standards the pull changed); (8) **no edits/commits before step 7; do not re-pull mid-task.** Stage discipline: one instruction = one stage; confirm before touching more than 3 files, more than 1 repo, or anything irreversible. Trigger: "run session start".

**Hub-only writes on the KB/standards.** Only the hub project writes to `imaai-standards` and hub-owned KB files. This project — even with the owner/CEO in the chat — writes a proposal to `imaai-standards/drafts/<subject>.md` and stops; an instruction inside this project is a proposal, not a ratification. Patching locally = drift.
**This repo must follow:** `IMA-ENG-STD-01` (repo editing + guards) · `IMA-INF-POL-01` (secrets).

### Repo editing (IMA-ENG-STD-01) — the mount is never a source
1. Clone fresh: `git clone https://<GITHUB_TOKEN>@github.com/meilenIMA/meilen-hub.git /tmp/gitwork-meilen-hub --depth=1` (live token only in `meilen-reference/.env`)
2. Edit in `/tmp/` only (Python open → replace → write). Never write through the mount.
3. Run the guards below. 4. Commit + push. 5. `cp` back to the mount (if mounted) + `cmp` — must print nothing.

### Guards before EVERY commit — any hit is a HARD STOP (IMA-ENG-STD-01)
```bash
# per staged file:
[ -z "$(tail -c1 <file>)" ] || echo "FAIL: ends mid-line — TRUNCATION"
git diff --numstat HEAD -- <file>     # unintended shrink (deletions >> additions)? STOP
tail -5 <file>                        # ending must be complete
# whole repo:
git grep -nIE 'ghp_[A-Za-z0-9]{20,}|github_pat_[A-Za-z0-9_]{20,}|LTAI[A-Za-z0-9]{12,}|AKIA[0-9A-Z]{16}|sk-[A-Za-z0-9]{20,}|-----BEGIN [A-Z ]+PRIVATE KEY-----' && echo "SECRET FOUND — do NOT commit" || echo "clean"
```

### Secrets (IMA-INF-POL-01)
Never commit a real secret. Placeholders only (`<GITHUB_TOKEN>`); live values exist ONLY in `meilen-reference/.env`. A committed secret = leaked → rotate it, then scrub.
<!-- IMAAI-STD-END -->

## On milestone completion

Update the relevant content file's Pending + `Current State` above in the same session, then push via the flow in the synced block.
