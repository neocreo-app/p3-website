# p3 website (Paul's site): agent instructions

Read this file before changing code, copy, or docs here. It is the shared source of truth for
every AI model (Claude, Codex, others); `CLAUDE.md` only points here.

## What this is

**Paul's own site,** the connective brand: the branded house over the house of brands. It tells the one story (the pursuit of progress, powered by dance) and is the only site that points to all four brands. Its asks are **soft:** follow, or pick a door.

- **Lead:** Jas: design and build.
- **The words are Paul's:** the story and voice are his (the authenticity is the asset), so
  Paul writes or approves every line of copy. He also helps on the tech side.
- **Status:** planning. New site; domain `⚠️ open`.

**Start here:** [`docs/SITE_OUTLINE.md`](docs/SITE_OUTLINE.md) is the plan: inventory, sitemap,
page by page, forms, redirects, open questions. **Do not build until Jas approves it,** with Paul's
sign-off on the copy.

## Read before you work

| File | When |
|---|---|
| [`docs/core/brands/p3.md`](docs/core/brands/p3.md) | **Anything a visitor sees.** The brand this site wears |
| [`docs/core/web/README.md`](docs/core/web/README.md) | The sites map and the draft method (Paul and Jas review it) |
| [`docs/core/web/style-guide.md`](docs/core/web/style-guide.md) | Colors, fonts, spacing: token roles only, never raw values |
| [`docs/core/web/page-patterns.md`](docs/core/web/page-patterns.md) | Page types and sections |
| [`docs/core/web/stack.md`](docs/core/web/stack.md) | Stack, HubSpot forms and meetings, redirects, SEO |
| [`docs/core/web/launch-checklist.md`](docs/core/web/launch-checklist.md) | Before going live or moving DNS |
| [`docs/core/rules/copy.md`](docs/core/rules/copy.md) | Writing or editing any words |
| [`docs/core/rules/verification.md`](docs/core/rules/verification.md) | Before saying something works or is live |
| [`docs/core/rules/working-with-us.md`](docs/core/rules/working-with-us.md) | How to explain, when to ask vs. act |
| [`docs/DECISIONS.md`](docs/DECISIONS.md) | Before re-opening a settled choice; after making a new one |

**`docs/core/` is a read-only copy of the shared house repo.** Do not edit it here; change it in
`../house`, then run `/sync-core`.

## Skills (Claude Code)

- `/safe-push`: before any push to `main`
- `/copy-pass`: before shipping new or changed copy
- `/sync-core`: refresh `docs/core/` and these skills from house
- `/new-site`: the outline workflow (already done for this site; use it to re-inventory)

## How it is hosted

- Code: GitHub `neocreo-app/p3-website`.
- Vercel project and domain: `⚠️ open` (not created yet).

## Stack

The house standard ([`docs/core/web/stack.md`](docs/core/web/stack.md)). Not scaffolded yet.

## Site-specific rules

1. Conduit, not centerpiece: point at the work and the worlds, not at Paul's face.
2. Soft asks only; no prices, no hard sells. Conversions happen on the brand sites.
3. Each brand gets one door card in its own words; the brand sites carry the detail.
4. No new dependencies or paid services without asking.

## Keeping docs true

- Found something that contradicts a doc? Fix it in the same change. Core docs: fix in house.
- A new non-obvious decision gets one line in `docs/DECISIONS.md`.
