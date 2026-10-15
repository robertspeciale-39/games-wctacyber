# games.wctacyber.org — WCTA Cyber Games

Sister site to apps.wctacyber.org. Same engine, same themes, same boot sequence;
this one lists games instead of study tools. Single-file, no build step.

```
index.html    the page (design system + boot sequence + grid). Rarely edit.
links.json    ALL your content. This is the file you edit.
CNAME         custom domain (games.wctacyber.org).
```

## Adding a game

Edit `links.json` only:

```json
{ "category": "Security+", "name": "My New Game", "url": "https://my-game.vercel.app/", "description": "One short line students will read on the card." }
```

Add the object to the `tools` array, bump `updated`, commit. Categories, colours,
filters, counts, the boot log and search all rebuild from that array. A new
`category` value creates a new group automatically.

Validate before committing: open `links.json` in a browser tab (Chrome shows a
parse error immediately). Commas go between items, never after the last one.

## Local preview

```bash
python3 -m http.server 8000   # fetch() is blocked on file://
```

## Notes

- Background music loads from `https://apps.wctacyber.org/audio/eyes-on-the-perimeter.mp3`
  (no copy kept here). To use a different track, add an `audio/` folder and
  change the `<audio id="bgm">` src in `index.html`.
- The six games seeded in `links.json` are also listed on apps.wctacyber.org.
