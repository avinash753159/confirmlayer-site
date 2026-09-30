# ConfirmLayer landing page

Single static page (`index.html`, no build step). Clean-room copy, no borrowed branding.

## Automatic deployment

`avinash753159/confirmlayer-site` is the source of truth. The GitHub Actions
workflow deploys every push to `main` to Prabhat's existing Cloudflare Worker,
`confirmlayer-site`, which serves `confirmlayer.com`. It can also be run manually
from the repository's Actions tab. Other branches and pull requests do not deploy.

The workflow requires repository Actions secrets `CLOUDFLARE_API_TOKEN` (a token
with permission to deploy Workers in the hosting account) and
`CLOUDFLARE_ACCOUNT_ID` (the hosting account ID). Never commit the API token.

Wrangler copies `index.html` and `assets/` into the ignored `dist/` directory.
Only those site files are uploaded. Validate locally with
`npx wrangler@4.144.0 deploy --dry-run`.

Before activating this workflow, disconnect the Cloudflare Builds connection to
`drgarg/confirmlayer-site` so that a push to the older copy cannot replace the
site deployed from Avinash's repo. In Cloudflare, open the Worker, then
Settings > Builds > Disconnect. The existing deployment stays live.

Contact CTA on the page points to hello@confirmlayer.com (alias already live on the Workspace account).
