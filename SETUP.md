# OCBC-style HTML presentation — repo setup

A self-contained system for building animated, OCBC-branded slide decks in
pure HTML/CSS/JS — no frameworks, no build step. It is extracted from the
OCBC CRAYON deck system: a fixed 1280×720 (16:9) stage that auto-scales to any
screen, with keyboard/wheel/touch navigation, reveal animations, a speaker-notes
drawer, and a mobile "rotate your device" cue.

In `web/template.html` only the **title slide** is pre-built (plus one blank
example slide). All other content is up to you, per deck — copy ready-made
slide patterns from `web/layouts.html`.

## What's in this repo

```
learningatlunch/
├── SETUP.md                          ← this file
├── CLAUDE.md                         ← the "skill": conventions Claude Code follows
├── README.md                         ← quick-start
├── index.html                        ← landing page listing every topic
├── speaker-notes-<topic>.html/.txt   ← per-topic speaker-notes pages
└── web/
    ├── template.html                 ← the deck template (title slide + blank slide)
    ├── layouts.html                  ← 9 ready-made slide patterns to copy from
    ├── python-data-foundations.html  ← full 34-slide example deck
    ├── components.html               ← gallery of the animated widgets
    ├── make_standalone.py            ← inlines fonts/images into one offline file
    ├── make_speaker_notes.py         ← notes page from the deck's data-notes
    └── assets/
        ├── bg_title_skyline.png      ← title-slide background image (skyline)
        ├── ocbc-logo.png             ← full OCBC logo (red, for light backgrounds — used on the cover)
        ├── ocbc-logo-white.png       ← full OCBC logo (white, for dark backgrounds)
        ├── ocbc-icon.png             ← small icon mark (red) — footer of light slides
        ├── ocbc-icon-white.png       ← small icon mark (white) — footer of dark slides
        └── charts/…                  ← chart PNGs used by the example deck
```

## How these decks are generated (the "skill")

