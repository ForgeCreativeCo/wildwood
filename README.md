# Wildwood

A first-person wilderness survival game that runs in the browser (Three.js, no build step).

You start in a huge forest with an axe, a knife, a cast-iron pan and a cooking pot. Chop trees, break stone, hunt, cook, farm, build shelter, and make it through the seasons, and stay away from what hunts at night.

## Run it

```
node tools/serve.mjs
```

Then open http://localhost:8123 and click into the window to look around.
Opening `index.html` directly also works, but realistic animal models only load over HTTP.

## Features

- Endless procedurally generated terrain: hills, ridges, lakes, mixed pine/oak/birch forest
- Survival stats: health, food, water, rest, warmth, stamina, plus sickness, bleeding, wetness and carry weight
- Wildlife: deer, elk, boar, hare and turkey as prey; wolves (packs, night), grizzly bears and cougars as predators
- Butchering for meat, hide, fur, bone, sinew, fat and feathers
- Crafting: spear, bow and arrows, torch, bandage, fur coat, hide boots, fur hat
- Building: campfire, lean-to, bedroll, garden plot, and log walls, doorway and roof on a 4 m grid (cabins)
- Cooking (pan and pot), boiling water, stew; farming potatoes and carrots
- Day/night cycle, four seasons (6 days each), weather: clear, overcast, fog, rain, thunderstorm, snow, blizzard
- Autosave every 60 s (browser localStorage)

## Controls

| Key | Action |
|---|---|
| WASD / Shift / Space / C | Move / sprint / jump / crouch |
| Mouse 1 | Use tool, attack, draw bow |
| Mouse 2 | Throw spear, cancel building |
| E / Q | Interact / fill pot at water |
| 1–6, wheel | Select tool |
| Tab / B / M | Inventory & crafting / build menu / map |
| F / G | Eat best food / drink boiled water |
| R | Rotate building |
| Esc | Pause |

## Project layout

- `index.html`: the whole game
- `models/`: optional rigged `.glb` animal models plus `manifest.json` (see [models/README.md](models/README.md))
- `references.html`: photo reference board for animals and tools (Wikimedia Commons, linked with licences)
- `tools/serve.mjs`: tiny local web server

## Debug

The page exposes `window.WW` in the browser console, e.g. `WW.time(21)`, `WW.weather('storm')`, `WW.give('wood', 20)`, `WW.spawn('bear')`.
