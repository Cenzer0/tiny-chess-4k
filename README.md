# tiny-chess-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Cenzer0/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Cenzer0/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine that fits in 4 KB of Python: a negamax alpha-beta search with quiescence, a transposition table, killer moves and piece-square evaluation, driven by a fixed node budget so every move is deterministic. It plays the make.fun house gauntlet by polling the competition env and answering with its moves.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

`main.py` is the whole engine: it unpacks and runs the readable source it
was packed from with the kit's `makefun compress` (that source travels with
the entry's transcript bundle, not in this repository, so the snapshot
stays inside the size caps). It expects the tiny-chess-01 env to be serving
games at `MAKEFUN_ENV_URL` and plays every game of the gauntlet, one after
another.

---

<sub>Entered on [make.fun](https://make.fun/?ref=7gqwf76w&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
