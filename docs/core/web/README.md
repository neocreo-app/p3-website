# Websites: how we build them

Where our website know-how collects: the sites map, a style system, and the stack, for every
site we run and the client sites we spin out. **Status: a working draft.** Paul and Jas have
their own process; the method and patterns here are Claude drafts to review and replace with it. The brands stay distinct. The way we build them, and the bones they share, are the same.

| File | What |
|---|---|
| [`style-guide.md`](style-guide.md) | The shared style system: token roles, type, spacing, what is shared vs. per brand. **Paul + Jas fill it in.** |
| [`page-patterns.md`](page-patterns.md) | Page types and the section library every site builds from |
| [`stack.md`](stack.md) | The standard stack, hosting, HubSpot forms and meetings, redirects, SEO |
| [`launch-checklist.md`](launch-checklist.md) | Moving a site off Wix or HubSpot CMS, and the go-live steps |
| [`site-outline-template.md`](site-outline-template.md) | The outline every site starts from (ours and clients') |

**Repo setup** (`AGENTS.md`, `docs/core/`, `docs/DECISIONS.md`) follows `nc-website` and
`basscats`. Their **designs** are not a reference; see [`style-guide.md`](style-guide.md).

Copy rules stay in [`../rules/copy.md`](../rules/copy.md). Each brand's voice stays in
[`../brands/`](../brands/). This folder links to them; it does not repeat them.

## The sites: branded house over a house of brands

There are two layers:

- **The house of brands.** Each brand site stands on its own. It wears one brand, has one
  audience, and makes one ask. It does not explain the other brands.
- **The branded house.** The p3 site is Paul's: the human thread. It is the only site that tells
  the one story and points to all four brands.

| Site | Domain | Wears | Its job | Main ask | Repo | Lead |
|---|---|---|---|---|---|---|
| **p3** | `⚠️ open` (name is p3 for now) | 🧵 p3, the connective brand ([`p3.md`](../brands/p3.md)) | Who Paul is, the one story, a door to each brand | Soft: follow, or pick a door | `neocreo-app/p3-website` | Jas (the words are Paul's) |
| **Pursuit of Progress** | pursuitofprogress.org | 📈 [PoP](../brands/pursuit-of-progress.md) | Consulting: GTMOps and the product paths | Book a call | `neocreo-app/pop` | Jas |
| **Primal Prancing** | primalprancing.com | 🦌 [PR2](../brands/primal-prancing.md) | Come dance, in Boulder or online | Come to class | `neocreo-app/pr2` | Jas |
| **BASS CATS** | basscats.org | 🐈 [BASS CATS](../brands/bass-cats.md) | The crew and its content | Join the Creative Club | `neocreo-app/basscats` | Jas |
| **Neocreo** | neocreo.io | 🌱 [Neocreo](../brands/neocreo.md) | The software | Apply for an account | `neocreo-app/nc-website` | Paul (Jas designs) |

**How the two layers touch.** A brand site links to the p3 site in its footer only, with a single
line. It never adds a "see our other brands" section. `⚠️ open (proposal):` the footer line reads
"A Paul Good project" and links to p3, and every site's copyright reads "© P to the 3 LLC".
Good enough while building (Paul, 2026-11-20).

## A draft method (not decided)

`⚠️ open:` **Claude's draft (2026-11-20), not a decision.** Paul and Jas have their own process;
they review this and replace it with theirs. Until then, it is a checklist of what a site move
touches. The outline
([`site-outline-template.md`](site-outline-template.md)) covers steps 1 to 4. **Nothing gets
built until Jas approves the outline,** with Paul's sign-off on offers, prices, and claims.

1. **Inventory.** List every live URL, every form, embed, and booking link, and anything that is
   placeholder or broken. Old URLs become redirects later, so miss none.
2. **Brand inputs.** Which brand the site wears, its brand file, its Canva tokens, its photos.
3. **Sitemap and page jobs.** One job and one ask per page, with the CTA heat set
   ([`../brands/README.md`](../brands/README.md#the-cta-heat-ladder-from-the-q3-content-sync)).
   Every old URL is either kept or mapped to a redirect.
4. **Copy draft.** Written into the outline page by page, then `/copy-pass`. Never invent
   features, numbers, or quotes.
5. **Tokens and sections.** Fill the brand's token values in [`style-guide.md`](style-guide.md).
   Build pages only from [`page-patterns.md`](page-patterns.md) sections.
6. **Build** on the standard stack ([`stack.md`](stack.md)).
7. **Forms and meetings.** HubSpot forms (with the hidden Brand field) and HubSpot meetings.
8. **Launch** with [`launch-checklist.md`](launch-checklist.md).
9. **Measure** after 30 days: form submits and meetings booked per page. Cut what nobody uses.

## Who does what

- **Jas leads the websites** (Paul, 2026-11-20): design, the build, the copy, and building out
  each site's offerings. She owns the visual identity (Canva) and the style guide. On BASS CATS,
  everything.
- **Paul** helps on the tech side, leads, and answers questions. He approves offers, prices, and
  claims (anything with money in it) and the brand architecture. On p3, the words are his.
- **Claude and other builders:** inventory, outline drafts, copy drafts, the build, the checks.
  They recommend; they do not decide the brand.

## One kit across sites

`⚠️ open:` **We figure this out by building PoP, PR2, and p3.** The expected shape (agreed
2026-11-20), to keep the sites consistent without a shared code package too early:

1. The **first site built is the starter.** It defines the tokens and the section components.
2. The **second site copies them** and changes only token values and content.
3. Once two sites run on it, the sections move into a **`site-starter` template repo**, and every
   new site, ours or a client's, starts from that. `⚠️ open:` template repo (recommended, simpler)
   vs. a shared npm package (only if we start fixing the same bug in many sites).

## Client sites

Same stack, same style system with the client's tokens, and whatever process we settle on.

- The client's brand file lives in **the client's repo**, never in house.
- A client repo gets only `house/web/` and `house/rules/`, never `house/brands/` (our brands
  are not theirs). `⚠️ open:` `sync-core` copies all of house today. Before the first client
  site, it needs a mode that skips `brands/`.
- One HubSpot portal per client, the client's, not ours.

## Order

Agreed 2026-11-20: outlines and copy now, builds after the 11-26 Neocreo move.
1. **Pursuit of Progress:** clearest copy source, and it ends the HubSpot CMS bill. It becomes the
   starter.
2. **Primal Prancing:** off Wix, copies the starter.
3. **p3:** the smallest site, but it needs Paul's founding story in his own words.
