# IMA AI Hub — Knowledge Base Index

**Repo:** meilen-hub · **Owner:** meilen (CEO)
**Version:** 0.1
**Last Updated:** 2026-09-17

The hub's own KB — org context, product/brand index, client records. Org standards live in `imaai-standards` (register `IMA-GOV-REF-01`) and are cited by ID, never duplicated here.

## File Structure

```
00-index.md               this file — entry point and load guide
01-group-overview.md      IMA AI structure, ventures, repo map                              (v0.1)
04-xx-*.md                products / companions — not yet created
05-xxx-xx-*.md            brands we own — not yet created
06-xxx-xx-*.md            client records (CEO-only; commercial terms live only here)        — not yet created
99-pending.md             org pending items
```

## Load by Task

```
Any work in this repo          CLAUDE.md (synced standards block) + 01-group-overview.md
Standards question              imaai-standards/00-register.md (register + task index)
Client commercial terms         the relevant 06-xxx file (once created) — never elsewhere
New project / repo              IMA-AIO-STD-01 New Project Checklist
Cross-project handoff           IMA-AIO-STD-02
```

## Rules

- Org standards apply in full — masters in `imaai-standards` (read-write from THIS project only; every other project is read-only there).
- No commercial terms outside `06-xxx` files, and never invented — only what the CEO supplies directly.
- No end-customer PII anywhere in this repo.
- Index files carry no Pending section; content files always do (`IMA-INF-STD-01` Part II.1).
- Numbers sequential, never reused (`IMA-INF-STD-01` Part II.2).
