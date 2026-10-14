# Session Tracker – PWA Ready

Your app is now a Progressive Web App (PWA). Users can install it from the browser.

## Files

| File                  | Purpose                              |
|-----------------------|--------------------------------------|
| `index.html`          | Main app (updated with PWA support)  |
| `manifest.json`       | App name, icons, display mode        |
| `sw.js`               | Service Worker (enables install)     |
| `icon-192.png`        | App icon 192×192                     |
| `icon-512.png`        | App icon 512×512                     |
| `apple-touch-icon.png`| iOS home screen icon                 |

## How to use / deploy

1. **Upload the whole folder** to any static hosting (Firebase Hosting, Netlify, GitHub Pages, Cloudflare Pages, your own server, etc.).

2. The site **must be served over HTTPS** (or `localhost`).  
   Opening the file directly (`file://`) will **not** show the Install option.

3. After opening the site on a phone:

   ### Android (Chrome)
   - Tap the **⋮** (three dots)
   - Look for **“Install app”** or **“Add to Home screen”**
   - Confirm → the app appears on the home screen and opens in standalone mode

   ### iPhone / iPad (Safari)
   - Tap the **Share** button
   - Choose **“Add to Home Screen”**
   - Confirm

## Notes

- The service worker caches the main page so the app can still open offline (basic support).
- Firebase and live sync still need an internet connection.
- You can replace the icons with your own (keep the same filenames or update `manifest.json`).

## Testing locally

```bash
# From this folder, start a simple HTTPS or HTTP server
npx serve .
# or
python3 -m http.server 8080
```

Then open `http://localhost:8080` on your phone (same Wi-Fi) or use Chrome DevTools → Application → Manifest / Service Workers.
