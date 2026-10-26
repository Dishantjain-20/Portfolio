# Dishant Jain — portfolio

Deploy-ready static site. `index.html` plus an `assets/` folder — keep them together.

## Before you publish

Search the file for `REPLACE-ME` and `dishantjain.example` — that is everything
that still needs your input. Items 1 and 2 below are open; items 3 and 4 are done.

1. **Set your domain.** `index.html` uses `https://dishantjain.example` as a
   placeholder in the canonical link, the Open Graph / Twitter tags and the
   JSON-LD block. Find-and-replace it with your real domain. Social previews
   need absolute URLs, so relative paths will not produce a link card.
2. **Replace `assets/og-cover.jpg`.** It is a 1200×630 crop of the campus
   summit photo, generated as a placeholder. This is the image that shows up
   when the link is pasted into WhatsApp, LinkedIn or Instagram, so it is worth
   choosing deliberately.
3. ~~Add your LinkedIn and Instagram URLs.~~ Done. LinkedIn is in the contact
   section and in the JSON-LD as `sameAs`. The app share-tracking parameters
   were stripped (`?utm_source=share_via…`) — per-share session junk that does
   not belong in markup.

   **Instagram was dropped** because the account is private, so the button
   led visitors to "This profile is private". To put it back once the
   account is public, add this line after the LinkedIn button in
   `.links`:

   ```html
   <a class="btn" href="https://www.instagram.com/dishant_20" target="_blank" rel="noopener">Instagram</a>
   ```

   and add `"https://www.instagram.com/dishant_20"` to the `sameAs` array in
   the JSON-LD block near the top of the file.
4. ~~Write the Tri Mandir story.~~ Done — the case study runs under the
   spotlight numbers as four blocks: brief, constraint, what I did, outcome.
   Confirmed accurate on 27 Oct 2026.

### Things to confirm

- **Brand activations** are now split into "people reached" (Goibibo 30,000,
  Google 10,000) and "activations delivered" (Shein 8, Philips 1, Goibibo 1,
  Google 1). Those last four sum to the 11 activations claimed under
  Operations, which is why the big two read as reach. Correct it if that is
  not what the numbers meant.
- **"20,000+ team execution hours"** (Under25) was labelled "on-ground
  execution hours". For one person since Dec 2025 that is not possible, so it
  now reads as team hours. Note it is also the same figure as "20,000+
  attendees" directly above it — worth checking one isn't a copy-paste.
- **"Under25 · SAC"** and **"Under25 · IRL"** are unexplained on the page.
- **Timeline gaps** at Nov 2019 – Oct 2020 and Oct – Dec 2022.

### Not done — needs you

- **Testimonials.** One client quote next to those numbers would carry real
  weight, but it has to be a real quote.
- **A CV to download.** The print stylesheet means Cmd-P → Save as PDF gives a
  clean light-background version of this page, so you may not need a separate
  file.

## Hosting

Any static host works. Netlify drop (`app.netlify.com/drop`) takes a folder
drag-and-drop and needs no account to test. GitHub Pages and Vercel also work.

To preview locally:

```bash
cd portfolio && ruby -run -e httpd . -p 8000
```

Then open `http://localhost:8000`.

## What changed from the single-file version

- All 88 media files were pulled out of the HTML (they were base64 data URIs)
  and now live in `assets/`. First load went from 11.5 MB to about 154 KB;
  the rest streams in as you scroll.
- Videos are real `.mp4` files, so they now play in Safari and on iPhone.
- Added meta description, Open Graph / Twitter tags, favicon, and Person
  structured data.
- Fixed the mobile bug where the hero caption detached from the photo and
  landed on the stats grid.
- Card numbers resize to fit; `40 acres`, `₹1.5Cr+`, `20,000+` and `30,000`
  no longer wrap or overflow at any width.
- Tabs are a real ARIA tablist with arrow-key navigation; the lightbox and
  mobile menu are proper dialogs with focus trapping and focus restore.
