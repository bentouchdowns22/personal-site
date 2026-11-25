# personal-site

My personal site, live at [benjaminatkinson.me](https://benjaminatkinson.me). One `index.html`, no build step, no libraries. The only external request is IBM Plex Mono from Google Fonts.

## Edit

The text lives in `<p id="intro">` in `index.html`. On load, a few lines of JavaScript type it out one character at a time; links inside it (like Babson College) are kept. Without JavaScript, or with reduced motion turned on, the text shows in full.

If you change the intro, also update the `description` and `og:description` tags in `<head>`, which link previews read.

## Preview

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy

The site is served by GitHub Pages from the `minimal-site` branch. Push to that branch and the site updates in about a minute.

```bash
git push origin minimal-site
```

The custom domain is set in the `CNAME` file (keep it) and under Settings → Pages.
