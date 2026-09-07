# Hydra OS landing — how to host later ($0)

**Do not deploy from this note until Founder says go.** This folder is static HTML+CSS only (no build step).

**Files:** `index.html` · `styles.css` · this README  
**Primary CTA:** https://complexity88.gumroad.com/l/hydra-os  
**Support:** hydra.os.help@proton.me

---

## Local preview (now)

```bash
cd landing
python -m http.server 8080
# open http://127.0.0.1:8080
```

Or open `index.html` directly in a browser (CSS path is relative; works either way).

---

## Option A — GitHub Pages (free)

1. Create a public (or private with Pages enabled) repo, e.g. `hydra-os-landing`.
2. Push the contents of this `landing/` folder to the repo root (or `/docs`).
3. GitHub → **Settings → Pages**:
   - Source: Deploy from a branch
   - Branch: `main` / root (or `/docs` if you used that)
4. Wait for the Pages URL (`https://<user>.github.io/<repo>/`).
5. Optional: custom domain under Pages → Custom domain (DNS at your registrar).

**CLI sketch:**

```bash
cd landing
git init
git add index.html styles.css README-HOST.md
git commit -m "Hydra OS marketing landing"
# create empty repo on GitHub, then:
git remote add origin git@github.com:<USER>/hydra-os-landing.git
git branch -M main
git push -u origin main
```

Then enable Pages in the GitHub UI as above.

---

## Option B — Cloudflare Pages (free)

1. Sign in at [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages**.
2. **Connect to Git** (recommended): link the repo that contains these files; build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/` (or the subfolder if the landing is not repo root)
3. Or **Direct Upload**: zip `index.html` + `styles.css`, upload via Wrangler / dashboard.
4. Deploy → get `*.pages.dev` URL. Attach a custom domain if you want.

No Node build required.

---

## Option C — Netlify (free tier)

1. [app.netlify.com](https://app.netlify.com) → **Add new site**.
2. **Import from Git**: connect the repo; publish directory = folder with `index.html` (e.g. `.` or `landing`). Build command: empty.
3. Or drag-and-drop the `landing/` folder onto Netlify Drop.
4. Site gets a `*.netlify.app` URL; optional custom domain in Domain settings.

---

## Checklist before you publish the site

- [ ] CTA still points to https://complexity88.gumroad.com/l/hydra-os
- [ ] Support email still `hydra.os.help@proton.me`
- [ ] No API keys / secrets in HTML or CSS
- [ ] Spot-check mobile + contrast
- [ ] Optional: replace the Demo placeholder with a self-hosted embed (Gumroad already has the video)

## Hard constraints (keep on the live page)

- No trading / get-rich promises  
- Trade / Operar called out as not included  
- Residual Spanish honesty kept  
- No personal LinkedIn face / photo  
- Lifetime = files, not tokens  

---

*Hosting guide only — this landing was not deployed by the agent that wrote it.*
