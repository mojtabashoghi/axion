# Axion

> **Axion is an offline-first Obsidian plugin that turns PDFs and Markdown into a unified environment for reading, research, and language learning**
>
> **🌐 Language:** [English](README.md) · [فارسی](README_fa.md) · **📖 User Guide:** [English](USER_GUIDE.md) · [فارسی](USER_GUIDE_fa.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![GitHub release](https://img.shields.io/github/v/release/mojtabashoghi/axion?include_prereleases)](https://github.com/mojtabashoghi/axion/releases)
[![Obsidian](https://img.shields.io/badge/Obsidian-1.4.0%2B-7C3AED)](https://obsidian.md)
[![Made with ONNX Runtime](https://img.shields.io/badge/ONNX%20Runtime-Web-005CED)](https://onnxruntime.ai)
[![Offline-first](https://img.shields.io/badge/offline--first-success)](https://github.com/mojtabashoghi/axion#-privacy)

Axion is an offline-first Obsidian plugin that turns PDFs and Markdown into a unified environment for reading, research, and language learning.
Highlight PDF pages, add sticky notes and text boxes, and use OCR to make scanned documents searchable. Translate text into multiple languages
with local or online models, and listen with neural TTS; audio is saved per sentence so you can build a personal audio archive of key sentences. 
Create SRS flashcards with audio from the same content, track your review habit with a heatmap, and export cards to Anki. 
The offline-first design helps protect source privacy and keeps PDFs, Markdown, translation, listening, and review together in one vault—no constant switching between apps.

---

## ✨ Features

### 🖍️ PDF reading & research
- **Highlights** with six colours and two marker shapes (rounded / flat).
- **Sticky notes** attached to a highlight (with translation and audio), or **free-floating** pins anywhere on the page.
- **Text boxes** anywhere on the page, with full font/colour/alignment control.
- Popups that edit the source note inline — no window switching.
- Automatic **recovery** of highlights from `%%hl:…%%` markers if the JSON sidecar is lost.
- **Floating dock** on top of the PDF with all the quick actions.

### 🌍 Translation
- **Google Translate** (fast, online).
- **Offline NLLB-200 distilled 600M** (~900 MB, run locally with ONNX Runtime Web).
- Automatic source-language detection.
- Native support for **German, English, French, Persian**.
- Persian punctuation fix-up, correct RTL rendering.

### 🔊 Read aloud (TTS)
- **Piper** neural voices running in a Web Worker.
- 27 voices across German, English, and French.
- Speed 0.5× – 2.0×.
- Audio **saved as WAV** in your vault and shared between notes, sticky notes and flashcards — each sentence is only generated once.

### 🃏 Flashcards with SRS
- **Spaced repetition** algorithm inspired by Anki (SM-2 variant).
- Two card layouts: *single* (all translations on one face) and *double* (front / back).
- Mark cards directly inside notes:
  - `:: text` → single card
  - `front ::: back` → two-sided card
- **Auto-create** cards from every pasted word/sentence (optional).
- **Review heatmap** with day streak and best streak.
- **Export to Anki** (`.apkg`) — cards + audio, opens in Anki Desktop and AnkiDroid.

### 📷 OCR
- **Tesseract.js** (WASM), works offline.
- Reads PDFs with a real text layer *directly* (exact + instant).
- Reads scanned pages and images with **OCR**, then copies to clipboard.
- Pre-processing: grey + contrast + up-scaling.
- Languages: Persian, English, German, French, Arabic.

### ⏱️ Pomodoro · ✅ To-do · 📅 Calendar
- Classic Pomodoro (focus / short break / long break, auto-advance, end sound).
- To-do list with start/end time and alarms.
- **Persian (Jalali) calendar** side-by-side with Gregorian — daily tasks and one-off days.

### 📸 Capture
- **Screenshot** with a drag region → clipboard (+ optional save to the study folder).
- **Screen recording** on desktop (microphone + system audio on Windows).
- On mobile: attach a video recorded with the device's own recorder.

### 🧩 Extras
- **Quick actions** bar at the top of the side panel.
- **Custom shortcut buttons**: launch a program / open a file / URL / send a key combo.
- **Context menu** on selected text: *Axion: sticky note + translation*.
- **Custom icons**: drop your own SVGs in the `icons/` folder.

---

## 📥 Installation

### From the Community Plugins browser
*(available once accepted into the directory)*

1. Settings → **Community plugins** → **Browse**.
2. Search **Axion** and install.
3. Enable the plugin.

### Manually

1. Download `main.js`, `manifest.json`, `styles.css` from the [latest release](https://github.com/mojtabashoghi/axion/releases).
2. Put them inside `YourVault/.obsidian/plugins/axion/`.
3. In Obsidian: Settings → Community plugins → **Reload** → enable **Axion**.

---

## 🚀 Quick start

1. Open any PDF. A **floating dock** appears top-right of the PDF area.
2. Click **highlight** → choose a colour → drag a rectangle over text.
3. Click **sticky** → click on the page → the note opens — start typing.
4. Add a translation with the **translate** button in the toolbar.
5. Click the **flashcard** button to turn the sticky note into a flashcard.
6. Review in the side panel → **Flashcards** section.
7. When done, **export to Anki** or keep everything inside Obsidian.

---

## 📁 Where the data lives

For each PDF, Axion creates a **study folder** next to the PDF:


### Global paths

| Data | Path |
|---|---|
| Flashcards database | `.obsidian/plugins/axion/flashcards.json` |
| Downloaded voices & engine | `.obsidian/plugins/axion/voices/` and `/runtime/` |
| Downloaded translation model | `.obsidian/plugins/axion/nllb/` |
| Downloaded OCR files | `.obsidian/plugins/axion/ocr/` |
| Global audio folder (unassigned notes) | `Language audio/` (configurable) |
| Icon overrides | `.obsidian/plugins/axion/icons/*.svg` |

---

## 🔒 Privacy

- **No telemetry.** Nothing leaves your device unless you ask for it.
- The **first time** you use translation, TTS or OCR, the required model is downloaded from `jsdelivr.net` / `huggingface.co` and cached locally.
- After that, translation (NLLB), TTS (Piper), OCR (Tesseract) run **fully offline**.
- Only **Google Translate** (if selected) always needs an internet connection.

---

## 🧱 Tech stack

| Layer | Technology |
|---|---|
| Plugin host | [Obsidian API](https://docs.obsidian.md/) |
| Language | TypeScript / ESBuild |
| TTS | [Piper](https://github.com/rhasspy/piper) — ONNX models, Web Worker |
| Offline translation | [NLLB-200](https://huggingface.co/facebook/nllb-200-distilled-600M) via [ONNX Runtime Web](https://onnxruntime.ai) |
| Online translation | Google Translate public endpoint |
| OCR | [Tesseract.js](https://github.com/naptha/tesseract.js) (WASM) |
| Anki export | [sql.js](https://sql.js.org) + [fflate](https://github.com/101arrowz/fflate) |

---

## 🛠️ Contributing

Issues and pull requests are welcome.  
Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

See the [CHANGELOG](CHANGELOG.md) for what's new.

---

## 📜 License

[MIT License](LICENSE.md) © 2026 Mojtaba Shoghi Samani
