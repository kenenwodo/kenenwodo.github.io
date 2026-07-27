# kenenwodo.github.io

Personal academic site for Kenechukwu (Kene) Nwodo. Static Jekyll site, hosted on
GitHub Pages. Content lives in per-entry files so adding a publication, talk, poster,
or service item is just dropping in one new file — no template edits.

## Run locally

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

## Where everything lives

| Page              | Edit this                                   |
|-------------------|---------------------------------------------|
| Home (About/News) | `_pages/about.md` and `_data/news.yml`      |
| Publications      | one file per paper in `_publications/`      |
| Research          | one file per role in `_research/`           |
| Talks             | one file per talk in `_talks/`              |
| Posters           | one file per poster in `_posters/`          |
| Service           | one file per item in `_service/`            |
| CV                | drop a dated PDF into `files/cv/` (see below) |
| Profile / links   | the `profile:` block in `_config.yml`       |
| Colors / styling  | `assets/css/main.css` (top `:root` block)   |

The photo is `images/kene_profile.jpg`. Replace it with the same filename to swap it.

## Adding content (copy a block, change the fields)

### A publication — new file in `_publications/`, e.g. `2027-usenix-agents.md`
```yaml
---
title: "Full paper title"
authors: "First Author, **Kenechukwu Nwodo**, Third Author."   # your name in **bold**
venue: "Conference or journal name"
year: 2027
category: "Conference Papers"   # Under Review | Book Chapters | Conference Papers | Thesis
order: 1                         # position within its category (lower = higher)
link: "https://doi.org/..."      # optional — leave "" for no link
note: ""                         # optional italic note, e.g. "Title withheld — under blind review"
---
```
If `link` is set, the title becomes a clickable link (with a ↗). If it's `""`, the
title is plain text.

### A talk — new file in `_talks/`, e.g. `2027-05-01-usenix-talk.md`
```yaml
---
title: "Talk title"
venue: "Where you're presenting"
location: "City, ST"
date: 2027-05-01
link: ""     # optional link to slides / event page
order: 1
---
Optional one-paragraph description goes here (below the front matter).
```

### A poster — new file in `_posters/`, e.g. `2027-08-01-ndss-agent-eval.md`
```yaml
---
title: "Poster title"
venue: "Where you're presenting"
location: "City, ST"
date: 2027-08-01
link: ""      # optional link to an event/abstract page
order: 1
---
```
To attach the poster PDF, drop a file into `files/posters/` with the **same name** as
the poster's `.md` file. So for `_posters/2027-08-01-ndss-agent-eval.md`, the PDF is
`files/posters/2027-08-01-ndss-agent-eval.pdf`. The "View poster (PDF)" button then
appears automatically — there's no path to type. If no matching PDF exists yet, no
button shows, and you can add the PDF later without touching the `.md` file.

Adding a poster at another conference is just those two same-named files: the `.md`
entry and (optionally) the matching `.pdf`.

### A research / experience entry — new file in `_research/`
```yaml
---
role: "Your role / title"
org: "Organization"
type: "Industry"     # "Graduate Research" or "Industry"
dates: "Jun 2027 – Aug 2027"
order: 1
---
Description. Bullet points work too — start lines with "- ".
```

### A service item — new file in `_service/`
```yaml
---
what: "Reviewer"                 # the thing you did / role / award
org: "Conference or organization"
category: "Review"               # Review | Teaching | Award | Affiliation
year: "2027"
order: 1
body: ""                         # optional extra sentence (used for teaching)
---
```

### A news item — edit `_data/news.yml`
```yaml
- order: 1                       # lower shows first
  date: "Sep 2027"
  text: "Markdown works here, incl. **bold** and [links](https://...)."
```

## Adding links to existing items
Every publication, talk, and poster file has a `link:` field. Fill it in to make the
title clickable — nothing else to change. (For a poster's PDF, see "Adding content"
above: same-named file in `files/posters/`.)

## Updating your CV
Drop the new PDF into `files/cv/` with a dated name in the form `cv-YYYY-MM-DD.pdf`,
e.g. `cv-2026-08-15.pdf`. The "CV" nav link automatically points to the newest one
(the site sorts by that date in the filename). No template or config edits needed.

Old versions stay in the folder as an archive — you can delete them or leave them;
they're not linked anywhere, only the newest is. The date is right there in the URL
when someone opens it. Use zero-padded numbers (`08` not `8`) so the sort stays correct.

