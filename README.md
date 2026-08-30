# Recipe Book

A small offline recipe app. One HTML file, no server, no account. Everything is stored
in the browser on the phone it is installed on.

## What it does

- **Add a recipe** — one button, then pick how it is coming in: take a photo of it, pick a photo
  already on the phone, give it a website address, type it in yourself, or add one someone sent.
  Photos and websites are read by Claude and come back as a title, ingredients, method, tags and
  times, ready to check before saving. Those two need a Claude key (Settings); the other three
  do not. Reading one recipe costs a couple of cents.
- **Where it came from** — every recipe carries a source, picked from chips (The book, Coles
  magazine, RecipeTin Eats, and whatever else she adds). The Recipes tab filters by it, and the
  scanner fills it in from the page.
- **Search by name or by ingredient** — typing `butter` finds every recipe with butter in it
  and tells you which line matched. Commas mean all of them: `spinach, chicken` finds only
  recipes with both, which is the what-is-in-the-fridge question. Filter by source first, tags
  behind a toggle.
- **Cooked lately / maybe tonight** — the kitchen page shows what you have made recently and
  nudges the ones you have not made in a while.
- **Photos, as many as you like** — of the finished dish and of the page it came from, each
  labelled. Scanning keeps the photographed page automatically, so the original handwriting is
  always there to check against. Tap one to enlarge it, make it the main picture, or delete it.
- **Per recipe** — a star rating, tick-off ingredients while you cook, notes, a dated
  comment each time you make it, and a list of every date it was made.
- **The plan** — turns the method into jobs with times and dependencies, then draws them on a
  timeline: solid where you are working, pale where you are waiting. Says how long it takes start
  to finish, how much of that is hands-on, how much longer on your own, and which jobs sit inside
  the long wait and can be handed to someone else. Costs one read, like a scan, and is thrown away
  if the method is edited.
- **Cook it step by step** — full screen, one step at a time in large type, with the next one
  shown faintly below. Tap the step when it is done and it advances and fills the progress bar.
  Ingredients are one tap away, the minutes that step mentions are offered as timer buttons, and
  the screen is held awake for as long as you are in it.
- **Ingredient groups** — an ingredient line ending in a colon ("For the sauce:") becomes a
  heading, the way a cookbook lays it out. The scanner keeps the groupings off the page.
- **A timer** — on the recipe, with the minutes the recipe itself mentions offered as buttons
  (it reads "simmer for 15 mins" out of the method). Leave the recipe and it follows you as a pill
  above the nav; tap it to go back. Beeps and buzzes when it is up, and survives a reload.
- **Keep the screen on while I cook** — a toggle on the recipe. Holds a screen wake lock so the
  phone stops dimming mid-method with floury hands. Released when you leave the recipe, and after
  three hours regardless. Hidden on browsers that do not support it.
- **Half it or double it** — ½× 1× 1½× 2× above the ingredients. Only the quantity at the front
  of each line moves, so "2 x 400 g tin" doubles to "4 x 400 g tin" and never "4 x 800 g".
  Grams and millilitres read as decimals, cups and spoons as fractions. The stored recipe is
  untouched; it is a way of reading it, not an edit.
- **It notices a recipe you already have** — before saving a scan or adding a shared one, it
  compares the name and the ingredients against the book and offers to open the one you have
  instead. Catches the same page scanned twice even when the wording comes out differently.
- **Send a recipe to someone** — turns it into a link. They tap it, the app asks whether to add
  it, and that is that. No key needed at either end, and nothing of theirs is overwritten.
  If the link opens in the wrong place (an iPhone with the app on the home screen keeps separate
  storage from Safari), paste the link into the box in Settings instead.
- **Backup and restore** — a JSON file with the photos in it, plus a CSV of the whole book.
  Restoring can add to what is already there rather than replacing it.

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
