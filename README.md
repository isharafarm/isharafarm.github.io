# Ishara Agriculture Multipurpose Farm website

Live site: https://ishworfarm.github.io/

A single page, bilingual (English and Nepali) website for Ishara Agriculture Multipurpose Farm, Chapakot, Gandaki Province, Nepal. It is plain HTML with no build step, published by GitHub Pages from the `main` branch.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole website: content, styling and scripts |
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
- **Adding photos:** upload the image to this repo (Add file, Upload files), then reference it in `index.html`, for example `<img src="fish.jpg" alt="Fish pond">`.

## Notes

- Product availability is described as seasonal on purpose. Avoid adding claims such as organic certification unless they are officially certified.
- The visitor's language choice is remembered in their own browser. First time visitors with a Nepali browser see Nepali automatically.
