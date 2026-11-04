# خوشلي — Khoshly

A one-page Arabic link-in-bio for فيصل الخالدي (خوشلي): his wordmark and
name, his accounts on Instagram, TikTok, WhatsApp (for ads and
collaborations), Snapchat and YouTube, and a marquee of the brands he has
worked with.

Live at **https://khoshly.com/** (GitHub Pages). `www.khoshly.com` and
`jelever.github.io/khoshly/` redirect there.

## Files

```
index.html                 the page; its CSS is inline, no JavaScript
404.html                   shown by GitHub Pages for any missing path
favicon.png                64×64, from the wordmark
apple-touch-icon.png       180×180, from the wordmark
CNAME                      the custom domain, khoshly.com
.nojekyll                  serve the files as they are (no Jekyll build)
assets/fonts/              Thmanyah Serif Display, five weights (woff2)
assets/img/                wordmark (webp), name (svg), og.png share image
assets/img/sponsors/       17 sponsor logos (jpg, 96 px high)
```

There is no build step: what is in `main` is what is served.

## Editing

- **A link or a handle:** edit the matching `<a class="tile …">` in
  `index.html`.
- **A sponsor:** add the logo to `assets/img/sponsors/` (jpg on white, 96 px
  high), then add it **twice** in the `.sp-track` list: once in the first
  group with its `alt` text, and once in the second group with `alt=""` and
  `aria-hidden="true"`. The marquee loops by sliding half its width, so both
  groups must hold the same logos in the same order.
- Preview locally from this folder (the site is served from the domain
  root):

  ```bash
  python -m http.server 8191
  # open http://localhost:8191/
  ```

## GitHub Pages

Repository `jelever/khoshly` (public: Pages on a free account needs it).
Settings → Pages: **Deploy from a branch → `main` / `(root)`**, custom
domain `khoshly.com`, *Enforce HTTPS* on. Every push to `main` goes live in
a minute or two. Keep the `CNAME` file: deleting it removes the domain.

## DNS (khoshly.com, on Cloudflare)

All records **DNS only** (grey cloud): GitHub issues the certificate itself
and cannot while Cloudflare proxies the traffic.

| Type | Name | Content |
|---|---|---|
| A | `@` | 185.199.108.153 |
| A | `@` | 185.199.109.153 |
| A | `@` | 185.199.110.153 |
| A | `@` | 185.199.111.153 |
| AAAA | `@` | 2606:50c0:8000::153 |
| AAAA | `@` | 2606:50c0:8001::153 |
| AAAA | `@` | 2606:50c0:8002::153 |
| AAAA | `@` | 2606:50c0:8003::153 |
| CNAME | `www` | `jelever.github.io` |

Recommended once: verify the domain for the `jelever` account (GitHub →
Settings → Pages → *Add a domain*), which gives a TXT record
`_github-pages-challenge-jelever`. It stops anyone else's repository from
claiming khoshly.com or its subdomains.
