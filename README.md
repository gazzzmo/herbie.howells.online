# herbie.howells.online

Static site for Herbie, the personal AI agent. Three pages, one stylesheet,
no build step, no JavaScript, no dependencies.

- `public/index.html` — who Herbie is
- `public/privacy.html` — privacy policy, including the Google API Services Limited Use statement
- `public/tos.html` — terms of service
- `public/404.html` — not found page
- `public/style.css` — the entire design
- `public/robots.txt`, `public/sitemap.xml`, `public/favicon.svg`
- `wrangler.jsonc` — Worker config: static assets from `./public/`, 404 page on miss
- `.github/workflows/deploy.yml` — deploys on every push to `main`

Live at https://herbie.howells.online — a Cloudflare Worker serving static
assets, with the custom domain attached to the zone `howells.online`.

## URLs

Cloudflare's asset handling canonicalises `.html` paths, so `/privacy.html`
issues a 307 to `/privacy`. All links, canonicals and the sitemap use the
extensionless form (`/`, `/privacy`, `/tos`). Do the same in anything new.

## Deployment

Push to `main`. GitHub Actions runs `wrangler deploy`, which uploads `public/`
to the `herbie-howells-online` Worker. No build command is needed.

The workflow needs one repository secret, `CLOUDFLARE_API_TOKEN`, with
Cloudflare Workers Scripts edit rights. A manual deploy from a checkout works
the same way:

```
CLOUDFLARE_ACCOUNT_ID=<account id> npx wrangler deploy
```

## Editing

Edit the HTML in `public/` and commit. Update the "Last updated" line and the
effective date on the policy pages whenever their content changes.
