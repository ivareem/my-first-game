# Game Feedback

## Result messages

- Battle win: “Battle won — Cell N is yours. X has been placed.”
- Battle loss: “Battle lost — the aliens claimed Cell N with O.”
- X line: “You won the board! X completed [named cells].”
- O line: “The aliens won the board. O completed [named cells].”
- Draw: “Stellar draw! Every cell is filled and neither side made a line.”

Every exchange names the counter and the health change. Battle and board victories use different wording so the player can tell them apart.

## Replay behavior

**Play again** appears after the board ends and starts directly on a fresh board. **Restart game** remains available during active play and help, clears all board and battle state, and never awards an abandoned square.

## Verification

- Confirm that every accepted response produces one explanation and one point of damage.
- Confirm there is no Next exchange after zero health.
- Confirm Return to board never places a second mark.
- Confirm result text identifies a win, loss, or draw and offers Play again.

