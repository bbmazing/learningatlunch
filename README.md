# Learning at Lunch

A GitHub-Pages site of **PPT-style HTML decks** — self-contained, animated,
16:9 presentations that run in any browser with zero libraries and work
fully offline. The deck system is adapted from
[bbmazing/ocbccrayon](https://github.com/bbmazing/ocbccrayon).

## What's here

| Path | What it is |
|---|---|
| `index.html` | Landing page listing every topic |
| `web/template.html` | 9-slide starter template — copy this to make a new deck |
| `web/python-data-foundations.html` | Full 34-slide example deck |
| `web/components.html` | Gallery of the animated widgets |
| `web/assets/` | Shared images (logos, cover background, chart PNGs) |
| `web/*.standalone.html` | Self-contained builds (fonts + images inlined) — these are what the landing page links to |
| `speaker-notes-*.html` / `.txt` | Editable speaker-notes pages per topic |

## Creating a new deck

```bash
# 1. copy the template and write your slides
cp web/template.html web/my-topic.html

# 2. build the self-contained standalone (needs internet for Google Fonts)
cd web
python make_standalone.py my-topic.html my-topic.standalone.html

# 3. generate the speaker-notes page from the deck's data-notes
cp ../speaker-notes-template.html ../speaker-notes-my-topic.html
python make_speaker_notes.py my-topic.html ../speaker-notes-my-topic.html \
       ../speaker-notes-my-topic.txt "Learning at Lunch — My Topic"

# 4. add a topic row for it on index.html
```

Full conventions live in [CLAUDE.md](CLAUDE.md).

## Presenting

Open the `.standalone.html` in any browser (it's a single file — email it,
AirDrop it, put it on a USB stick, anything).

`→` / `←` navigate · `N` speaker notes · `R` replay a demo · `F` fullscreen ·
append `?static` to the URL to snap all animations to their final state
(useful for printing to PDF), `#12` to deep-link to slide 12.

## Publishing

Enable GitHub Pages on this repo (Settings → Pages → deploy from branch) and
the landing page goes live at the repo's Pages URL. The `.nojekyll` file is
already in place.
