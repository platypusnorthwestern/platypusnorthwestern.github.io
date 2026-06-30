# Platypus NU — Chapter Website

Static site for the Northwestern University chapter of the Platypus Affiliated Society. Plain HTML/CSS/JS, no build step — ready for GitHub Pages.

## Deploying

1. Push this repo to GitHub (e.g. `platypus-nu/platypus-nu.github.io`, or any repo name).
2. In **Settings → Pages**, set source to the `main` branch, root folder.
3. Site goes live at `https://<org-or-user>.github.io/<repo>/` (or the root domain if the repo is named `<user>.github.io`).

## Structure

```
index.html      — landing page (reading group/coffee hours, events feed, latest Review, latest SPS, Instagram)
events.html     — full scrollable/searchable archive of past events (from Northwestern_Events.docx)
about.html      — chapter blurb + links to Platypus founding documents
contact.html    — email, Instagram, general inquiries
assets/style.css
assets/fonts/   — DIN font family (licensed, included by client)
assets/img/     — chapter logo
```

## Updating content

**Reading group / coffee break hours** — edit the `.sched-row` entries in `index.html` each quarter.

**Upcoming events** — `index.html` currently shows an empty state. When an event is scheduled, replace the empty-state card content with `.event-mini` blocks (date tag, name, location/time).

**Platypus Review / Shit Platypus Says** — update the two `.pub-card` blocks in `index.html` whenever a new issue or episode drops. Both pull from platypus1917.org/platypus-review/ and /shit-platypus-says/.

**Past events** — add new `.event-row` entries to the top of `events.html`. Each row needs a `data-type` (panel / teach-in / workshop / transcript, space-separated if multiple) and `data-year` for filtering.

## Instagram feed

The landing page reserves a tiled section for recent posts from **@nu.platypus**, currently shown as placeholder tiles linking out to the profile. Instagram's official API requires a Meta developer app + access token and isn't something that can be safely embedded in a public static repo (the token would be exposed client-side). Two real options if a live feed is wanted:

- **Embed widget service** (e.g. SnapWidget, Elfsight, Behold) — sign up for a free tier, they handle the Instagram API auth server-side and give you a copy-paste `<iframe>`/script snippet. Drop that into the `.ig-strip` card in `index.html` in place of the placeholder grid.
- **Manual curation** — swap the placeholder tiles for actual screenshots/photos each time you update the site, with the image and caption as alt text.

## Fonts

DIN family (Black, Bold, Medium, Regular, Light + italics/alternates) is loaded via `@font-face` from `assets/fonts/`. Confirm your organization's license permits webfont distribution in a public repo before publishing; if not, restrict the repo or swap to a licensed-for-web alternative.
