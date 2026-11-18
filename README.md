# personal-site

My personal site, live at [benjaminatkinson.me](https://benjaminatkinson.me). One `index.html`, no build step, no libraries. The only external request is IBM Plex from Google Fonts.

## Edit

Everything you'd change is in the `CONFIG` block at the top of the script in `index.html`: `name`, `descriptor`, and the `links` list (`label`, `url`, `note`). Links are numbered automatically. Links to other sites open in a new tab.

Also update the `<title>`, `description`, `og:*` and `twitter:*` tags in `<head>` to match. Link previews don't run JavaScript, so they read those tags instead of `CONFIG`.

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

The custom domain is set in the `CNAME` file (keep it) and under Settings → Pages. DNS at the registrar points `benjaminatkinson.me` to GitHub Pages.
