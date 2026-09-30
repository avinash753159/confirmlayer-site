# ConfirmLayer landing page

Single static page (`index.html`, no build step). Clean-room copy, no borrowed branding.

## Push to GitHub + Cloudflare Pages (for Avinash or Prabhat)

`gh` is not authenticated on the Muse box, so run these on a logged-in machine:

```bash
cd ~/workspace/confirmlayer/site
git init -b main
git add index.html README.md
git commit -m "ConfirmLayer landing page v1"
gh repo create confirmlayer-site --private --source=. --push
```

Then in Cloudflare: Pages > Create > Connect to Git > select `confirmlayer-site` > framework preset "None", build command empty, output directory `/`. Deploy, then add the custom domain `confirmlayer.com` (Prabhat adjusts DNS as offered).

Contact CTA on the page points to hello@confirmlayer.com (alias already live on the Workspace account).
