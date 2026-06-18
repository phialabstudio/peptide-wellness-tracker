# GLP-1 & Peptide Wellness Tracker

A private, installable wellness tracker for logging injections, weight, mood, and side effects — with a one-tap doctor summary. It runs in your browser and installs to your phone like a normal app (a **Progressive Web App**, or PWA). No app store needed.

---

## How to install the app

### iPhone & iPad
Use **Safari** for this — it won't install from Chrome on iPhone.

1. Open the app link in Safari.
2. Tap the **Share** icon (the square with an upward arrow) at the bottom of the screen.
3. Scroll down and tap **Add to Home Screen**.
4. Tap **Add** in the top corner.
5. Open the app from its new icon — it runs full-screen, with no browser bar.

### Android
1. Open the app link in **Chrome**.
2. Tap the **Install** button on the banner that slides up — or open the **⋮** menu (top right) and choose **Install app**.
3. Confirm. The icon lands on your home screen and in your app drawer.

### Computer (Chrome or Edge)
1. Open the link.
2. Click the **install icon** in the address bar — or **⋮ menu → Install**.

---

## Using the app

**It works offline.** After you've opened it online once, it keeps working with no internet — entries save instantly to your device.

**It updates itself.** When you reopen the app with an internet connection, it loads the latest version automatically. If anything looks off right after an update, fully close and reopen it once.

**Your data stays on your device.** Nothing is uploaded to a server — your logs are stored privately on your own phone. That keeps it private and offline-friendly, but it also means:

- Clearing your browser data, uninstalling the app, or switching to a new phone will **erase your logs**.
- To keep a permanent copy, use **Doctor Summary → export** every so often and save the file.

**To remove the app:** press and hold the icon, then tap Remove / Uninstall. This also clears the data stored on the device.

---

## Deploy & maintain (developer notes)

**Files in this project:**

- `index.html` — the full app, with PWA wiring built in
- `manifest.json` — app name, colors, and icon references
- `sw.js` — service worker (handles offline caching)
- `icon-192.png`, `icon-512.png` — home-screen icons

**To deploy:** place all five files in the project root and push to Vercel. HTTPS (required for PWAs) is automatic.

**To ship an update:**

1. Edit `index.html`.
2. In `sw.js`, bump the cache name: `glp1-tracker-v1` → `v2` → `v3` …
3. Push.

Skipping step 2 leaves returning users stuck on the old cached version — it's the most common PWA mistake, so make it a habit.

**To change the icon:** replace `icon-192.png` and `icon-512.png` with your own logo, keeping the same filenames and sizes (192×192 and 512×512). Keep the logo inside the center ~80% so Android's rounded crop doesn't clip it.

**To verify it's working:** install it on a phone, or open Chrome DevTools → Application tab (check Manifest + Service Workers), or run a Lighthouse PWA audit.
