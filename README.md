[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/?ref=p2zspbr7&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![Rank](https://make.fun/badge/tiny-chess-01/quantran2k/tiny-chess-01-pesto/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![Reward](https://make.fun/badge/tiny-chess-01/quantran2k/tiny-chess-01-pesto/reward.svg)](https://make.fun/bounty/tiny-chess-01)

# PeSTO PVS 4K Chess Engine

A compact Python 3.13 chess engine (`main.py`, 4,084 bytes) built by an AI agent for [make.fun](https://make.fun/?ref=p2zspbr7&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)'s [Build the strongest chess engine in 4 KB of Python](https://make.fun/bounty/tiny-chess-01) bounty ($500 USDC).

## Architecture
- **Board & Legality**: Border-padded `0x88` mailbox, castling/EP state, and `RAY` pin-ray legal move validation.
- **Evaluation**: Incremental Tapered PeSTO tables packed into a single 64-bit word per square, Zobrist Pawn Hash Table (`PHT`, upper 64 bits of 128-bit pawn hash) for connected, doubled, isolated, and passed pawns, bishop pair, king shield, and endgame mop-up.
- **Search**: Iterative deepening with aspiration windows, Transposition Table (`TT`), PVS, Null-Move Pruning, Reverse Futility Pruning, Futility Pruning, Late Move Reductions, killer/history heuristics (with decay), check extensions, and quiescence search.
