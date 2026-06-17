# FRC 2024 CRESCENDO — Robot Study Dashboard

An interactive catalog of **96 teams** that publicly released downloadable CAD for the 2024
CRESCENDO season, with **11 curated ★ study picks** carrying full subsystem deep-dives mined
from each team's Chief Delphi release/reveal thread.

## Files

| File | What it is |
|---|---|
| `FRC2024_Crescendo_Robot_Study_Dashboard.html` | The interactive dashboard (desktop table + mobile cards, search / archetype / CAD / confidence filters). |
| `FRC2024_Crescendo_TopTeams_DeepDive.html` / `.pdf` | Printable deep-dive of the 11 study picks (subsystem cards + lessons). |
| `index.html` / `deep-dive.html` / `deep-dive.pdf` | The same outputs prepped for GitHub Pages, with the dated "Updated…" banner + "What's changed" panel. |
| `pipeline/` | The build pipeline: `config.py`, `codex_data.json` (96 teams), `deepdive_extra.py` (deep profiles + picks), build scripts, and the discovery inputs (`_cad_links.txt`, `_names.txt`). |

## Notes

- **EPA / rank are pending a Statbotics API outage** (HTTP 500 at build time, 2026‑06‑16) and
  will be backfilled when the API recovers — the table is sorted by team number until then.
- Every team here released **downloadable CAD**, so all are CAD = Yes / High confidence.
- Discovery: Spectrum 3847 CAD Collection (2024). Mechanism detail: Chief Delphi.
- Built from the `frc-robot-study-dashboard` skill, mirroring the 2025 REEFSCAPE dashboard.

## Rebuild

```
cd pipeline
python3 build_dashboard.py
python3 build_deepdive_html.py
python3 build_deepdive_pdf.py
python3 apply_changelog.py      # regenerates ../index.html + banner
```

See `PUBLISH_SETUP.md` for the one-time GitHub Pages setup.
