# QSLforge

**Amateur Radio QSL Card Generator**  
*by IU8TVG + ClaudeAI*

A free, offline-capable tool to generate QSL cards from ADIF log files.  
No server, no registration, no data collection — everything runs locally in your browser.

---

## Features

- Load any QSL card image (JPG, PNG, WebP) — **automatically remembered** between sessions
- Import ADIF log files (`.adi` / `.adif`)
- Drag & drop field placement with live preview (mouse and touch)
- Per-field settings: font, size, color, bold, shadow, alignment
- **Global font size** — apply the same size to all fields at once
- Date formatted as DD/MM/YYYY, time as HH:MM
- Light / dark UI theme toggle
- **Collapsible panels** for a cleaner workspace
- Layout and field settings saved automatically (localStorage)
- Export / import configuration as JSON
- **Language switcher** dropdown (IT / EN, extensible)
- Generate and download QSL cards as PNG (single or ZIP)
- Internationalisation support via `locales/` JSON files

---

## Supported ADIF fields

`CALL` · `QSO_DATE` · `TIME_ON` · `BAND` · `FREQ` · `MODE` · `RST_SENT` · `RST_RCVD`  
`NAME` · `QTH` · `GRIDSQUARE` · `DXCC` · `TX_PWR` · `COMMENT` · `OPERATOR`  
`IOTA` · `CQZ` · `ITUZ` · `STATE` · `CONT`  
`POTA_REF` · `SOTA_REF` · `WWFF_REF`

---

## Usage

1. Open `index.html` in any modern browser — no installation needed.
2. **Step 1 — Setup**: load your QSL image (it will be remembered next time), click fields to place them, drag to position.
3. **Step 2 — Import log**: load your `.adi` / `.adif` file, select the QSOs.
4. **Step 3 — Generate**: generate all cards and download as PNG or ZIP.

---

## File structure

```
index.html           ← main application (single file, works standalone)
LICENSE              ← MIT License
README.md            ← this file
locales/
  it.json            ← Italian (default, built-in fallback)
  en.json            ← English
```

---

## Adding a language

1. Copy `locales/en.json` to `locales/xx.json` (use ISO 639-1 code, e.g. `de`, `fr`, `es`)
2. Translate all values (keep the keys unchanged)
3. In `index.html` find the `LANGS` array and add your language:
   ```js
   const LANGS = [
     { code: 'it', label: 'Italiano' },
     { code: 'en', label: 'English'  },
     { code: 'de', label: 'Deutsch'  }, // ← add this
   ];
   ```
4. The dropdown will show the new language automatically on next load.

---

## Image persistence

QSLforge saves your QSL card image automatically using **IndexedDB** (built into every modern browser). No size limits apply. If IndexedDB is unavailable (e.g. private/incognito mode in some browsers), it falls back to localStorage for images under 2 MB.

To remove the saved image, use the **🖼 Reset immagine** button in the Configuration panel.

---

## Privacy

QSLforge runs entirely in your browser. No data is ever sent to any server.  
The only external requests are:

- **Google Fonts** (Orbitron, Share Tech Mono, Exo 2) — loaded at startup for typography
- **cdnjs.cloudflare.com** (JSZip) — loaded only when downloading a ZIP archive

If you need fully offline operation, download the fonts and embed them in the HTML file.

---

## License

MIT License — © 2026 IU8TVG  
See [LICENSE](LICENSE) for full terms.

---

73 de IU8TVG
