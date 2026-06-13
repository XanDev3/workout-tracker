# 3-Day Recomp Log

A single-file, offline-capable workout tracker for a 3-day full-body recomposition + posture program. No build step, no dependencies, no backend.

## What it is

`index.html` is the entire app — HTML, CSS, and JavaScript in one file. Open it in a browser and it runs. It logs reps and weight per set, shows your last session and all-time best per lift, runs a rest timer with an audible cue, and keeps full session history.

## Storage & privacy

The app stores data **locally in your browser** via `localStorage`. That means:

- Your training data lives only in the browser on the device you use it on. It is never uploaded anywhere.
- The repo and the site can be fully public without exposing any of your numbers — the data isn't in the repo, it's in your browser.
- Data is per-device and per-URL. Use a stable URL (don't switch between the IP and the hostname), or your log will appear "empty" because the browser treats a different origin as a different site.

For backup or moving between devices, use the **Export / Import backup (JSON)** buttons in the History tab. Exported files drop nicely into iCloud Drive, Dropbox, etc.

## Deploy to GitHub Pages

```bash
cd workout-tracker
git init
git add .
git commit -m "Initial commit: workout tracker"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `root` → Save.**

After a minute the site is live at:

```
https://<your-username>.github.io/<repo-name>/
```

Because the file is named `index.html`, that root URL loads the app directly.

## Add it to your iPhone home screen

1. Open the GitHub Pages URL in Safari.
2. Tap the Share button → **Add to Home Screen.**
3. Launch it from the icon — it runs full-screen like a native app, and `localStorage` persists between launches.

## Notes

- Audio for the rest timer is unlocked by your first tap (a browser requirement) and is muted by the iOS silent switch, as expected.
- The rest timer is timestamp-based, so a brief screen lock won't freeze it — on unlock it shows the true time remaining.
- Demo links point to the SmartWorkout exercise library.
