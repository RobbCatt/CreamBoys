# Cream Boys Fantasy League — Setup Guide

## What you need (all free)
- GitHub account → github.com
- Supabase account → supabase.com
- Netlify account → netlify.com
- Anthropic API key → console.anthropic.com

---

## Step 1 — Supabase (database)

1. Go to supabase.com → New project → name it "creamboys"
2. Once created, go to **SQL Editor** and run this:

```sql
create table app_data (
  key text primary key,
  value jsonb,
  updated_at timestamp default now()
);
```

3. Go to **Settings → API**
4. Copy your **Project URL** and **anon/public key**
5. Open `public/index.html` and paste them into the CONFIG block at the top:

```javascript
window.CONFIG = {
  SUPABASE_URL: "https://YOUR-PROJECT.supabase.co",
  SUPABASE_KEY: "your-anon-key-here",
};
```

---

## Step 2 — GitHub (host your code)

1. Go to github.com → New repository → name it "creamboys"
2. Upload all files from this folder to the repo

---

## Step 3 — Netlify (deploy the site)

1. Go to netlify.com → Add new site → Import from GitHub
2. Select your "creamboys" repo
3. Build settings: leave everything blank (no build command needed)
4. Click **Deploy**
5. Go to **Site Settings → Environment Variables** and add:
   - Key: `ANTHROPIC_API_KEY`
   - Value: your Anthropic API key from console.anthropic.com

---

## Step 4 — Go live!

Your site will be at something like `https://creamboys.netlify.app`

Share the link with the boys. Everyone sees the same data in real time.

On iPhone: Share → Add to Home Screen → looks just like an app!

---

## Updating the roster

Use the **Line Up** tab in the app to manually add/edit/remove players anytime.
The **🔄 Auto-Refresh** button pulls the latest roster automatically.
