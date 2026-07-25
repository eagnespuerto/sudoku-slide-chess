# Sudoku Slide Chess

A playable reading of [xkcd 3139, "Chess Variant"](https://xkcd.com/3139/) — Randall Munroe's sliding number puzzle chess. Numbered officers, one hole, a board that rotates.

**Play it:** https://eagnespuerto.github.io/sudoku-slide-chess/

## How it plays

Every piece carries a number. One square is a hole. Three moves, three prices:

- **Chess move — cost 1.** Click a piece. If it can legally reach the hole, the ringed square lights up. The piece glides there; the hole takes its place. Sliders are blocked by other pieces, as always.
- **Swap — cost 2.** Two pieces trade squares if *either* one attacks the other. Dashed rings mark the partners. Turn on *duels only* for the tighter game, where both must attack.
- **Rotate — cost 3.** Use the handles beside the board, or the arrow keys, to cycle the hole's row or column by one. Every square in that line shifts and the far end wraps around. Only lines through the hole may rotate, so the hole is your cursor.

You win when no number repeats in any row, column or region.

## Board sizes

- 4×4 · 2×2 regions · 15 pieces
- 6×6 · 2×3 regions · 35 pieces
- 9×9 · 3×3 regions · 80 pieces

Clearing numbers *and* ranks together is fine. Making every (rank, number) pair distinct is not, at 6×6: that is Euler's problem of the 36 officers, ruled out by Tarry in 1901 — there is no pair of orthogonal Latin squares of order 6. It works at 4×4 and 9×9, and only there among these three. The puzzle never asks for it.

## Keys

`← ↑ → ↓` rotate · `U` undo · `R` redo · `H` hint · `Esc` deselect

## Running locally

It's a single HTML file with no build step or dependencies. Open `index.html` in a browser, or serve the folder:

```
python -m http.server
```

## Credits

- **Concept:** [xkcd 3139, "Chess Variant"](https://xkcd.com/3139/) by Randall Munroe (8 September 2025), captioned *sliding number puzzle chess*. Used only as inspiration; xkcd is published under [CC BY-NC 2.5](https://creativecommons.org/licenses/by-nc/2.5/).
- **Pieces:** the Cburnett set by Colin M.L. Burnett, [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/), as distributed with [lichess](https://github.com/lichess-org/lila/tree/master/public/piece/cburnett).
- **The sudoku, the pricing and the rotation rules** are this page's own doing.

## License

MIT for the game code. Embedded third-party assets keep their original licenses — see [LICENSE](LICENSE).
