# AAA Marketplace

**AAA Marketplace** is a hyperlocal services Progressive Web App (PWA) by **Manglam World** —
*"Your city. Every service. One platform."*

The app is **Hindi-first** (`lang="hi-IN"`, tagline *हर सेवा, एक ऐप*) and is built to be installed
to the home screen and used like a native app.

---

## ⚠️ This branch is a build artifact

The default branch (`gh-pages`) contains **compiled output**, not source. It is **overwritten on
every deploy**.

> **Do not make source edits on this branch.** Any change committed here will be **lost** the next
> time the site is deployed.

The application source (a Vite project — note the hashed bundle names in `assets/`) lives **outside
this repository**. Changes must be made there and redeployed; there is currently no source branch in
this repo to contribute to.

---

## Deployment

- Hosted on **GitHub Pages**, served from the **`/aaa-marketplace/` sub-path** — not the domain root.
- `.nojekyll` stops GitHub Pages from running the output through Jekyll, which would otherwise strip
  files and directories beginning with an underscore.
- `404.html` is **byte-identical to `index.html`**. This is the standard GitHub Pages trick for a
  single-page app: any unknown deep link falls back to the app, which then handles routing client-side.

---

## Project structure

| Path | What it actually is |
|------|---------------------|
| `index.html` | App shell / entry point |
| `404.html` | SPA fallback — a copy of `index.html` (see above) |
| `assets/` | **Vite build output**: two hashed JS bundles and one hashed CSS file. No images or fonts here — fonts are loaded from Google Fonts at runtime |
| `banners/` | 3 promotional banner images (`assistant`, `medicine`, `offer`) |
| `services/` | 6 service-category **photographs** (`ac`, `cleaning`, `electrician`, `massage`, `plumber`, `salon`) — images only, not pages or listings |
| `icons3d/` | 83 PNG service-category icons |
| `sw.js` | Workbox-generated service worker (precaching + offline support) |
| `workbox-*.js` | Workbox runtime library used by `sw.js` |
| `registerSW.js` | Registers `sw.js` with scope `/aaa-marketplace/` |
| `manifest.webmanifest` | PWA manifest — name, icons, theme, display mode |
| `favicon.svg`, `icon-192.png`, `icon-512.png` | Favicon and installable app icons (192px, 512px, plus a maskable variant) |
| `.nojekyll` | Disables Jekyll processing on GitHub Pages |

---

## PWA configuration

- **Display:** `standalone`, locked to `portrait`
- **Theme colour:** `#2563eb` · **Background:** `#ffffff`
- **Scope:** `/aaa-marketplace/`
- **Offline:** precaching via the Workbox service worker
- **Icons:** 192px, 512px and a maskable 512px variant

---

## Known issues

Both of these originate in the source project and must be fixed there — correcting them on this
branch would be undone by the next deploy.

- **`start_url` is outside the app's scope.** The manifest sets `"start_url": "/"` while `"scope"`
  is `/aaa-marketplace/`. Since the site is served from that sub-path, launching the installed app
  can land on the domain root rather than the app itself.
- **Pinch-zoom is disabled.** `index.html` sets `maximum-scale=1.0, user-scalable=no` on the
  viewport. This gives a more native feel but prevents users from zooming, which is an accessibility
  barrier (WCAG 1.4.4) and matters for a public services app.
