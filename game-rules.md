# Alien Tic-Tac-Toe — Rules and Controls

## Goal

Win short battles to place X marks and complete a three-in-a-row line before the aliens complete an O line.

## How to play

1. Select an empty board square with touch or a pointer, or focus it with Tab and activate it with Enter or Space.
2. Read the alien's move and select Shield, Blast, or Dodge. Shield counters Laser, Blast counters Shield, and Dodge counters Claw.
3. After a nonterminal exchange, select **Next exchange**. A battle win places X; a battle loss places O.
4. Continue until X wins, O wins, or the full board draws. Use **Play again** for a fresh board.

## Board rules

- The board contains nine cells numbered from left to right and top to bottom.
- Only an empty cell can start a battle.
- Selecting a cell makes it pending and locks the entire board until that battle finishes.
- A finished battle assigns the pending cell exactly once. No automatic opponent move follows.
- X wins with any row, column, or diagonal. O completing a line is a loss for the player.
- Check all eight lines before checking whether a full board is a draw.

## Battle rules

- Every battle starts with player health 2 and alien health 2.
- Alien moves use the fixed sequence Laser, Shield, Claw and restart at Laser for each battle.
- Shield counters Laser; Blast counters Shield; Dodge counters Claw.
- A correct response removes exactly 1 alien health. Any other response removes exactly 1 player health.
- Only the first response in an exchange is accepted. Response buttons lock after it.
- If both sides still have health, **Next exchange** advances to the next alien move.
- Zero alien health ends the battle immediately as a win. Zero player health ends it immediately as a loss.
- A battle lasts at most three exchanges and cannot draw.

## Visible states and transitions

| State | Allowed action | Expected result |
| --- | --- | --- |
| Instructions | Start game | Opens an empty board; nothing changes before Start. |
| Choose a cell | Select one empty cell | Records that cell, locks the board, and opens a fresh battle. |
| Choose a response | Select Shield, Blast, or Dodge once | Applies one damage event and locks all response buttons. |
| Exchange feedback | Select Next exchange | Shows the next alien move and enables fresh response buttons. |
| Battle summary | Select Return to board | Keeps the awarded mark and unlocks the remaining empty cells. |
| Board result | Select Play again | Clears the entire board and begins cell selection immediately. |
| Any active state | Open How to play | Opens modal help while preserving board, battle, health, pending cell, and feedback. |
| Help open | Close help | Returns to the preserved state without causing a move. |
| Any active state, including help | Restart game | Clears the board and all battle state, awards no pending mark, and returns to cell selection. |

## Invalid and repeated actions

- Occupied cells and all cells during a battle are disabled.
- Additional response activations during feedback do nothing.
- Next exchange is unavailable after either side reaches zero health.
- Returning from a battle summary never assigns another mark.
- An abandoned battle cannot award a delayed mark after Restart.

## Reset behavior

Restart game and Play again both clear all nine cells, the pending cell, both health values, exchange number, accepted response, feedback, winner, and winning line. Play again is shown after a board result. Restart is available throughout active play and inside help.

## Partner test cases

1. Win Cell 1 with Shield, Next exchange, Blast. Confirm one X and no automatic O.
2. Lose a cell with Blast, Next exchange, Shield. Confirm one O.
3. Try an occupied cell and repeated response activation. Confirm neither changes state twice.
4. Complete X and O lines, then the documented full-board draw pattern.
5. Restart before responding, during feedback, and after a board result. Confirm a clean empty board each time.
6. Open and close help during feedback. Confirm health, pending cell, and feedback remain unchanged.

