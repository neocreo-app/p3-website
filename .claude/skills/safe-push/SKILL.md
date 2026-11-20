---
name: safe-push
description: >-
  Safely push commits to main. Use when the user wants to push, ship, publish,
  launch, or "send it up" to main, because every push to main goes live on the
  site. Pulls first, scans for secrets and big files, runs the real build,
  pushes, then confirms the live site. Do NOT use for commit-only requests;
  committing is safe. (Shared skill from the house repo; edit it there.)
---

# Safe Push

`main` auto-deploys to the live site. The site's URL and owner are in this repo's
`AGENTS.md`. This skill runs the same safe sequence every time. A clean result pushes without
asking again; a risky result stops and asks a direct yes/no.

## 1. Survey (never skip)

```bash
git fetch -q
git status -sb
git rev-list --left-right --count @{u}...HEAD
```

- **Behind (first number > 0):** someone else pushed. `git pull --rebase`, resolve conflicts,
  start over at step 1.
- **Ahead == 0:** nothing to push. Say so and stop.
- **Uncommitted changes:** list them. Ask whether to commit them (staged by file name) or leave
  them out. Never `git add -A` on someone else's behalf.

## 2. What is going out

```bash
git log --oneline @{u}..HEAD
git diff --stat @{u}..HEAD
```

Summarize the commits in a sentence or two, in plain language.

## 3. Risk gate: stop and ask if ANY is true

- **Possible secret:** `.env*`, `*.pem`, `*.key`, or added lines like a key or token.
  Check: `git diff @{u}..HEAD | grep -iE "(api[_-]?key|secret|token|password)\s*[:=]"`
- **Big file** (over about 10 MB) added. PDFs, video, and image sets belong in Vercel Blob.
- **Domain, redirects, or hosting config changed:** `vercel.json`, or `redirects` /
  `rewrites` in `next.config.*`.
- **New dependency** in `package.json` that the user did not ask for.
- **Database migration or SQL** in the commits. It must already exist on the database the site
  uses, or the deploy breaks.
- **`docs/core/` changed by hand** (not by `/sync-core`). Core edits belong in the house repo.

Otherwise the push is **clean**.

## 4. Build (if there is a `package.json`)

```bash
npm install
npm run build
```

Stop any running `npm run dev` first: building while it runs corrupts it. If the build fails,
do not push. Show the error and fix it first. Afterward, if the dev server misbehaves, delete
`.next` and restart it.

No `package.json` (a plain HTML site): skip the build, and open the changed page to check it
loads.

## 5. Push

```bash
git push origin main
git status -sb
```

## 6. Confirm the deploy

A successful push is not proof. Check:

- Vercel shows the new deployment as **Ready** (Deployments tab, or the check on the GitHub
  commit).
- The live site shows the change. Hard-refresh or use a private window.

If the deploy failed or the site is broken, say so plainly and recommend **Instant Rollback** in
Vercel (Deployments → last good deploy → ⋯ → Instant Rollback), then fix on a branch.

## 7. Report

What was pushed (commit range and a one-line theme), the risk verdict, whether the build passed,
and whether the live site shows the change. Say what you skipped.
