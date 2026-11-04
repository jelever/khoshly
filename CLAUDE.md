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
- Address: https://khoshly.com/ (canonical; `CNAME` file in the repo).
  `www` and `jelever.github.io/khoshly/` redirect there. DNS is on
  Cloudflare, records DNS only; the table is in `README.md`
- GitHub: `jelever/khoshly` (public). `MBajily` is **not** a collaborator:
  git's stored login is `MBajily`, so push with `gh`'s `jelever` login:
  `git -c credential.helper= -c 'credential.helper=!gh auth git-credential' push`.
  Settings → Pages is changed by the user, not from Claude Code

Keep every asset path **relative** in `index.html`. `404.html` uses
`<base href="/">` because GitHub Pages serves it at any depth.

---

## Status — 2026-11-04

**Done and verified**

- Template unpacked: 5 font weights, wordmark, name and 17 sponsor logos
  extracted to `assets/` (the marquee's second set was byte-identical, so it
  reuses the same files). Proper `<head>` (lang/dir on `<html>`, canonical,
  Open Graph with `assets/img/og.png`, favicon). Links, labels, alt texts and
  icon SVGs compared against the original by script: identical.
- Published 2026-11-04 at https://jelever.github.io/khoshly/ (Pages built
  60eb224). Live `index.html` byte-identical to the commit; fonts, logos,
  icons and og.png 200; missing paths 404 with the custom page; http 301 to
  https.

**Open work, in priority order**

1. khoshly.com: DNS records at Cloudflare (README → DNS), then push the
   `CNAME` commit, check the domain in Settings → Pages, wait for the
   certificate, tick *Enforce HTTPS*, smoke-test apex, `www` and the
   github.io redirect.
2. Verify the domain for the `jelever` account (TXT
   `_github-pages-challenge-jelever`).
3. Confirm the client may self-host Thmanyah Serif Display on a public site
   (the font files are downloadable).

---

## Run it

```bash
python -m http.server 8191  # from this folder: http://localhost:8191/
```

Use port 8191 or another uncommon one; check the answering server is this
one before testing (other sessions run their own servers).
