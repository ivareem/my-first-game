# Alien Tic-Tac-Toe

A solo browser game where every empty tic-tac-toe square starts a short alien battle. Win the battle to place X; lose it and the aliens place O. There is no automatic opponent board move.

## Play locally

Open `index.html` in a modern browser. The game is a self-contained static file with no installation, account, external asset, or network request required.

## Battle counters

- Shield counters Laser
- Blast counters Shield
- Dodge counters Claw

Each battle starts with 2 health per side. Three X marks in a row win the board, three O marks lose it, and a full board without a line draws.

## Project files

- `index.html` — complete playable game
- `game-brief.md` — concept, scope, and completion checks
- `game-rules.md` — exact board, battle, control, and reset rules
- `game-style.md` — blue-and-orange visual direction and accessibility notes
- `game-feedback.md` — result and replay messages
- `game-test-report.md` — observed Chromium checks and remaining manual checks
- `project-state.md` — current checkpoint and handoff

## Validation

Automated Chromium playthroughs covered two- and three-exchange battles, all eight winning lines, an O line, the documented draw pattern, last-cell win precedence, repeated input, help preservation, restart, replay, keyboard activation, and a 390-pixel-wide layout. A real touchscreen, screen reader, and independent human playtest remain to be checked.

