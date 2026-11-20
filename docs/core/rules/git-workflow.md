# Git workflow (every repo)

Our sites deploy from `main` on Vercel: **every push to `main` goes live** within about a
minute. Every other branch and pull request gets a **preview URL**.

## Every session

1. **Pull first:** `git pull --rebase` (or Sync in VS Code). Someone else may have pushed.
2. **Work in small commits.** One change, one commit, a message that says what and why.
3. **Stage files by name:** `git add path/to/file`, or commit only named paths with
   `git commit -- path/to/file`. **Never** `git add -A`, `git add .`, or `git commit -a`: they
   sweep in files you (or another chat) did not mean to ship.
4. **Before pushing to `main`, run `/safe-push`.** It pulls, scans for secrets and big files,
   builds, pushes, and checks the live site.

## Things that never go in git

- **Secrets:** API keys, tokens, passwords, `.env` files. They go in Vercel Project Settings →
  Environment Variables.
- **Big files:** PDFs, video, large image sets. They go in Vercel Blob (or another file store).

## When a push breaks the live site

**Roll back first, fix second.** In Vercel: open the project → **Deployments** → find the last
good deploy → **⋯ menu** → **Instant Rollback** (or Promote to Production). Then fix it on a
branch.

## Branches and previews

- Use a branch (for example `jas/magazine-viewer`) for anything risky or multi-day. Push it and
  test on the Vercel preview link, on a real phone.
- Each repo's `AGENTS.md` says whether its owner launches straight to `main` or merges through
  pull requests.

## Do not touch from code or chat

Domain, DNS, and Vercel team or billing settings. Ask Paul.
