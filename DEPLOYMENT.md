# Deploying PCCE Website to www.pcce.co.uk

## Step 1 — Add your images

Before anything else, save these two files into the `assets/` folder:
- `assets/logo.png` — the PCCE logo (the one you shared)
- `assets/danny.jpg` — your speaker photo (the one you shared)

Just drag them into the `PCCE website/assets/` folder on your Mac.

---

## Step 2 — Push to GitHub

Open Terminal and run:

```bash
cd "/Users/dannybartlett/Documents/Claude/Projects/PCCE website"
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/pcce-website.git
git push -u origin main
```

> Replace `YOUR-USERNAME` with your GitHub username. Create a new **public** repository called `pcce-website` at https://github.com/new first.

---

## Step 3 — Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, choose **GitHub Actions**
4. The site will deploy automatically — check the **Actions** tab for progress
5. It will be live at `https://YOUR-USERNAME.github.io/pcce-website/` initially

---

## Step 4 — Point your IONOS domain at GitHub Pages

Log into IONOS and add these DNS records for `pcce.co.uk`:

| Type  | Host | Value               |
|-------|------|---------------------|
| A     | www  | 185.199.108.153     |
| A     | www  | 185.199.109.153     |
| A     | www  | 185.199.110.153     |
| A     | www  | 185.199.111.153     |
| CNAME | www  | YOUR-USERNAME.github.io |

Also add an A record for the **apex domain** (`@`) pointing to the same four IPs if you want `pcce.co.uk` (without www) to redirect.

DNS changes can take up to 24 hours to propagate. GitHub Pages will automatically provision an SSL certificate (HTTPS) once DNS is live.

---

## Step 5 — Enable HTTPS in GitHub Pages settings

Once DNS propagates:
1. Go to Settings → Pages
2. Tick **Enforce HTTPS** ✓

---

## Updating the site later

Every time you push a change to the `main` branch, GitHub Actions will automatically redeploy the site within ~60 seconds.

```bash
# Make a change, then:
git add .
git commit -m "Update content"
git push
```
