# Soundboard

A mobile-first, single-page soundboard that runs entirely in the browser. No build step, no server, no account.

## Features

- Multiple boards with colored pads; tap to play/stop, with per-pad fade-in, loop and fade-out
- Built-in sound library (~45 synthesized sounds) with search, categories and favorites
- Upload any number of audio files from your device (stored in your browser, no limit besides disk space)
- Rename pads (tap the name in Edit mode) and edit sounds: volume, speed, trim handles on a waveform, keep/remove a selection
- Settings and sounds are saved locally in the browser (localStorage + IndexedDB)
- **Download profile** / **Import profile**: move boards, settings and uploaded audio to another device as one `.json` file
- Installable as a PWA and works offline once loaded
- English and Bahasa Indonesia

## Run locally

Open `index.html` in a browser. For PWA/offline features, serve it over HTTP instead:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a new GitHub repository and push these files to the `main` branch.
2. In the repository, go to **Settings → Pages** and set **Source** to **GitHub Actions**.
3. The included workflow (`.github/workflows/pages.yml`) publishes the site on every push. Your site will be at `https://<your-username>.github.io/<repo-name>/`.

Alternatively, choose **Deploy from a branch → main → / (root)** in Pages and ignore the workflow.

```bash
git init -b main
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Data and privacy

Everything stays on your device. Nothing is uploaded anywhere. Clearing your browser's site data deletes your boards and sounds, so use **Settings → Download profile** to back them up regularly.

Data is stored per origin, so a profile on `localhost` is separate from one on your GitHub Pages address; move it between them with Download/Import profile.

## Project structure

```
index.html              the whole app (HTML, CSS, JS)
sw.js                   service worker for offline use (bump VERSION after changes)
manifest.webmanifest    PWA manifest
icons/                  app icons
.github/workflows/      GitHub Pages deployment
```

## License

MIT, see [LICENSE](LICENSE).
