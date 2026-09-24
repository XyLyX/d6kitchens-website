# Publishing D6 Kitchens updates

Only genuine announcements, new kitchen brands, launches and company milestones go here. Not routine site edits.

1. Add `_updates/<slug>.md`:

```
---
title: Dilli 6 launches on Talabat
date: 2026-10-01T09:00:00+04:00
slug: dilli-6-launches-on-talabat
description: One or two sentences shown in the list and in RSS readers.
image: /images/updates/dilli-6-launch.jpg   # optional
image_alt: Dilli 6 thali on the pass         # required if image is set
status: published                            # or draft
---
Body in Markdown: paragraphs, ## headings, - lists, **bold**, *italic*, [links](/), ![images](/path.jpg)
```

2. Run `node scripts/build-updates.mjs`, then commit and push.

Rules
- Never change `slug` or `date` after publishing: the GUID `tag:d6kitchens.com,<date>:updates/<slug>` is built from them. If you must rename, set `guid:` to the old value.
- `status: draft` and future-dated posts are left out of `/updates/` and `/feed.xml`.
- Files in `_updates/` are publicly reachable while Netlify publishes the repo root, so don't commit drafts you want kept private.
- The build fails on missing fields, bad dates, bad slugs, duplicate slugs or missing images.
