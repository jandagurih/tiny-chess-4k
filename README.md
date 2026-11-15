# tiny-chess-4k

Entry for the make.fun bounty `tiny-chess-01`: a 4 KB chess engine.

## Files

- `main.py` - the entry itself. The readable source is compressed (lzma +
  base85) and unpacked at import time so the whole engine fits the 4,096-byte
  limit. It speaks the UCI-like protocol the harness expects.
- `LICENSE` - MIT.

## How it plays

Alpha-beta search with quiescence, a transposition table, late move reductions,
null-move pruning, check extensions, killer moves and repetition detection at
the root. Evaluation is material plus piece-square terms, pawn structure and a
small king-safety term.

## Result

Local practice runs against the kit's reference opponents score 2.5/6
(Elo ~1191 on the kit's anchor scale); the pass mark is 1154.
