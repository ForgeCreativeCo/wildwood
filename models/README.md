# Animal models

Drop rigged, animated `.glb` files in this folder and list them in `manifest.json`.
Any species without a model keeps using the built-in procedural animal.

1. Copy `manifest.example.json` to `manifest.json`.
2. Keep only the species you have files for. Valid species keys:
   `deer`, `elk`, `boar`, `rabbit`, `turkey`, `wolf`, `bear`, `cougar`.
3. Serve the game over HTTP (browsers block loading models from `file://`):

   ```
   node tools/serve.mjs
   ```

   Then open http://localhost:8123. The start screen lists which models loaded.

## Manifest fields

| Field | Required | Meaning |
|---|---|---|
| `file` | yes | File name inside `models/` |
| `yaw` | no | Degrees to rotate so the animal faces forward. If it walks backwards use `180`, sideways `90` or `-90`. |
| `scale` | no | Fixed scale. By default the model is auto-sized to a real-world height and length for the species. |
| `clips` | no | Animation names for `idle`, `eat`, `walk`, `run`, `attack`, `death`. If omitted, they are guessed from the clip names (e.g. "Walk", "Gallop", "Attack_Bite", "Death"). |
| `walkSpeed` / `runSpeed` | no | Ground speed (m/s) the walk/run clips were authored at, to stop foot sliding. |

## Format tips

- Export as glTF Binary (`.glb`) with animations, skinning and textures embedded.
- Aim for under ~30k triangles and 2k textures per animal. Up to ~18 animals are on screen at once.
- Check the licence on every model (CC0 / CC-BY / purchased royalty-free), and keep attribution here if it's needed.

## Attribution

<!-- List CC-BY credits here, e.g. "Grey Wolf by <author>, CC-BY 4.0, <url>" -->
