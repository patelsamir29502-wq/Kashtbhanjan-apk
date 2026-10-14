# Shree Kasthbhanjan — Android APK project

## Chrome test
Open `index.html` in Chrome. For the best browser compatibility, serve the folder from a local web server rather than opening as `file://`.

## Build APK using GitHub Actions
1. Create a GitHub repository.
2. Upload all files/folders from this ZIP to the repository root (including the hidden `.github` folder).
3. Push to `main` or `master`.
4. Open **Actions** → **Build Android APK** and wait for it to finish.
5. Open the completed workflow run → **Artifacts** → download `Kasthbhanjan-debug-APK`.
6. Extract the artifact ZIP; it contains `app-debug.apk`.

You can also start a build manually from Actions → Build Android APK → Run workflow.

## Project layout
- `index.html` — app screen
- `style.css` — app styling
- `script.js` — app logic
- `package.json` — Capacitor and plugin dependencies
- `capacitor.config.json` — Android app identity/config
- `www/` — web assets copied into the Android app during build
- `.github/workflows/android.yml` — cloud APK build workflow

## Important notes
- The app stores its records in browser/app local storage and IndexedDB. Use the built-in Backup/Restore regularly.
- WhatsApp actions require WhatsApp or a compatible browser/app to be available.
- The workflow builds a **debug APK** for testing. A Play Store/release APK needs a signing key and a separate release workflow.
- This package preserves the features and logic in the supplied HTML. Device-specific actions (file sharing, print, folder access) can behave differently in Chrome and Android WebView; test them on the target phone.
