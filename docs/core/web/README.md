# Websites: how we build them

One method, one stack, one style system for every site we run, and for the client sites we
spin out. The brands stay distinct. The way we build them, and the bones they share, are the same.

| File | What |
|---|---|
| [`style-guide.md`](style-guide.md) | The shared style system: token roles, type, spacing, what is shared vs. per brand. **Paul + Jas fill it in.** |
| [`page-patterns.md`](page-patterns.md) | Page types and the section library every site builds from |
| [`stack.md`](stack.md) | The standard stack, hosting, HubSpot forms and meetings, redirects, SEO |
| [`launch-checklist.md`](launch-checklist.md) | Moving a site off Wix or HubSpot CMS, and the go-live steps |
| [`site-outline-template.md`](site-outline-template.md) | The outline every site starts from (ours and clients') |

Copy rules stay in [`../rules/copy.md`](../rules/copy.md). Each brand's voice stays in
[`../brands/`](../brands/). This folder links to them; it does not repeat them.

## The sites: branded house over a house of brands

There are two layers:

- **The house of brands.** Each brand site stands on its own. It wears one brand, has one
  audience, and makes one ask. It does not explain the other brands.
- **The branded house.** The p3 site is Paul's: the human thread. It is the only site that tells
  the one story and points to all four brands.

| Site | Domain | Wears | Its job | Main ask | Repo | Owner |
|---|---|---|---|---|---|---|
| **p3** | `⚠️ open` | 🧵 Paul, the connective brand ([`paul.md`](../brands/paul.md)) | Who Paul is, the one story, a door to each brand | Soft: follow, or pick a door | `neocreo-app/p3-website` | Paul |
| **Pursuit of Progress** | pursuitofprogress.org | 📈 [PoP](../brands/pursuit-of-progress.md) | Consulting: GTMOps and the product paths | Book a call | `neocreo-app/pop` | Paul |
| **Primal Prancing** | primalprancing.com | 🦌 [PR2](../brands/primal-prancing.md) | Come dance, in Boulder or online | Come to class | `neocreo-app/pr2` | Paul (Jas = community face) |
| **BASS CATS** | basscats.org | 🐈 [BASS CATS](../brands/bass-cats.md) | The crew and its content | Join the Creative Club | `neocreo-app/basscats` | Jas |
| **Neocreo** | neocreo.io | 🌱 [Neocreo](../brands/neocreo.md) | The software | Apply for an account | `neocreo-app/nc-website` | Paul |

**How the two layers touch.** A brand site links to the p3 site in its footer only, with a single
line. It never adds a "see our other brands" section. `⚠️ open (proposal):` the footer line reads
"A Paul Good project" and links to p3, and every site's copyright reads "© P to the 3 LLC".

## The method

Every site, ours or a client's, goes through the same nine steps. The outline
([`site-outline-template.md`](site-outline-template.md)) is where steps 1 to 4 live. **Nothing
gets built until Paul (and Jas, for anything visual) approve the outline.**

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

- **Paul:** brand architecture, offers, prices, claims, and anything with money in it.
- **Jas:** visual identity (Canva), the style guide, design calls. On BASS CATS, everything.
- **Claude and other builders:** inventory, outline drafts, copy drafts, the build, the checks.
  They recommend; they do not decide the brand.

## One kit across sites

The sites are separate repos. To keep them consistent without a shared code package too early:

1. The **first site built is the starter.** It defines the tokens and the section components.
2. The **second site copies them** and changes only token values and content.
3. Once two sites run on it, the sections move into a **`site-starter` template repo**, and every
   new site, ours or a client's, starts from that. `⚠️ open:` template repo (recommended, simpler)
   vs. a shared npm package (only if we start fixing the same bug in many sites).

## Client sites

Same method, same stack, same style system with the client's tokens.

- The client's brand file lives in **the client's repo**, never in house.
- A client repo gets only `house/web/` and `house/rules/`, never `house/brands/` (our brands
  are not theirs). `⚠️ open:` `sync-core` copies all of house today. Before the first client
  site, it needs a mode that skips `brands/`.
- One HubSpot portal per client, the client's, not ours.

## Order

`⚠️ open (proposal):` outlines and copy now, builds after the 11-26 Neocreo move.
1. **Pursuit of Progress:** clearest copy source, and it ends the HubSpot CMS bill. It becomes the
   starter.
2. **Primal Prancing:** off Wix, copies the starter.
3. **p3:** the smallest site, but it needs Paul's founding story in his own words.
