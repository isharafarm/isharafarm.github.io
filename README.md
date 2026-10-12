# Ishara Agriculture Multipurpose Farm website

Live site: https://ishworfarm.github.io/

A single page, bilingual (English and Nepali) website for Ishara Agriculture Multipurpose Farm, Chapakot, Gandaki Province, Nepal. It is plain HTML with no build step, published by GitHub Pages from the `main` branch.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole website: content, styling and scripts |
| `404.html` | Page shown for broken or mistyped links |
| `img/` | Website photos (currently sample photos from Wikimedia Commons) |
| `og-image.png` | Preview image shown when the link is shared on WhatsApp, Facebook, Viber, etc. |
| `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` | Icons for phone home screens and browser tabs |
| `site.webmanifest` | Lets visitors add the site to their phone home screen |
| `robots.txt`, `sitemap.xml` | Tell search engines what to index |
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
- **Replacing a sample photo with a real farm photo:** see the next section.

## Replacing the sample photos

The site currently uses sample photos from Wikimedia Commons, each marked "Sample photo" on the page and credited in the footer (the licences require that credit). To swap in a real farm photo:

1. Crop the photo to landscape 4:3 (for example 1280 x 960) and keep it under about 200 KB. Free tools such as squoosh.app can resize and convert it.
2. Upload it to the `img/` folder with a new name, for example `img/fish-pond.jpg`.
3. In `index.html`, find the matching `<img src="img/fish.webp" ...>` and change the `src` to the new file. Update its `alt` text (English) and the matching `img.*` entry in the `NE` list (Nepali) to describe the real photo.
4. Delete the `<span class="photo-note" ...>Sample photo</span>` next to that image.
5. Delete that photo's line from the "Photo credits" list in the footer. When no sample photos are left, delete the whole `<details class="credits">` block.

| Image in page | Product |
|---|---|
| `img/hero-hills-1200.webp`, `img/hero-hills-720.webp` | Main banner (two sizes: desktop and phone) |
| `img/fish.webp` | Fish |
| `img/honey.webp` | Honey |
| `img/shiitake.webp` | Japanese shiitake |
| `img/lemon.webp` | Lemon and Nibuwa |
| `img/duck.webp` | Ducks |
| `img/amriso.webp` | Amriso |
| `img/dalle-khursani.webp` | Spices |

## Languages and search engines

- English is the default address: https://ishworfarm.github.io/
- Nepali has its own address: https://ishworfarm.github.io/?lang=ne . Share this link with Nepali speaking customers.
- Both addresses are listed in `sitemap.xml` and linked to each other in the page head (`hreflang`), so search engines can show the right language.
- When the page text changes a lot, update the `<lastmod>` dates in `sitemap.xml`.
- The search description is the `<meta name="description">` tag (English) and `page.desc` in the `NE` list (Nepali). Keep both under about 160 characters where possible, and mention the main products and Chapakot.
- Product details are also listed in the structured data block (`application/ld+json`) at the top of `index.html`. If a product is added or removed, update it there too.

## Notes

- Product availability is described as seasonal on purpose. Avoid adding claims such as organic certification unless they are officially certified.
- The visitor's language choice is remembered in their own browser. First time visitors with a Nepali browser see Nepali automatically.
