# counto

Fullscreen canvas abacus-style score counter. Single file: `index.html`.

Add players, tap a name to drop a bead onto their column, tap the top terminal to take one off. Layout scales with player count and stack height. Players, counts, and view mode persist in the browser.

## Players

- Tap **+** (top right) to add a player. Names are typed in the overlay (max 12 characters).
- Long-press a player name to rename them.
- Long-press the grey **−** terminal at the top of a column to remove that player.

## Beads

Tap a player name to drop a bead. The count only goes up after the bead lands. Tap the **−** terminal to cancel an in-flight drop, or subtract one if nothing is falling.

Denominations, bottom of the stack to top:

| Value | Color |
| --- | --- |
| 100 | orange |
| 50 | purple |
| 10 | blue |
| 5 | red |
| 1 | off-white |

Higher-value beads are wider and sit lower on the rod. Ones sit on top. Max count per player is 1000.

## View modes

Toolbar button next to **+** toggles the stack view:

- **◆ collapsed** — compress into as few beads as possible (100 / 50 / 10 / 5 / 1). A carry drop crushes the beads it replaces as it falls.
- **≡ flat** — one bead per count. Every 5th / 10th / 50th / 100th bead uses that denomination look. No crush.

## Reset

Long-press **↻** (top left, 1 second):

- If anyone still has beads: clear all counts, keep names.
- If every count is already zero: clear names too.

Short-press does nothing. Mode and data are stored under `counto_players_v1`.
