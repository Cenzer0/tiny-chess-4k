# Tiny Chess Engine

A compact chess engine for the make.fun tiny-chess-01 competition,
written from scratch in Python. It plays the house gauntlet through the
contest environment: `POST /game` serves the game in play, `POST /move`
plays a move, and the loop ends when the environment answers `done`.

## How it plays

The engine uses a 0x88 board with negamax alpha-beta search, a capture
quiescence search with check evasions, a transposition table, MVV-LVA
plus killer and history move ordering, null-move pruning, and delta
pruning in quiescence. It searches by iterative deepening on a fixed
node budget (150,000 nodes a move), never by a clock, so every trial
replays identically. The evaluation is material plus piece-square tables
with a bishop-pair bonus and a separate king table for the endgame. It
also refuses to repeat a position for the third time when another move
exists. Move generation is verified against standard perft suites
(start position, Kiwipete and the usual tactical positions).

## Files

- `main.py` — the whole engine, 3,904 bytes, the only file the trial
  runs. It is the packed form of `engine_ship.py`, produced by the kit's
  `makefun compress` command.
- `engine_ship.py` — the readable source of `main.py`.
- `LICENSE` — MIT.
- `.makefun/owner.json` — the claim file naming the entrant's wallet.

## Strength

On the kit's practice trial (6 games, first 6 rungs of the gauntlet)
it scores 3.5/6: wins against depth-2, depth-3 and depth-4, a draw
against nodes-250k, losses against nodes-100k and nodes-500k, for a
practice Elo of about 1,370 — above the 1,154 floor for the final.
