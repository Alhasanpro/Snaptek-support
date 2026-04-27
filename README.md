# Snaptek-support

# Pushing the Snaptek support page live (GitHub Pages)

You'll get a free public URL like `https://<your-username>.github.io/snaptek-support/`. Use that URL as your **Support URL** in App Store Connect.

## Option A — fastest, all in the browser (no terminal)

1. Go to https://github.com and sign in (create an account if you don't have one).
2. Click the **+** in the top-right → **New repository**.
3. Name it: `snaptek-support` &nbsp;·&nbsp; Visibility: **Public** &nbsp;·&nbsp; Check **Add a README** &nbsp;·&nbsp; click **Create repository**.
4. In the new repo, click **Add file → Upload files**. Drag **both files** from this folder into the upload area:
   - `index.html`
   - `icon.png` &nbsp;(the page references it as `icon.png` — they must live in the same folder)

   Then click **Commit changes**.
5. Go to **Settings → Pages** (left sidebar).
6. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **main** &nbsp;·&nbsp; Folder: **/ (root)** &nbsp;·&nbsp; click **Save**.
7. Wait ~1 minute. Refresh the Pages settings page — your URL appears at the top:
   `https://<your-username>.github.io/snaptek-support/`
8. Open it. Done.

## Option B — terminal (if you prefer git)

```bash
# from the folder containing index.html
git init
git add index.html
git commit -m "Snaptek support page"
git branch -M main
# create an empty repo on github.com first, then:
git remote add origin https://github.com/<your-username>/snaptek-support.git
git push -u origin main
```

Then enable Pages from **Settings → Pages** as in step 5–7 above.

## Use it in App Store Connect

1. Open **App Store Connect → My Apps → Snaptek**.
2. In the **App Information** section, set **Support URL** to your GitHub Pages URL.
3. Save. Apple checks this URL during review — make sure it loads publicly.

## Custom domain (optional)

If you own a domain (e.g. `snaptek.app`):

1. In your DNS provider, add a CNAME record pointing `support` (or `www`) to `<your-username>.github.io`.
2. In **Settings → Pages**, enter the custom domain (e.g. `support.snaptek.app`) and check **Enforce HTTPS** once the cert provisions.

## Updating the page later

Edit `index.html` on GitHub (pencil icon) → **Commit changes**. The site updates within a minute. No rebuild needed.

## App icon

The page is wired to load `icon.png` from the same folder as `index.html`. Drop your Snaptek icon there (square PNG, 512×512 or 1024×1024 works great) and name it exactly `icon.png` — the page picks it up automatically. If the file isn't present, an SVG fallback renders so nothing breaks.

When uploading to GitHub, upload `icon.png` alongside `index.html` so both end up in the repo root.

## Quick local preview before deploy

Open `index.html` in any browser by double-clicking — it's a single self-contained file.