There is no packaged/marketplace skill behind this system — the decks are plain
HTML, written by **Claude Code** (https://claude.ai/code) following the
conventions in this repo's `CLAUDE.md`. That file *is* the skill: it tells
Claude the scaffold to copy, the theme, and what to produce for each topic
(deck + standalone build + speaker notes + landing-page row).

To generate a deck, open the repo in Claude Code and prompt it, e.g.:

> Create a new deck `web/<topic>.html` about **\<topic\>** using
> `web/template.html` as the scaffold — match it exactly (theme, fonts,
> reveal system, notes drawer). ~N slides, every slide has a visual,
> speaker notes in `data-notes`.

And for a component gallery:

> Create `web/components-<topic>.html` — a bento-grid gallery showcasing each
> animated widget/visual from the `<topic>` deck as a standalone card,
> mirroring the style of `web/components.html`.

### GitHub reference links

| What | Link |
|---|---|
| Source repo (this system was extracted from it) | https://github.com/bbmazing/ocbccrayon |
| Source conventions file | https://github.com/bbmazing/ocbccrayon/blob/main/CLAUDE.md |
| Reference deck (the scaffold this template is cut from) | https://github.com/bbmazing/ocbccrayon/blob/main/web/python-data-foundations.html |
| Reference components gallery | https://github.com/bbmazing/ocbccrayon/blob/main/web/components.html |
| Original template folder | https://github.com/bbmazing/ocbccrayon/tree/claude/presentation-template-setup-9m21th/presentation-template |
| Standalone builder (inlines fonts/images into one file) | https://github.com/bbmazing/ocbccrayon/blob/main/web/make_standalone.py |
| Speaker-notes generator (notes page from `data-notes`) | https://github.com/bbmazing/ocbccrayon/blob/main/web/make_speaker_notes.py |

Note: Claude Code also has a `pptx` skill for real PowerPoint `.pptx` files —
that is **not** what this uses. These decks are pure HTML by design.

## Creating a new deck

1. Copy `web/template.html` → `web/<topic>.html` (all decks share the same
   `web/assets/` folder — the template references it with the relative path
   `assets/...`).
2. Open it in a browser — it already works. No server needed (fonts load from
   Google Fonts; everything else is local).
3. Write your slides, borrowing patterns from `web/layouts.html`.
4. Build the standalone + speaker notes and add a landing-page row — see
   `CLAUDE.md` for the exact commands.
5. GitHub Pages: enable Pages on the repo — the empty `.nojekyll` at the root
   is already in place so the site is served as plain static files.

## Edit the title slide

The cover is the first `<section>` in the file. Everything you'd change is
here:

```html
<section class="slide dark cover active" data-notes='["Speaker note 1","Speaker note 2"]'>
  <div class="bg"></div><div class="scrim"></div>          <!-- skyline image + white fade -->
  <div class="inner">
    <img class="logo" src="assets/ocbc-logo.png" alt="OCBC" />
    <h1 data-r data-d="1">Your Topic<span class="red">Goes Here</span></h1>
    <div class="rule" data-r data-d="2"></div>              <!-- red accent bar -->
    <div class="meta" data-r data-d="3">
      <strong>Series / event name · Audience</strong><br/>
      One-line description of the session<br/>
      Duration · Format
    </div>
    <div class="program" data-r data-d="4">Topic N of the program · OCBC</div>
  </div>
  <div class="foot"><span class="pg">01</span></div>
</section>
```

- **Title**: the `<h1>` is two lines — the first line dark ink, the
  `<span class="red">` line OCBC red (it renders as its own line).
- **Background image**: `assets/bg_title_skyline.png`, referenced from the
  `.cover .bg` rule in the CSS. Swap the file (or the path) to change it; the
  `.scrim` overlay fades it to white on the left so the title stays readable.
- **Logo**: `assets/ocbc-logo.png`, top-left. Adjust size via `.cover .logo`
  (`height:34px`).
- Also update the `<title>` in `<head>`.

## The scaffold, in 60 seconds

- **Stage**: the deck is authored at exactly 1280×720; `fit()` scales it to the
  viewport (using `visualViewport`, re-fitting on rotate/resize). Design in
  absolute pixels — never worry about responsiveness inside a slide.
- **Slides**: each `<section class="slide">` is one slide. Add `dark` for the
  dark red/charcoal treatment (covers, section dividers, closing slides).
  Page numbers, progress bar and nav dots are generated from slide order —
  insert or reorder slides freely.
- **Reveal animations**: put `data-r` on any element to fade/slide it in when
  the slide activates; stagger with `data-d="1"` … `data-d="12"`
  (each step ≈ 80 ms).
- **Speaker notes**: per-slide `data-notes='["…","…"]'` (a JSON array of
  strings — mind the single-vs-double quotes). Press **N** to toggle the
  drawer.
- **Counters**: `<div data-count="90" data-suffix="%">0</div>` animates
  0 → 90%. `data-prefix` also supported.
- **Controls**: → / ← (also Space, Enter, PageUp/Down, Home/End), mouse wheel,
  touch swipe, **N** notes, **F** fullscreen. `#5` in the URL deep-links to
  slide 5.
- **`?static`**: append to the URL to snap all animations to their final
  state — use for PDF export or QA screenshots.
- Honours `prefers-reduced-motion`; on small portrait screens a
  "rotate your device" overlay appears.

## Adding content slides (later)

Duplicate the example slide (slide 2 in the template) before the
`<!-- SLIDE-INSERT -->` marker:

```html
<section class="slide" data-notes='["…"]'>
  <div class="kicker" data-r><span class="badge"></span>Section label</div>
  <h2 class="slide-title" data-r data-d="1">Slide title</h2>
  <div class="body-area">
    <!-- your content, staggered with data-r / data-d -->
  </div>
  <div class="foot"><div class="mark"><img src="assets/ocbc-icon.png" alt=""/>OCBC</div><span class="pg">02</span></div>
</section>
```

On **dark** slides use the white assets: `ocbc-icon-white.png` /
`ocbc-logo-white.png`. The `.pg` number is overwritten automatically at load,
so its hardcoded value doesn't matter.

Style conventions to keep decks looking like one series: titles centered only
when alone, body content left-aligned; every slide gets a visual; add new
component CSS per deck as needed on top of the shared tokens.

## Theme reference

| Token | Value | Use |
|---|---|---|
| `--red` | `#EC1B23` | OCBC red — accents, kickers, highlights |
| `--red-dark` / `--red-deep` | `#B3141A` / `#7A0E12` | gradients, hover states |
| `--ink` | `#1A1A1A` | headings on light slides |
| `--text` / `--muted` / `--faint` | `#1F2937` / `#6B7280` / `#9AA1AC` | body text hierarchy |
| `--surface` / `--card` | `#FFFFFF` / `#F5F5F6` | slide + card backgrounds |
| `--tint-red` | `#FCEEEF` | light red fills behind accents |

Fonts (loaded from Google Fonts in `<head>`):
**Manrope** (headings, 500–800) · **Inter** (body, 400–700) ·
**JetBrains Mono** (code / numbers, 400–700).
