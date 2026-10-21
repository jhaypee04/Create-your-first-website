ChargeTrack PWA setup
====================

Files in this package:
- chargetrack.html: updated app shell with Install app button and PWA metadata.
- manifest.webmanifest: app name, display mode and icons.
- sw.js: service worker for app-shell caching/offline fallback.
- icons/icon-192.png and icons/icon-512.png: install icons.

Deploy all of these at the SAME directory/path on your HTTPS host. Keep the filename chargetrack.html, because the manifest and service worker refer to it. Keep your existing app.js and config.js beside chargetrack.html as before; they are not replaced by this package.

Requirements and behavior:
- The site must be served over HTTPS (localhost is acceptable for development); opening the HTML as file:// will not enable PWA installation.
- On supported Android/desktop browsers, the Install app button invokes the browser install prompt when available.
- On iPhone/iPad, tap Install app for instructions, then in Safari use Share -> Add to Home Screen.
- The browser decides whether to show its native prompt. If the button gives instructions, use the browser's menu to install/add to Home Screen.
- Service-worker caching provides an app-shell/offline fallback, but live Google Sheets API operations still need a network connection.

If you rename chargetrack.html to index.html, update start_url and the service-worker APP_SHELL/fallback paths accordingly.
