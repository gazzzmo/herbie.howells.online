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

Pages use absolute paths (`/style.css`), so they work from any depth and from
either host.

## Deployment

Cloudflare, connected to this repository. Push to `main` and it builds and
publishes automatically.

Two ways to attach it, both fine:

| Route | Settings |
|---|---|
| Worker with static assets | Build command blank, deploy command `npx wrangler deploy` (the default). `wrangler.jsonc` at the root tells Wrangler where the files are. |
| Pages | Framework preset None, build command `exit 0`, build output directory `public` |

Custom domain: `herbie.howells.online`.

## Editing

Edit the HTML in `public/` and commit. Cloudflare publishes within a minute.
Update the "Last updated" line and the effective date on the policy pages
whenever their content changes.
