# AGENTS.md

Personal site for jonti.ca. Static files in `public/`, served by
Cloudflare Pages.

## Git

Personal repo: `JontiH/jonti_website`. Local git config sets
`user.name = JontiH` and pushes over SSH with `~/.ssh/JontiH`. Run `gh`
with `GH_TOKEN=$(gh auth token --user JontiH)`.

## Cloudflare

| Name | ID |
|------|----|
| Account | `7679249973b3ca7cd658c198c69e1e5e` |
| Pages project | `jonti-website` (`jonti-website.pages.dev`) |

Deploys run from `.github/workflows/deploy-pages.yml` on every push to
`main`, using the `CLOUDFLARE_API_TOKEN` repo secret.

Use a token scoped to this project only, not the TBC one. Local scripts
read it from `.env` (gitignored; see `.env.example`). The same token goes
in the repo secret. Permissions:

- Account: Cloudflare Pages Edit
- Account: D1 Edit (for the pizza page's vote storage)
- Zone `jonti.ca`: Zone Read, DNS Edit (once the zone exists)

## Domain

`jonti.ca` is registered at GoDaddy and is being transferred to Hover.
Nameservers are still GoDaddy's, so the custom domain is not connected
yet.
