# dwagon-clip-detector 🐲

Automatic detection of notable moments (screams 😱 & laughter 😂) in Lina's VODs,
from **sound alone** — to help clippers spot the interesting bits without
rewatching everything.

## 🔗 The page

**→ https://vhann-astray.github.io/dwagon-clip-detector/**

Each detected moment links straight to the exact spot in the YouTube VOD.

### Features

- **Embedded player**: click a timestamp → the video jumps right to the moment
  (no reload if it's the same VOD).
- **Type filters**: screams, laughter…
- **Sorting**: chronological (default), best score first, or lowest.
- **Minimum-score filter** and **VOD title search**.
- **Per-VOD timeline**: every peak is clickable (color = type, height = intensity).
- **Links**: open in a new tab ↗ or copy the timestamped link ⧉.

## How it works (in brief)

Each VOD's sound is analyzed by an audio model ([PANNs](https://github.com/qiuqiangkong/audioset_tagging_cnn),
trained on AudioSet) that recognizes screams, laughter, and more. Peaks are
grouped, scored, and exported as timestamps. **No video is ever cut**: the tool
only provides timestamps.

## Repository contents

- `index.html` — the page (static, served by GitHub Pages).
- `data.json` — the data (VODs + detected moments), reloaded on every visit.

Data is regenerated locally and `data.json` is updated — no private data is
published here.
