# Resource Library — Deployment Guide

## What you need
- A free [Netlify](https://netlify.com) account
- A free [GitHub](https://github.com) account
- Your Airtable personal access token

---

## Step 1 — Get your Airtable token

1. Go to https://airtable.com/create/tokens
2. Click **Create new token**
3. Name it "Resource Library"
4. Under **Scopes**, add: `data.records:read`
5. Under **Access**, add your **BM Program Management** base
6. Click **Create token** and copy it — you'll need it in Step 4

---

## Step 2 — Put the code on GitHub

1. Go to https://github.com/new and create a **new repository** (name it `resource-library`, keep it private)
2. On your computer, open a terminal in this project folder and run:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/resource-library.git
git push -u origin main
```

---

## Step 3 — Deploy to Netlify

1. Go to https://app.netlify.com → **Add new site** → **Import an existing project**
2. Choose **GitHub** and select your `resource-library` repo
3. Build settings will auto-detect from `netlify.toml` — leave them as-is
4. Click **Deploy site**

---

## Step 4 — Add your Airtable token (keeps it secret)

1. In Netlify, go to **Site configuration** → **Environment variables**
2. Click **Add a variable**
3. Key: `AIRTABLE_TOKEN`
4. Value: paste the token from Step 1
5. Click **Save**
6. Go to **Deploys** → **Trigger deploy** → **Deploy site** to rebuild with the token

---

## Step 5 — Share with students

Your site will be live at something like `https://amazing-name-123.netlify.app`

You can set a custom subdomain for free:
- In Netlify → **Domain management** → **Options** → **Edit site name**
- Change it to e.g. `tbj-resources` → your URL becomes `https://tbj-resources.netlify.app`

---

## Updating content

You don't need to redeploy when you update Airtable — the app always fetches live data.
Only redeploy if you change the code.
