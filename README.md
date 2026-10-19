# EPUB Reader

A static EPUB reader styled after Apple Mail. Three panes: your library, the chapter list, and the reading pane.

- **Add books** with the + button or by dragging an `.epub` onto the page.
- **Library is saved in your browser** (IndexedDB) on that device. Nothing is uploaded anywhere, and nothing is stored in this repo.
- **Text options** (the `Aa` button): Serif, Sans, **OpenDyslexic**, or the book's own font; text size; line spacing; Auto / Light / Dark.
- Reading position and read/unread chapters are remembered per book.
- Left/right arrow keys move between sections.
- **Look up & search:** right-click a word or selected phrase (on touch screens, select text) for **Look up** (built-in offline dictionary, single words, handles forms like *running* → *run*), **Ask Google**, or **Copy**. No outside requests are made; the dictionary is part of this repo.

## Publish on GitHub Pages

1. Put these files at the root of a repo.
2. Repo **Settings → Pages → Build and deployment → Deploy from a branch**, choose your branch and folder.
3. Open `https://<username>.github.io/<repo>/`.

It needs to be served over http(s) (GitHub Pages is), so opening `index.html` straight from disk won't work. To try it locally: `python3 -m http.server` in this folder, then visit http://localhost:8000.

## Files

- `index.html` — the whole app
- `epub.min.js`, `jszip.min.js` — epub.js (BSD-2-Clause) and JSZip (MIT), bundled so there are no external requests
- `opendyslexic-*.woff2` — OpenDyslexic (SIL Open Font License 1.1, see `LICENSE-OpenDyslexic.txt`)
- `dict/` — built-in dictionary, one JSON file per first letter, loaded only when you look a word up. Built from WordNet 3.0 (Princeton University; licence in `LICENSE-WordNet.txt`) with older words that WordNet lacks filled in from Webster's 1913 Unabridged Dictionary (public domain)
