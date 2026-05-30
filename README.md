# Zygal Admin Portal — User Guide PWA

A Progressive Web App (PWA) version of the Zygal Admin Portal Interactive User Guide. Installable on any device, works offline, and delivers a native app-like experience.

## Features

- ✅ **Installable** — Add to Home Screen on iOS, Android, and desktop
- ✅ **Offline support** — Full content available without internet via Service Worker
- ✅ **Responsive** — Works on mobile, tablet, and desktop
- ✅ **Fast** — Cache-first loading strategy for instant page loads
- ✅ **Auto-updates** — Service Worker detects and fetches new versions automatically

## File Structure

```
zygal-pwa/
├── index.html       # Main app (the user guide)
├── manifest.json    # PWA Web App Manifest
├── sw.js            # Service Worker (offline caching)
├── README.md        # This file
└── icons/           # PWA icons (all sizes)
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png
    ├── icon-384.png
    └── icon-512.png
```

## Deployment

### GitHub Pages (Recommended)

1. Push this folder to a GitHub repository
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Your PWA will be live at `https://<username>.github.io/<repo-name>/`

> **Important:** GitHub Pages serves over HTTPS, which is required for Service Workers and PWA installation.

### Other Hosts

Any static HTTPS host works: Netlify, Vercel, Cloudflare Pages, Firebase Hosting, etc.

## Testing Locally

Use a local HTTPS server (Service Workers require HTTPS or `localhost`):

```bash
# Python (simplest)
python3 -m http.server 8080
# Then open http://localhost:8080

# Node.js (npx)
npx serve .
```

## PWA Audit

Run a Lighthouse audit in Chrome DevTools → Lighthouse tab to verify PWA compliance.

## Updating the Guide

Replace `index.html` with the new version. The Service Worker cache version (`CACHE_NAME` in `sw.js`) will auto-invalidate on next visit when you bump it:

```js
// sw.js — bump this when deploying a new version
const CACHE_NAME = 'zygal-guide-v2'; // ← increment
```

---

Built with ❤️ for the Zygal Admin Portal team.
