# Clear – PDF redactor

Clear is a single-page web app for blacking out parts of a PDF. It runs entirely
inside the browser: the PDF is opened, marked and rebuilt in the tab and is never
uploaded anywhere.

## Use it

**Locally, no install and no internet needed**

1. Download or clone this repository (keep the `vendor` folder next to `index.html`).
2. Double-click `index.html` to open it in Chrome, Edge, Firefox or Safari.

**Hosted on GitHub Pages**

1. In the repository settings open *Pages*.
2. Under *Build and deployment* choose *Deploy from a branch*, pick `main` and `/ (root)`, then save.
3. After a minute the app is live at `https://<your-user>.github.io/<repo-name>/`.

Any other static host works the same way: upload `index.html` and the `vendor` folder.

## How it works

1. **Open a PDF** with the button or by dropping it onto the page. The
   automatic rules run straight away: every price or dollar amount is covered,
   and so is any line mentioning payment details (payment method, amount paid
   or due, card, EFT, BPAY, BSB or account details). Either rule can be switched
   off in the sidebar; the choice is remembered.
2. **Redact more areas** by dragging a box on any page, or type text and press
   *Redact all matches*. Quick patterns cover email addresses, Australian
   phone numbers, vehicle identification numbers (VINs) and prices in one click.
   Boxes are white with a red outline on screen (the outline is not exported);
   hover over one to peek at what is underneath.
3. To un-redact something, click its box to select it, then remove the box with
   its **×**, the *Delete* key, or a double-click. *Undo* (also Ctrl/Cmd+Z)
   steps back through changes.
4. **Export redacted PDF** is what actually removes the text. It flattens every
   page to a single picture with the covered areas painted solid white and builds
   a fresh PDF called `<name>-redacted.pdf` in your downloads folder. The output
   contains no text, fonts, layers, form fields or metadata from the original, so
   the covered content cannot be recovered with a PDF editor or an image editor.
   Your original file is never changed.

Password-protected PDFs must have the password removed before they can be opened.

## Privacy and network use

The only network requests the page makes are for its web font and, only if the
bundled copies in `vendor` are missing, the two open-source libraries it depends
on (loaded from cdnjs). The PDF itself never leaves the browser tab.

## Project layout

| Path | Purpose |
|------|---------|
| `index.html` | The whole app: markup, styles and script |
| `vendor/pdfjs/` | [pdf.js](https://github.com/mozilla/pdf.js) 3.11.174 (rendering and text search), Apache-2.0 |
| `vendor/pdf-lib/` | [pdf-lib](https://github.com/Hopding/pdf-lib) 1.17.1 (building the exported PDF), MIT |

See `vendor/README.md` for how to upgrade the bundled libraries.
