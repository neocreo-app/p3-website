---
name: new-site
description: >-
  Start or move a website the house way: inventory the current site, then draft
  docs/SITE_OUTLINE.md from the house template, ready for Paul and Jas to approve.
  Use when the user says "new site", "move our site off Wix / HubSpot", "outline the
  website", or "spin up a client site". Plans only; it never builds. (Shared skill
  from the house repo; edit it there.)
---

# New site

Produces an **outline**, not a site. Building starts only after Paul (and Jas, for visuals)
approve it. Context is in `docs/core/web/README.md` (a working draft; Paul and Jas's own process
wins where they differ).

## 1. Read first

- `docs/core/web/README.md`: the sites map, the draft method, client-site rules
- `docs/core/web/site-outline-template.md`: the outline shape
- `docs/core/web/page-patterns.md`: page types and sections
- The brand file the site wears: `docs/core/brands/<brand>.md`. **For a client site,** the
  client's brand file lives in this repo, not in `docs/core`. If there is none, the first open
  question is the client's brand basics (who it's for, the feeling, the main ask).

## 2. Inventory the current site (if there is one)

1. Fetch `/sitemap.xml` (Wix and HubSpot both publish one) to list every URL.
2. Read each page. Wix renders in the browser, so if a fetch comes back nearly empty, request the
   page with a normal browser user agent and strip the HTML to text.
3. Record per URL: what it is, its sections, forms, embeds, booking or ticket links, and anything
   placeholder, broken, or outdated (template text, Lorem ipsum, invented testimonials, wrong
   links).

## 3. Draft the outline

Copy the template into `docs/SITE_OUTLINE.md` and fill every section:

- Each new page uses a page type and sections from `page-patterns.md`.
- Every old URL is kept or mapped to a redirect.
- Copy drafts follow `docs/core/rules/copy.md` and the brand's voice. Never invent features,
  numbers, prices, or quotes: mark `⚠️ open:` instead.
- Anything that defines the brand, the offer, or a price is a recommendation marked `⚠️ open`,
  not a decision.

## 4. Hand it over

Tell the user in plain language: the sitemap in one list, what you would cut and why, and the
open questions they need to answer. Do not start building.
