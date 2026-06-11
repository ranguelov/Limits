# MrBit — Limits (interactive prototype)

A self-contained, interactive UX prototype of the MrBit deposit/session **Limits** flow,
rendered inside a mobile browser shell. Built with React (bundled) and compiled to a single
`index.html` — no build step or network required to view it.

## What's inside

- **Three dashboard versions** (switch from the "popup closed" screen):
  - V1 — list cards with status dot + Edit/Create
  - V2 — `+` cards (not set) and expanded cards with allowance/spend
  - V3 — chevron rows (not set) and detailed active cards (default)
- **Full flow:** create / edit / remove a deposit or session limit
- **Business rules:** Daily ≤ Weekly ≤ Monthly hierarchy with automatic adjustment
- **Asymmetric friction:** tightening a limit applies instantly; raising/removing needs
  password + a 24-hour delay
- **Screens:** amount input (presets + range), recommendation, auto-adjustment,
  review & confirm, removal pending, top toast notifications

Open `index.html` in any browser.

## Files

- `index.html` — the deployable site (open this)
- `limits-prototype.html` — identical copy (working filename)

## Deploy (GitHub + Cloudflare Pages)

The site is a single static file, so any static host works. Steps:

### 1. Push to GitHub
```bash
cd "<this folder>"
git init
git add index.html README.md .gitignore
git commit -m "MrBit Limits prototype"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

### 2. Cloudflare Pages
- Dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
- Pick the repo, then set:
  - **Build command:** *(leave empty)*
  - **Build output directory:** `/`
- **Save and Deploy.** Cloudflare serves `index.html` at the root.

### Fastest alternative (no Git)
Cloudflare Pages → **Create** → **Upload assets** → drag this folder in → Deploy.
