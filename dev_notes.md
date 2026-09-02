# Counto — dev notes

Single-file canvas abacus-style score counter. All logic lives in `index.html`.

## Layout / objects

- `App` owns canvas, players, falling beads, stack mode, pointer holds
- `Player` is name + count
- `FallingBead` is the in-flight drop; count increments only on land
- Toolbar: reset / stack-mode toggle / add player
- Columns scale with player count; bead size scales with tallest visual stack

## Stack modes

- **collapsed** (default, ◆): compress into 100 / 50 / 10 / 5 / 1 beads; crush lower beads as a carry drop passes them
- **flat** (≡): one bead per count; ordinal denom (100/50/10/5/1) with no crush
- Mode + players persist in `localStorage` key `counto_players_v1`

## Beads

- 1 off-white, 5 red, 10 blue, 50 purple, 100 orange
- Width mult and corner radius grow with denomination
- High-value beads sit at the bottom of a column; ones on top

## Input

- Tap name: drop a bead
- Tap terminal (−): remove last pending drop, else decrement count
- Long-press terminal: remove player
- Long-press name: open name editor overlay
- Long-press reset: clear counts (or clear names too if already all zero)
- Short-press reset does nothing; name-clear is long-press-when-zero only

## Previous Change Log

- Persist stack mode; add orange 100 denomination bead
- Update index.html
- Toolbar button toggles collapsed vs flat stack mode
- Refactor: App/Player/FallingBead objects, StackMode, single draw path
- Update index.html
- Crush lower beads as falling carry bead passes them
- Falling carry beads show red/blue/purple and land as that denomination
- Stack order: high value beads at bottom, ones on top
- Compress stacks: 5/10/50 beads replace lower ones; reverse on subtract
- Move special purple bead style from 25s to 50s
- Roundrect beads; 25s purple larger; corner radii by type
- Long-press reset clears names when zero; long-press name opens editor
- Persist players and counts in localStorage
- Update index.html
- Headroom +2 beads; long-press terminal removes player; mobile name overlay input
- Bigger beads from col width; 10 fill screen; width mult 1/1.2/1.4; grey single outlines; min name btn
- Tight fixed bead spacing, larger beads, white names, grey terminal with minus
- Toolbar top; + moved up; blue 10s; yellow whites; shine-matched outlines; scale 10→100 beads
- Med dark green bg; bead only lands after drop; reset requires release before name-clear
- Update README with usage
- Add Counto single-file canvas abacus counter app
- Initial commit
