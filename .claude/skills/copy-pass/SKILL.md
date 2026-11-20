---
name: copy-pass
description: >-
  Check new or changed visitor-facing copy against the house copy rules and the
  brand's voice before it ships. Use when the user asks to review, tighten, or
  check copy, or before shipping a page with new words. (Shared skill from the
  house repo; edit it there.)
---

# Copy pass

## 1. Find the copy

Look at what changed: `git diff` (uncommitted) or `git diff @{u}..HEAD` (unpushed), or the
page or file the user names. Pull out only the words a visitor will read (headings, body,
buttons, alt text, page titles and descriptions). Ignore code names, URLs, and comments.

## 2. Know the brand

Read this repo's `AGENTS.md` to see which brand the site wears, then read:

- `docs/core/rules/copy.md`: house rules for every brand
- `docs/core/brands/<brand>.md`: that brand's voice, feeling, asks, and what it is NOT
- `docs/core/brands/README.md`: exact names and the CTA heat ladder

## 3. Check each line

Flag, with the exact line and a suggested rewrite:

- **Hard rules:** em dashes, wrong brand-name spelling, uppercase eyebrow labels, hype words.
- **Brand fit:** does it sound like the brand's voice? Does it drift into something the brand
  is NOT (for example, BASS CATS sounding like a course or a party-hard brand; Neocreo sounding
  like a rival CRM or open signup)?
- **Claims:** any feature, number, price, or quote that you cannot trace to the docs. Flag it;
  do not "fix" it by inventing a source.
- **Next step:** does the page have one clear ask, and is its heat earned?

## 4. Report

A short list: rule broken → line → suggested rewrite. Keep Paul and Jas's own phrases. Then ask
before applying the changes, unless the user already said to apply them.
