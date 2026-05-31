# Voices of the Wild Earth — mythweaver.org

A free, permanent archive site for **The Idaho Mythweaver's** *Voices of the Wild Earth*
podcast. Plain HTML/CSS — no build step, no server, no recurring hosting cost. Hosted on
GitHub Pages; the domain stays registered at Squarespace and simply points here.

## What's in here
- `index.html` — landing page (story, the peoples honored, full episode archive)
- `episodes/*.html` — one page per episode (Apple Podcasts player + listening links)
- `assets/style.css`, `assets/img/` — theme and optimized images
- `CNAME` — tells GitHub Pages to serve this at `mythweaver.org`
- `.nojekyll`, `robots.txt`, `sitemap.xml`

Audio is **not** stored here. Episodes stream from the podcast's own feed
(`anchor.fm/s/104b18190`) via the Apple/Spotify players, so nothing breaks when the old
Squarespace site is cancelled.

## Deploy (one time)
1. Create the repo `voicesofthewildearth/voices` on GitHub (done).
2. Upload the **contents of this folder** to the repo root (so `index.html` is at the top).
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / `/ (root)` → Save.
4. Settings → Pages → **Custom domain**: enter `mythweaver.org` → Save (the `CNAME` file already sets this).
5. Wait for the green check, then tick **Enforce HTTPS**.

## Point the domain (in Squarespace DNS)
In Squarespace → Domains → mythweaver.org → DNS settings, set:
- Four **A** records for the host `@` →
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- One **CNAME** record: host `www` → `voicesofthewildearth.github.io`

DNS can take a few hours to propagate. Once it resolves and HTTPS is enforced, the old
Squarespace **website** subscription can be cancelled — keep only the domain registration.

## Updating later
Edit the HTML directly, or re-run the generator (`build.py` + `episodes.py`) and re-upload.
