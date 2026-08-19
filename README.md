# chross22.github.io

Personal academic site for Camille H. Ross. Jekyll, hosted on GitHub Pages,
built from `master` with GitHub's stock Jekyll — no Actions, no Node, no custom
plugins.

## Previewing locally

```bash
./bin/serve      # http://localhost:4000, live-reloads on save
./bin/build      # build into _site/ exactly the way GitHub Pages will
```

Both scripts pin **Ruby 3.3** and a UTF-8 locale. That is deliberate: the
`github-pages` gem requires Ruby < 4.0, so a plain `brew install ruby` (which
now gives 4.x) cannot build this site. If `./bin/serve` fails, run
`brew install ruby@3.3` then `bundle install`.

Run `./bin/build` before pushing. It builds with `--safe`, which mirrors the
Pages sandbox, so a clean run here means a clean deploy.

---

## How to add a publication

Create a file in `_publications/` named `YYYY-MM-DD-short-slug.md`:

```yaml
---
title: "Full title of the paper"
collection: publications
permalink: /publication/YYYY-MM-DD-short-slug   # never change this once published
date: 2026-03-15
authors:
  - "Ross, C. H."          # exactly "Ross, C. H." gets bolded automatically
  - "Coauthor, A. B."
venue: "Journal Name"
volume: "12"
issue: "3"                  # leave as "" if there isn't one
pages: "45–60"              # en dash, not a hyphen
doi: "10.1234/example"      # bare DOI, no https://
pdf: "/files/paperN.pdf"    # leave as "" if you can't host the PDF
type: journal               # journal | report
status: published           # published | in-review
featured: false             # true puts it on the homepage
excerpt: 'One or two sentences. Used on list pages and as the meta description.'
---

The abstract goes here as plain text. Nothing else — the PDF button, the DOI
link, and the citation box are all generated from the fields above.
```

**Two things that matter:**

- **Never edit `permalink:` on a publication that is already live.** Those URLs
  are in your CV and may be indexed by Google Scholar. If a slug truly must
  change, add `redirect_from:` with the old value in the same commit.
- **`pdf:` advertises the file to Google Scholar** via a `citation_pdf_url` tag.
  Only set it if the publisher permits self-archiving. Elementa (CC-BY) is fine;
  check Inter-Research (MEPS, ESR) and others before hosting.

## How to add a talk or a teaching entry

Drop a file in `_talks/` or `_teaching/`. **The directory decides which list it
appears in** — the `collection:` line in the front matter does not. (An outreach
talk was previously in `_talks/` with `collection: teaching`, so it showed under
Talks while living at a `/teaching/` URL.)

```yaml
---
title: "Title of the talk"
collection: talks           # must match the directory
type: "Invited Seminar"     # Contributed Presentation | Invited Lecture | ...
permalink: /talks/YYYY-MM-DD-short-slug
venue: "Where it happened"
date: 2026-03-15
location: "City, State, Country"
---

Optional body text. If you leave it empty, the entry is not linked to its own
page — it just appears in the list.
```

## How to add a news item

Edit `_data/news.yml` and add a block **at the top**:

```yaml
- date: 2026-03-15
  text: "What happened. *Markdown* works here."
  url: /publication/some-slug     # optional
  url_text: "Read the abstract"   # optional
```

The newest four appear on the homepage; all of them appear on `/news/`.

## How to update the CV PDF

Export it and save it as `files/Camille-Ross-CV.pdf` — the **same filename every
time**. Dated filenames break every link you have ever emailed. The HTML CV at
`/cv/` also prints cleanly (⌘P) as a fallback.

## Other data files

| File | Drives |
|---|---|
| `_data/news.yml` | homepage news, `/news/` |
| `_data/media.yml` | `/media/` |
| `_data/software.yml` | `/code/` |
| `_data/research.yml` | homepage research cards + `/research/` anchors |
| `_data/navigation.yml` | the top nav |

## Adding a photo

Drop the image in `images/` and set it in `_config.yml`:

```yaml
author:
  photo: "portrait.jpg"
```

That is the only change needed. With no photo, the homepage renders an abstract
contour motif instead. Set `photo: none` to remove the slot entirely.

---

## Design constraints worth preserving

- **The site always opens dark.** `prefers-color-scheme` is deliberately not
  consulted, so a visitor whose OS is set to light still gets the dark theme
  and every first-time visitor sees the same thing. Light is available only if
  someone clicks the toggle. The switch lives in three places that must agree:
  the `:root:not([data-theme="light"])` rule in `_sass/site/_tokens.scss`, the
  toggle icon rules in `_components.scss`, and `isDark()` in `_layouts/base.html`.
- **Colour never carries meaning on its own.** Every text colour clears 4.5:1 on
  both backgrounds, in both themes, under normal vision, protanopia,
  deuteranopia, tritanopia, and greyscale. `--accent` and `--link` are nearly
  identical in *luminance*, so they are invisibly different in greyscale — every
  place they are used also carries a border, weight, shape, or text cue. Body
  links are always underlined. See the contract at the top of
  `_sass/site/_tokens.scss` before changing any colour.
- **No external requests.** No webfonts, no CDN, no analytics, no JS files. Icons
  are inline SVG; the stylesheet is ~13 KB.
- **Colours live in `_sass/site/_tokens.scss` only.** Components reference
  semantic tokens (`--text`, `--link`), never raw hex. Dark mode reassigns about
  a dozen declarations and nothing else.

## Domain

The site is served at **https://camilleross.org**. Two things must agree, or
Google Scholar will advertise PDFs at a host that no longer serves them:

- `CNAME` at the repo root — what GitHub Pages reads
- `url:` in `_config.yml` — what every absolute link, the feed, and the
  `citation_pdf_url` tags are built from

### DNS records

Apex is canonical; GitHub redirects `www` to it automatically.

| Type  | Name  | Value                  |
|-------|-------|------------------------|
| A     | `@`   | `185.199.108.153`      |
| A     | `@`   | `185.199.109.153`      |
| A     | `@`   | `185.199.110.153`      |
| A     | `@`   | `185.199.111.153`      |
| AAAA  | `@`   | `2606:50c0:8000::153`  |
| AAAA  | `@`   | `2606:50c0:8001::153`  |
| AAAA  | `@`   | `2606:50c0:8002::153`  |
| AAAA  | `@`   | `2606:50c0:8003::153`  |
| CNAME | `www` | `chross22.github.io.`  |

The four A records are GitHub's anycast addresses — all four, not one. The
AAAA records are optional but cost nothing and cover IPv6-only clients.

Then in the repo: **Settings → Pages → Custom domain**, enter `camilleross.org`,
save, and once the certificate is issued tick **Enforce HTTPS**. The
certificate can take up to an hour; the tickbox stays greyed out until it is
ready, which is normal and not an error.

