# NEPA Date Nights

A hand-curated guide to date-night spots across Northeastern Pennsylvania — from
midday-afternoon adventures to late-night dance floors. Bars, music, creative
nights, drive-ins, seasonal attractions, and more.

The entire site is a single self-contained page: [`index.html`](index.html).
No build step, no dependencies — open it in a browser or serve it statically.

## Hosting on your own domain

**GitHub Pages (free):**

1. In this repo go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to **Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
3. Under **Custom domain**, enter your domain (e.g. `datenights.example.com`)
   and save. GitHub will add the `CNAME` for you.
4. At your DNS provider, point the domain at GitHub Pages:
   - Subdomain (`datenights.example.com`): add a `CNAME` record →
     `<your-username>.github.io`
   - Apex domain (`example.com`): add `A` records → `185.199.108.153`,
     `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
5. Wait for DNS to propagate, then tick **Enforce HTTPS** in the Pages settings.

**Netlify / Vercel / Cloudflare Pages:** drag-and-drop this folder or connect
the repo — no build command needed, publish directory is the repo root.

## Updating the site

Edit `index.html` directly (venue data lives in a `VENUES` array near the top
of the script) and commit. If you host via GitHub Pages, changes go live on
push.
