# games.wctacyber.org — WCTA Cyber Games

Sister site to apps.wctacyber.org. Same look, themes and boot sequence, but a flat
grid: **one card per game, no categories.** Each game is its own Vercel app and
handles its own per-class tabs. Single-file, no build step.

```
index.html    the page (design system + boot sequence + grid). Rarely edit.
links.json    ALL your content. This is the file you edit.
CNAME         custom domain (games.wctacyber.org).
```

## Adding a game

Edit `links.json` only:

```json
{"name": "My New Game", "url": "https://my-game.vercel.app/", "description": "One short line students will read on the card."}
```

Add the object to the `games` array, bump `updated`, commit. Cards show in the order
listed, numbered GAME 01, 02, ... with accent colours that cycle automatically. The
top-bar count, boot log and search all rebuild from the array.

Validate before committing: open `links.json` in a browser tab (Chrome shows a parse
error immediately). Commas go between items, never after the last one.

## Local preview

```bash
python3 -m http.server 8000   # fetch() is blocked on file://
```

## Notes

- Background music loads from `https://apps.wctacyber.org/audio/eyes-on-the-perimeter.mp3`
  (no copy kept here). To use a different track, add an `audio/` folder and change the
  `<audio id="bgm">` src in `index.html`.
- "Connections" currently has two cards (AP Cyber and Security+). When one tabbed
  Connections app exists, replace both with a single "Connections" entry.
