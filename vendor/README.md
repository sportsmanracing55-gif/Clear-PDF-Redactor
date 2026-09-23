# Bundled libraries

These are unmodified release builds, copied from npm so that `index.html`
works with no internet connection. If they are missing (for example when only
`index.html` is copied somewhere on its own), the page falls back to loading the
same versions from cdnjs.

| Library | Version | Files | Licence |
|---------|---------|-------|---------|
| [pdf.js](https://github.com/mozilla/pdf.js) | 3.11.174 | `pdfjs/pdf.min.js`, `pdfjs/pdf.worker.min.js`, `pdfjs/cmaps/`, `pdfjs/standard_fonts/` | Apache-2.0 (`pdfjs/LICENSE`) |
| [pdf-lib](https://github.com/Hopding/pdf-lib) | 1.17.1 | `pdf-lib/pdf-lib.min.js` | MIT (`pdf-lib/LICENSE.md`) |

To upgrade, install the new version with npm and copy the same files across,
then update the version numbers in the CDN fallback URLs near the top of the
script in `index.html`.
