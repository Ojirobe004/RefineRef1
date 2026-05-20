# RefineRef1

> Fix your references. All of them. Instantly.

RefineRef is a single-file web app that bulk-reformats academic references to **APA 6th edition** using Claude AI. Upload your Word document, get a clean, numbered reference list back in seconds — with flagged warnings on any entries that need your attention.

Built for researchers and students who have too many references to fix one by one.

---

## Features

- **Drag & drop `.docx` upload** — works with your existing Word documents
- **Bulk formatting** — reformats every reference in one go, no matter how many
- **APA 6th edition compliant** — powered by Claude (`claude-sonnet-4-20250514`)
- **Smart flagging** — uncertain entries get a ⚠️ with a note explaining what's missing or ambiguous
- **Chunked processing** — handles large documents by splitting into chunks and combining results
- **Copy or download** — grab your output as plain text instantly
- **Zero setup** — one HTML file, runs in any browser, no backend, no install
- **Privacy-first** — your API key is never stored; it lives in memory for the session only

---

## Usage

### Option 1 — Run locally

1. Download `refineref.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Enter your [Anthropic API key](https://console.anthropic.com/)
4. Upload your `.docx` file
5. Click **Format References**
6. Copy or download your formatted list

### Option 2 — GitHub Pages (recommended)

1. Fork this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app will be live at `https://yourusername.github.io/refineref`

No server required. The app runs entirely in the browser.

---

## Requirements

- A modern browser
- An [Anthropic API key](https://console.anthropic.com/) (you pay only for what you use; typical usage costs a few cents per run)
- A `.docx` file containing your references

---

## How it works

1. **Extracts** raw text from your `.docx` using [Mammoth.js](https://github.com/mwilliamson/mammoth.js)
2. **Chunks** the text into manageable segments for the API
3. **Sends** each chunk to Claude with a strict APA 6th edition formatting prompt
4. **Combines** all responses and renders them in a numbered list
5. Flags anything ambiguous with ⚠️ so you can review manually

---

## Privacy & Security

- Your API key is held **in memory only** and cleared when you close or refresh the tab
- No data is sent anywhere except the Anthropic API to process your references
- No analytics, no tracking, no backend

---

## Stack

| Layer | Tool |
|---|---|
| UI | Vanilla HTML, CSS, JavaScript |
| Document parsing | [Mammoth.js](https://github.com/mwilliamson/mammoth.js) |
| AI formatting | [Anthropic Claude API](https://docs.anthropic.com) |
| Fonts | Syne, DM Sans, JetBrains Mono (Google Fonts) |
| Hosting | GitHub Pages (optional) |

---

## Limitations

- Only accepts `.docx` files (not `.doc` or `.pdf`)
- Output is plain text — formatting as a Word doc is not yet supported
- Accuracy depends on how well-structured your existing references are; very messy or incomplete entries may still need manual review
- Requires an active internet connection (API calls)

---

## Roadmap

- [ ] Download output as a formatted `.docx`
- [ ] Support for APA 7th edition toggle
- [ ] Side-by-side diff view (original vs. formatted)
- [ ] Detect and group references by chapter

---

## License

MIT — do whatever you want with it.

---

*Built with [Claude](https://claude.ai) by Anthropic.*
