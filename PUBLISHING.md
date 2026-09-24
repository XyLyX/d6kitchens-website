# Publishing D6 Kitchens Insights

Insight articles (industry perspectives on food, hospitality and kitchen operations) plus genuine announcements, new kitchen brands, launches and milestones go here. Not routine site edits.

1. Add `_insights/<slug>.md`:

```
---
title: Dilli 6 launches on Talabat
date: 2026-10-01T09:00:00+04:00
slug: dilli-6-launches-on-talabat
description: One or two sentences shown in the list and in RSS readers.
image: /images/insights/dilli-6-launch.jpg   # optional, must be under /images/ or /assets/
image_alt: Dilli 6 thali on the pass         # required if image is set
status: published                            # or draft
---
Body in Markdown: paragraphs, ## headings, - lists, 1. numbered lists, > pull quotes, | pipe | tables |, **bold**, *italic*, [links](/), ![images](/path.jpg)
```

2. Commit and push. Netlify runs `node scripts/build.mjs` and publishes `dist/`. To preview locally, run the same command and open `dist/`.

Rules
- Never change `slug` or `date` after publishing: the GUID `tag:d6kitchens.com,<date>:insights/<slug>` is built from them. If you must rename, set `guid:` to the old value.
- `status: draft` and future-dated posts are left out of `/insights/` and `/feed.xml`.
- Only files listed in `PUBLIC` in `scripts/build.mjs` are published. `_insights/`, scripts and docs never reach the live site.
- The build fails on missing fields, bad dates, bad slugs, duplicate slugs or missing images.
- `/updates/` permanently redirects to `/insights/` (see `netlify.toml`).