- Removed the dead CSS (`.ph`, `.phrow`, `.feat`, `.mas`, `.cities`, `.th`,
  `.stat`, `.gal`, the stray `bar` selector, duplicate `.mapbox`/`.map`) and
  the `.cl` class collision between the map labels and the full-bleed band.
- Added a print stylesheet.

### Content pass

- **Hero image** is now the live show (stage, truss, crowd) instead of a candid
  of crew looking at phones. Its caption said "Live show" while its alt text
  said "Backstage briefing"; the backstage shot moved into the Live events wall.
- **Skills row**: the group selfie became the rig-and-stage build. The third
  image had an `object-position: 90% 50%` crop that cut the subject's head off.
- **Brand logo wall** renders as flat white marks with colour on hover, instead
  of mixed full-colour cartoons, gradients and wordmarks on a black page.
- **Scale vs Operations** each carry a line saying whether the numbers are
  single-event peaks or running totals, so "30+ vendors" and "250+ vendors"
  no longer look contradictory.
- **Contact** gained an availability line, a WhatsApp deep link, and
  LinkedIn / Instagram buttons.
- **Map** carries an "indicative, not to scale" note. The outline is
  hand-drawn and does not follow official boundaries — if this goes on a
  public domain, consider replacing it with a licensed outline or dropping
  the map in favour of the city list, which already carries the information.

## Round 3 changes

- Role line removed from the hero portrait caption (it stays in the Journey
  timeline, where it is your actual job title).
- **SAC / IRL** are spelled out as "Summit at Campus" and "Under25 IRL",
  with a card each explaining what the two IPs are and how they differ.
- ₹1.5Cr+ now carries **~US$180K** in all three places it appears.
- Brand activations renamed to the campaigns: **Goibibo Student Pass,
  Google One, Shein Verse, Philips OneBlade**.
- **Photo wall** restyled from pastel polaroids with tape to flat editorial
  cards with a caption rail — reads international rather than scrapbook.
- **Map replaced** with a routes diagram: every city linked back to Pune,
  hover or tap a city to light its route. No national outline, so the
  boundary-accuracy problem is gone. Labels no longer collide or clip.
- Hero image served at 2x on retina via `srcset`.

- Item 10 in your list came through empty.
- The Under25 figures in the IP cards (200+ summits, 36 cities) are
  company-reported from press coverage, not independently verified. They
  describe Under25, not your personal numbers, which stay at 30 and 13.
- The hero upscale cannot add detail that was not in the 1000px source. If
  you still have the original export of that photo, dropping it in at
  2000px wide would look genuinely sharper.

## Timeline, reconciled against the resume

The NH7 Weekender role and the Oct 2020 – Jan 2022 backstage work are now a
single entry reading **Oct 2019 – Jan 2022**, the way the resume groups them,
with the backstage period as a secondary note. Everything else matched
already: Yaha Jan 2023 – Nov 2025, Arihant Apr 2022 – Sep 2022.

### Two things on the resume to fix

1. **The Under25 start date reads "Dec 2026 – Current".** That is a future
   date, so it cannot be current. The portfolio says Dec 2025 and I left it
   there, but correct whichever is right in both places.
2. **The profile says "6 years of experience"**, while the portfolio says
   "7+ years in production". From Oct 2019 that is seven years, so the
   resume line looks like it was written a while ago and not updated.

A gap remains at **Oct – Dec 2022**, between Arihant ending and Yaha
starting. The resume has the same gap, so the portfolio is faithful to it —
worth a line if anyone asks.

### Education and languages

Added as a two-column block closing the Journey section, and mirrored into
the JSON-LD as `alumniOf` and `knowsLanguage`. No degree name is claimed for
the 2018–2021 course, since the resume does not state one — only the years
and the marks. Your home address is on the resume and deliberately stays off
a public page.
