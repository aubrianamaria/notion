# Images for Pantry → Plate

Put image files here (e.g. `banana.jpg`, `roast-chicken.jpg`) to show them on
**every device**, not just the browser they were added in.

## How it works
The app has a `DEFAULT_IMAGES` map near the top of the `<script>` in `index.html`.
It maps an item's **id** to an image URL. Rendering uses, in order:

1. a photo set in the app for that item (saved on one device only), then
2. `DEFAULT_IMAGES[id]` (shared via this repo), then
3. the emoji tile fallback.

## To add an image
1. Commit the image file into this `images/` folder (any device can do this via
   github.com → the folder → "Add file" → "Upload files").
2. Add a line to `DEFAULT_IMAGES` in `index.html`, e.g.:
   ```js
   const DEFAULT_IMAGES = {
     banana: 'images/banana.jpg',
     roastchicken: 'images/roast-chicken.jpg',
   };
   ```
   You can also point at any public `https://…` image URL instead of a repo file.
3. The image then appears on the live site for everyone, on any device.

## Finding an item's id
Open `index.html` and look in `DEFAULT_INGREDIENTS` / `DEFAULT_DISHES` /
`DEFAULT_MEALS` — each entry has an `id:` (e.g. `id:'banana'`, `id:'roastchicken'`).
Or just tell Claude "use this image for bananas" with the URL and it'll wire it up.

> Note: the live GitHub Pages site is served from the deploy branch, so images
> must be committed there too (Claude handles this when wiring images in).
