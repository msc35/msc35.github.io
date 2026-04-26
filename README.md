# Guidera — Marketing Site (static HTML)

A multi-page static site for the Guidera marketing presence. No build step, no dependencies — pure HTML / CSS / vanilla JS. Drop these files into any static host (GitHub Pages, Netlify, Cloudflare Pages, S3, etc.).

## What's inside

```
index.html          ← Home
features.html
how-it-works.html
cities.html
faq.html
about.html
404.html            ← Custom 404 (GitHub Pages serves this automatically)
robots.txt
sitemap.xml
styles.css          ← Single shared stylesheet (design system)
main.js             ← Vanilla JS: scroll header, mobile menu, reveal animations
assets/
  compass-pin.svg   ← PLACEHOLDER — replace with your real app icon / 3D pin
  phone-map.svg     ← PLACEHOLDER — replace with your real screenshot
  phone-audio.svg   ← PLACEHOLDER — replace with your real screenshot
  phone-chat.svg    ← PLACEHOLDER — replace with your real screenshot
```

## Deploying to GitHub Pages

1. Create (or open) your Pages repo (e.g. `msc35.github.io` or a project repo with Pages enabled).
2. Copy every file from this folder into the root of that repo.
3. Commit & push. That's it — `https://msc35.github.io/...` will serve `index.html`.

If you're serving from a project repo (e.g. `msc35.github.io/guidera-site/`), you may want to update the `SITE_URL` in `sitemap.xml` and the canonical paths.

## Replacing the placeholder images

The four SVG files in `assets/` are intentionally minimal placeholders so the layout works out of the box. Replace them with your real assets:

| Placeholder file        | Replace with                                      |
|-------------------------|---------------------------------------------------|
| `assets/compass-pin.svg`| Your 3D compass pin / app icon (PNG or SVG, ~440×440) |
| `assets/phone-map.svg`  | iPhone screenshot of the map view (~240×480 ratio)|
| `assets/phone-audio.svg`| iPhone screenshot of the audio player              |
| `assets/phone-chat.svg` | iPhone screenshot of the chat / follow-up view    |

You can keep the same filenames (easy drop-in) or change the names — just update the `<img src="...">` references in the HTML files.

For the social share image (Open Graph / Twitter), every page currently points to `assets/compass-pin.svg`. Replace with a proper `og.jpg` (1200×630 recommended) and update the `og:image` / `twitter:image` meta tags in each HTML file's `<head>`.

## Editing content

All copy lives directly in the HTML files. Search-and-replace works fine. The design system is in `styles.css` — change the CSS variables at the top of the file to retheme the whole site:

```css
:root {
  --forest: #0F4C3A;
  --terra: #C8553D;
  --cream: #FAF7F2;
  ...
}
```

## Notes

- Fonts (Instrument Serif + Geist) load from Google Fonts.
- Animations respect `prefers-reduced-motion`.
- All App Store buttons link to your existing App Store URL.
- Footer auto-updates the year via `main.js`.
