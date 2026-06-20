# t1consult.com — T1 Consulting LLC marketing site

Static marketing site for **T1 Consulting LLC**, positioning the firm across product
development, manufacturing, strategy, and new product development (NPD). Led by
Thomas J. Russo, former President & CEO of First Alert.

> **Boundary:** This is the *public, Stark-free* marketing site. Confidential client,
> legal, and engagement material lives in the **private** `t1consulting-stark` repo —
> never mix the two. Every claim on this site traces to **public sources only**.

## Stack

- Plain static HTML + one shared stylesheet (`/assets/styles.css`). No build step.
- Brand tokens (navy `#0F172A`, slate `#334155`, gold `#CA8A04`, Inter) are defined once
  in `:root` in the stylesheet.
- The "T1 │• Consulting" lockup is reproduced in HTML/CSS (`.brand`) — no image asset.

## Pages

| Path | File |
|---|---|
| `/` | `index.html` |
| `/services/` | `services/index.html` |
| `/about/` | `about/index.html` |
| `/contact/` | `contact/index.html` |
| 404 | `404.html` |

## Hosting

GitHub Pages, fronted by Cloudflare — same pattern as `aunshin-site`.

- `CNAME` binds the custom domain `t1consult.com`.
- `.nojekyll` disables Jekyll processing (serve files as-is).
- DNS: apex `A` records → GitHub Pages IPs (`185.199.108–111.153`), proxied through the
  `t1consult.com` Cloudflare zone (`2704990115f989c83f84a9e522a245f0`); SSL mode `full`.
  **Mail records (MX/SPF/DKIM/DMARC) are left untouched.**

## Deploy

Edit a file, then:

```bash
git add -A && git commit -m "…" && git push
```

GitHub Pages redeploys in ~1 minute.

## Local preview

```bash
python3 -m http.server -d . 8080   # → http://localhost:8080
```
