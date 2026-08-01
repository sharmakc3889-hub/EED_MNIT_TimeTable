# Academic Time-Table

A single-page web app for building and managing an academic department's
weekly timetable — classes, subjects, faculty, technicians, research
scholars/labs, and period/day scheduling — with clash detection and
Excel export.

**[Live demo →](#)** *(replace `#` with your GitHub Pages URL once enabled — see below)*

## Features

- Weekly timetable grid, configurable days-per-week, periods/day, period
  length, gaps, and lunch break
- Classes/sections, subjects, faculty, technicians, and research scholars
  management
- Lab/batch assignment to scholars and technicians
- Subject ↔ faculty mapping with credit/hour tracking
- Clash detection across the schedule
- Optional admin password lock for editing
- Export to Excel (`.xlsx`) via SheetJS
- All data is saved locally in the browser (`localStorage`) — no backend,
  no account, no data leaves the device

## Tech stack

This is a **zero-build, single-file** app: `index.html` loads React,
Babel Standalone, Tailwind CSS, and SheetJS from public CDNs, and
transpiles the embedded JSX in the browser at load time. There is
nothing to install and nothing to compile.

## Running locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`,
   pick the `main` branch and `/ (root)` folder, then save.
4. GitHub will publish the site at
   `https://<your-username>.github.io/<repo-name>/`.

No further configuration is required — the app is fully static.

## Data & privacy

All timetable data is stored only in the visiting browser's
`localStorage` (key `timetable-portal-v3`). Nothing is sent to a server.
Clearing browser data/cache will erase the saved timetable, so use the
Excel export for backups.

## License

MIT — see [LICENSE](LICENSE).
