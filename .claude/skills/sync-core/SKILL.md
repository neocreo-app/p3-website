---
name: sync-core
description: >-
  Refresh this repo's shared core (docs/core/ and the shared skills) from the
  house repo. Use when the user says "sync core", "update the house docs",
  "pull the latest brand docs", or after the house repo changed. (Shared skill
  from the house repo; edit it there.)
---

# Sync core

The shared core (brands, rules, shared skills) is edited in the **house** repo and copied into
each repo. This refreshes the copy. It never edits house.

## 1. Find the house repo

It should sit next to this repo: `../house`.

- **Found:** `git -C ../house pull --rebase`
- **Missing:** tell the user, and offer to clone it next to this repo:
  `git clone https://github.com/neocreo-app/house.git ../house`
  (If cloning fails with "not found", the user needs to be added to the house repo on GitHub.)

## 2. Check this repo is safe to change

`git status -sb` here. If `docs/core/` or `.claude/skills/` have uncommitted edits, stop and
ask: core edits made here would be overwritten, and belong in house instead.

## 3. Copy

```bash
bash ../house/scripts/sync-core.sh .
```

## 4. Review and commit

- `git status -sb` and `git diff --stat`. Summarize what changed in plain language (which brand
  docs, which rules, which skills).
- If nothing changed, say so and stop.
- Commit only the synced paths:
  `git add docs/core .claude/skills && git commit -m "Sync core from house <short hash>" -- docs/core .claude/skills`
  (The house commit hash is in `docs/core/SYNCED_FROM.md`.)
- Do not push as part of this skill. If the user wants it live, run `/safe-push`.
