# Kannada Words Trainer

A browser-based PWA for practising Kannada word recognition (ಪದ) with Devanagari annotations and English meanings. Part of a series of Kannada script trainers for learners who already read Hindi or Marathi.

## Live app

https://agpathak.github.io/Kannada_words/

## What it covers

The deck contains **100 common Kannada words** across everyday categories. Each card shows the Kannada script word during a timed glimpse, then reveals the Devanagari annotation and English meaning for self-scoring.

| Category | Examples |
|---|---|
| Common / Home | ಮನೆ (मने) ನೀರು (नीरु) |
| Food | ಅನ್ನ ಹಾಲು ಸಕ್ಕರೆ ಉಪ್ಪು |
| Nature | ಮಳೆ ಸೂರ್ಯ ಮರ ನದಿ ಪರ್ವತ |
| People & Family | ಅಪ್ಪ ಅಮ್ಮ ಅಣ್ಣ ಅಕ್ಕ ಮಿತ್ರ |
| Time | ಬೆಳಗ್ಗೆ ಸಂಜೆ ರಾತ್ರಿ ಇಂದು ನಾಳೆ |
| Adjectives | ದೊಡ್ಡ ಚಿಕ್ಕ ಹೊಸ ಸುಂದರ ಬಿಸಿ |
| Emotions & Abstract | ಪ್ರೀತಿ ಭಯ ಸಂತೋಷ ಸತ್ಯ ಜೀವನ |
| Transport & Place | ವಿಮಾನ ರೈಲು ಬಸ್ ನಗರ ಗ್ರಾಮ |

## Training method

Each card goes through three stages:

1. **Glimpse** — the Kannada word is shown for 1, 3, or 5 seconds; read the shape, don't spell it out
2. **Reveal** — the word stays on screen alongside its Devanagari annotation and English meaning
3. **Self-score** — mark whether you recognised the word correctly

Scoring drives a **Leitner-lite spaced repetition** system: correct answers promote a word to a higher box (seen less often); mistakes reset it to Box 0 (seen most often). The weighted sampler prioritises unseen and weak words automatically.

## Features

- Embedded deck — no external files or CSV upload needed
- 100 words with Devanagari annotations (no Latin transliteration)
- Leitner-lite weighting: Box 0–3 combined with per-word error rate
- **Mixed mode** — weighted sampling across the full deck
- **Weak words mode** — targets only words with mistakes or low accuracy
- Configurable glimpse time (1 / 3 / 5 seconds) and session size (10 / 20 / 50 / 100)
- Optional speech synthesis on reveal (kn-IN)
- Optional auto-advance after scoring
- Per-word stats: box level, accuracy, wrong count, last seen
- Session history with accuracy and duration
- Installable as a PWA on iOS and Android
- No server, no backend, no build step — one HTML file

## Files

- `index.html` — the entire app; deck data embedded as a JS array
- `manifest.json` — PWA metadata
- `sw.js` — service worker for offline support
- `icon-192.png`, `icon-512.png` — app icons
- `.nojekyll` — prevents GitHub Pages from processing the repo with Jekyll

## Deploy on GitHub Pages

1. Create a new GitHub repository (e.g. `Kannada_words`)
2. Upload all files to the repository root
3. Go to **Settings → Pages**
4. Under **Build and deployment**, set:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main`, folder `/ (root)`
5. Save — GitHub will provide a Pages URL within a minute or two
6. On iPhone: open the URL in Safari → Share → **Add to Home Screen**

## Local use

Open `index.html` directly in any browser — no server needed. Progress is saved in `localStorage` (key `kn_words_progress_v1`) and persists across sessions in the same browser.

## Tech

Plain HTML, CSS, and JavaScript. Tailwind CSS via CDN. Noto Sans Kannada via Google Fonts. Hosted on GitHub Pages.

## Companion apps

| App | Covers |
|---|---|
| [Kannada Alphabet Trainer](https://github.com/AGPATHAK/Kannada_alphabet) | Base letter recognition |
| [Kannada Matras Trainer](https://github.com/AGPATHAK/Kannada_matra) | Consonant + vowel sign combinations |
| [Kannada Conjuncts Trainer](https://github.com/AGPATHAK/Kannada_conjucts) | Conjunct consonants |
| **Kannada Words Trainer** | Common vocabulary (this app) |
