# Mini Toads Gallery

A clean, auto-updating gallery for the **Mini Toads** Solana collection.

Collection address:  
`AE3o4tmcnLHAX1PSSMsRLLnxV3eXAoidXnM7kXwS6cp5`

---

## What it does

- Beautiful static gallery hosted on **GitHub Pages**
- Shows every piece with **image + name + links** (mallow · Tensor · Solscan)
- GitHub Action runs **every 8 hours** and checks for new artworks
- When a new piece appears on-chain → the gallery is updated automatically

---

## Quick Setup (5 minutes)

### 1. Create the repository

1. Go to [github.com/new](https://github.com/new)
2. Name it e.g. `mini-toads-gallery`
3. Keep it **Public**
4. Click **Create repository**

### 2. Upload the files

You can either:

**Option A – Upload via web**
- Download this folder as ZIP
- On the new repo page → **Add file** → **Upload files**
- Drag the whole contents of `mini-toads-gallery` (index.html, style.css, data/, .github/, README.md)

**Option B – Git (recommended)**
```bash
git clone https://github.com/YOUR_USERNAME/mini-toads-gallery.git
cd mini-toads-gallery
# copy all files from this project into the folder
git add .
git commit -m "Initial Mini Toads gallery"
git push
```

### 3. Add free Helius API key (required)

1. Go to [https://dev.helius.xyz](https://dev.helius.xyz) and sign up (free)
2. Create an API key
3. In your GitHub repo:
   - **Settings** → **Secrets and variables** → **Actions**
   - **New repository secret**
   - Name: `HELIUS_API_KEY`
   - Value: paste your key
4. Click **Add secret**

### 4. Enable GitHub Pages

1. Repo **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` (or `master`) → `/ (root)`
4. Save

Your site will be live at:  
`https://YOUR_USERNAME.github.io/mini-toads-gallery/`

### 5. First run

Go to **Actions** tab → select **Check for new Mini Toads** → **Run workflow**

After it finishes, refresh the site. New pieces will appear automatically from now on.

---

## Manual trigger

You can force an update anytime from the **Actions** tab.

---

## Customization

- Change the check interval: edit `.github/workflows/check-new-nfts.yml`  
  (cron expression, currently `0 */8 * * *`)
- Style: edit `style.css`
- Card links / layout: edit `index.html`

---

## Notes

- Free Helius plan is more than enough for this use case.
- The Action only commits when there are actual changes (new NFTs).
- Images are loaded from the on-chain metadata / CDN.

Enjoy the gallery! 🐸
