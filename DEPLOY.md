# 🚀 Quick Deploy Guide

The GitHub token doesn't have repo-creation permissions, so here's the 2-minute manual setup:

## Step 1: Create the repo (30 seconds)
1. Go to: https://github.com/new
2. Repository name: `saanvi-turns-one`
3. Set to **Public**
4. Do NOT check "Add a README" (we already have one)
5. Click **Create repository**

## Step 2: Tell Kai the repo is created
Just message: "repo is created" — Kai will push all the files and enable GitHub Pages automatically.

## Or push manually:
```bash
cd saanvi-invite-site
git remote add origin https://github.com/shravanpn7/saanvi-turns-one.git
git push -u origin main
```

## Step 3: Enable GitHub Pages
1. Go to: https://github.com/shravanpn7/saanvi-turns-one/settings/pages
2. Source: **Deploy from a branch**
3. Branch: **main** / **/ (root)**
4. Click Save

## Step 4: Activate FormSubmit.co
1. Open your live site and submit a test RSVP with your own email
2. Check your email for a confirmation email from FormSubmit
3. Click the activation link — this is a one-time step
4. After activation, all future RSVPs will forward to your Gmail

Your site will be live at: **https://shravanpn7.github.io/saanvi-turns-one/**
