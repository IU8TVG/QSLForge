# QSLforge v1.0b

**Amateur Radio QSL Card Generator**  
*by IU8TVG*

> ⚠ **Beta release** — the software is provided as-is, without warranties of any kind. Use at your own risk.  
> 🤖 Developed with the assistance of generative AI (Claude by Anthropic). Code reviewed and adapted by the author.

A free, offline-capable tool to generate QSL cards from ADIF log files.  
No server, no registration, no data collection — everything runs locally in your browser.

---

## Features

- Load any QSL card image (JPG, PNG, WebP) — **automatically remembered** between sessions
- Import ADIF log files (`.adi` / `.adif`)
- Drag & drop field placement with live preview (mouse and touch)
- Per-field settings: font, size, color, bold, shadow, alignment
- **Global text style** — apply font size and/or color to all fields at once; values used as defaults for new fields
- Date formatted as DD/MM/YYYY, time as HH:MM
- Light / dark UI theme toggle
- **Collapsible panels** — image upload panel auto-closes after loading
- Layout and field settings saved automatically (localStorage)
- Export / import configuration as JSON
- **Language switcher** dropdown (IT / EN, extensible)
- Generate and download QSL cards as PNG (single or ZIP)
- Internationalisation support via `locales/` JSON files
- First-visit disclaimer and AI disclosure modal

---

## Supported ADIF fields

`CALL` · `QSO_DATE` · `TIME_ON` · `BAND` · `FREQ` · `MODE` · `RST_SENT` · `RST_RCVD`  
`NAME` · `QTH` · `GRIDSQUARE` · `DXCC` · `TX_PWR` · `COMMENT` · `OPERATOR`  
`IOTA` · `CQZ` · `ITUZ` · `STATE` · `CONT`  
`POTA_REF` · `SOTA_REF` · `WWFF_REF`

---

## Usage

1. Open `index.html` in any modern browser — no installation needed.
2. **Step 1 — Setup**: load your QSL image (remembered on next visit), click fields to place them, drag to position. Use the global style panel to set a common font size and color.
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

1. Copy `locales/en.json` to `locales/xx.json` (ISO 639-1 code, e.g. `de`, `fr`, `es`)
2. Translate all values — keep the keys unchanged
3. In `index.html` find the `LANGS` array and add your entry:
   ```js
   const LANGS = [
     { code: 'it', label: 'Italiano' },
     { code: 'en', label: 'English'  },
     { code: 'de', label: 'Deutsch'  }, // ← add this
   ];
   ```
4. The dropdown updates automatically on next load.

---

## Image persistence

QSLforge saves your QSL card image automatically using **IndexedDB**.  
Fallback to localStorage for images under 2 MB if IndexedDB is unavailable (e.g. private/incognito mode in some browsers).  
To remove the saved image use the **🖼 Reset immagine** button in the Configuration panel.

---

## Privacy

QSLforge runs entirely in your browser. No data is ever sent to any server.  
The only external requests are:

| Request | When |
|---|---|
| **Google Fonts** (Orbitron, Share Tech Mono, Exo 2) | Page load |
| **cdnjs.cloudflare.com** (JSZip) | Only when downloading a ZIP |

For fully offline operation, download the fonts and embed them in the HTML file.

---

## Changelog

### v1.0b *(2026)*
- Initial public beta release
- ADIF import with field placement on QSL image
- IndexedDB image persistence with localStorage fallback
- Light/dark theme, collapsible panels, touch drag support
- Global text style (size + color) with per-field override
- Language switcher (IT/EN) with external `locales/` JSON files
- First-visit disclaimer and AI disclosure modal
- Export/import layout configuration as JSON
- PNG download (single) and ZIP batch download

---

## License

MIT License — © 2026 IU8TVG  
See [LICENSE](LICENSE) for full terms.

---

73 de IU8TVG
