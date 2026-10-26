# Mock Test App by Tausif — Android

The app is in `www/` (a single `index.html`). Two ways to get it on an Android phone.

## Option A — Install from Chrome (no build, 2 minutes)
1. Upload the contents of `www/` to any HTTPS host (GitHub Pages, Netlify, Cloudflare Pages, Vercel).
2. Open the URL in Chrome on the phone → menu ⋮ → **Install app** / **Add to Home screen**.
3. It opens full-screen like a normal app and works offline after the first load.

## Option B — Real APK (Capacitor + Android Studio)
Needs Node 18+, Android Studio (includes the SDK) and JDK 17.
```
npm install
npx cap add android
npx cap sync android
npx cap open android      # opens Android Studio
```
In Android Studio: **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
The debug APK appears in `android/app/build/outputs/apk/debug/`. Copy it to the phone and install it
(allow "Install unknown apps"). For Play Store use **Build → Generate Signed Bundle**.

Note: Tailwind, pdf.js and the Inter font are loaded from CDNs, so the very first launch needs internet.
The Chrome install (Option A) caches them for offline use; for a fully offline APK, bundle those libraries into `www/`.
