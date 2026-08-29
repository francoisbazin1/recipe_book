# Recipe Book

A small offline recipe app. One HTML file, no server, no account. Everything is stored
in the browser on the phone it is installed on.

## What it does

- **Scan a recipe** — photograph a cookbook page, a handwritten card, or a screenshot of a
  website. The pictures go to Claude and come back as a title, ingredients, method, tags and
  times, ready to check and save. Needs your own Claude API key (Settings). A scan costs a
  couple of cents.
- **Type one in** — same form, no key needed.
- **Search by name or by ingredient** — typing `butter` finds every recipe with butter in it
  and tells you which line matched. Tag chips narrow it further.
- **Cooked lately / maybe tonight** — the kitchen page shows what you have made recently and
  nudges the ones you have not made in a while.
- **Per recipe** — a photo, a star rating, tick-off ingredients while you cook, notes, a dated
  comment each time you make it, and a list of every date it was made.
- **Backup and restore** — a JSON file with the photos in it, plus a CSV of the whole book.

## Install on a phone

Open the site, then Add to Home Screen. It runs full screen and works with no signal.

## Privacy

Recipes, photos and the API key never leave the phone, apart from the pictures you choose to
scan, which go to Anthropic and are not kept. There is no server and no account.

## Files

| File | What it is |
|---|---|
| `index.html` | the whole app |
| `sw.js` | offline cache — **bump `CACHE` on every change or phones keep the old version** |
| `manifest.webmanifest`, `icon*` | home screen install |
