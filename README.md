# QSLforge

**Amateur Radio QSL Card Generator**  
*by IU8TVG*

A free, offline-capable tool to generate QSL cards from ADIF log files.  
No server, no registration, no data collection — everything runs locally in your browser.

---

## Features

- Load any QSL card image (JPG, PNG, WebP)
- Import ADIF log files (`.adi` / `.adif`)
- Drag & drop field placement with live preview
- Per-field settings: font, size, color, bold, shadow, alignment
- Date formatted as DD/MM/YYYY, time as HH:MM
- Light / dark UI theme
- Layout saved automatically (localStorage)
- Export / import configuration as JSON
- Generate and download QSL cards as PNG (single or ZIP)
- Internationalisation support via `locales/` JSON files

## Supported ADIF fields

`CALL` · `QSO_DATE` · `TIME_ON` · `BAND` · `FREQ` · `MODE` · `RST_SENT` · `RST_RCVD`  
`NAME` · `QTH` · `GRIDSQUARE` · `DXCC` · `TX_PWR` · `COMMENT` · `OPERATOR` · `IOTA` · `CQZ` · `ITUZ` · `STATE` · `CONT`

---

## Usage

1. Open `qsl-generator.html` in any modern browser — no installation needed.
2. **Step 1 — Setup**: load your QSL image, click fields to place them, drag to position.
3. **Step 2 — Import log**: load your `.adi` / `.adif` file, select the QSOs.
4. **Step 3 — Generate**: generate all cards and download as PNG or ZIP.

---

## File structure

```
qsl-generator.html   ← main application (single file, works standalone)
LICENSE              ← MIT License
README.md            ← this file
locales/
  it.json            ← Italian (default, built-in fallback)
  en.json            ← English
```

## Adding a language

1. Copy `locales/en.json` to `locales/xx.json` (use ISO 639-1 code, e.g. `de`, `fr`, `es`)
2. Translate all values (keep the keys unchanged)
3. Set the language in the browser console:
   ```js
   localStorage.setItem('qslforge_lang', 'xx');
   location.reload();
   ```

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
