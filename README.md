# Stremio Auth Key Bookmarklet 🔖

A small, ready-made page that exposes a bookmarklet for quickly viewing your Stremio `auth.key` that lives in your browser's `localStorage`.

## What this file/page is and does ✨
- The repository contains `index.html` — a simple page that provides a bookmarklet.
- When executed in the context of the Stremio web app (while logged in), the bookmarklet reads the `profile` object from `localStorage`, extracts `auth.key`, and displays it in a prompt.
- No data is transmitted off your machine by the bookmarklet; it runs entirely in your browser.

## Features ✅
- One-file tool: `index.html` contains the bookmarklet code and a small UI.
- Instant access: shows the Stremio auth token without opening dev tools.
- Minimal and transparent: the exact JS is visible in the page.

## How it works (high level) 💡
The bookmarklet evaluates JavaScript in the current page that does the following:

```js
const key = JSON.parse(localStorage.getItem('profile')).auth.key;
prompt('Your Stremio Auth Key:', key);
```

That code reads the `profile` entry from `localStorage`, pulls out `auth.key`, and surfaces it to you via a prompt.

> ⚠️ Note: This only works when a Stremio session is present in the browser (i.e., you're logged in and `localStorage.profile` is available).

## Security & Privacy 🔒
- The bookmarklet runs locally in your browser and does not send your key to any server.
- Use responsibly: do not use this tool to access or extract keys from accounts you do not own or have permission to access.

## Files
- `index.html` — the page and the bookmarklet link.

## License
No license specified. Use at your own risk.
