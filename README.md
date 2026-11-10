# Brad N Tiff Hub: app shell

This is a small installable app that opens the Brad N Tiff Hub full screen, with its own icon and splash screen and without Google's "created by a Google Apps Script user" bar.

The hub itself still runs on Google Apps Script. This page only frames it. Each person signs in with their own Google account, and Drive sharing still decides what they see.

## Files

| File | What it does |
|---|---|
| `index.html` | The splash screen and the frame that holds the hub. **The `HUB_URL` line is the only thing to edit.** |
| `manifest.webmanifest` | The app's name, icon and colors, so Chrome offers **Install app** |
| `sw.js` | Keeps the splash screen and icons on the device so the app opens instantly. It never caches hub data. |
| `icons/` | App icons (regular and maskable), the Apple touch icon and favicons |
| `fonts/` | Big Shoulders Display and Schibsted Grotesk, the hub's fonts (SIL Open Font License) |
| `robots.txt` | Keeps search engines out |

## Updating

- **Hub code changes** (Code.gs or Index.html) never need anything here. The app always loads the live hub.
- **Shell changes:** edit the file on GitHub and commit. Pages updates within a minute, and the app picks it up the next time it opens. If you change an icon, also change `VERSION` in `sw.js` (for example to `bt-hub-shell-v2`).

## If the app opens to a blank page or a "refused to connect" message

Usually it means Chrome isn't signed in to Google right now. Tap **Open in Chrome** on the splash screen (or open the hub link in Chrome), sign in, then reopen the app.

When a hub update needs a new Google permission, approve it the same way: open the hub link in Chrome once.
