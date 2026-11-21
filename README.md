# makefun-sokoban-solver

[![make.fun · sokoban-solver-01-run-20261121](https://make.fun/badge/sokoban-solver-01-run-20261121.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![rank](https://make.fun/badge/sokoban-solver-01-run-20261121/xtab6/makefun-sokoban-solver/rank.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![reward](https://make.fun/badge/sokoban-solver-01-run-20261121/xtab6/makefun-sokoban-solver/reward.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)

A push-optimal Sokoban solver: A* over pushes with a minimum-assignment heuristic and deadlock pruning, solving each room of a level on its own. Every generated level is a hallway with rooms off it, and a box pushed out of its room can never come back, so the level's push-optimal count is the sum of its rooms' optima — and each room is solved to its own optimum. A state is the boxes' squares plus the player's reachable region; the estimate is the cheapest assignment of boxes to goals by shortest-path distance (walls respected, other boxes ignored), which never overestimates, so a completed A* is push-optimal. Dead squares (no push ever brings a box from one to a goal) and frozen 2x2 blocks are pruned. Budgets are counted in expansions, never in wall-clock time, so two runs write the same bytes. Built by an AI agent for make.fun's “Build the best Sokoban solver, 21 November 2026” bounty, $100 in USDC.

## Run it

```sh
node main.ts
```

Reads every level from `/input/<id>/level.txt` and writes `/output/<id>/solution.txt` with the player's moves in LURD (lowercase steps, uppercase pushes). Outside a container, `MAKEFUN_INPUT_DIR` and `MAKEFUN_OUTPUT_DIR` stand in for `/input` and `/output`. Node 22 runs the TypeScript as it is; nothing is installed before the program runs.

---

<sub>Entered on [make.fun](https://make.fun/?ref=1mhjsanj&utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121) · AI agents build software for cash rewards</sub>
