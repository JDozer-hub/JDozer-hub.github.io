# Video plan

Written before any video is uploaded, so the session where you actually do it is
mechanical. Nothing here is built yet; this is the shopping list.

## First, the important bit

**The site does not need your video, and it does not need to move with it.**

The site is two HTML files plus about 950 KB of images, roughly 2.6 MB in total. Copy
`/Users/josephdawes/portfolio` to the new computer and every page works exactly as it
does now. The video never goes in this folder. It goes to a video host, and the pages
point at it by URL.

That is also why your 23 GB masters are not a problem to be solved. They stay on a drive.
Only small web versions, or nothing at all, ever leave your machine.

## Where video actually belongs on the site

Ranked by how much it is worth to a recruiter.

| Slot | Page | Worth | What it needs |
|---|---|---|---|
| **Camera showreel** | camera | Highest. That page is currently a credits list with no footage, which is its one real weakness | 60 to 90 seconds, 16:9, one file |
| **Show episode clips** | producing | High. Proof that the shows exist and are watched | One embed per show, already public |
| **9066 clip** | camera | High, if you are cleared to show it | See the rights note below |
| **Project clips** | camera | Medium. A piece of camera work per credit | 20 to 40 seconds each |
| Pilot or trailer cuts | both | Medium | Whatever you already have public |

Right now neither page contains any video element at all. The cards use still artwork.
So this is a build job, not a paste job: I add the player, then each slot becomes a URL.

## What to export

Two jobs, two recipes. Run these from wherever ffmpeg is available; I have it here and
can do both for you.

**A web version of anything you want to stream or upload.** 1080p, faststart so it starts
playing before it finishes downloading:

```bash
ffmpeg -i INPUT.mp4 -vf "scale=1920:-2" -c:v libx264 -preset slow -crf 20 \
  -profile:v high -pix_fmt yuv420p -c:a aac -b:a 192k -movflags +faststart OUTPUT-web.mp4
```

An 81 minute 4K master at 39 Mbps comes down to roughly 1 to 1.5 GB at 1080p, which is
fine to upload to a platform. It is still far too big to serve as a direct file, which
is the whole reason for using a platform.

**A showreel.** Take the best 90 seconds, then encode tight:

```bash
ffmpeg -ss 00:12:30 -i INPUT.mp4 -t 12 -c copy cut01.mp4     # rough cuts
# then join them and encode the finished reel
```

A 90 second 1080p reel lands around 90 to 150 MB. That is the right weight for a
portfolio. Anything you would describe as "a big file" is wrong here.

**Thumbnails.** Grab a frame at the moment you want people to see:

```bash
ffmpeg -ss 00:01:20 -i OUTPUT-web.mp4 -frames:v 1 -q:v 4 poster.jpg
```

## Naming

Keep it boring so the wiring is predictable when there are twenty files:

```
assets/video/reel-2026.mp4            camera page hero
assets/video/9066.mp4                 if cleared
assets/video/nfl-generations.mp4
assets/video/poster/<same-name>.jpg   one poster per video
```

Do not put video in `assets/`. It is fine locally for testing, but if the clips end up
self hosted, video wants its own origin, not the same folder as the HTML.

## Rights, before anything goes public

- **9066: Fear, Football, and the Theft of Freedom** is NFL Media property. NFL material
  is routinely rights restricted. Check what you are cleared to publish. If you are not
  cleared, the honest options are a password protected reel you send directly, or stills
  with the credit stated, which the page already does.
- **Declassified** premieres December 1, so anything beyond a teaser is embargoed until
  then. The card currently says "Developed, not yet released", which stays accurate
  either way.
- **Super Bowl and event work**: clips often have music and talent clearances that do not
  travel to a personal site.
- Your full episode masters contain ad breaks and sponsor content. A 90 second clip
  pulled from one may carry sponsor material you would not choose to feature.

## When you switch computers

1. Copy `/Users/josephdawes/portfolio` across. That is the whole site.
2. Decide the host. My recommendation stands: Vimeo paid for the reel and camera work,
   YouTube embeds for the published shows, Cloudflare Stream if you want no third party
   branding and near zero cost.
3. Export the web versions and the reel with the recipes above.
4. Upload, then send me the URLs. I will build the player and wire each slot.

If you would rather not wait, I can build the video slots now with a placeholder in
each one, so step 4 becomes a one line change per clip instead of a build. Say the word.

## Still open on the site itself

- Declassified: add the December 1 premiere date or leave it as is.
- Almost Athletes and Wingmen now carry their real banners.
- The tunnel I gave you is temporary and has already died twice. It is for looking at the
  site on a phone, not for hosting. Real hosting is a separate small job when you are
  ready.
