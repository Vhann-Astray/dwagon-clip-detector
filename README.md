# dwagon-clip-detector 🐲

Automatic detection of notable moments (screams 😱 & laughter 😂) in Lina's VODs,
from **sound alone** — to help clippers spot the interesting bits without
rewatching everything.

## 🔗 The page

**→ https://vhann-astray.github.io/dwagon-clip-detector/**

Each detected moment links straight to the exact spot in the YouTube VOD.

### Features

- **Embedded player**: click a moment → the video jumps right to it (no reload if
  it's the same VOD); `←/→` step through moments.
- **Per-VOD timeline** with a **storyboard filmstrip**: colored ticks (color =
  type, height = score) are clickable; hovering shows a **preview card** (frame +
  timestamp + type/score + the spoken line); clicking an empty spot seeks there.
- **Focus a VOD** (📌): isolates it and spreads the filmstrip over **several rows**
  to fill the screen — more frames, dense clusters easier to click.
- **Transcript panel** (📄): read the full auto-transcript and jump by line, with
  a **search** supporting a **simple regex** and a **"Whole word"** toggle
  (`Para\b` matches "Para" but not "Paradox"); Enter / Prev-Next cycle through
  matches.
- **Type filters** (screams, laughter…), **minimum-score filter**, **VOD-title
  search**, and newest/oldest ordering.
- **Links**: open in a new tab ↗ or copy the timestamped link ⧉.

## How it works (in brief)

Each VOD's sound is analyzed by an audio model ([PANNs](https://github.com/qiuqiangkong/audioset_tagging_cnn),
trained on AudioSet) that recognizes screams, laughter, and more. Peaks are
grouped, scored, and exported as timestamps. **No video is ever cut**: the tool
only provides timestamps.

## Repository contents

- `index.html` — the page (static, served by GitHub Pages).
- `data.json` — the data (VODs + detected moments), reloaded on every visit.
- `transcripts.json` — consolidated auto-transcript segments, loaded in the
  background to power the transcript search.

Data is regenerated locally and the JSON files are updated — no private data is
published here (see `.gitignore`).
