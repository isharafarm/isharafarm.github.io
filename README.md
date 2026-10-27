# Ishara Agriculture Multipurpose Farm website

Live site: https://isharafarm.github.io/

A single page, bilingual (English and Nepali) website for Ishara Agriculture Multipurpose Farm, Chapakot, Gandaki Province, Nepal. It is plain HTML with no build step, published by GitHub Pages from the `main` branch.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole website: content, styling and scripts |
| `404.html` | Page shown for broken or mistyped links |
| `og-image.png` | Preview image shown when the link is shared on WhatsApp, Facebook, Viber, etc. |
| `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` | Icons for phone home screens and browser tabs |
| `site.webmanifest` | Lets visitors add the site to their phone home screen |
| `robots.txt`, `sitemap.xml` | Tell search engines what to index |
| `img/` | Farm photos used on the page |
| `video/` | Gallery videos (MP4) and their cover images |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Making changes on GitHub

1. Open `index.html` in this repo and click the pencil icon (Edit this file).
2. Make the change (use Ctrl+F / Cmd+F to find the text).
3. Click **Commit changes**, add a short description, and commit to `main`.
4. The live site updates within about a minute or two. Check progress under the **Actions** tab.

## Where the text lives

Every piece of text exists in two places, and both should be updated together:

- **English** is written directly in the page, on elements marked `data-i18n="some.key"`.
- **Nepali** is in the `NE` list inside the `<script>` near the bottom of `index.html`, under the same key.

Example: the honey description is `data-i18n="honey.p"` in the page, and `"honey.p": "..."` in the `NE` list.

## Common edits

- **Phone / WhatsApp number:** search for `9779846036728` and `9846036728` and replace every occurrence.
- **Product descriptions:** search for the product name, then update the matching key in the `NE` list.
- **Photos:** see "Farm photos" below.

## Farm photos

All photos on the site are the farm's own, stored in `img/` as WebP (small and fast on phones). Products without a photo yet (Honey, Shiitake, Ducks) show a drawn icon instead.

| File | Used for |
|---|---|
| `img/farm-hills-1200.webp`, `img/farm-hills-720.webp` | Main banner (desktop and phone sizes) |
| `img/fish.webp` | Fish |
| `img/nibuwa.webp` | Lemon and Nibuwa |
| `img/amriso.webp` | Broom Grass (Amriso) |
| `img/akbare-khursani.webp` | Spices |

To add or replace a photo:

1. Crop it to landscape 4:3 (product photos 640 x 480, banner 1200 x 900) and keep it under about 200 KB. squoosh.app can resize and convert to WebP, and it also removes the phone's location data.
2. Upload it to `img/` (Add file, Upload files).
3. In `index.html`, point the `<img src="...">` at the new file. For a product that still shows a drawing, replace its `<svg>...</svg>` inside `<div class="art ...">` with an `<img>` like the Fish one.
4. Each photo has an English description in `alt="..."` and a Nepali one in the `NE` list under the matching `img.*` key. Update both.

## Gallery

The "Life on the farm" section (`id="gallery"` in `index.html`) shows photos and videos. Each item is a `<figure>` with a caption; the English caption is in the page and the Nepali one is in the `NE` list under the matching `gal.*` key.

- **Videos** are MP4 (H.264), 720p, so they play on iPhone, Android and Windows. They have no sound (audio is removed) and only download when a visitor taps play. Keep each under about 10 MB. iPhone `.MOV` files must be converted first, for example with HandBrake (preset "Fast 720p30"), which also removes location data.
- Each video has a cover image (`video/<name>-poster.webp`) shown before it plays.
- To add an item, copy an existing `<figure>` block, change the file names, the `width`/`height` (the file's real size), and the caption key, then add the Nepali caption to the `NE` list.

## Languages and search engines

- English is the default address: https://isharafarm.github.io/
- Nepali has its own address: https://isharafarm.github.io/?lang=ne . Share this link with Nepali speaking customers.
- Both addresses are listed in `sitemap.xml` and linked to each other in the page head (`hreflang`), so search engines can show the right language.
- When the page text changes a lot, update the `<lastmod>` dates in `sitemap.xml`.
- The search description is the `<meta name="description">` tag (English) and `page.desc` in the `NE` list (Nepali). Keep both under about 160 characters where possible, and mention the main products and Chapakot.
- Product details are also listed in the structured data block (`application/ld+json`) at the top of `index.html`. If a product is added or removed, update it there too.

## Notes

- Product availability is described as seasonal on purpose. Avoid adding claims such as organic certification unless they are officially certified.
- The visitor's language choice is remembered in their own browser. First time visitors with a Nepali browser see Nepali automatically.
