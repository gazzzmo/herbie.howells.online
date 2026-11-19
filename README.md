# herbie.howells.online

Static site for Herbie, the personal AI agent. Three pages, one stylesheet,
no build step, no JavaScript, no dependencies.

- `index.html` — who Herbie is
- `privacy.html` — privacy policy, including the Google API Services Limited Use statement
- `tos.html` — terms of service
- `404.html` — not found page
- `style.css` — the entire design
- `robots.txt`, `sitemap.xml`, `favicon.svg`

## Deployment

Hosted on Cloudflare Pages, connected to this repository. Push to `main` and
Cloudflare builds and publishes automatically. No build command, no output
directory (the repository root is the site).

Custom domain: `herbie.howells.online`, a CNAME to the Pages project.

## Editing

Edit the HTML directly and commit. Cloudflare publishes within a minute.
Update the "Last updated" line and the effective date on the policy pages
whenever their content changes.
