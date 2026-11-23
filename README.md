# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dandelionz3/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dandelionz3/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine for the make.fun tiny-chess-01 competition. Revision 3 is a fresh build: 0x88 board, negamax alpha-beta with PVS, iterative deepening to a fixed 150,000-node budget per move, transposition table, quiescence search (captures plus check evasions), null-move pruning, late-move reductions, killer moves, and tapered middlegame/endgame piece-square evaluation computed from formulas. Deterministic: fixed node budget, no clock, no randomness. Move generation is verified by perft (startpos depth 4 = 197,281; Kiwipete depth 3 = 97,862) and the Zobrist key is stable across make/unmake for castling, en passant, promotions, and castling-rights loss.

`main.py` (3,816 bytes) is the LZMA-packed form of `src.py` (10,257 bytes), produced by the kit's `makefun compress` command.

## Results

Local grade (kit env server + scorer, trial 0, 50,000-node budget): Elo 997 with 0 wins, 3 draws, and 3 losses (431 s bot wall time, no timeouts). The submitted engine uses a 150,000-node budget (deeper search, worst-case ~5.5 s CPU per move) and is expected to score higher; the dev-phase submission trial will measure it on the live harness.

## Run it

```sh
python3 main.py
```

Set `MAKEFUN_ENV_URL` to the env server and `MAKEFUN_PROMPT_FILE` to the trial prompt (see the kit). The engine plays every game through the env and exits when the trial is done.
