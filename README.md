# SOI Crafts Browser

A self-contained browser for Shadows of Isildur's craft system — every craft,
its phases, skill checks, restrictions, the objects involved, and full
input→output lineage tracing, generated from the game's own craft definitions.

**Browse it: https://sebguer.github.io/soi-crafts/**

- **Overview** — totals by group, command, skill (checked vs starter crafts),
  profession tier, clan rank, restriction, and craftable objects by item type.
  Every row click-throughs to the filtered list.
- **Crafts** — search across names, commands, objects, skills, clans, races
  and mobs; as you type, chips offer to search that word in one field instead
  (subcraft names, input/output objects, echo text, skill checks, …) with live
  counts, and `field:word`, `"quoted phrase"` and `-word` syntax is shown
  under the box; stackable filters whose
  drop-downs can be ordered by count or alphabetically; a **⬇ CSV** button
  that downloads the filtered list. Click a craft for its full
  phase-by-phase detail, including where each input comes from and where
  each output goes.
- **Objects** — the reverse index: every craft-involved object with per-role
  usage counts and the crafts that make or consume it (CSV export too).

Entirely static: one HTML file, no server, works offline if saved.

Staff-hidden crafts are excluded from this public build.

## Regenerating

`index.html` is generated — do not edit it by hand. The generator
(`generate.py` + `template.html`) parses the engine's `regions/crafts` flat
file and object prototypes; it lives alongside the game data checkout and is
run with `--no-hidden --out <this repo>/index.html`, then committed here.
