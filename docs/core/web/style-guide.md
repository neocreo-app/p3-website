# Website style guide

**Status: a scaffold for Paul and Jas to fill in together.** Structure is proposed; values are
`⚠️ open` until Jas confirms them from Canva. Canva is the source of truth for every brand's look;
this file is how that look reaches code. If they disagree, Canva wins, and this file gets fixed.

## The idea: family resemblance, not sameness

Every site should feel like it came from the same house, while each brand still looks like
itself.

| Shared by every site (the bones) | Set per brand (the skin) |
|---|---|
| Layout grid and page widths | Colors |
| Spacing scale | Fonts |
| Type scale (the size steps) | Imagery and illustration style |
| Section patterns ([`page-patterns.md`](page-patterns.md)) | Voice ([`../brands/`](../brands/)) |
| Button, link, and form behavior | Corner radius and texture, if a brand wants its own |
| Accessibility floor (contrast, focus, alt text) | Light, dark, or both |
| Motion rules (subtle, respects reduced-motion) | |

## Token roles

In code, a component never uses a raw color or font. It uses a **role**, and each brand sets
the value of every role once. Changing a brand's look means changing its values, never its
components.

| Role | What it is for |
|---|---|
| `--color-bg` | Page background |
| `--color-surface` | Cards, bands, panels on top of the background |
| `--color-text` | Body text |
| `--color-text-muted` | Secondary text, captions |
| `--color-heading` | Headings, if they differ from body text |
| `--color-accent` | The brand color: buttons, links, highlights |
| `--color-accent-contrast` | Text sitting on the accent color |
| `--color-border` | Dividers, card edges, inputs |
| `--font-display` | Big headlines |
| `--font-body` | Everything else |
| `--radius` | Corner roundness for cards, buttons, inputs |

`⚠️ open:` whether brands need a second accent (`--color-accent-2`) or a section-band color.
Add a role only when two brands need it.

## Brand values

`⚠️ open:` every value below, from Jas's Canva guidelines. The known starting points are noted.

| Role | 🧵 p3 | 📈 PoP | 🦌 PR2 | 🐈 BASS CATS | 🌱 Neocreo |
|---|---|---|---|---|---|
| `--color-bg` | | | | | dark (dark-only today) |
| `--color-accent` | | | | | `#22d3ee` on the site, differs from the app; reconcile |
| `--font-display` | | | | | Inter today |
| `--font-body` | | | | | Inter today |
| Light / dark | | | | | Dark only |
| Canva link | | | | | |

## The shared scales

`⚠️ open (proposal):` start from these, then adjust in the session.

- **Type scale:** 6 steps, from small to display: 14 / 16 / 20 / 28 / 40 / 56 px on desktop,
  with display stepping down on phones. Body text is never smaller than 16 px.
- **Spacing scale:** 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 px. Sections are separated by
  64 to 96 px.
- **Widths:** text columns about 680 px; content up to 1200 px; 16 px side gutter on phones.
- **Buttons:** one primary style (accent fill) and one secondary style (outline) per brand. One
  primary button per section.

## Session agenda: Paul + Jas

1. Walk this file's "shared vs. per brand" table. Is anything on the wrong side?
2. Fill the brand values table from Canva, one brand at a time.
3. Agree on the type and spacing scales. Look at them on a real page, not in the abstract.
4. Decide light/dark per brand.
5. Pick the photo direction per brand (who is in them, candid vs. posed).
6. Decide the footer line between brand sites and p3 ([`README.md`](README.md)).
