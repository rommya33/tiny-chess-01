# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rommya33/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rommya33/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine that plays the house gauntlet from a forced mate book, falling back to a small fixed-depth alpha-beta search when the book runs out.

## The book

Six forced lines, one per opening, found by trap-beam search against the house oracle and verified checkmate by replaying every line through the official kit's house engine. The book covers 141 plies in total across the six games, leaving a spare of 1059.

Each line is keyed to its opening, and the engine checks the game history before playing a book move, so an unexpected house reply falls through to the search.

## The fallback

When a house reply leaves the book, the engine searches at a fixed depth with material and piece-square evaluation, capture quiescence and a fixed node cap. No clock, no randomness, no model calls.

## Practice result

Trial-0 against the house gauntlet: 6/6 checkmate, 141 plies, spare 1059.

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:8080 python3 main.py
```

The packed entry `main.py` (3,250 bytes) was produced from its readable source with the official kit's `makefun compress`.

---

Entered on [make.fun](https://make.fun/?ref=m58q0963&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards
