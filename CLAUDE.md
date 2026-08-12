# Learning at Lunch — repo notes

GitHub-Pages site (`.nojekyll`) for the Learning at Lunch session series.
`index.html` is the landing page; each topic is a self-contained animated 16:9
HTML deck under `web/`. The deck system is adapted from
`bbmazing/ocbccrayon` — same scaffold, same build scripts.

## Layout

- `index.html` — landing page listing every topic.
- `web/template.html` — **start here**: a 9-slide starter deck showing every
  core layout (cover, quote, agenda cards, two-column, stat row, card grid,
  process flow, section divider, closing). Copy it to `web/<topic>.html` and
  replace the placeholder content.
- `web/python-data-foundations.html` — a full 34-slide example deck (from
  ocbccrayon) showing what a finished topic looks like.
- `web/components.html` — bento gallery of the animated widgets available.
- `web/assets/` — shared images (logos, cover skyline, chart PNGs).
- `web/make_standalone.py` / `web/make_speaker_notes.py` — build scripts.
- `speaker-notes-<topic>.html` + `.txt` — per-topic speaker-notes pages, at
  repo root (inline edit + localStorage + download .txt).

## Adding a new topic (IMPORTANT — produce all three artifacts)

1. **Deck**: copy `web/template.html` → `web/<topic>.html`, write the slides,
   then build `web/<topic>.standalone.html` with `make_standalone.py`.
2. **Speaker notes**: copy `speaker-notes-template.html` →
   `speaker-notes-<topic>.html`, then regenerate it from the deck's
   `data-notes` with `make_speaker_notes.py` (also writes the `.txt`).
3. **Landing page**: add a `.topic` block to `index.html` mirroring the
   existing rows — a `.t-head` (label · title · "Available" badge) plus a
   3-button `.actions` row: **Open the deck** → `web/<topic>.standalone.html`,
   **Components** → `web/components.standalone.html`, **Speaker notes** →
   `speaker-notes-<topic>.html` (new tab).

## Build / regenerate

```bash
cd web
# 1. rebuild the deck's self-contained standalone (inlines fonts + images)
python make_standalone.py <topic>.html <topic>.standalone.html
# 2. regenerate the speaker-notes page/.txt FROM the deck's data-notes
#    (the deck is the single source of truth; edit notes in data-notes,
#     never in the notes page directly)
python make_speaker_notes.py <topic>.html ../speaker-notes-<topic>.html \
       ../speaker-notes-<topic>.txt "Learning at Lunch — <Deck Title>"
```

`make_speaker_notes.py` rewrites only the `<div id="notes">` list, the two
slide-count strings, and the `.txt` mirror — all page chrome is preserved.
Whenever deck content or slide order changes, rebuild the standalone AND
regenerate the speaker notes.

## Deck system

All decks share one scaffold (see `web/template.html`): a fixed 1280×720
`.deck` scaled to the viewport by `fit()` (uses `visualViewport`, re-fits on
`orientationchange`); reveal-on-active animations via `[data-r]`/`data-d`;
animated counters via `data-count`/`data-prefix`/`data-suffix`; a notebook
playback demo player (`.demo-slide`, replay with `R`); speaker-notes drawer
(`N`); and a portrait "rotate your device" cue for mobile. Match this
scaffold exactly so all decks read as one series.

Theme: red `#EC1B23` accent on light surfaces, dark cover/dividers/closing;
fonts Manrope / Inter / JetBrains Mono. Every slide has a visual; titles
centered only on cover/dividers, body left-aligned.

Keys in a deck: `→`/`←` navigate · `N` notes · `R` replay demo · `F`
fullscreen. `?static` in the URL snaps animations to final (for PDF/QA
screenshots); `#<n>` deep-links to slide n.

## data-notes gotchas

Slide notes live in `data-notes='[...]'` — a JSON array inside a
single-quoted HTML attribute. **Never put a raw apostrophe (`'`) in a
note** — it terminates the attribute and breaks both the in-deck notes
drawer and `make_speaker_notes.py`. Use a right single quote `’` or an
HTML entity instead. Escape double quotes as `\"` (JSON escaping).

## Branding

The assets are currently the OCBC set carried over from ocbccrayon
(`ocbc-logo*.png`, `ocbc-icon*.png`, `bg_title_skyline.png`). To rebrand,
drop replacement PNGs into `web/assets/` and update the `<img>` refs in the
cover/footers, then rebuild the standalones.
