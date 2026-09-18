# Sunside — installable bus seat advisor

A small PWA that tells you which side of the bus to sit on, based on the sun's
real position, your route, and current sky conditions.

## Deploy on GitHub Pages (5 minutes)

1. Create a new repo, e.g. `sunside` (github.com/new).
2. Upload all the files in this folder (`index.html`, `manifest.webmanifest`,
   `sw.js`, `icon-180.png`, `icon-192.png`, `icon-512.png`) to the repo root.
3. Go to the repo's **Settings → Pages**, set Source to "Deploy from a branch",
   branch `main`, folder `/ (root)`. Save.
4. After a minute your app is live at
   `https://<your-username>.github.io/sunside/`.
5. Open that link on your phone (Chrome/Edge on Android, Safari on iOS) and
   choose "Add to Home Screen" / accept the install prompt.

Because it's hosted on your own domain (not inside claude.ai), the
"use live sky conditions" button works fully — it calls the free
Open-Meteo API directly, no key needed.

## Files
- `index.html` — the app itself
- `manifest.webmanifest` — tells the browser it's installable, sets icons/name
- `sw.js` — service worker, caches the app shell so it opens instantly and
  works offline (only the live-weather lookup needs a connection)
- `icon-180.png` / `icon-192.png` / `icon-512.png` — home screen icons

## Extending it
- Add more Nairobi stages/areas: edit the `PLACES` object near the top of
  `index.html`'s `<script>`.
- Wire in real matatu route numbers instead of area-to-area guessing.
- Swap the Open-Meteo call for a different weather provider if you prefer.
