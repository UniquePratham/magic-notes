# Magic Notes

A notes app that keeps everything in your browser — no account, no server, no sync to anyone else. Write a note, bookmark the ones you keep coming back to, and it is still there when you reopen the tab.

**Live:** https://magic-notes1.web.app

## Features

- **Create notes** with a title and body, validated so an empty or one-character note is rejected
- **Bookmarks** — mark any note and filter down to just the bookmarked ones
- **Delete** individual notes
- **Persists in `localStorage`**, so notes survive a reload and never leave the device
- **Search** across titles and bodies
- Responsive Bootstrap layout with a dark navbar

## How it works

Everything is client-side. `app.js` reads and writes two `localStorage` keys:

| Key | Contents |
|---|---|
| `notes` | JSON array of `{ title, text, date }` |
| `bookMarkindexes` | JSON array of indexes into `notes` |

Because the state lives in the browser, there is no backend to deploy and no data to leak. The trade-off is that notes are per-browser and per-device — clearing site data clears the notes.

## Tech

Plain HTML, CSS and JavaScript with Bootstrap 4, jQuery and DataTables loaded from CDNs. No build step.

## Run locally

```bash
# any static server works
npx serve .
# or
python -m http.server 8080
```

Then open http://localhost:8080.

## Deploy

```bash
firebase deploy --only hosting --project magic-notes1
```

## License

MIT — see [LICENSE](LICENSE).
