# City Smash 3D

A fast, casual 3D monster-rampage game built with [Three.js](https://threejs.org/). Grow bigger by smashing buildings, dodge helicopter gunfire, and beat your best score before the 90-second timer runs out.

**[Play it in your browser](https://talibmohd0099.github.io/city-smash-3d/)**

## Controls

- **Touch:** drag anywhere to move, tap **SMASH!** to slam the ground
- **Keyboard:** WASD / arrow keys to move, Space to slam

## Project structure

- `index.html` / `www/index.html` — the game itself (single self-contained HTML file)
- `android/` — the Capacitor-generated Android project
- `.github/workflows/build-apk.yml` — builds a debug APK on every push to `main`

## Building the APK yourself

1. Push a change to `main` (or run the workflow manually from the **Actions** tab).
2. Once it finishes, open the **city-smash-3d-debug-apk** artifact on that run and download `app-debug.apk`.
3. Copy it to an Android phone and install it (you'll need to allow installs from unknown sources).

### Building locally

```bash
npm install
cp index.html www/index.html
npx cap sync android
cd android
./gradlew assembleDebug
```

The APK will be at `android/app/build/outputs/apk/debug/app-debug.apk`.

## Editing the game

All game code lives in `index.html`. After making changes, copy it into `www/index.html` before syncing Capacitor (the GitHub Actions workflow does this automatically).
