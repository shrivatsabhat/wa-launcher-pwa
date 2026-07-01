# Send to WhatsApp — PWA

A one-screen tool: pick a country, type a number, tap **Open in WhatsApp**.
Installable on Android and iOS as a home-screen app. Works offline once installed.

## Files
- `index.html` — the app
- `manifest.json` — PWA metadata (name, icons, colors)
- `sw.js` — service worker (offline caching)
- `icons/` — app icons (192px, 512px)

## Deploy on GitHub Pages (free, ~2 minutes)

1. Create a new GitHub repository (e.g. `wa-launcher`). Public repos get free Pages hosting.
2. Upload all files in this folder to the repo root, keeping the `icons/` folder intact.
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**.
4. Branch: `main`, folder: `/ (root)`. Save.
5. Wait ~1 minute, then open the URL GitHub gives you, e.g.
   `https://<your-username>.github.io/wa-launcher/`

That's it — HTTPS is automatic on GitHub Pages, which is required for the
install prompt and service worker to work.

## Installing it
- **Android (Chrome)**: open the URL → a banner offers "Add" → tap it. Or use
  the browser menu → "Add to Home screen" / "Install app".
- **iPhone/iPad (Safari)**: open the URL → tap the Share icon → **Add to Home
  Screen**. (Safari doesn't support one-tap install prompts, hence the manual
  step — the app shows this instruction automatically on iOS.)

## Notes
- No backend, no analytics, no data leaves the device — everything runs
  client-side and phone numbers are never stored anywhere except the
  browser's local storage (only the last-used country code, to save a tap
  next time).
- To add more countries, edit the `COUNTRIES` array near the top of the
  `<script>` block in `index.html`.
