# خوشلي — Khoshly

A one-page Arabic link-in-bio for فيصل الخالدي (خوشلي): his wordmark and
name, his accounts on Instagram, TikTok, WhatsApp (for ads and
collaborations), Snapchat and YouTube, and a marquee of the brands he has
worked with.

Live at **https://jelever.github.io/khoshly/** (GitHub Pages).

## Files

```
index.html                 the page; its CSS is inline, no JavaScript
404.html                   shown by GitHub Pages for any missing path
favicon.png                64×64, from the wordmark
apple-touch-icon.png       180×180, from the wordmark
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
- Preview locally from the folder above this one, so the paths match
  GitHub Pages:

  ```bash
  cd ..   # the folder that contains khoshly/
  python -m http.server 8191
  # open http://localhost:8191/khoshly/
  ```

## GitHub Pages

Repository `jelever/khoshly` (public: Pages on a free account needs it).
Set once by the owner: **Settings → Pages → Build and deployment → Deploy
from a branch → `main` / `(root)`**. Every push to `main` then goes live in
a minute or two.

## Moving to a custom domain later

1. Add a `CNAME` file containing the domain, and set the domain in
   Settings → Pages (owner only); tick *Enforce HTTPS* once the certificate
   is issued.
2. DNS at the registrar: apex A records to GitHub Pages
   (185.199.108.153, .109.153, .110.153, .111.153), `www` a CNAME to
   `jelever.github.io`.
3. In `index.html`, change the canonical and `og:` URLs to the new domain.
4. In `404.html`, change `<base href="/khoshly/">` to `<base href="/">`.
