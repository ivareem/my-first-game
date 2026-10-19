# Alien Tic-Tac-Toe — Test Report

## Version and environment

- Version: Local playable checkpoint 03
- File: `/workspace/my-first-game/index.html`
- Browser: Headless Chromium
- Laptop viewport: 1280 × 900
- Phone viewport: 390 × 844
- Date: October 19, 2026

## Observed checks

| Check | Status | Actual observation |
| --- | --- | --- |
| Instructions before Start | Passed | The introduction was visible and the game board was hidden until Start game was activated. |
| Board lock | Passed | Selecting an empty cell disabled all nine cells until its battle finished. |
| One response per exchange | Passed | Two rapid activations applied one damage event; health remained within 0–2. |
| Two-exchange win and loss | Passed | Shield/Blast produced X with player 2, alien 0; Blast/Shield produced O with player 0, alien 2. |
| Third-exchange outcomes | Passed | Shield/Shield/Dodge produced X; Blast/Blast/Blast produced O; neither offered a fourth exchange. |
| One battle, one mark | Passed | Battle completion assigned only the pending cell; Return to board did not assign another mark. |
| Occupied cell | Passed | Awarded cells remained disabled. |
| Help during battle | Passed | Opening and closing help preserved the pending cell, health, and exchange feedback. |
| Restart during feedback | Passed | Restart cleared every mark and the active battle without awarding the pending cell. |
| Restart from help | Passed | Restart inside the modal cleared the board and returned to nine selectable cells. |
| All winning lines | Passed | All three rows, three columns, and two diagonals produced an immediate X board win. |
| O line | Passed | O on Cells 1, 2, and 3 produced an immediate alien board win. |
| Full-board draw | Passed | X,O,X,X,O,O,O,X,X produced a draw after Cell 9. |
| Last-cell win precedence | Passed | X,O,O,O,X,X,X,O,X produced an X win on Cells 1, 5, and 9 rather than a draw. |
| Play again | Passed | Replay cleared marks, winner, pending cell, health, and feedback. |
| Keyboard activation | Passed | Focusing a board cell and pressing Enter started its battle. |
| Phone-width layout | Passed | The 390-pixel layout had no horizontal overflow; board and battle controls remained visible. |
| Console and page errors | Passed | The complete automated playthrough produced no console or page errors. |
| Visual inspection | Passed | The introduction and active battle were inspected at laptop width; the active battle was inspected at phone width. Text, pending state, health, and actions were readable. |

## Not tested

- A complete Tab/Shift+Tab keyboard playthrough
- A real phone or physical touchscreen
- Screen-reader announcements
- An independent person's uncoached two-minute playtest
- A deployed URL

## Next check

Have another person open `index.html`, play without coaching for two minutes, and record whether they understand that one battle awards one square and that the alien does not take an extra board turn.

