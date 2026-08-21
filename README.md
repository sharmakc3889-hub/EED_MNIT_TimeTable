# MNIT EE Academic Timetable Portal

Static, single-page timetable application (React 18 + Babel Standalone, all client-side).

## Files

- `index.html` — the application. All data lives in the visiting browser's `localStorage`.
- `data.json` — timetable dataset (departments, classes, subjects, faculty, rooms, timetable slots, scholars, technicians). Exported from the app via **Download backup**.
- `.nojekyll` — tells GitHub Pages to skip Jekyll processing (not strictly required here, but harmless and standard).

## How seeding works

On first load in a browser with no saved data, `index.html` fetches `data.json` (same folder) and seeds the app with it. From then on, edits made in that browser persist only in that browser's `localStorage` — GitHub Pages is static hosting, so there is no shared server-side database. Each visitor gets their own independent copy starting from `data.json`.

To reset a browser back to the published dataset, clear the site's local storage (Admin panel usually exposes "Restore backup", or clear it via browser devtools) and reload.

## Publishing on GitHub Pages

1. Create a new GitHub repository (public, or private on a plan that supports Pages).
2. Push these three files to the repo root (branch `main`):
   ```bash
   git init
   git add index.html data.json .nojekyll README.md
   git commit -m "Initial timetable portal"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Site will publish at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

## Updating the published dataset

Whenever you want the *published* (fresh-visitor) dataset to change:

1. In the app, use **Download backup** to export the current data as JSON.
2. Replace `data.json` in the repo with the new export.
3. Commit and push. New visitors (or anyone who clears local storage) will see the update; existing visitors' in-browser data is untouched until they clear storage or use **Restore backup** with the new file manually.
