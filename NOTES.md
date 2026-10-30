# Portfolio site: handover notes

Tailored to Joseph Dawes' producing and camera work. The resume is the source of
truth for every title, date, responsibility and number on the site.

## Pages

| File | What it is |
|---|---|
| `index.html` | Producing page. Positioning, PAVE portfolio totals, five selected producing projects, experience, capabilities, education and contact. |
| `camera.html` | Camera and field production. Top level nav item on both pages. |
| `archive/index-v1-clean.html` | The earlier placeholder prototype, kept for reference only. Not linked from anywhere. |
| `styled.html` | The earlier style lab (three art directions on placeholder content). Superseded by the two pages above. Not linked. |

Opening pages use any static server, not `file://`:

```bash
cd /Users/josephdawes/portfolio && python3 -m http.server 8766
# http://127.0.0.1:8766/index.html
```

## Art direction

Broadcast: condensed uppercase display type, hard rules, a data panel language for
numbers, lower third headers on case studies, SMPTE colour bars under the header.
The camera page keeps the same family but switches to a cyan accent and a slate
and bracket register, so it reads as its own destination without becoming a
different website. Palette is deliberately narrow so the real show artwork carries
the colour.

## Content decisions worth knowing

- **Portfolio totals are qualified on the page.** 12.26M views, 3.996M watch hours and
  four series are labelled PAVE portfolio totals across their respective reporting
  periods through October 29, 2026, with a note that the periods differ per series and
  that these are channel and portfolio results rather than one person's output alone.
- **Series results look different from portfolio totals on purpose.** Clues (7.08 million
  views, 2.99 million watch hours) and Crimes of Reddit (2.29 million views) use the cyan
  display treatment inside their own cards. Nothing was recalculated or extrapolated.
- **Declassified is marked "Developed, not yet released."** It is never described as launched.
- **Hidden History shows no series figure**, because none is published for it. The card says so.
- **Almost Athletes and Wingmen are two separate shows** and get a case card each. The
  100,000 to 200,000 subscriber range and the 90,000 to 300,000 average view range are
  reported at channel level in their own shared panel, because the resume reports them for
  the channels rather than per show, and they are not split between the two shows.
- **Roles are listed exactly as credited.** Where a title credits Joseph as producer rather
  than camera, the camera field says "Not itemised for this title" instead of implying a
  camera credit. The camera page has a block explaining this.
- **No phone number, home address or reference details** appear anywhere. Contact is the
  resume email only.
- Visible copy uses no em dashes, no en dashes and no emojis.

## Assets

Every image on the site is real material supplied by Joseph, resized for delivery only.
Nothing was generated, mocked up or invented.

| File | Source | Used on |
|---|---|---|
| `assets/shows/clues-art.jpg` | Channel art from YouTube `@CluesPod` | Clues card |
| `assets/shows/crimes-of-reddit-art.jpg` | Channel art from YouTube `@CrimesOfRedditPod` | Crimes of Reddit card |
| `assets/shows/hidden-history-art.jpg` | Channel art from YouTube `@hiddenhistorypod` | Hidden History card |
| `assets/shows/crime-house-art.jpg` | Channel art from YouTube `@crimehousestudios` | Prepared, unused (network badge) |
| `assets/shows/wingmen-art.jpg` | Supplied by Joseph, 1548x372 banner | Wingmen card |
| `assets/shows/almost-athletes-art.jpg` | Key art from the show's own site, cropped to a 1200x288 banner | Almost Athletes card |
| `assets/shows/declassified-walder.jpg` | `Desktop/DECLASSIFIED EP1/tracy_walder_cia_2.jpg` | Declassified card |
| `assets/shows/hidden-history-wordmark.png` | `Hidden History white stacked logo-4.png` | Prepared, currently unused |
| `assets/camera/f581.jpg` etc | `frame_581.jpg`, `frame_909.jpg`, `frame_1146.jpg`, `frame_1379678.jpg` | Camera archive, neutral captions |
| `assets/shows/clues.jpg`, `crimes-of-reddit.jpg`, `hidden-history.jpg` | Episode thumbnails | Superseded by the channel art above, unused |

Channel art was pulled from each channel's avatar and served at 900px, then downscaled to 640
for delivery. The show banners are wide, so the two Wave cards use a full width banner layout
rather than a card column, which would crop the talent out.

`assets/clips/` holds eight synthetic clips generated with ffmpeg during the earlier
prototype. They are **not referenced by any page now** and can be deleted.

## Ambiguities and missing material

1. **Unattributed studio frames.** The four archive frames carry no show label in the
   source material, so they are captioned neutrally and the page says so. Tell me which
   productions they belong to and each caption can name the show.
2. **Two further PAVE series appear in the asset library but not in the brief:**
   `CTCC` reads "Conspiracy Theories, Cults, and Crimes" and `MTCS` reads "Murder True
   Crime Stories" on their own thumbnails. The resume does not state Joseph's role on
   either, so neither is claimed on the site. They are the obvious candidates for the
   fourth series figure and for extra case studies.
3. **No camera material for the confirmed camera credits.** There is no footage, still
   or reel for 9066: Fear, Football, and the Theft of Freedom, NFL Generations, NFL AAPI
   or the Super Bowl work, so those are handled typographically. A showreel cut, a few
   stills from the 9066 shoot, or any behind the scenes photography would turn the camera
   page from a credits list into a portfolio.
4. **Full episode masters exist and are not used:** `CLUES_CELESTE RIVAS HERNANDEZ_V3-FINAL.mp4`
   (23 GB), `HH_Ep23_Final with Ads.mp4` (17 GB), `HH_Lead-Masks_V3_FINAL.mp4` (14 GB).
   Too large to serve directly. They are the raw material for a reel or for stills.
   Note `Gigantopithosis_*_Kling_30_.mp4` is AI generated, not production footage.
5. **Episode counts and launch dates** are not on the site, because the resume does not give
   them and they were not invented.
6. **Both Wave shows now carry real artwork.** Wingmen came from Joseph; Almost Athletes was
   taken from the show's own site as key art and cropped to the same banner shape, because the
   supplied Almost Athletes image never arrived. Both banners are 4.16 to 1, so the two cards
   present at identical size. The only stock that is unused here is the Almost Athletes channel
   avatar, a cartoon A on yellow, available if a square mark is ever wanted.

## Reviewing changes

Opening both pages in a browser at desktop and phone widths is the fastest review. The
review harness used during this pass lives outside the project, in
`~/.hermes/cache/scratch/review.mjs`, so no test files were added to the site.
