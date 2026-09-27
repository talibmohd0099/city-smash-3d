# Rooftop Rush (MVP)

A rooftop chase runner built from City Smash 3D's assets. You run along a straight line of rooftops with the police right behind you, and each level ends at a glowing blue building.

It is a separate, self-contained page (`rooftop-rush/index.html`). Nothing else in the repo links to it or depends on it yet.

## How to play

- The runner runs forward on its own. There are 3 lanes on every rooftop.
- **Gaps:** tap JUMP for normal gaps, and hold JUMP for a long jump over big ones. A small step up or down between touching roofs needs nothing.
- **Planks:** some gaps have wooden planks in one or more lanes. Run across them or jump.
- **Ledges:** a jump that comes up a little short grabs the ledge and climbs up. That slows you down, so the police gain on you. Coming up far short, or running into a tall wall, means you fall.
- **Rooftop obstacles:** jump over or dodge AC units, dodge water tanks, and slide under (or jump over) striped bars.
- **Police:** stumbling lets the police close in. The Escape bar shows how far ahead you are, and it refills while you run clean. If it empties, you're caught.
- **Coins:** coins mark the path of a good jump.
- **Stars:** ★ finish · ★★ collect 60% of the coins · ★★★ no stumbles.
- **Levels:** levels get longer and faster, with more long gaps and obstacles. The look cycles through City Smash's four themes. Each level's layout is the same every time you play it.

## Controls

- **Touch:** swipe left/right to change lanes, tap JUMP or swipe up to jump (hold for a long jump), swipe down to slide
- **Keyboard:** A/D or ←/→ to change lanes, Space/W/↑ to jump (hold for a long jump), S/↓ to slide, P/Esc to pause

## How the physics works

- Forward speed is constant per level (11 m/s at level 1, up to 16 m/s). Jumping uses a take-off speed and gravity, with lighter gravity while JUMP is held (up to 0.3 s) for the long jump.
- Every frame the game finds the rooftop or plank under the runner to decide between standing, falling and landing. Crossing the front wall of a higher roof means a step up (up to 0.6 m), a ledge climb (up to 1.3 m), or a bonk.
- A short grace period lets a jump still count just after running off an edge, and a press just before landing is remembered.
- The level builder simulates each jump to work out how far it can carry for the height difference. It then sizes every gap to fit inside that reach with a margin, so no gap is impossible.
- The police replay the runner's own path from a moment earlier, so they make the same jumps. Stumbles shorten that delay.

## What's reused from City Smash 3D

Building window textures, rooftop tanks, snow caps, the four themes, street lamps, the helicopter, the synth sound effects, the confetti and the whole UI style. They are copied into this file, because the original game is one closed script with nothing to import. The runner, the police officer, cars, rooftop obstacles, planks and the goal building are new and built from boxes in code.

## Not in the MVP yet

3D character models, moving platforms, turns/corners, a sprint power-up, music, and a link from the main game's menu.
