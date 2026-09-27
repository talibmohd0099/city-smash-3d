# City Smash 3D

A fast, casual 3D monster-rampage game built with [Three.js](https://threejs.org/). Grow bigger by smashing buildings, dodge helicopter gunfire, and smash every building in the city before the timer runs out to reach the next level.

## Intro

Pressing **Start** plays a short skippable intro (once per launch) as one continuous camera move: a person's view from a building window as the monster arrives, then out to a helicopter and the pilot's cockpit view, then down into the game.

## Levels

- Level 1: 106 buildings, 90 seconds. Clear the whole city to unlock the next level (progress is saved).
- Each level has 2.5% more buildings and 2.5% more helicopter pressure, plus 2 extra seconds.
- The monster starts each level 1% bigger and stronger (0.4% per level after level 10).
- The city's look changes every 5 levels: Sunset City, Sunny Day, Night Lights, Snow Day (then repeats).
- Win with 8+ seconds left for 2 stars, 15+ seconds left for 3 stars.

All of these numbers are constants near the top of the `levels` section in `index.html`.

**[Play it in your browser](https://talibmohd0099.github.io/city-smash-3d/)**

## Controls

- **Touch:** drag anywhere to move, tap **SMASH!** to slam the ground
- **Keyboard:** WASD / arrow keys to move, Space to slam, Esc or P to pause
- **Pause** (top-right button) to resume, restart the level, open settings or go back to the menu. The game also pauses by itself when the app goes to the background.
- **Settings:** sound volume, vibration on/off, intro video on/off, and reset progress

## Project structure

- `index.html` / `www/index.html` — the game itself (single self-contained HTML file)
- `android/` — the Capacitor-generated Android project
- `.github/workflows/build-apk.yml` — builds a debug APK on every push to `main`

## Getting the APK

Every push to `main` builds a fresh debug APK, automatically:

- **Easiest — Releases:** go to the [Releases page](https://github.com/talibmohd0099/city-smash-3d/releases), open the latest one, and download `city-smash-3d.apk` directly.
- **Alternative — Actions artifact:** open the **Actions** tab, click the latest successful **Build APK** run, and download the `city-smash-3d-debug-apk` artifact (comes zipped) from the bottom of the page.

Either way, copy the APK to an Android phone and install it (you'll need to allow installs from unknown sources).


### Building locally

```bash
npm install
cp index.html www/index.html
cp -r lib www/
npx cap sync android
cd android
./gradlew assembleDebug
```

The APK will be at `android/app/build/outputs/apk/debug/app-debug.apk`.

## Editing the game

All game code lives in `index.html`. After making changes, copy it into `www/index.html` before syncing Capacitor (the GitHub Actions workflow does this automatically).

The game works fully offline: Three.js (r128, MIT) and the Baloo 2 font (SIL OFL) are bundled in `lib/` with their licenses.
