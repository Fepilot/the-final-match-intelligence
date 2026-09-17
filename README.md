# THE FINAL · Match Intelligence

**Spain v Argentina · FIFA World Cup 2026 Final — an interactive data story, built end‑to‑end with a single Copilot Cowork prompt.**

🔗 **Live app:** https://fepilot.github.io/the-final-match-intelligence/

> *FerPilot · Football Intelligence Exploration*

---

## What this is

This repo is a single‑prompt case study. I gave GitHub Copilot Cowork the raw match data for the 2026 World Cup Final (an Opta/WhoScored‑style event feed, its data dictionary, and a post‑match report PDF) plus one long prompt (see [`PROMPT.md`](PROMPT.md)), and asked it to take full ownership of the process — from understanding and validating the raw data to designing, building and testing a finished interactive product. No manual data cleaning, no back‑and‑forth spreadsheet work: Copilot explored the files, audited them, derived its own metrics, and shipped [`index.html`](index.html) — a self‑contained, dependency‑free interactive application.

The result answers one question — **"How was this World Cup Final really decided?"** — through an animated pitch, a story mode, a player explorer, and a head‑to‑head comparison, instead of a conventional stats dashboard.

## The four modes

- **Explore** — an animated pitch with play / pause / scrub / speed controls, period, team, player and event‑type filters, persist and normalise toggles, live running totals, and a density timeline marking goals, cards and big chances.
- **What the data tells us** — 8 editorial story moments (e.g. *"The First Warning"*, *"Enzo Walks"*, *"The Territory Never Moved"*). Selecting one loads its supporting evidence directly onto the pitch and timeline.
- **Player explorer** — all 34 players, their event footprint and zone counts. Deliberately **not** a heat map — it counts recorded events, not tracked movement.
- **Spain v Argentina** — 21 event‑derived metrics by period, territory by period, the full shot map, plus a separate second‑source panel for the 15 report‑only metrics (pressures, line breaks, recovery time) that the event feed itself cannot produce.
- **About the data** — sources, every correction applied, every derivation rule, and what is deliberately left blank.

## Why it looks and behaves this way

The source is **event data**, not tracking data: every coordinate marks a recorded action (where a pass started, where a tackle was made, where a shot was struck) — never a continuous player position. So the application:

- never interpolates a player's position between two events, and never draws anything *between* two recorded events;
- never shows pitch control, proximity‑based pressure, off‑ball shape, or velocity;
- animates strictly from one recorded event to the next — a sequence of measurements, not a reconstruction of play.

## Known data issues, found and fixed by Copilot during the build

- **Stale score metadata.** The event file's `home_score`/`away_score` columns read `0–0` on every row. Cross‑checking the actual `isGoal` events (one goal: Ferran Torres, 106') against the independent post‑match report (which states Spain 1–0 Argentina) confirmed the metadata field was stale. The application reports **1–0**; the source file itself was left untouched.
- **Row order.** Rows were sorted by raw `minute:second`, which interleaves second‑half stoppage time with extra time. Events were re‑sorted by period, then minute, then second.
- **Mirrored coordinate frame.** Each team's coordinates are recorded in its own attacking frame (opposing‑team duel pairs satisfy x₁+x₂=100, y₁+y₂=100 exactly). Argentina's events are mirrored onto one shared absolute pitch so both teams can be shown together.
- **A duplicate event id** was found and handled by keying on row position instead of dropping data.
- **Inconsistent period labels** in the raw file vs. the data dictionary were reconciled against a clean derived global clock.

Every correction is documented in the app's "About the data" panel, alongside the exact rules used for every derived metric (progressive pass, final‑third entry, penalty‑area entry, regain, average touch position, attempt on target).

## What's deliberately left blank

No xG (not present in the event file and not reproducible), no possession percentage (no possession‑chain data — touch share is shown instead, labelled as such), no physical/distance/sprint data, and no formation shape (formation ids exist but are not decoded into a shape). Nothing here is estimated to fill the gap.

## Files

| File | Description |
|---|---|
| [`index.html`](index.html) | The complete application — self‑contained HTML/CSS/JS, no build step, no external dependencies. Also the file served by GitHub Pages. |
| [`PROMPT.md`](PROMPT.md) | The original prompt given to Copilot Cowork that produced the application in a single pass. |

## Running it locally

No build tooling required — it's a single static HTML file:

```bash
# Windows
start index.html

# macOS
open index.html

# or just open the file in any modern browser
```

## Tech notes

- Vanilla HTML/CSS/JS, no frameworks, no build step, no external requests — all match data is embedded inline as JSON.
- Pitch and shot map rendered as SVG; the event‑density timeline is rendered on `<canvas>`.
- Deployed via GitHub Pages directly from this repository.

## Credit

Inspired by the Executive Formula 1 dashboard from David Hurtado — [Telemetría F1 · GP de Bélgica 2026 · Spa-Francorchamps · Antonelli vs Verstappen](https://davidhurtadoai.github.io/Explorations/Formula1-Spa2026.html).

---

*Built as a FerPilot exploration of how AI can transform raw sports data into an interactive story — one prompt, full ownership, from raw event feed to finished data product.*
