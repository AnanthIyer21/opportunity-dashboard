# Opportunity Radar

A self-updating dashboard of opportunities for a math/CS student: jobs,
internships, competitions, hackathons, fellowships, founder programs and events
across global hubs.

- **Live dashboard:** served via GitHub Pages from this repo (`index.html`)
- **Data:** `opportunities.json` — updated every morning at 07:30 (Europe/Zurich)
  by a scheduled Claude task following `UPDATE_INSTRUCTIONS.md`
- **Tracking:** ★ Save / ✓ Applied / ✕ Hide states are stored in the browser
  (localStorage), so they're per-device and never leave the machine.

Built with a single static HTML file — no build step, no dependencies.
