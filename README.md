# personal-site

A one-page personal website. Single `index.html`: vanilla HTML and CSS, a few lines of JS, no build step, no libraries. The only external request is IBM Plex from Google Fonts.

## Edit the content

All text and links live in the `CONFIG` object at the top of the `<script>` in `index.html`:

```js
const CONFIG = {
  name: "Your Name",
  descriptor: "Student and builder. Based in Massachusetts.",
  links: [
    { label: "GitHub", url: "https://github.com/you", note: "Code" },
    { label: "Email",  url: "mailto:you@example.com", note: "Contact" },
  ],
};
```

- **name**: the large heading, the browser tab title, and the footer.
- **descriptor**: the gray line under the name, and the page's meta description.
- **links**: rendered in order and numbered 01, 02, 03 automatically. Add, remove or reorder entries freely. `note` is the small uppercase text on the right.

Links open in the same tab. Links to other sites get `rel="noopener"` automatically.

**Also update the static tags in `<head>`.** Just below the script are `<title>`, `description`, `og:*` and `twitter:*` tags with the same name and descriptor. Link previews (iMessage, Slack, LinkedIn, X) don't run JavaScript, so they read these tags directly. Change them to match whenever you change `name` or `descriptor`.

## Preview locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Deploy to GitHub Pages

1. Push the branch with your changes and merge it into `main`.
2. On GitHub, open the repo's **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose `main` and `/ (root)`, and click **Save**.
4. After a minute the site is live at `https://<your-username>.github.io/personal-site/`.

Optional extras:

- **Custom domain**: add it under Settings → Pages → Custom domain. GitHub commits a `CNAME` file to the repo; keep it. Then point your DNS at GitHub Pages (a `CNAME` record to `<your-username>.github.io` for a subdomain, or GitHub's `A` records for an apex domain) and tick **Enforce HTTPS**.
- **Skip Jekyll**: GitHub Pages runs Jekyll by default. It's harmless here, but an empty `.nojekyll` file at the root turns it off and makes deploys slightly faster.
