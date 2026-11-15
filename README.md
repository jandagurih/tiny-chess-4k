# 4 KB chess engine

A deterministic alpha-beta chess engine in **2,512 bytes** of Python 3.13 (the source is
carried compressed inside `main.py` and unpacked at start), entered in make.fun's
*Build the strongest chess engine in 4 KB of Python* (tiny-chess-01).

- **Board**: a 120-square array with wall sentinels; no clocks anywhere, so a replay
  plays the same moves byte for byte.
- **Search**: iterative deepening to 5 plies, alpha-beta over capture-ordered moves,
  killer moves, null-move pruning, check extension, and quiescence over captures and
  promotions, with mate scores at the leaves.
- **Evaluation**: material, piece-square terms, pawn advancement, passed pawns,
  isolated pawns, king safety and the bishop pair.
- **Draws**: a repetition of the position is scored 0, so the engine does not throw a
  winning position away by repeating moves.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

MIT licensed. See `LICENSE`.
