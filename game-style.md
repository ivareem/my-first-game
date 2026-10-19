# Game Style

## Visual direction

- Deep blue space background and blue board cells
- Orange borders, pending-cell treatment, and primary actions
- White X marks and orange O marks, with text labels and shapes supporting color
- One original rounded alien with expressive eyes, antennae, and neutral, hurt, victorious, and defeated expressions
- Inline SVG and CSS only; no external character art or network assets

## Readability requirements

- Responsive two-column laptop layout and single-column phone layout
- Minimum comfortable touch targets and visible keyboard focus
- Written health values plus bars
- Explicit pending-cell and result text
- Reduced-motion support

## Observed checks

- The introduction and active battle were visually inspected at 1280 × 900.
- The active battle was visually inspected at 390 × 844 with no horizontal overflow.
- Board state, pending square, health, counters, and action buttons were readable at both widths.
- Focusing a board cell and pressing Enter started a battle.

## Remaining checks

A complete keyboard route, touch behavior on a real device, screen-reader output, and an independent human playtest remain to be checked.

