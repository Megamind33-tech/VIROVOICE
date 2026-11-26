# Viro voice

The natural voice of **Viro**, the voice assistant inside the HOF launcher. HOF downloads these four files once (about 143 MB, on Wi-Fi), checks each one's SHA-256, and then speaks on the phone with no internet and no server.

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `duration_predictor.onnx` | 582,729 | `3b84b5626d9bad3238822bc7bf8a22f7fcec05d1de6ddc48ada7570fe66e84dd` |
| `text_encoder.onnx` | 7,251,273 | `cbb96db1dc8b3e3093d8d423296bc1699806ac06b00a38c6346d9ff30e4d261e` |
| `vector_estimator.onnx` | 34,041,483 | `0cbf3f00818b3b8bff87bd6374651cef402af50b0c4efdf923ebb9b1394a8340` |
| `vocoder.onnx` | 101,405,066 | `19bd51f47a186069c752403518a40f7ea4c647455056d2511f7249691ecddf7c` |

## The voice library

`manifest.json` lists the shared model files and every voice. A voice is just one small style file in `voices/` (about 420 KB), so a new voice costs the user a fraction of a second to download, not another 143 MB.

| Voice | Style file | | Voice | Style file |
|---|---|---|---|---|
| Mwila (woman) | `voices/F1.json` | | Kabwe (man) | `voices/M1.json` |
| Thandi (woman) | `voices/F2.json` | | Daniel (man) | `voices/M2.json` |
| Ruth (woman) | `voices/F3.json` | | Mulenga (man) | `voices/M3.json` |
| Naomi (woman) | `voices/F4.json` | | Joseph (man) | `voices/M4.json` |
| Bupe (woman) | `voices/F5.json` | | Samuel (man) | `voices/M5.json` |

### Adding a voice

1. Put the style file in `voices/` (for example `voices/F6.json`).
2. Add an entry to `manifest.json` with its `id`, `name`, `about`, `style` (the file name without `.json`), `file`, `bytes`, `sha256`, and `"builtin": false`.
3. Commit to `main`. HOF checks the manifest, shows the new voice under **More voices**, and downloads only that one file after checking its SHA-256.

## Download

Each file is available at `https://github.com/Megamind33-tech/VIROVOICE/raw/main/<file name>`. The HOF app does this for you: open **Viro**, then **Voices**, then **Get Viro's natural voices**.

## Licence

These are the Supertonic 2 models, used under the **BigScience Open RAIL-M** licence (see `LICENSE`). It allows free and commercial use, and it passes on the licence's use restrictions to anyone who receives the files. Please keep `LICENSE` with them if you redistribute.
