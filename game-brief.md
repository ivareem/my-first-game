# Alien Tic-Tac-Toe — Game Brief

## Concept

Alien Tic-Tac-Toe is a solo browser game where the player chooses a square on a three-by-three board, fights a short alien battle for that square, and tries to complete an X line before the aliens complete an O line.

## Player and purpose

- **Intended player:** A casual player who can use a mouse, keyboard, or touchscreen.
- **Purpose:** Deliver a short, understandable strategy game with a playful space theme.
- **Expected round length:** About 3–7 minutes.
- **Main action:** Choose an empty board square, then counter the alien's move during the battle for that square.

## Visual direction

- **Palette:** Use a strong blue-and-orange game board. Blue is the main board and space color; orange highlights borders, the pending square, and primary actions.
- **Board readability:** Empty squares, X marks, O marks, the pending square, and the winning line must remain distinct. Use labels, shapes, and contrast as well as color.
- **Alien characters:** Use original, family-friendly animated aliens with rounded silhouettes, large expressive eyes, clear facial reactions, and playful personalities. They may evoke the warmth and polish of a classic animated feature, but must not copy a recognizable Disney character, costume, name, or signature design.
- **Alien variety:** Start with one original alien design and show a few simple expressions for neutral, hit, victory, and defeat states. Additional aliens can wait until the game loop works.
- **Assets:** Prefer original inline SVG or CSS shapes so the game works offline without downloaded character art.
- **Accessibility:** Keep text and controls readable on both blue and orange surfaces, retain visible keyboard focus, and never communicate health or outcomes through color alone.

## Playable first version

1. The player reads the instructions and starts with an empty three-by-three board.
2. Selecting one empty square locks the entire board and starts one battle for that square.
3. Each battle starts with 2 player health and 2 alien health.
4. Alien moves follow the predictable sequence Laser, Shield, Claw. The correct counters are Shield, Blast, Dodge.
5. A correct response removes 1 alien health. Any other response removes 1 player health. Each accepted response damages exactly one side once.
6. If both sides still have health, the player uses **Next exchange** before responding again.
7. Winning the battle places one X in the selected square. Losing places one O. The alien never takes a separate board turn.
8. Three X marks in a row, column, or diagonal wins the board. Three O marks loses the board. A full board with no line is a draw. Lines are checked before a draw.
9. If the board continues, **Return to board** allows another empty square to be chosen. A finished board offers **Play again**.
10. **Restart game** is available during active play and clears the board and any battle in progress without awarding a mark.

There is no numeric score in the first version. Progress is shown through X and O marks, battle health, and the final board result.

## Controls

- Board squares and actions are standard buttons usable by touch or pointer.
- Keyboard players use Tab to move focus and Enter or Space to activate a button.
- Battle responses are **Shield**, **Blast**, and **Dodge** buttons.
- Other controls are **Start**, **Next exchange**, **Return to board**, **Restart game**, and **Play again**.

## Three build increments

1. **Board prototype:** Select and lock a pending square, resolve it once as X or O with temporary test controls, detect all eight lines and draws, and reset the board.
2. **Battle prototype:** Run the fixed three-move battle sequence, apply one damage event per response, end immediately at zero health, and reset the battle.
3. **Connected game:** Use the real battle result to award the pending square exactly once, remove temporary controls, evaluate the board immediately, and reset all state correctly.

## Five observable completion checks

1. **One battle, one square:** Selecting Cell 1 locks the board. Winning its battle places exactly one X in Cell 1, with no automatic O elsewhere.
2. **Battle outcomes:** Shield then Blast wins after two exchanges with player health 2 and alien health 0. Blast then Shield loses after two exchanges with player health 0 and alien health 2.
3. **Board endings:** X on Cells 1, 2, and 3 produces an immediate player win; O on those cells produces an immediate alien win; a full board without a line produces a draw.
4. **Invalid and repeated actions:** Selecting an occupied cell does nothing. Repeatedly activating one response before Next exchange applies damage only once. A resolved battle cannot award its square twice.
5. **Complete reset:** Restarting during battle immediately clears all nine cells and all battle state without awarding the pending square. Play again after a board result also starts with nine empty cells and fresh battle state.

## First-version exclusions

- Automatic opponent board moves
- Random alien move order or random damage
- Timers, sound, downloaded artwork, or animation-heavy effects
- Recognizable copyrighted characters, logos, costumes, or traced character artwork
- Multiple levels, inventories, upgrades, or alternate battle moves
- Multiplayer, accounts, databases, global leaderboards, payments, or external services

## Later ideas

After the complete loop passes its checks, possible additions include randomized alien moves, several alien appearances, optional sound, or a local best-of-series record. These are not part of the first version.

