# firestorm-diagrams

Diagrams of the Apple M1 Firestorm core, drawn from the claims in
[uarch-map](https://github.com/ihagedo/uarch-map). The atlas at
https://www.isaachagedorn.com/uarch-map/atlas/ shows them in ten maps, with the map's evidence beside
each figure. Every value carries its confidence from the map, and conjectures are kept apart from
measurements.

## Layout

- `drawio/` the figures in editable form, one file per set and one page per figure
- `figures/` the figures as SVG
- `sheets/` one generated sheet per block of the map
- `png/` PNG renders of the figures and sheets
- `walkthroughs/` each figure read step by step, with the shapes each step points at
- `atlas.yaml` the ten maps in reading order and the figures and sheets in each
- `coverage.json` which blocks and mechanisms each figure draws

## Conventions

The border of a box and the glyph beside a value both say how well the value is known.

| glyph | meaning |
|---|---|
| ● | three or more measurements |
| ◆ | two sources |
| ○ | one source |
| ◇ | derived from other values |
| ~ | read from a patent or by analogy |
| ? | conjecture, or unknown |
| + | proposed here |

Wires have four kinds: instruction flow (1.6 px), data (2.8 px), control (1.2 px, dashed 5 3) and
allocate or release (1.2 px, dashed 2 3). A two-way flow is drawn as two one-way arrows.

Colour says where a block lives. The front end is blue, the back end green and the memory side red,
and a block between two of them takes the mix: cyan for the decode to rename hand-off, yellow for the
load-store unit, purple for the instruction side's caches, orange for the L2 and SLC, and silver for
the die and clusters. Magenta is only for what isn't known.

Boxes hold names and values, not sentences.

## Contributing

Open a file from `drawio/` in draw.io (the desktop app or app.diagrams.net), fix or redraw the figure,
and open a pull request with the edited file. Keep the ids of the shapes you change, since they tie
each shape back to its block in the map. A new shape can have any id.

The SVG and PNG files are generated, so a pull request only needs the `.drawio` file. I regenerate the
rest after merging it.
