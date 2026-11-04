# CLAUDE.md — Khoshly (khoshly)

Loaded automatically for sessions in this folder, on top of the portfolio
rules in `../../CLAUDE.md`.

---

## What this is

A one-page Arabic link-in-bio for فيصل الخالدي, the cook behind "خوشلي":
wordmark, name, five platform tiles (Instagram, TikTok, WhatsApp for ads and
collaborations, Snapchat, YouTube), a marquee of 17 sponsor logos and a
footer. The design came finished, as a Claude-artifact HTML export with every
font and image inlined as base64
(`Downloads/Telegram Desktop/خوشلي (3).html`, 2026-11-04). It was unpacked
into files with the design, texts and links unchanged. Change the design only
when asked.

- Language: Arabic only, RTL
- Stack: one static `index.html` with inline CSS; no JavaScript, no build
- Hosting: GitHub Pages from branch `main`, folder `/` (root); no Railway
- Address: https://jelever.github.io/khoshly/ (no custom domain yet; the
  steps are in `README.md`)
- GitHub: `jelever/khoshly` (public). `MBajily` is a collaborator, not
  admin: Settings → Pages and other repository settings need `jelever`

Keep every asset path **relative** in `index.html`: the site is served under
`/khoshly/` today and possibly at a domain root later. `404.html` is the
exception: it uses `<base href="/khoshly/">` because it is served at any
depth.

---

## Status — 2026-11-04

**Done and verified**

- Template unpacked: 5 font weights, wordmark, name and 17 sponsor logos
  extracted to `assets/` (the marquee's second set was byte-identical, so it
  reuses the same files). Proper `<head>` (lang/dir on `<html>`, canonical,
  Open Graph with `assets/img/og.png`, favicon). Links, labels, alt texts and
  icon SVGs compared against the original by script: identical.

**Open work, in priority order**

1. The owner `jelever` creates the public repository `jelever/khoshly`
   and adds `MBajily`; push `main`; owner turns on Pages (branch `main`,
   root). Then smoke-test the live address.
2. Confirm the client may self-host Thmanyah Serif Display on a public site
   (the font files are downloadable once published).
3. Custom domain, if the client wants one.

---

## Run it

```bash
cd ..                       # statics/, so the URL path matches Pages
python -m http.server 8191  # http://localhost:8191/khoshly/
```

Use port 8191 or another uncommon one; check the answering server is this
one before testing (other sessions run their own servers).
