# Lulu Maths PWA — Updated

This is the updated subtraction-only version for Android tablets and iPads.

## Changes in this version
- Removed Addition and Word Problems from the home screen.
- Shows up to 10 subtraction questions on each page.
- A small handwriting canvas sits next to each subtraction expression.
- Removed the Save button. Each pen stroke auto-saves; **Next page** and **Previous** also save the visible page before navigating.
- Each answer has its own clear (×) button.
- Page count adjusts automatically when exercises are added or imported.
- Handwriting remains stored locally on the tablet; it is not uploaded to GitHub.
- Offline app cache version updated to v3.

## Install/update
Host on HTTPS (for example, GitHub Pages). When replacing these files, keep `index.html`, `exercises.js`, `sw.js`, `manifest.webmanifest` and `icon.svg` at the repository root. Open the live app while online and refresh it to receive updates.

## Add more subtraction exercises
Edit `exercises.js` and add items to the `subtraction` array:

```js
{"id":"sub-021","prompt":"52 − 4 =","answer":"48"}
```

Use a unique ID for each question. Pages are automatically calculated as `ceil(number of questions / 10)`, so 20 questions means 2 pages and 105 questions means 11 pages.

You can also use Parent / Teacher Tools inside the app to import JSON in this format:

```json
{
  "subtraction": [
    {"id":"sub-021","prompt":"52 − 4 =","answer":"48"}
  ]
}
```

Imported questions are saved locally in this browser. To publish questions to every device, update `exercises.js` in the hosted repository.

## Notes
- This version saves handwriting images locally with each question ID.
- It does not automatically read stylus handwriting to grade answers yet.
- For offline functionality, open the online app after updates once, then reopen from the Home Screen app icon.
