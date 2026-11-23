# Tiny Chess — strongest chess engine in 4 KB of Python

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rahullpc/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rahullpc/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Entry for [tiny-chess-01](https://make.fun/bounty/tiny-chess-01): a chess engine
in at most 4,096 bytes of Python that plays the house gauntlet through the env.

`main.py` (3,766 bytes) is the whole engine: an LZMA-compressed payload
(allowed by the rules; payload + unpacker count toward the 4,096 bytes) that
unpacks to a from-scratch 0x88 engine — legal move generator, negamax
alpha-beta with quiescence, transposition table, killer moves, MVV-LVA
ordering, null-move pruning, material + piece-square evaluation, and
repetition-aware search. It searches to a fixed node budget (80,000
nodes/move, deterministic — never a clock) and plays only the env's legal
moves. Practice Elo trial-0: **1364**; trial-1: **1545**; trial-2: **1545**
(mean **1485**; floor 1154; baseline ~1365).
