# Monster Dash: City Smash Run

A second game built from City Smash 3D's assets: an endless 3-lane runner. The monster charges down Main Street, smashing through small buildings, dodging or slamming tall towers, grabbing coins and swatting helicopters.

It is a separate, self-contained page (`monster-dash/index.html`). City Smash 3D itself (`index.html`, `www/`, `android/`) is untouched.

## How to play

- Small buildings crumble when you run through them (points, and a little power back).
- Tall towers with a yellow arrow over them cost 25 power if you run into them. Change lanes to dodge them, or **SMASH!** them. The SMASH! button turns yellow and pulses when a slam right now will hit.
- Helicopters hover ahead and shoot at the lane you're in, so change lanes to dodge. They then swoop low over you: SMASH! them for 250 points.
- Coins give points and a little power.
- The run speeds up as you go, and the city's look changes every 500 m (Sunset City, Sunny Day, Night Lights, Snow Day).
- Stars for distance: 500 m, 1,200 m, 2,500 m. Best score and distance are saved.

## Controls

- **Touch:** swipe left/right to change lanes, swipe up or tap **SMASH!** to slam
- **Keyboard:** A/D or ←/→ to change lanes, Space / W / ↑ to slam

## What's reused from City Smash 3D

The monster and helicopter models, building window textures, rooftop tanks and snow caps, the four themes, street lamps and trees, townsfolk, debris/dust/smoke effects, all the synth sound effects, the confetti, and the whole UI style (font, colours, chips, cards, buttons). They are copied into this file, because the original game is one closed script with nothing to import.

## Running it

Open `monster-dash/index.html` in a browser (it needs internet for Three.js and the font). If GitHub Pages serves this repo, it will be at `/city-smash-3d/monster-dash/` once merged.
