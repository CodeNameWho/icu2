# LocShare — Cross-Platform PWA (iOS + Android)

Privacy-first live location sharing. No trackers, no analytics, no accounts required.

## Files

| File | Purpose |
|------|---------|
| `location-share.html` | The full app (host + view) |
| `assets/manifest.json` | PWA manifest (Android install, TWA) |
| `assets/sw.js` | Service worker (offline cache) |
| `assets/icon-192.png` | App icon |
| `assets/icon-512.png` | Large app icon |
| `assets/splash-*.png` | iOS Safari startup screens |

## Install on iPhone (iOS Safari)

1. Open your hosted URL in **Safari** (not Chrome — iOS only supports PWA install via Safari)
2. Tap the **Share** icon (box with arrow) at the bottom of Safari
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **Add** — the app icon appears on your home screen
5. Open it — runs fullscreen with no browser UI

> The `apple-mobile-web-app-capable`, `apple-touch-icon`, and splash screen meta tags ensure it looks and feels native on iOS.

## Install on Android (Chrome)

1. Open your hosted URL in **Chrome**
2. An install banner will appear at the top — tap **Install**
3. Or: tap Chrome menu → **Add to Home screen**

## Host the app (required for both platforms)

Upload all files to any static HTTPS host:

- **GitHub Pages** (free): push to a repo, enable Pages in Settings
- **Netlify** (free): drag-and-drop the folder at netlify.com/drop
- **Cloudflare Pages** (free): connect your repo

Your URL will be something like `https://yourname.github.io/locshare/location-share.html`

## Turn it into a native Android APK (TWA)

See the `twa-locshare/` folder included in this ZIP. Follow `twa-locshare/README.md` to build a signed APK with Android Studio.

## Privacy

- Zero analytics SDKs
- Zero ad networks  
- GPS coordinates sent peer-to-peer via WebRTC (not through a server)
- Public STUN server (stun.l.google.com) used for NAT traversal only
- Session handshake uses a public WebSocket relay — it never sees GPS data
- Nothing stored after page refresh
