# Lulu Maths PWA

Touch/stylus-friendly maths practice app for Android tablets and iPads.

## What it does
- Stylus or finger handwriting on an answer canvas
- Undo / Clear / Save
- Saves handwriting locally on the device
- Multiple exercise categories
- Shuffle questions
- PWA install support
- Offline app shell after first online load
- Exercise library kept separate in `exercises.js`
- Parent/Teacher import and export of exercise JSON

## Install on Android
A service worker requires HTTPS (or localhost during development). Host this folder on any static HTTPS host such as GitHub Pages, Netlify, Cloudflare Pages or your own web server.

Then on Chrome for Android:
1. Open the app URL while online.
2. Choose **Add to Home screen** / **Install app**.
3. Open Lulu Maths from the home-screen icon.
4. After the first load, ordinary worksheet use works offline.

## Add more exercises
Edit `exercises.js` and add more objects to an existing category:

```js
{"id":"sub-021","prompt":"52 − 4 =","answer":"48"}
```

A category is simply an array of exercise objects. The home screen creates its cards dynamically, so adding a new category such as `shapes` automatically creates a new activity card.

## Important limitation
The child’s handwriting is saved as stroke data, but this starter version does **not** automatically read handwriting to determine whether it is correct. Automatic marking can be added later with either a numeric keypad answer field or optional handwriting OCR.


### Imported exercise sets
Exercise imports are stored in the browser's local storage, so they remain available after closing and reopening the app. If you update `exercises.js` on your hosted version, the service worker checks the app shell/exercise data online first and falls back to the cached copy when offline.
