# GO CLAUDE YOURSELF — VERCEL DEPLOY GUIDE

---

## WHAT'S IN THIS FOLDER

```
go-claude-yourself-DEPLOY/
├── src/
│   └── App.js              ← The entire React app
├── public/
│   └── index.html          ← HTML shell
├── package.json            ← Dependencies
├── .gitignore              ← Keeps node_modules out of Git
└── DEPLOY-INSTRUCTIONS.md  ← This file
```

⚠️ YOU STILL NEED TO MANUALLY COPY THESE FILES INTO public/:
- soap-bar.png
- bg-bubbles.png
- claude-glitch.png
- 07. Soap.mp3
- 17. Corporate World.mp3

Copy them from: C:\Users\xP4R4\Desktop\go-code-yourself\public\

---

## STEP 1 — COPY YOUR MEDIA FILES

Open File Explorer.
Go to: C:\Users\xP4R4\Desktop\go-code-yourself\public\
Select ALL files EXCEPT index.html.
Copy them into: C:\Users\xP4R4\Desktop\go-claude-yourself-DEPLOY\public\

---

## STEP 2 — CREATE A GITHUB REPO

1. Go to https://github.com and sign in
2. Click the green "New" button (top left)
3. Name it: go-claude-yourself
4. Set it to PUBLIC
5. Do NOT check "Add README" or "Add .gitignore"
6. Click "Create repository"
7. Copy the repo URL shown — looks like:
   https://github.com/YOUR_USERNAME/go-claude-yourself.git

---

## STEP 3 — PUSH TO GITHUB

Open a terminal (Command Prompt or PowerShell).
Run these commands one at a time:

```
cd C:\Users\xP4R4\Desktop\go-claude-yourself-DEPLOY

git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/go-claude-yourself.git
git push -u origin main
```

Replace YOUR_USERNAME with your actual GitHub username.
When prompted, sign in to GitHub.

---

## STEP 4 — DEPLOY ON VERCEL

1. Go to https://vercel.com and sign in (use "Continue with GitHub")
2. Click "Add New Project"
3. Find "go-claude-yourself" in your repo list — click "Import"
4. On the Configure page:
   - Framework Preset: Create React App (auto-detected)
   - Root Directory: ./ (leave as default)
   - Build Command: npm run build (auto-filled)
   - Output Directory: build (auto-filled)
5. Click "Deploy"
6. Wait ~60 seconds

Vercel will give you a live URL like:
https://go-claude-yourself.vercel.app

---

## STEP 5 — CUSTOM DOMAIN (OPTIONAL)

In your Vercel project dashboard:
1. Click "Settings" → "Domains"
2. Type your domain (e.g., goclaudeyourself.com)
3. Follow the DNS instructions Vercel gives you
4. Point your domain registrar's nameservers or add the CNAME/A record shown

---

## FUTURE UPDATES

Every time you make changes to App.js, just run:

```
cd C:\Users\xP4R4\Desktop\go-claude-yourself-DEPLOY
git add .
git commit -m "describe your change here"
git push
```

Vercel auto-deploys within ~30 seconds of every push.

---

## AUDIO NOTE

If audio doesn't play on the live site, rename the files:
- "07. Soap.mp3"        → soap.mp3
- "17. Corporate World.mp3" → corporate.mp3

Then update these two lines in App.js:
  '/17.%20Corporate%20World.mp3'  →  '/corporate.mp3'
  '/07.%20Soap.mp3'               →  '/soap.mp3'

Then commit and push again.
