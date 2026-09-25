# Memora — legal & support site

Three static pages Apple requires before Memora can be reviewed:

| Page | Used as |
|---|---|
| `index.html` | **Support URL** in the App Store listing |
| `privacy.html` | **Privacy Policy URL** in the listing, and linked from the paywall |
| `terms.html` | **Terms of Use**, linked from the paywall |

No build step, no dependencies. `style.css` carries the app's palette from
`memora/src/theme/tokens.ts` and supports light and dark.

## Publishing to GitHub Pages

From this folder:

```bash
git init
git add .
git commit -m "Memora legal and support pages"
git branch -M main
git remote add origin https://github.com/cy-crypto/-memora-site.git
git push -u origin main
```

Create the `-memora-site` repo on GitHub first (public — Pages needs it public on
the free plan, and these pages are meant to be public anyway). Then:

**Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.**

Live a minute or two later at:

```
https://cy-crypto.github.io/-memora-site/
https://cy-crypto.github.io/-memora-site/privacy.html
https://cy-crypto.github.io/-memora-site/terms.html
```

Those exact URLs are already wired into `memora/src/config.ts`. If you change the
repo name or username, change `SITE` there to match.

## Pointing a custom domain at it later

Add the domain under **Settings → Pages → Custom domain**, create a `CNAME` file
here containing the domain, and update `SITE` in `memora/src/config.ts`. The page
filenames stay the same, so nothing else moves.

## Before submitting

- [ ] All three URLs load over HTTPS in a browser
- [ ] The contact address on each page is one you actually read
- [ ] Dates at the top of `privacy.html` and `terms.html` are current
- [ ] `terms.html` reviewed by someone qualified — see the note in the repo's
      release docs; the liability and governing-law sections are a starting
      template, not legal advice
