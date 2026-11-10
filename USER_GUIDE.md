# Axion — User Guide

**🌐 Language:** [English](USER_GUIDE.md) · [فارسی](USER_GUIDE_fa.md)

> Welcome to Axion, the all-in-one plugin for studying and researching PDFs and for language learning.
> This guide walks you from installation to every feature, with tips and troubleshooting.

**Table of contents**

1. [What is Axion?](#1-what-is-axion)
2. [Requirements](#2-requirements)
3. [Installation](#3-installation)
4. [First launch](#4-first-launch)
5. [Core concepts](#5-core-concepts)
6. [PDF highlights](#6-pdf-highlights)
7. [Sticky notes](#7-sticky-notes)
8. [Text boxes](#8-text-boxes)
9. [Translation](#9-translation)
10. [Read aloud (TTS)](#10-read-aloud-tts)
11. [Flashcards](#11-flashcards)
12. [OCR](#12-ocr)
13. [Pomodoro, To-do, Calendar](#13-pomodoro-to-do-calendar)
14. [Screenshots and screen recording](#14-screenshots-and-screen-recording)
15. [Quick actions and custom shortcuts](#15-quick-actions-and-custom-shortcuts)
16. [Settings reference](#16-settings-reference)
17. [Commands](#17-commands)
18. [Data and backup](#18-data-and-backup)
19. [Troubleshooting](#19-troubleshooting)
20. [FAQ](#20-faq)
21. [Privacy](#21-privacy)
22. [Getting help](#22-getting-help)

---

## 1. What is Axion?

Axion turns Obsidian + PDF into a complete language-learning workspace. You can:

- **Highlight** text on PDFs and add **sticky notes** right next to it.
- **Translate** selected text into other languages (online or **offline**).
- **Hear** the text spoken by natural neural voices (**offline**).
- Turn any word or sentence into a **flashcard** reviewed with spaced repetition.
- **Export** everything to Anki in one click.
- **Read scanned pages and images** with OCR.
- Manage your study with **Pomodoro**, **to-do** and a **Persian calendar**.

All computation stays on your device once the models are downloaded. Your data, audio files and cards live inside your vault.

---

## 2. Requirements

| Component | Minimum |
|---|---|
| Obsidian | **1.4.0** or newer |
| Desktop | Windows 10+, macOS 12+, or Linux (AppImage / deb) |
| Mobile | Android 10+ / iOS 15+ (limited: no screen recording) |
| RAM | 2 GB free for offline translation, 512 MB for other features |
| Disk | ~1 GB free if you use all offline models |

Axion works **without** an internet connection after the first download of each model. Only the online translation engine needs the internet every time.

---

## 3. Installation

### Option A — Community plugins (once published)

1. Open Obsidian → **Settings** → **Community plugins** → **Browse**.
2. Search for **Axion** → **Install** → **Enable**.

### Option B — Manual installation

1. Download `main.js`, `manifest.json`, `styles.css` from the [latest release](https://github.com/mojtabashoghi/axion/releases).
2. Place them inside `YourVault/.obsidian/plugins/axion/`.
3. In Obsidian: **Settings** → **Community plugins** → **Reload** → toggle **Axion** on.

### Option C — BRAT (beta testers)

1. Install the **BRAT** plugin from the community directory.
2. In BRAT: **Add Beta plugin** → paste `mojtabashoghi/axion`.
3. Enable Axion.

---

## 4. First launch

When you enable Axion the first time:

1. The **side panel** opens on the right with seven sections: *Capture*, *Player*, *Flashcards*, *Heatmap*, *Pomodoro*, *To-Do*, *Calendar*.
2. A **floating dock** appears on top of any PDF you open.
3. Nothing is downloaded yet. The first time you *translate*, *read aloud* or *scan an image*, the required model is downloaded and cached. You can also pre-download from **Settings → Axion**.

**Recommended first steps**

- Open a PDF → click **🖍️ highlight** → choose a colour → drag a rectangle over text.
- Add a **sticky note** to that highlight → add a **translation**.
- Press the **flashcard** button in the sticky note toolbar.
- Go to the side panel → **Flashcards** → review.

---

## 5. Core concepts

### Study folders

Every PDF you highlight or annotate gets its **own study folder** next to it:


The **note (`Chapter 3.md`) is the source of truth** — if you edit it in another app, Axion picks up the change. The `.json` files are caches for positioning and recovery.

### The side panel

The right-hand panel is where you'll spend most of your time. Every section can be collapsed independently, and the panel remembers your choices.

| Section | What it does |
|---|---|
| **Capture** | Recording, mic, screen, screenshot, settings shortcut |
| **Player** | Playback control for whatever is being spoken |
| **Flashcards** | Review session with SRS grading |
| **Heatmap** | Your study history (streaks, total reviews) |
| **Pomodoro** | Focus timer with automatic breaks |
| **To-Do** | Daily task list with time-based alarms |
| **Calendar** | Persian (Jalali) + Gregorian, with tasks |

### The PDF dock

When a PDF is open you'll see a floating toolbar. Drag it by the grip on the left. Collapse it with the **⌄** button if it's in the way.

| Button | Action |
|---|---|
| 🖍️ | Highlight tool (choose colour and mode) |
| 📝 | Sticky note tool |
| ✏️ | Text box tool |
| 👁️ | OCR (read a region) |
| 🌐 | Translate selected text |
| 🔊 | Read selected text |
| 🃏 | Turn the selected text into a flashcard |
| 📋 | Toggle auto-paste from the clipboard |
| 📷 | Screenshot / screen recording menu |
| ↗️ | Open the PDF's note |
| ⚙️ | Axion settings |
| ✏️ (Markdown) | Markdown formatting for the note or open sticky note |

---

## 6. PDF highlights

### Create a highlight

1. Click the **🖍️ highlight** button on the dock (or use the command palette → *Axion: highlight*).
2. The cursor changes; drag a rectangle over the text you want.
3. Release. The highlight is created instantly.

The dock's popover lets you pick:

- **Mode**: *Highlight only* / *Highlight + sticky note* / *Highlight + sticky note (no translation)*
- **Shape**: rounded corners (like a marker) or flat corners
- **Colour**: yellow / green / pink / blue / orange / purple

The chosen mode and colour are remembered for the next highlight.

### Edit or delete a highlight

- **Click a highlight without a note** → a delete button appears.
- **Right-click a highlight** → menu with *Make a sticky note*, *Colour…*, *Round corners*, *Delete*.

### Recovery

If you ever lose `highlights.json`, don't panic. Axion scans the note for `%%hl:…%%` markers and rebuilds the file from them next time you open the PDF.

---

## 7. Sticky notes

There are two kinds of sticky notes:

### 7.1. Attached to a highlight

These appear as a small pin next to a highlight and contain a note that belongs to the highlighted text.

**To create one**

1. Choose *Highlight with sticky note* in the highlight tool popover.
2. Drag over text.
3. The note opens automatically. Start typing.

**What's inside**

- **Rendered lines** — each line shows the text, its translation (red = language 1, blue = language 2), with play buttons and Persian RTL support.
- **Your note** — free-form text under the lines. You can write `::` or `:::` here to make a flashcard.
- **Footer** — the page number and a link to open the note in the main editor.

### 7.2. Free sticky notes (not attached to a highlight)

These are pins you place anywhere on a page.

**To create one**

1. Click **📝 sticky** on the dock.
2. Choose a type:
   - **Empty** — a Markdown note.
   - **Table** — pick rows × columns, then click.
3. Choose a colour.
4. Click on the page.

Free sticky notes can be:

- **Dragged** by their pin to any position.
- **Renamed** by double-clicking the label next to the pin.
- **Edited** with Markdown, a table, or the OCR'd text.

### Pin, close, delete

- **Pin** — keeps the popup open until you click the pin button again.
- **Close (✕)** — deletes the whole sticky note, its flashcard (if any) and the highlight from the PDF.

> **Tip:** the sticky-note toolbar has its own **preview** button (eye icon) that flips between the rendered Markdown and the raw source without losing your cursor.

---

## 8. Text boxes

To place plain text anywhere on a page (like a label, a heading, or a note on a diagram):

1. Click **✏️ text** on the dock.
2. Click on the page (or drag a horizontal line to fix the width).
3. Type.

A small toolbar appears above the box:

- **Font** — any font installed on your system.
- **A− / A+** — font size.
- **B / I** — bold / italic.
- **Left / Centre / Right** — alignment.
- **Colour** — text colour (7 presets).
- **Background** — 6 colours or none.

Drag the box by its grip to move it. Drag the right edge to change the width. Escape to exit.

---

## 9. Translation

Axion has **two translation engines** — you can pick which one is used first, and Axion falls back to the other if the first fails.

### Online (Google Translate)

- Fast, no download required.
- Requires an internet connection **every time**.
- Recommended if you translate occasionally.

### Offline (NLLB-200 distilled 600M)

- ~900 MB download once.
- Runs entirely on your device (WASM + ONNX).
- Slower on first launch (loading the model), fast afterwards.
- **Recommended if you translate often** or need privacy.

### Configure

**Settings → Axion → Translation →**

- *Preferred engine* — Google / Offline
- *Fall back to the other engine* — on/off
- *Download model* — button
- *Unload model after N minutes* — free RAM

### Use

Select text in a note → right-click → **Axion: sticky note + translation**, or click the **🌐** button on the PDF dock.

Inside a sticky note, the **🌐** button in its toolbar adds a translation *under the current line*.

### Languages

- **Automatic detection** for the source language.
- Persian punctuation (؟ ؛ ،) is fixed automatically.
- RTL rendered correctly everywhere.

---

## 10. Read aloud (TTS)

Axion uses **Piper**, a fast neural TTS that runs fully offline in the browser.

### Voices

**Settings → Axion → Read aloud →**

| Language | Voices |
|---|---|
| German | Thorsten (male), Kerstin, Ramona, Eva K, Karlsson, Pavoque, MLS, Thorsten emotional |
| English | Lessac, Amy, Ryan, HFC (male/female), Joe, Kathleen, Alba, Alan, Jenny, Cori, LibriTTS, MLS |
| French | Siwis, Tom, UPMC, Gilles, MLS, MLS 1840 |

Pick one voice per language.

### Use

- **Select text → 🔊 button** (or *Axion: read selection aloud*).
- **Inside a sticky note** — the ▶ button next to each line.
- **On a PDF** — the ▶ button in the translated line.

The **Player** section of the side panel shows:

- Play / Pause / Stop
- Speed (0.5× – 2.0×, remembers your choice)
- Seek bar with elapsed / total time

### Audio caching

The first time a line is read, its `.wav` is saved in the study folder's `audio/` directory. The **same file** is used:

- Next time you play that line
- For the flashcard of that line
- For the exported Anki card

You'll never generate the same sentence twice.

---

## 11. Flashcards

Axion uses **spaced repetition** (a variant of the Anki SM-2 algorithm).

### Creation

There are four ways to make a flashcard:

1. **Automatic** — from any word or sentence you paste into a note (opt-in).
2. **Manual button** — click **🃏** on the dock or in the sticky note toolbar.
3. **Note markers** — write in your sticky note:
   - `:: text` → single card (all translations on one face)
   - `front ::: back` → two-sided card
   - `text` (with the *flashcard button*) → single card
4. **From an existing highlight** — right-click → *Make a sticky note*, then press the flashcard button.

### Review

Open the side panel → **Flashcards** section.

You'll see:

- The current card (front only in two-sided mode).
- **Show answer** button.
- Four buttons: **Again / Hard / Good / Easy**, each showing when you'll see the card again.
- A **🗑 Delete** button.
- A link to the source note.

**Keyboard shortcuts** during review:

| Key | Action |
|---|---|
| Space / Enter | Reveal the answer |
| 1 | Again |
| 2 | Hard |
| 3 | Good |
| 4 | Easy |

### Review limits

**Settings → Axion → Flashcards → New cards per day** — how many never-seen cards you'll see each day. Due cards are always unlimited.

### Heatmap

The **Heatmap** section shows your last 20 weeks:

- **Today** — how many reviews you did today.
- **Day streak** — consecutive days with at least one review.
- **Best streak** — all-time record.
- **Last 20 weeks** — total reviews.
- The grid itself, hover to see the exact number on each day.

### Export to Anki

**Settings → Axion → Flashcards → Export to Anki**

1. Enter your **deck name**.
2. *(Optional)* toggle **Create missing audio** to generate any missing `.wav` files first.
3. Click **Export .apkg**.

The `.apkg` file is created in `Language audio/Anki export/`. Open it with **Anki Desktop** or **AnkiDroid**.

The export includes:

- Two-sided or single card layout — matches your settings.
- All audio files.
- Proper font / colour / RTL formatting.

---

## 12. OCR

Axion can read text from:

- **PDFs with a real text layer** — instantly and exactly, no OCR needed.
- **Scanned PDF pages** — via Tesseract.
- **Images in your notes** — via Tesseract.

### Setup

**Settings → Axion → OCR →**

- Tick your **languages** (Persian, English, German, French, Arabic).
- Choose **quality** — *Best* (more accurate, larger) or *Fast*.
- Click **Download** to pre-download the files.
- Enable **Download automatically** so the first scan downloads on demand.

### Use

1. Click **👁️ OCR** on the dock (or use the command palette).
2. Drag a rectangle over the area you want to read.
3. Wait a moment while Tesseract works (progress is shown).
4. The text is copied to your **clipboard**. If *Auto paste* is on, it lands in your note automatically.

### Tips

- Draw the rectangle **tightly** around the text.
- For small print, set **Enlarge before reading** to 3×.
- For photos with a coloured background, turn **Grey + contrast** off.
- For one line of text (a title, a label), set **What is in the rectangle** to *One line*.

---

## 13. Pomodoro, To-do, Calendar

### Pomodoro

**Side panel → Pomodoro**

- Big ring shows the countdown.
- ▶ / ⏸ / ↺ / ⏭ buttons.
- Below: *🍅 today: N · round: X/4*

**Settings → Axion → Pomodoro →** Focus / Short break / Long break / Long break after — minutes and count.

The timer keeps running even when you switch notes. **Auto-advance** starts the next phase automatically.

### To-Do

**Side panel → To-Do**

Each task has:

- Text
- Optional start time (`from`) and end time (`to`)
- Optional single date (`on`) — leave empty to repeat daily

**Alerts:**

- A tune plays when a task starts and when it ends.
- An optional notice is also shown.
- Tune and volume are configurable.

**Suggested length** — when you only enter the start time, end time is auto-filled (`start + suggested length`).

### Calendar

**Side panel → Calendar**

- **Persian (Jalali) calendar** with Gregorian subtitle.
- Click any day → see tasks for that day.
- Add a task for that day right there.
- Tasks without a date appear every day. Tasks with a date appear only on that date.

---

## 14. Screenshots and screen recording

### Screenshot

1. Click **📷 capture** on the dock → **camera** icon, or use *Axion: screenshot* from the command palette.
2. Drag a rectangle over anything on the screen.
3. The image is copied to the **clipboard**. If *Save image* is on, it's also saved to the PDF's study folder → `images/`.

If the clipboard isn't available (some Linux setups), the screenshot is always saved to disk.

### Screen recording

*Desktop only.*

1. Click **📷 capture** → **record** icon.
2. Choose what to record — a screen or a window.
3. Choose options:
   - **Microphone** on/off
   - **System audio** on/off (Windows only)
   - **Quality** — low / medium / high
   - **Frame rate** — 15 / 30 / 60 fps
   - **Max height** — 720 / 1080 / native
4. Recording starts. During recording you can:
   - ⏸ Pause / resume
   - 🎤 Mute / unmute mic
   - 🔈 Mute / unmute system audio
5. Click **stop**. The file is saved in the PDF's `Video/` subfolder and linked in the study note.

**On mobile:** Axion cannot record the screen. Use your device's own screen recorder and press **📎 Attach recording** to add the video.

---

## 15. Quick actions and custom shortcuts

### Quick actions

**Settings → Axion → Shortcut buttons**

Turn on the round buttons you want at the top of the side panel (max 11):

| Icon | Action |
|---|---|
| 📝 | Sticky note from selection |
| 🃏 | Flashcard from selection |
| 🖍️ | Highlight tool |
| ✏️ | Insert text |
| 🌐 | Translate selection |
| 🔊 | Read selection aloud |
| 👁️ | OCR |
| 📷 | Capture |
| ↗️ | Open the PDF note |
| 📋 | Toggle auto-paste |
| ⚙️ | Open settings |

### Custom shortcuts

Below the fixed quick actions, a **scrollable row of your own buttons** appears. Each button can:

- Launch a program (PowerToys, OCR tool, script…)
- Open a file
- Open a URL
- Send a key combination to the OS (e.g. `win+alt+s`)

**To add:** click **+** at the end of the row, or **Settings → Axion → Your own shortcut buttons → Add**.

Fields:

- **Name** — hover text
- **Icon** — an emoji or 1–2 letters
- **Program, file or link** — full path or URL
- **Arguments** — optional, supports `{selection}`, `{note}`, `{notepath}`, `{vault}`
- **Keyboard shortcut** — optional combo like `win+alt+s`

Right-click a custom button to **edit**, **move** or **delete** it.

---

## 16. Settings reference

**Settings → Axion →**

| Section | Key settings |
|---|---|
| **Shortcut buttons** | Which quick actions appear, default colour for manual stickies, right-click menu on text |
| **Your own shortcut buttons** | Custom launchers |
| **Capture** | Format (PNG / JPEG / WebP), quality, dimming, save images |
| **Recording** | Format (WebM / MP4 / auto), quality, FPS, height, mic / system on by default, ask for source each time |
| **Read aloud** | Language (auto / fixed), fallback language, voice per language, save audio, audio folder, playback speed |
| **Translation** | Preferred engine, fallback, NLLB model download, auto-unload after N minutes |
| **Flashcards** | Auto-create, layout (single/double), back languages, new cards per day, autoplay, week start |
| **Anki** | Deck name, generate missing audio on export |
| **Pomodoro** | Focus / Short / Long / Round length, auto-advance, end sound |
| **OCR** | Languages, quality, download, auto-download, use text layer, pre-processing, PSM, keep line breaks, idle time |

---

## 17. Commands

All commands are available in **Command Palette** (`Ctrl/Cmd + P`) under "Axion:".

| Command | What it does |
|---|---|
| **Axion: toggle auto paste** | Turn auto-paste from clipboard on/off |
| **Axion: turn the selected text into a sticky note** | Wrap the selection in a sticky note |
| **Axion: make a sticky note + flashcard** | Wrap the selection and create a flashcard |
| **Axion: read selected text aloud** | TTS on the selection |
| **Axion: stop reading** | Stop TTS |
| **Axion: play / pause reading** | Play/Pause the player |
| **Axion: translate the selected text** | Translate the selection |
| **Axion: download offline translation model** | Pre-download NLLB |
| **Axion: OCR region** | Select a rectangle on screen and copy its text |
| **Axion: export flashcards to Anki** | Generate the `.apkg` |
| **Axion: open the study panel** | Open the side panel |
| **Axion: update the toolbars of ALL sticky notes** | Adds the preview button to old notes |
| **Axion: add colour circles to the sticky-note toolbars of this note** | Same, for the current note |

---

## 18. Data and backup

### What to back up

- **Your vault** — the source of truth for all highlights and notes.
- `.obsidian/plugins/axion/flashcards.json` — your SRS state and review history.
- `.obsidian/plugins/axion/voices/` — downloaded voices (regenerable but slow).
- `.obsidian/plugins/axion/nllb/` — offline translation model (regenerable).
- `.obsidian/plugins/axion/ocr/` — OCR data (regenerable).

### Moving to another device

Copy your vault. Open it. Axion detects the study folders and rebuilds the highlights automatically. Voices and models are **not** copied by the vault — redownload from the settings if you want offline.

### Resetting a study folder

Delete the `Chapter 3/` folder next to the PDF. Axion rebuilds it on next open (from `%%hl:…%%` markers in the note, if present).

---

## 19. Troubleshooting

### "Sticky note did not open"

- The highlight has no note — right-click → *Make a sticky note*.
- The note file is missing — check the study folder for `<PDF name>.md`.
- Restart Obsidian and try again.

### "Voice not ready" / TTS downloads every time

- Check **Settings → Axion → Read aloud → Audio folder** — the folder must exist.
- Verify the study folder exists next to the PDF.
- Open the developer console (`Ctrl+Shift+I`) and look for errors during download.

### "Translation is slow"

- First use always downloads the model (~900 MB). Subsequent uses are fast.
- Set **Unload model after** to a high value (e.g. 60) so it stays in RAM.
- If you don't need offline, switch to Google Translate.

### "OCR can't find text"

- Draw a tighter rectangle.
- Set **Enlarge** to 3×.
- For colour backgrounds, disable **Grey + contrast**.
- For a single line, set mode to **One line**.

### "Recordings are silent"

- On Windows: check that **System audio** is on and the source is a **screen** (not a window).
- On other systems: system audio cannot be recorded — only microphone.
- Check that the microphone is on in the recording bar.

### "The dock disappeared"

- It appears only when a PDF tab is active. Open a PDF.
- Check **Settings → Axion → Dock** (if the option exists) is enabled.

### "The plugin does not load"

- Check **Settings → Community plugins** — the toggle is on.
- Open the console (`Ctrl+Shift+I`) and copy any red error.
- Delete `main.js` and re-install from the release.

---

## 20. FAQ

**Q: Does Axion send my data anywhere?**  
A: Only the initial model downloads (voices, translation, OCR) and, if you choose it, Google Translate. Everything else stays local.

**Q: Can I use Axion on mobile?**  
A: Yes for reading, translation, flashcards, TTS, OCR, Pomodoro, to-do, calendar. Screen recording is desktop-only.

**Q: Can I sell a plugin that uses Axion's code?**  
A: The Axion code is **MIT** — you can. But the offline translation model **NLLB-200 is CC-BY-NC 4.0 (non-commercial)**. Commercial use requires replacing the model.

**Q: How do I import my existing Anki cards into Axion?**  
A: Not supported yet. Planned.

**Q: Are my audio files generated every time?**  
A: No. Each sentence is hashed and cached. The same `.wav` is reused across notes, sticky notes and flashcards.

**Q: Can I export individual decks?**  
A: Not yet — one export with the deck name you set in settings.

---

## 21. Privacy

- **No telemetry. No analytics. No accounts.**
- Every file remains in your vault.
- Downloads only from: `jsdelivr.net` (voices, OCR), `huggingface.co` (NLLB model), `translate.googleapis.com` (Google Translate).
- After download, TTS, offline translation and OCR **work fully offline**.

---

## 22. Getting help

- **Bug reports / feature requests**: [GitHub Issues](https://github.com/mojtabashoghi/axion/issues)
- **Discussions**: [GitHub Discussions](https://github.com/mojtabashoghi/axion/discussions)
- **Security**: see [SECURITY.md](SECURITY.md)

When reporting a bug, please include:

- OS and version
- Obsidian version
- Axion version
- Steps to reproduce
- Console output (if any)

Happy learning! 🎓