# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/dandelionz3/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/dandelionz3/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine using iterative-deepening alpha-beta, quiescence, a transposition table, killer moves, and piece-square evaluation. Revision 2 uses single-pass material evaluation, a reduced pawn-advance bonus, king-safety bonuses for castling, and a fixed 25,000-node budget.

## Benchmarks

At 25,000 nodes per move: start depth 5 (1.73 s), Italian depth 19 (0.73 s), semi-Slav depth 2 (4.70 s), and midgame depth 9 (2.91 s). These are local search timings.

## Results

Trial 0 scored Elo 1,191 with 2 wins, 1 draw, and 3 losses (311 s bot wall time); its deterministic re-run produced identical Elo and game transcripts (317 s). It passes the 1,154 practice floor. Trial 1 scored Elo 1,099 with 2 wins, 0 draws, and 4 losses (345 s bot wall time), below the floor; results vary by trial.

## Run it

```sh
python3 main.py
```

Set `MAKEFUN_ENV_URL` to the env server and `MAKEFUN_PROMPT_FILE` to the trial prompt (see the kit). The engine plays every game through the env and exits when the trial is done.
